---
title: Microsoft SQL Server e Azure SQL Connector per Microsoft Search
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
description: Configurare Microsoft SQL Connector per Microsoft Search.
ms.openlocfilehash: 412f7979e6e76b68828124a2984aabd3b4ed5f42
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408952"
---
# <a name="azure-sql-and-microsoft-sql-server-connectors"></a>Connettori di Azure SQL e Microsoft SQL Server

Con un connettore di Microsoft SQL Server o di Azure SQL, l'organizzazione può individuare e indicizzare i dati da un database di SQL Server locale o da un database ospitato nell'istanza SQL di Azure nel cloud. Il connettore indicizza il contenuto specificato in Microsoft Search. Per mantenere l'indice aggiornato con i dati di origine, supporta le ricerche per indicizzazione periodiche complete e incrementali. Con questi connettori SQL, è anche possibile limitare l'accesso ai risultati della ricerca per alcuni utenti.

Questo articolo è per gli amministratori di Microsoft 365 o per tutti gli utenti che configurano, eseguono e monitorano un connettore SQL Server o Microsoft Azure. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi. 

## <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a>Installare l'agente del connettore grafico (necessario solo per il connettore di Microsoft SQL Server locale)
Per accedere ai dati di terze parti locali, è necessario installare e configurare l'agente del connettore grafico. Per ulteriori informazioni, vedere [installare l'agente del connettore grafico](on-prem-agent.md) .  

