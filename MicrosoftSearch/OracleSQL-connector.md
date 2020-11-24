---
title: Oracle SQL Connector per Microsoft Search
ms.author: vivg
author: Vivek
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore SQL Oracle per Microsoft Search.
ms.openlocfilehash: cf7946533b3806bb730cdc6a31f7745ebad2c59d
ms.sourcegitcommit: ac4e261c01262be747341f810d2d1faf220d3961
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2020
ms.locfileid: "49382678"
---
# <a name="oracle-sql-connector"></a>Connettore SQL Oracle

Con il connettore Oracle SQL, l'organizzazione può individuare e indicizzare i dati da un database Oracle locale. Il connettore indicizza il contenuto specificato in Microsoft Search. Per mantenere l'indice aggiornato con i dati di origine, supporta le ricerche per indicizzazione periodiche complete e incrementali. Con il connettore SQL Oracle, è anche possibile limitare l'accesso ai risultati della ricerca per alcuni utenti.

Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitorano un connettore SQL Oracle. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.

## <a name="install-the-graph-connector-agent"></a>Installare l'agente del connettore grafico
Per accedere ai dati di terze parti locali, è necessario installare e configurare l'agente del connettore grafico. Per ulteriori informazioni, vedere [installare l'agente del connettore grafico](on-prem-agent.md) .  

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati
Per connettere il connettore SQL Oracle a un'origine dati, è necessario configurare il server di database che si desidera sottoporre a ricerca per indicizzazione e l'agente del connettore grafico locale. È quindi possibile connettersi al database con il metodo di autenticazione necessario.

Per il connettore Oracle SQL, è necessario specificare il nome host, la porta e il servizio (database) insieme al metodo di autenticazione preferito, nome utente e password.

> [!NOTE]
> È necessario che il database esegua Oracle Database Version 11g o versione successiva affinché il connettore sia in grado di connettersi. Il connettore supporta il database Oracle ospitato nelle piattaforme di Windows, Linux e VM di Azure.

Per eseguire la ricerca nel contenuto del database, è necessario specificare le query SQL quando si configura il connettore. Queste query SQL devono assegnare un nome a tutte le colonne di database che si desidera indicizzare, ad esempio le proprietà di origine, compresi i join SQL che è necessario eseguire per ottenere tutte le colonne. Per limitare l'accesso ai risultati della ricerca, è necessario specificare gli elenchi di controllo di accesso (ACL, Access Control List) all'interno delle query SQL quando si configura il connettore.

## <a name="full-crawl-required"></a>Ricerca per indicizzazione completa (obbligatorio)
In questo passaggio viene configurata la query SQL che esegue una ricerca per indicizzazione completa del database. La **ricerca per** indicizzazione completa consente di selezionare tutte le colonne o le proprietà che si desidera rendere **Queryable**, **reperibili o recuperabili**. È inoltre possibile specificare le colonne ACL per limitare l'accesso ai risultati della ricerca a utenti o gruppi specifici.

> [!Tip]
> Per ottenere tutte le colonne necessarie, è possibile partecipare a più tabelle.

