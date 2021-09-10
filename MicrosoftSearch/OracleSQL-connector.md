---
title: Connettore SQL Graph Oracle per Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurare il connettore di SQL Graph Oracle per Microsoft Search.
ms.openlocfilehash: 804bee89f8529630df5741f68b9f112c69307b4f
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973502"
---
<!---Previous ms.author:vivg --->

# <a name="oracle-sql-graph-connector"></a>Connettore SQL Graph Oracle

Il connettore SQL Graph Oracle consente all'organizzazione di individuare e indicizzare i dati da un database Oracle locale. Il connettore indicizza il contenuto specificato Microsoft Search. Per mantenere aggiornato l'indice con i dati di origine, supporta ricerche per indicizzazione periodiche complete e incrementali. Con il connettore di SQL Oracle, è anche possibile limitare l'accesso ai risultati della ricerca per determinati utenti.

> [!NOTE]
> Leggere [**l'articolo Setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup instructions.

Questo articolo è per chiunque configura, esegue e monitora un connettore di SQL Graph Oracle. Integra il processo di installazione generale e mostra le istruzioni che si applicano solo al connettore di SQL Graph Oracle. In questo articolo sono inoltre incluse informazioni sulla [risoluzione dei](#troubleshooting) problemi e [sulle limitazioni.](#limitations)

## <a name="before-you-get-started"></a>Prima di iniziare

### <a name="install-the-graph-connector-agent"></a>Installare l'agente Graph connettore

Per accedere ai dati di terze parti locali, è necessario installare e configurare l'agente Graph connettore. Per [ulteriori informazioni, vedere Install the Graph connector agent.](graph-connector-agent.md)  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nella interfaccia di amministrazione di Microsoft 365

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Passaggio 2: assegnare un nome alla connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: Configurare le impostazioni di connessione

Per connettere il connettore di SQL Oracle a un'origine dati, è necessario configurare il server di database di cui si desidera eseguire la ricerca per indicizzazione e l'agente del connettore di Graph locale. È quindi possibile connettersi al database con il metodo di autenticazione richiesto.

Per il connettore SQL Oracle, è necessario specificare il nome host, la porta e il servizio (database) insieme al metodo di autenticazione, al nome utente e alla password preferiti.

> [!NOTE]
> Il database deve eseguire il database Oracle versione 11g o successiva perché il connettore sia in grado di connettersi. Il connettore supporta il database Oracle ospitato su piattaforme Windows, Linux e Azure VM.

Per eseguire ricerche nel contenuto del database, è necessario specificare SQL query quando si configura il connettore. Queste SQL devono assegnare un nome a tutte le colonne di database che si desidera indicizzare, ovvero le proprietà di origine, inclusi gli eventuali join SQL che devono essere eseguiti per ottenere tutte le colonne. Per limitare l'accesso ai risultati della ricerca, è necessario specificare gli elenchi di controllo di accesso (ACL) all'interno SQL query quando si configura il connettore.

## <a name="step-3a-full-crawl-required"></a>Passaggio 3a: ricerca per indicizzazione completa (obbligatorio)

In questo passaggio viene configurata la query SQL che esegue una ricerca per indicizzazione completa del database. La ricerca per indicizzazione completa seleziona tutte le colonne o le proprietà in cui si desidera selezionare le opzioni **Query**, **Cerca** o **Recupera**. È inoltre possibile specificare colonne ACL per limitare l'accesso dei risultati della ricerca a utenti o gruppi specifici.

> [!Tip]
> Per ottenere tutte le colonne necessarie, è possibile unire più tabelle.

![Script che mostra OrderTable e AclTable con proprietà di esempio.](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Selezionare colonne di dati (obbligatorie) e colonne ACL (facoltativo)

Nell'esempio viene illustrata la selezione di cinque colonne di dati che contengono i dati per la ricerca: OrderId, OrderTitle, OrderDesc, CreatedDateTime e IsDeleted. Per impostare le autorizzazioni di visualizzazione per ogni riga di dati, è possibile selezionare le colonne ACL seguenti: AllowedUsers, AllowedGroups, DeniedUsers e DeniedGroups. Per tutte queste colonne di dati è possibile selezionare le opzioni **Query**, **Cerca** o **Recupera**.

Selezionare le colonne di dati come illustrato in questa query di esempio: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Per gestire l'accesso ai risultati della ricerca, è possibile specificare una o più colonne ACL nella query. Il SQL consente di controllare l'accesso a livello di record. È possibile scegliere di disporre dello stesso controllo di accesso per tutti i record di una tabella. Se le informazioni ACL sono archiviate in una tabella separata, potrebbe essere necessario eseguire un join con tali tabelle nella query.

L'utilizzo di ogni colonna ACL nella query precedente è descritto di seguito. Nell'elenco seguente vengono illustrati i quattro **meccanismi di controllo di accesso**.

* **AllowedUsers**: Questa opzione consente di specificare l'elenco degli ID utente che potranno accedere ai risultati della ricerca. Nell'esempio seguente, l'elenco di utenti: john@contoso.com, keith@contoso.com e lisa@contoso.com avrebbe accesso solo a un record con OrderId = 12.
* **AllowedGroups**: Questa opzione consente di specificare il gruppo di utenti che potranno accedere ai risultati della ricerca. Nell'esempio seguente, i gruppi sales-team@contoso.com possono accedere solo al record con OrderId = 12.
* **DeniedUsers**: Questa opzione consente di specificare l'elenco degli utenti che **non** hanno accesso ai risultati della ricerca. Nell'esempio seguente, gli utenti john@contoso.com e keith@contoso.com non hanno accesso al record con OrderId = 13, mentre tutti gli altri utenti hanno accesso a questo record.
* **DeniedGroups**: Questa opzione consente di specificare il gruppo di utenti che **non** hanno accesso ai risultati della ricerca. Nell'esempio seguente i gruppi engg-team@contoso.com e pm-team@contoso.com non hanno accesso al record con OrderId = 15, mentre tutti gli altri utenti hanno accesso a questo record.  

![Dati di esempio che mostrano OrderTable e AclTable con proprietà di esempio.](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Tipi di dati supportati

Nella tabella seguente sono riepilogati i tipi di dati supportati dal connettore di SQL Oracle. La tabella riepiloga inoltre il tipo di dati di indicizzazione per il tipo di dati SQL supportato. Per ulteriori informazioni sui tipi di dati supportati Graph microsoft Graph per l'indicizzazione, fare riferimento alla documentazione relativa ai [tipi di risorse delle proprietà.](/graph/api/resources/property?preserve-view=true&view=graph-rest-beta#properties)

| Categoria | Tipo di dati di origine | Tipo di dati di indicizzazione |
| ------------ | ------------ | ------------ |
| Tipo di dati numero | NUMBER(p,0) | int64 (per p <= 18) <br> double (per p > 18) |
| Tipo di dati numero a virgola mobile | NUMBER(p,s) <br> FLOAT(p) | double |
| Tipo di dati data | DATE <br> TIMESTAMP <br> TIMESTAMP(n) | datetime |
| Tipo di dati carattere | CHAR(n) <br> VARCHAR <br> VARCHAR2 <br> LONG <br> CLOB <br> NCLOB | stringa |
| Tipo di dati carattere Unicode | NCHAR <br> NVARCHAR | stringa |
| Tipo di dati RowID | ROWID <br> UROWID | stringa |

Per qualsiasi altro tipo di dati attualmente non supportato direttamente, è necessario eseguire in modo esplicito il cast della colonna a un tipo di dati supportato.

### <a name="watermark-required"></a>Filigrana (obbligatorio)

Per evitare l'sovraccarico del database, il connettore esegue in batch e riprende le query di ricerca per indicizzazione completa con una colonna filigrana di ricerca per indicizzazione completa. Utilizzando il valore della colonna watermark, ogni batch successivo viene recuperato e l'esecuzione di query viene ripresa dall'ultimo checkpoint. Si tratta essenzialmente di un meccanismo per controllare l'aggiornamento dei dati per le ricerche per indicizzazione complete.

Creare frammenti di codice di query per filigrane come illustrato negli esempi seguenti:

* `WHERE (CreatedDateTime > @watermark)`. Cita il nome della colonna della filigrana con la parola chiave riservata `@watermark` . È possibile ordinare la colonna della filigrana solo in ordine crescente.
* `ORDER BY CreatedDateTime ASC`. Ordinare in base alla colonna della filigrana in ordine crescente.

Nella configurazione illustrata nell'immagine seguente, `CreatedDateTime` è la colonna filigrana selezionata. Per recuperare il primo batch di righe, specificare il tipo di dati della colonna filigrana. In questo caso, il tipo di dati è `DateTime` .

![Configurazione della colonna filigrana.](media/MSSQL-watermark.png)

La prima query recupera il primo **numero N** di righe utilizzando: "CreatedDateTime > January 1, 1753 00:00:00" (min value of DateTime data type). Dopo il recupero del primo batch, il valore più alto restituito nel batch viene salvato come checkpoint se le righe sono `CreatedDateTime` ordinate in ordine crescente. Un esempio è 1 marzo 2019 03:00:00. Il batch successivo di **N** righe viene quindi recuperato utilizzando "CreatedDateTime > March 1, 2019 03:00:00" nella query.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorare le righe eliminate in modo recidiva (facoltativo)

Per escludere le righe eliminate in modo recidiva nel database dall'indicizzazione, specificare il nome e il valore della colonna di eliminazione recidiva che indica che la riga è stata eliminata.

![Impostazioni di eliminazione recidiva: "Colonna di eliminazione recidiva" e "Valore della colonna di eliminazione recidiva che indica una riga eliminata".](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Ricerca per indicizzazione completa: gestire le autorizzazioni di ricerca

Selezionare **Gestisci autorizzazioni** per scegliere le varie colonne di controllo di accesso (ACL) che specificano il meccanismo di controllo di accesso. Selezionare il nome di colonna specificato nella query di ricerca per indicizzazione SQL completa.

Ogni colonna ACL deve essere una colonna multivalore. Questi valori ID multipli possono essere separati da separatori, ad esempio punto e virgola (;), virgola (,) e così via. È necessario specificare questo separatore nel campo **separatore** di valori.

I tipi di ID seguenti sono supportati per l'utilizzo come ACL:

* **Nome entità utente (UPN):** un nome dell'entità utente (UPN) è il nome di un utente di sistema in un formato di indirizzo di posta elettronica. Un UPN (ad esempio: john.doe@domain.com) è costituito dal nome utente (nome di accesso), dal separatore (simbolo @) e dal nome di dominio (suffisso UPN).
* **Azure Active Directory (AAD):** in Azure AD, ogni utente o gruppo ha un ID oggetto simile a 'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b'
* ID di sicurezza di **Active Directory (AD):** in un'installazione di Active Directory locale, ogni utente e gruppo dispone di un identificatore di sicurezza univoco non modificabile simile a 'S-1-5-21-3878594291-2115959936-132693609-65242'.

![Impostazioni delle autorizzazioni di ricerca per configurare gli elenchi di controllo di accesso.](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Passaggio 3b: ricerca per indicizzazione incrementale (facoltativo)

In questo passaggio facoltativo, fornire una SQL query per eseguire una ricerca per indicizzazione incrementale del database. Con questa query, il connettore SQL determina eventuali modifiche apportate ai dati dopo l'ultima ricerca per indicizzazione incrementale. Come nella ricerca per indicizzazione completa, selezionare tra le opzioni **Query**, **Cerca** o **Recupera**. Specificare lo stesso set di colonne ACL specificato nella query di ricerca per indicizzazione completa.

I componenti nell'immagine seguente sono simili ai componenti di ricerca per indicizzazione completa con un'eccezione. In questo caso, "ModifiedDateTime" è la colonna della filigrana selezionata. Esaminare i [passaggi completi della ricerca per](#step-3a-full-crawl-required) indicizzazione per informazioni su come scrivere la query di ricerca per indicizzazione incrementale e vedere l'immagine seguente come esempio.

![Script di ricerca per indicizzazione incrementale che mostra le proprietà OrderTable, AclTable e di esempio che possono essere utilizzate.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Passaggio 4: Assegnare etichette di proprietà

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-5-manage-schema"></a>Passaggio 5: Gestire lo schema

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-search-permissions"></a>Passaggio 6: Gestire le autorizzazioni di ricerca

È possibile scegliere di utilizzare gli [elenchi di](#full-crawl-manage-search-permissions) controllo di accesso specificati nella schermata di ricerca per indicizzazione completa oppure di ignorarli per rendere visibile il contenuto a tutti gli utenti.

## <a name="step-7-choose-refresh-settings"></a>Passaggio 7: Scegliere le impostazioni di aggiornamento

Il connettore di SQL Oracle supporta le pianificazioni di aggiornamento per le ricerche per indicizzazione complete e incrementali. È consigliabile impostare entrambe le opzioni.

Una pianificazione di ricerca per indicizzazione completa trova le righe eliminate precedentemente sincronizzate con l'indice Microsoft Search ed eventuali righe spostate fuori dal filtro di sincronizzazione. Quando ci si connette per la prima volta al database, viene eseguita una ricerca per indicizzazione completa per sincronizzare tutte le righe recuperate dalla query di ricerca per indicizzazione completa. Per sincronizzare nuove righe e apportare aggiornamenti, è necessario pianificare ricerche per indicizzazione incrementali.

## <a name="step-8-review-connection"></a>Passaggio 8: verificare la connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!--- ## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md). -->

## <a name="troubleshooting"></a>Risoluzione dei problemi

Di seguito è riportato un elenco degli errori comuni rilevati durante la configurazione del connettore e dei possibili motivi.

| Passaggio di configurazione | Messaggio di errore | Possibili motivi |
| ------------ | ------------ | ------------ |
| Impostazioni di database | Errore dal server di database: timeout della richiesta di connessione | Nome host non valido <br> Host non raggiungibile |
| Impostazioni di database | Errore dal server di database: ORA-12541: TNS: Nessun listener | Porta non valida |
| Impostazioni di database | Errore dal server di database: ORA-12514: TNS: il listener attualmente non conosce il servizio richiesto nel descrittore del connettore | Nome servizio (database) non valido |
| Impostazioni di database | Errore dal server di database: accesso non riuscito per l'utente ' `user` '. | Nome utente o password non validi |

## <a name="limitations"></a>Limitazioni

Il connettore SQL Oracle presenta queste limitazioni nella versione di anteprima:

* Il database locale deve eseguire Oracle Database versione 11g o successiva.
* Gli ACL sono supportati solo utilizzando un nome dell'entità utente (UPN), Azure Active Directory (Azure AD) o la sicurezza di Active Directory.
* L'indicizzazione di contenuto rtf all'interno di colonne di database non è supportata. Esempi di questo tipo di contenuto sono HTML, JSON, XML, BLOB e analisi di documenti presenti come collegamenti all'interno delle colonne del database.