## <a name="register-an-app-for-azure-sql-connector-only"></a>Registrare un'app (solo per il connettore SQL di Azure)
Per il connettore SQL di Azure, è necessario registrare un'app in Azure Active Directory per consentire all'app di ricerca Microsoft di accedere ai dati per l'indicizzazione. Per ulteriori informazioni sulla registrazione di un'app, fare riferimento alla documentazione di Microsoft Graph su come [registrare un'app](https://docs.microsoft.com/graph/auth-register-app-v2). 

Dopo aver completato la registrazione delle app e aver preso nota del nome dell'app, dell'ID dell'applicazione (client) e dell'ID tenant, è necessario [generare un nuovo segreto client](https://docs.microsoft.com/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret). Il segreto client verrà visualizzato solo una volta. Tenere presente & archiviare il segreto client in modo sicuro. Utilizzare l'ID client e il segreto client durante la configurazione di una nuova connessione in Microsoft Search. 

Per aggiungere l'app registrata al database SQL di Azure, è necessario eseguire le operazioni seguenti:
 - Accedere al database SQL di Azure
 - Aprire una nuova finestra di query
 - Creare un nuovo utente eseguendo il comando ' Crea utente [nome app] da PROVIDER esterno '
 - Aggiungere un utente al ruolo eseguendo il comando ' exec sp_addrolemember ' db_datareader ', [nome app]' oppure ' ALTER ROLE db_datareader ADD MEMBER [nome app]'

>[!NOTE]
>Per revocare l'accesso a qualsiasi applicazione registrata in Azure Active Directory, fare riferimento alla documentazione di Azure sulla [rimozione di un'app registrata](https://docs.microsoft.com/azure/active-directory/develop/quickstart-remove-app).

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati
Per connettere il connettore Microsoft SQL Server a un'origine dati, è necessario configurare il server di database che si desidera sottoporre a ricerca per indicizzazione e l'agente on-Prem. È quindi possibile connettersi al database con il metodo di autenticazione necessario.

> [!NOTE]
> È necessario che il database esegua SQL Server versione 2008 o successiva per il connettore Microsoft SQL Server per potersi connettere.

Per il connettore SQL di Azure, è sufficiente specificare il nome o l'indirizzo IP del server a cui si desidera effettuare la connessione. Il connettore SQL di Azure supporta solo l'autenticazione di Azure Active Directory Open ID Connect (OIDC) per la connessione al database.

Per una maggiore sicurezza, è possibile configurare le regole del firewall IP per il database o SQL Server di Azure. Per ulteriori informazioni sulla configurazione delle regole del firewall IP, fare riferimento alla documentazione relativa alle [regole del firewall IP](https://docs.microsoft.com/azure/azure-sql/database/firewall-configure). Aggiungere i seguenti intervalli di indirizzi IP client nelle impostazioni del firewall.

| Area geografica | Intervallo IP |
| ------------ | ------------ |
| NAM | 52.250.92.252/30, 52.224.250.216/30 |
| EUR | 20.54.41.208/30, 51.105.159.88/30 |
| APC | 52.139.188.212/30, 20.43.146.44/30 |

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
Nella tabella seguente sono riepilogati i tipi di dati SQL supportati nei connettori SQL di MS SQL e Azure. La tabella riepiloga anche il tipo di dati di indicizzazione per il tipo di dati SQL supportato. Per ulteriori informazioni sui tipi di dati supportati dai connettori di Microsoft Graph per l'indicizzazione, fare riferimento alla documentazione sui [tipi di risorse della proprietà](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties). 

| Categoria | Tipo di dati di origine | Tipo di dati di indicizzazione |
| ------------ | ------------ | ------------ |
| Data e ora | data <br> datetime <br> datetime2 <br> smalldatetime | datetime |
| Valore numerico esatto | bigint <br> int <br> smallint <br> tinyint | Int64 |
| Valore numerico esatto | po' | boolean |
| Numerico approssimativo | galleggiante <br> reale | doppio |
| Stringa di caratteri | char <br> varchar <br> testo | stringa |
| Stringhe di caratteri Unicode | nchar <br> nvarchar <br> ntext | stringa |
| Altri tipi di dati | uniqueidentifier | stringa |

Per qualsiasi altro tipo di dati attualmente non supportato direttamente, è necessario eseguire il cast esplicito di una colonna a un tipo di dati supportato.

### <a name="watermark-required"></a>Filigrana (obbligatoria)
Per evitare sovraccarichi del database, il connettore esegue il batch e riprende le query di ricerca per indicizzazione complete con una colonna di filigrana full-crawl. Se si utilizza il valore della colonna filigrana, ogni batch successivo viene recuperato e l'esecuzione di query viene ripresa dall'ultimo checkpoint. In sostanza si tratta di un meccanismo per controllare l'aggiornamento dei dati per le ricerche per indicizzazione complete.

Creare frammenti di query per le filigrane come illustrato negli esempi seguenti:
* `WHERE (CreatedDateTime > @watermark)`. Citare il nome della colonna della filigrana con la parola chiave riservata `@watermark` . Se l'ordinamento della colonna della filigrana è crescente, utilizzare `>` ; in caso contrario, utilizzare `<` .
* `ORDER BY CreatedDateTime ASC`. Ordinare la colonna della filigrana in ordine crescente o decrescente.

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

## <a name="next-steps-customize-the-search-results-page"></a>Passaggi successivi: personalizzare la pagina dei risultati di ricerca
Creare i propri tipi di verticali e di risultati, in modo che gli utenti finali possano visualizzare i risultati della ricerca dalle nuove connessioni. Senza questo passaggio, i dati della connessione non verranno visualizzati nella pagina dei risultati della ricerca.

Per ulteriori informazioni su come creare i verticali e MRTs, vedere Personalizzazione della [pagina dei risultati di ricerca](customize-search-page.md).

## <a name="limitations"></a>Limitazioni
I connettori SQL presentano queste limitazioni nella versione di anteprima:
* Connettore Microsoft SQL Server: il database locale deve eseguire SQL Server versione 2008 o successiva.
* Gli elenchi ACL sono supportati solo utilizzando un nome dell'entità utente (UPN), Azure Active Directory (Azure AD) o la sicurezza di Active Directory. 
* L'indicizzazione del contenuto RTF all'interno delle colonne di database non è supportata. Esempi di contenuto di questo tipo sono HTML, JSON, XML, BLOB e analisi dei documenti che esistono come collegamenti all'interno delle colonne di database.