![Script che mostra OrderTable e AclTable con proprietà di esempio](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Selezionare le colonne di dati (obbligatorio) e le colonne ACL (facoltativo)
In questo esempio viene illustrata la selezione di cinque colonne di dati che contengono i dati per la ricerca: OrderId, OrderTitle, OrderDesc, CreatedDateTime ed andeleted. Per impostare le autorizzazioni di visualizzazione per ogni riga di dati, è facoltativamente possibile selezionare le colonne ACL seguenti: AllowedUsers, AllowedGroups, DeniedUsers e DeniedGroups. Tutte queste **colonne di dati** possono essere rese **Queryable**, reperibili o **recuperabili**.

Selezionare colonne di dati come illustrato in questa query di esempio: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`
 
Per gestire l'accesso ai risultati della ricerca, è possibile specificare una o più colonne ACL nella query. Il connettore SQL consente di controllare l'accesso a ogni livello di record. È possibile scegliere di avere lo stesso controllo di accesso per tutti i record di una tabella. Se le informazioni ACL sono archiviate in una tabella separata, potrebbe essere necessario eseguire una join con tali tabelle nella query.

Di seguito viene descritto l'utilizzo di tutte le colonne ACL nella query precedente. Nell'elenco seguente vengono illustrati i 4 **meccanismi di controllo di accesso**. 
* **AllowedUsers**: specifica l'elenco di ID utente che saranno in grado di accedere ai risultati della ricerca. Nell'esempio seguente, l'elenco di utenti: john@contoso.com, keith@contoso.com e lisa@contoso.com avrebbe accesso solo a un record con OrderId = 12. 
* **AllowedGroups**: specifica il gruppo di utenti che saranno in grado di accedere ai risultati della ricerca. Nell'esempio seguente, il gruppo sales-team@contoso.com avrebbe accesso solo al record con OrderId = 12.
* **DeniedUsers**: specifica l'elenco di utenti che **non** hanno accesso ai risultati della ricerca. Nell'esempio seguente, gli utenti john@contoso.com e keith@contoso.com non dispongono dell'accesso a record con OrderId = 13, mentre tutti gli altri hanno accesso a questo record. 
* **DeniedGroups**: specifica il gruppo di utenti che **non** hanno accesso ai risultati della ricerca. Nell'esempio seguente, i gruppi engg-team@contoso.com e pm-team@contoso.com non dispongono dell'accesso a record con OrderId = 15, mentre tutti gli altri hanno accesso a questo record.  

![Dati di esempio che mostrano OrderTable e AclTable con le proprietà di esempio](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Tipi di dati supportati
Nella tabella seguente sono riepilogati i tipi di dati supportati dal connettore SQL Oracle. La tabella riepiloga anche il tipo di dati di indicizzazione per il tipo di dati SQL supportato. Per ulteriori informazioni sui tipi di dati supportati dai connettori di Microsoft Graph per l'indicizzazione, fare riferimento alla documentazione sui [tipi di risorse della proprietà](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties). 

| Categoria | Tipo di dati di origine | Tipo di dati di indicizzazione |
| ------------ | ------------ | ------------ |
| Tipo di codice | NUMERO (p, 0) | Int64 (per p <= 18) <br> doppio (per p > 18) |
| Tipo di codice a virgola mobile | NUMERO (p, s) <br> A virgola mobile (p) | doppio |
| Data tipo di dati | Data <br> TIMESTAMP <br> TIMESTAMP (n) | datetime |
| Tipo di carattere | CHAR (n) <br> VARCHAR <br> VARCHAR2 <br> LUNGO <br> CLOB <br> NCLOB | stringa |
| Tipo di carattere Unicode | NCHAR <br> NVARCHAR | stringa |
| Tipo di RowID | ROWID <br> UROWID | stringa |

Per qualsiasi altro tipo di dati attualmente non supportato direttamente, è necessario eseguire il cast esplicito di una colonna a un tipo di dati supportato.

### <a name="watermark-required"></a>Filigrana (obbligatoria)
Per evitare sovraccarichi del database, il connettore esegue il batch e riprende le query di ricerca per indicizzazione complete con una colonna di filigrana full-crawl. Se si utilizza il valore della colonna filigrana, ogni batch successivo viene recuperato e l'esecuzione di query viene ripresa dall'ultimo checkpoint. In sostanza si tratta di un meccanismo per controllare l'aggiornamento dei dati per le ricerche per indicizzazione complete.

Creare frammenti di query per le filigrane come illustrato negli esempi seguenti:
* `WHERE (CreatedDateTime > @watermark)`. Citare il nome della colonna della filigrana con la parola chiave riservata `@watermark` . È possibile ordinare la colonna della filigrana solo in ordine crescente.
* `ORDER BY CreatedDateTime ASC`. Ordinare la colonna della filigrana in ordine crescente.

Nella configurazione illustrata nella figura seguente, `CreatedDateTime` è la colonna della filigrana selezionata. Per recuperare il primo batch di righe, specificare il tipo di dati della colonna filigrana. In questo caso, il tipo di dati è `DateTime` .

![Configurazione colonna filigrana](media/MSSQL-watermark.png)

La prima query recupera il primo numero **N** di righe utilizzando: "CreatedDateTime > January 1, 1753 00:00:00" (valore minimo del tipo di dati DateTime). Dopo il recupero del primo batch, il valore massimo `CreatedDateTime` restituito nel batch viene salvato come checkpoint se le righe sono ordinate in ordine crescente. Un esempio è il 1 ° marzo 2019 03:00:00. Viene quindi recuperato il batch successivo di **N** righe utilizzando "CreatedDateTime > 1 marzo 2019 03:00:00" nella query.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorare le righe eliminate temporaneamente (facoltativo)
Per escludere la possibilità di indicizzare le righe eliminate temporaneamente nel database, specificare il nome e il valore della colonna di eliminazione temporanea che indica che la riga è stata eliminata.

![Soft delete Settings: "soft delete column" e "value of soft delete column che indica una riga eliminata"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Ricerche per indicizzazione complete: gestione delle autorizzazioni di ricerca
Fare clic su **Gestisci autorizzazioni** per selezionare le varie colonne di controllo di accesso (ACL) che specificano il meccanismo di controllo di accesso. Selezionare il nome della colonna specificato nella query SQL di ricerca per indicizzazione completa. 

Ognuna delle colonne ACL dovrebbe essere una colonna multivalore. Questi valori ID multipli possono essere separati da separatori, ad esempio punto e virgola (;), virgola (,) e così via. È necessario specificare questo separatore nel campo **separatore di valori** .
 
I tipi di ID seguenti sono supportati per l'utilizzo come ACL: 
* **Nome dell'entità utente (UPN)**: un nome dell'entità utente (UPN) è il nome di un utente di sistema in un formato di indirizzo di posta elettronica. Un UPN (ad esempio: john.doe@domain.com) è costituito da nome di accesso, separatore (il simbolo @) e nome di dominio (suffisso UPN). 
* **ID di Azure Active Directory (AAD)**: in Azure ad, ogni utente o gruppo ha un ID oggetto che ha un aspetto simile a "e0d3ad3d-0000-1111-2222-3c5f5c52ab9b" 
* **ID di sicurezza di Active Directory (ad)**: in una configurazione degli annunci locali, tutti gli utenti e i gruppi dispongono di un identificatore di sicurezza univoco e non modificabile che ha un aspetto simile a-1-5-21-3878594291-2115959936-132693609-65242.

![Impostazioni delle autorizzazioni di ricerca per configurare gli elenchi di controllo di accesso](media/MSSQL-ACL2.png)

## <a name="incremental-crawl-optional"></a>Ricerca per indicizzazione incrementale (facoltativa)
In questo passaggio facoltativo, fornire una query SQL per eseguire una ricerca per indicizzazione incrementale del database. Con questa query, il connettore SQL determina le modifiche apportate ai dati dall'ultima ricerca per indicizzazione incrementale. Come **nella ricerca per** indicizzazione completa, selezionare tutte le colonne che si desidera rendere **Queryable**, reperibili o **recuperabili**. Specificare lo stesso insieme di colonne ACL specificato nella query di ricerca per indicizzazione completa.

I componenti nell'immagine seguente sono simili ai componenti di ricerca per indicizzazione completi con una sola eccezione. In questo caso, "ModifiedDateTime" è la colonna della filigrana selezionata. Esaminare i [passaggi per la ricerca per indicizzazione completa](#full-crawl-required) per informazioni su come scrivere la query di ricerca per indicizzazione incrementale e vedere come esempio l'immagine seguente.

![Script di ricerca per indicizzazione incrementale che mostra OrderTable, AclTable e proprietà di esempio che è possibile utilizzare.](media/MSSQL-incrcrawl.png)

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca 
È possibile scegliere di utilizzare gli [ACL specificati nella schermata di ricerca per indicizzazione completa](#full-crawl-manage-search-permissions) oppure è possibile sovrascriverli per rendere il contenuto visibile a tutti.

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento
Il connettore Oracle SQL supporta le pianificazioni di aggiornamento per le ricerche per indicizzazione complete e incrementali. È consigliabile impostare entrambi.

Una pianificazione di ricerca per indicizzazione completa rileva le righe eliminate precedentemente sincronizzate con l'indice Microsoft Search e tutte le righe che sono state spostate fuori dal filtro di sincronizzazione. Quando si esegue la connessione al database, viene eseguita una ricerca per indicizzazione completa per sincronizzare tutte le righe recuperate dalla query di ricerca per indicizzazione completa. Per sincronizzare nuove righe e rendere gli aggiornamenti, è necessario pianificare ricerche per indicizzazione incrementali.

## <a name="next-steps-customize-the-search-results-page"></a>Passaggi successivi: personalizzare la pagina dei risultati di ricerca
Creare i propri tipi di verticali e di risultati, in modo che gli utenti finali possano visualizzare i risultati della ricerca dalle nuove connessioni. Senza questo passaggio, i dati della connessione non verranno visualizzati nella pagina dei risultati della ricerca.

Per ulteriori informazioni su come creare i verticali e MRTs, vedere Personalizzazione della [pagina dei risultati di ricerca](customize-search-page.md).

## <a name="limitations"></a>Limitazioni
Il connettore SQL Oracle ha queste limitazioni nella versione di anteprima:
* È necessario che il database locale esegua il database Oracle versione 11g o versioni successive.
* Gli elenchi ACL sono supportati solo utilizzando un nome dell'entità utente (UPN), Azure Active Directory (Azure AD) o la sicurezza di Active Directory. 
* L'indicizzazione del contenuto RTF all'interno delle colonne di database non è supportata. Esempi di contenuto di questo tipo sono HTML, JSON, XML, BLOB e analisi dei documenti che esistono come collegamenti all'interno delle colonne di database.

## <a name="troubleshooting-guide"></a>Guida alla risoluzione dei problemi
Sotto è un elenco di errori comuni osservati durante la configurazione del connettore e dei loro possibili motivi.
| Passaggio di configurazione | Messaggio di errore | Possibili motivi |
| ------------ | ------------ | ------------ |
| Impostazioni di database | Errore da server database: timeout richiesta di connessione | Nome host non valido <br> Host non raggiungibile |
| Impostazioni di database | Errore da server database: ORA-12541: TNS: No listner | Porta non valida |
| Impostazioni di database | Errore da server database: ORA-12514: TNS: Listner attualmente non è a conoscenza del servizio richiesto nel descrittore del connettore | Nome del servizio (database) non valido |
| Impostazioni di database | Errore da server database: accesso non riuscito per l'utente ' `user` '. | Nome utente o password non validi |