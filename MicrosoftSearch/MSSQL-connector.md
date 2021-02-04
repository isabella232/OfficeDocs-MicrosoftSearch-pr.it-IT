---
title: Connettore Microsoft SQL Microsoft SQL Server Graph per Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore di Azure SQL e Microsoft SQL Graph per Microsoft Search.
ms.openlocfilehash: 9f0a0a617541c6e27196a183d3283e0f05163dec
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097440"
---
<!---Previous ms.author: vivg --->

# <a name="azure-sql-and-microsoft-sql-server-graph-connectors"></a>Connettori Graph di Azure SQL e Microsoft SQL server Microsoft

Il server Microsoft SQL o il connettore Azure SQL Graph consente all'organizzazione di individuare e indicizzare i dati da un database SQL Server locale o da un database ospitato nell'istanza di Azure SQL nel cloud.
Il connettore Graph indicizza il contenuto specificato in Microsoft Search. Per mantenere aggiornato l'indice con i dati di origine, supporta ricerche per indicizzazione periodiche complete e incrementali. Con questi connettori SQL, è anche possibile limitare l'accesso ai risultati della ricerca per determinati utenti.

> [!NOTE]
> Leggere [**l'articolo configurazione del connettore Graph**](configure-connector.md) per comprendere il processo generale di configurazione dei connettori di Graph.

Questo articolo è per tutti gli utenti che configurano, eseguiti e monitorano un connettore Graph di Azure SQL e Microsoft SQL server. Integra il processo di configurazione generale e mostra le istruzioni che si applicano solo per il connettore Graph di Azure SQL e Microsoft SQL server. Questo articolo include anche informazioni sulle [limitazioni](#limitations) per il server Microsoft SQL e i connettori di SQL Azure.

## <a name="before-you-get-started"></a>Prima di iniziare

### <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a>Installare l'agente del connettore Graph (necessario solo per microsoft SQL server locale)

Per accedere ai dati di terze parti locali, è necessario installare e configurare l'agente connettore Graph. Per ulteriori informazioni, vedere Install [the Graph connector agent.](on-prem-agent.md)  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nell'interfaccia di amministrazione di Microsoft 365

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Passaggio 2: Assegnare un nome alla connessione

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: Configurare le impostazioni di connessione

### <a name="register-an-app-for-azure-sql-connector-only"></a>Registrare un'app (solo per il connettore SQL Azure)

Per il connettore SQL Azure, è necessario registrare un'app in Azure Active Directory per consentire all'app Microsoft Search di accedere ai dati per l'indicizzazione. Per altre informazioni sulla registrazione di un'app, fai riferimento alla documentazione di Microsoft Graph su come [registrare un'app.](https://docs.microsoft.com/graph/auth-register-app-v2)

Dopo aver completato la registrazione dell'app e aver preso nota del nome dell'app, dell'ID applicazione (client) e dell'ID tenant, devi [generare un nuovo segreto client.](https://docs.microsoft.com/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret) Il segreto client verrà visualizzato una sola volta. Ricordarsi di & il segreto client in modo sicuro. Usare l'ID client e il segreto client durante la configurazione di una nuova connessione in Microsoft Search.

Per aggiungere l'app registrata al database SQL Azure, è necessario:

- Accedere al database SQL Azure
- Aprire una nuova finestra di query
- Creare un nuovo utente eseguendo il comando 'CREATE USER [nome app] FROM EXTERNAL PROVIDER'
- Aggiungere un utente al ruolo eseguendo il comando 'exec sp_addrolemember 'db_datareader', [nome app]' o 'ALTER ROLE db_datareader ADD MEMBER [nome app]'

>[!NOTE]
>Per revocare l'accesso a qualsiasi app registrata in Azure Active Directory, consultare la documentazione di Azure sulla [rimozione di un'app registrata.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-remove-app)

### <a name="connection-settings"></a>Impostazioni di connessione

Per connettere il connettore di server Microsoft SQL a un'origine dati, è necessario configurare il server di database che si desidera sottosegando alla ricerca per indicizzazione e l'agente locale. È quindi possibile connettersi al database con il metodo di autenticazione richiesto.

> [!NOTE] 
> Il database deve eseguire SQL server versione 2008 o successiva per la connessione del connettore di server microsoft SQL server.

Per il connettore SQL Azure, è necessario specificare solo il nome del server o l'indirizzo IP a cui si desidera connettersi. Il connettore SQL Azure supporta solo l'autenticazione OIDC (Open ID Connect) di Azure Active Directory per la connessione al database.

Per una sicurezza più avanzata, è possibile configurare le regole del firewall IP per il server o il database SQL Azure. Per ulteriori informazioni sulla configurazione delle regole del firewall IP, vedere la documentazione relativa [alle regole del firewall IP.](https://docs.microsoft.com/azure/azure-sql/database/firewall-configure) Aggiungere i seguenti intervalli IP client nelle impostazioni del firewall.

| Area geografica | Intervallo IP |
| ------------ | ------------ |
| NAM | 52.250.92.252/30, 52.224.250.216/30 |
| EUR | 20.54.41.208/30, 51.105.159.88/30 |
| APC | 52.139.188.212/30, 20.43.146.44/30 |

Per eseguire ricerche nel contenuto del database, è necessario specificare SQL query al momento della configurazione del connettore. Queste SQL query devono assegnare un nome a tutte le colonne di database che si desidera indicizzare, ovvero le proprietà di origine, inclusi eventuali join SQL che devono essere eseguiti per ottenere tutte le colonne. Per limitare l'accesso ai risultati della ricerca, è necessario specificare elenchi di controllo di accesso (ACL) all'interno SQL query quando si configura il connettore.

## <a name="step-3a-full-crawl-required"></a>Passaggio 3a: Ricerca per indicizzazione completa (obbligatorio)

In questo passaggio viene configurata la query SQL che esegue una ricerca per indicizzazione completa del database. La ricerca per indicizzazione completa seleziona tutte le colonne o le proprietà in cui si desidera selezionare le opzioni **Query,** **Ricerca** o **Recupera.** È inoltre possibile specificare colonne ACL per limitare l'accesso ai risultati della ricerca a utenti o gruppi specifici.

> [!Tip]
> Per ottenere tutte le colonne necessarie, è possibile unire più tabelle.

![Script che mostra OrderTable e AclTable con proprietà di esempio](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Selezionare colonne di dati (obbligatorio) e colonne ACL (facoltativo)

Nell'esempio viene illustrata una selezione di cinque colonne di dati che contengono i dati per la ricerca: OrderId, OrderTitle, OrderDesc, CreatedDateTime e IsDeleted. Per impostare le autorizzazioni di visualizzazione per ogni riga di dati, è possibile selezionare facoltativamente queste colonne ACL: AllowedUsers, AllowedGroups, DeniedUsers e DeniedGroups. Tutte queste colonne di dati dispongono inoltre delle opzioni **Query,** **Ricerca** o **Recupera.**

Selezionare le colonne di dati come illustrato in questa query di esempio: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Per gestire l'accesso ai risultati della ricerca, è possibile specificare una o più colonne ACL nella query. Il SQL consente di controllare l'accesso a livello di record. È possibile scegliere di disporre dello stesso controllo di accesso per tutti i record di una tabella. Se le informazioni ACL sono archiviate in una tabella separata, potrebbe essere necessario eseguire un join con tali tabelle nella query.

L'utilizzo di ogni colonna ACL nella query precedente è descritto di seguito. Nell'elenco seguente vengono illustrati i quattro **meccanismi di controllo di accesso.**

- **AllowedUsers:** questa colonna specifica l'elenco degli ID utente che possono accedere ai risultati della ricerca. Nell'esempio seguente, l'elenco degli utenti: john@contoso.com, keith@contoso.com e lisa@contoso.com avrebbe accesso solo a un record con OrderId = 12.
- **AllowedGroups**: questa colonna specifica il gruppo di utenti che potranno accedere ai risultati della ricerca. Nell'esempio seguente il gruppo sales-team@contoso.com avrebbe accesso solo al record con OrderId = 12.
- **DeniedUsers:** questa colonna specifica l'elenco di utenti che **non** hanno accesso ai risultati della ricerca. Nell'esempio seguente gli utenti john@contoso.com e keith@contoso.com non hanno accesso al record con OrderId = 13, mentre tutti gli altri utenti hanno accesso a questo record.
- **DeniedGroups:** questa colonna specifica il gruppo di utenti che **non** hanno accesso ai risultati della ricerca. Nell'esempio seguente i gruppi engg-team@contoso.com e pm-team@contoso.com non hanno accesso al record con OrderId = 15, mentre tutti gli altri utenti hanno accesso a questo record.  

![Dati di esempio che mostrano OrderTable e AclTable con proprietà di esempio](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Tipi di dati supportati

Nella tabella seguente sono riepilogati SQL tipi di dati supportati nei connettori di SQL e azure SQL. Nella tabella viene inoltre riepilogato il tipo di dati di indicizzazione per il tipo di SQL supportato. Per ulteriori informazioni sui tipi di dati supportati dai connettori di Microsoft Graph per l'indicizzazione, vedere la documentazione relativa ai [tipi di risorse delle proprietà.](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true)

| Categoria | Tipo di dati di origine | Tipo di dati di indicizzazione |
| ------------ | ------------ | ------------ |
| Data e ora | data <br> datetime <br> datetime2 <br> smalldatetime | datetime |
| Numeri esatti | bigint <br> int <br> smallint <br> tinyint | int64 |
| Numeri esatti | bit | boolean |
| Numero approssimativo | float <br> real | double |
| Stringa di caratteri | char <br> varchar <br> text | stringa |
| Stringhe di caratteri Unicode | nchar <br> nvarchar <br> ntext | stringa |
| Altri tipi di dati | uniqueidentifier | stringa |

Per qualsiasi altro tipo di dati attualmente non direttamente supportato, è necessario eseguire in modo esplicito il cast della colonna a un tipo di dati supportato.

### <a name="watermark-required"></a>Filigrana (obbligatorio)

Per evitare l'overload del database, il connettore esegue il batch e riprende le query di ricerca per indicizzazione completa con una colonna di filigrane per la ricerca per indicizzazione completa. Utilizzando il valore della colonna filigrana, ogni batch successivo viene recuperato e l'esecuzione di query viene ripresa dall'ultimo checkpoint. In sostanza, questo meccanismo controlla l'aggiornamento dei dati per le ricerche per indicizzazione complete.

Creare frammenti di codice di query per filigrane come illustrato negli esempi seguenti:

- `WHERE (CreatedDateTime > @watermark)`. Cita il nome della colonna della filigrana con la parola chiave `@watermark` riservata. Se l'ordinamento della colonna della filigrana è crescente, utilizzare `>` ; in caso contrario, utilizzare `<` .
- `ORDER BY CreatedDateTime ASC`. Ordinare in base alla colonna della filigrana in ordine crescente o decrescente.

Nella configurazione mostrata nell'immagine seguente, `CreatedDateTime` è la colonna della filigrana selezionata. Per recuperare il primo batch di righe, specificare il tipo di dati della colonna della filigrana. In questo caso, il tipo di dati è `DateTime` .

![Configurazione colonna filigrana](media/MSSQL-watermark.png)

La prima query recupera il primo **numero N** di righe utilizzando: "CreatedDateTime > January 1, 1753 00:00:00" (valore minimo del tipo di dati DateTime). Dopo il recupero del primo batch, il valore più alto restituito nel batch viene salvato come checkpoint se le righe sono ordinate `CreatedDateTime` in ordine crescente. Un esempio è il 1° marzo 2019 03:00:00. Il batch successivo di **N** righe viene quindi recuperato utilizzando "CreatedDateTime > March 1, 2019 03:00:00" nella query.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorare le righe eliminate in modo reciso (facoltativo)

Per escludere le righe eliminate in modo resciso nel database dall'indicizzazione, specificare il nome e il valore della colonna con eliminazione rescisa che indica che la riga è stata eliminata.

![Impostazioni di eliminazione recisa: "Colonna di eliminazione rescisa" e "Valore della colonna di eliminazione rescisa che indica una riga eliminata"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Ricerca per indicizzazione completa: gestire le autorizzazioni di ricerca

Selezionare **Gestisci autorizzazioni per** scegliere le varie colonne di controllo di accesso (ACL) che specificano il meccanismo di controllo di accesso. Selezionare il nome di colonna specificato nella query di ricerca per indicizzazione SQL completa.

Ogni colonna ACL deve essere una colonna multivalore. Questi valori ID multipli possono essere separati da separatori, ad esempio punto e virgola (;), virgola (,) e così via. È necessario specificare questo separatore nel campo **separatore di** valore.

I tipi di ID seguenti sono supportati per l'utilizzo come ACL:

- **Nome entità utente (UPN):** un nome dell'entità utente (UPN) è il nome di un utente di sistema in un formato di indirizzo di posta elettronica. Un UPN (ad esempio: john.doe@domain.com) è costituito dal nome utente (nome di accesso), dal separatore (simbolo @) e dal nome di dominio (suffisso UPN).
- **ID di Azure Active Directory (AAD):** in Azure AD, ogni utente o gruppo ha un ID oggetto simile a "e0d3ad3d-0000-1111-2222-3c5f5c52ab9b".
- ID di sicurezza di **Active Directory (AD):** in una configurazione di Active Directory locale, ogni utente e gruppo dispone di un identificatore di sicurezza univoco non modificabile simile a "S-1-5-21-3878594291-2115959936-132693609-65242".

![Impostazioni delle autorizzazioni di ricerca per configurare gli elenchi di controllo di accesso](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Passaggio 3b: Ricerca per indicizzazione incrementale (facoltativo)

In questo passaggio facoltativo specificare una query SQL eseguire una ricerca per indicizzazione incrementale del database. Con questa query, il connettore SQL determina eventuali modifiche apportate ai dati dopo l'ultima ricerca per indicizzazione incrementale. Come nella ricerca per indicizzazione completa, selezionare tutte le colonne in cui si desidera selezionare le opzioni **Query,** **Ricerca** o **Recupera.** Specificare lo stesso set di colonne ACL specificato nella query di ricerca per indicizzazione completa.

I componenti nell'immagine seguente sono simili ai componenti di ricerca per indicizzazione completa con un'eccezione. In questo caso, "ModifiedDateTime" è la colonna della filigrana selezionata. Esaminare i [passaggi completi della ricerca per](#step-3a-full-crawl-required) indicizzazione per informazioni su come scrivere la query di ricerca per indicizzazione incrementale e vedere l'immagine seguente come esempio.

![Script di ricerca per indicizzazione incrementale che mostra le proprietà OrderTable, AclTable e di esempio che è possibile utilizzare.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Passaggio 4: Assegnare etichette di proprietà

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-5-manage-schema"></a>Passaggio 5: Gestire lo schema

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-6-manage-search-permissions"></a>Passaggio 6: Gestire le autorizzazioni di ricerca

È possibile scegliere di utilizzare gli [elenchi di](#full-crawl-manage-search-permissions) controllo di accesso specificati nella schermata di ricerca per indicizzazione completa oppure di eseguirne l'override per rendere il contenuto visibile a tutti.

## <a name="step-7-choose-refresh-settings"></a>Passaggio 7: Scegliere le impostazioni di aggiornamento

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-8-review-connection"></a>Passaggio 8: esaminare la connessione

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="next-steps-customize-the-search-results-page"></a>Passaggi successivi: Personalizzare la pagina dei risultati di ricerca

Creare verticali e tipi di risultati personalizzati, in modo che gli utenti finali possano visualizzare i risultati della ricerca da nuove connessioni. Senza questo passaggio, i dati della connessione non vengono visualizzati nella pagina dei risultati della ricerca.

Per ulteriori informazioni su come creare verticali e mrt, vedere Personalizzazione della pagina [dei risultati di ricerca.](customize-search-page.md)

<!---## Troubleshooting-->

<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitazioni

I SQL connettori hanno queste limitazioni nella versione di anteprima:

- Connettore SQL server Microsoft: il database locale deve essere SQL server versione 2008 o successiva.
- La sottoscrizione di M365 e la sottoscrizione di Azure (che ospita il database di Azure SQL) devono trovarsi nello stesso Azure Active Directory.
- Gli elenchi di controllo di accesso sono supportati solo tramite un nome dell'entità utente (UPN), Azure Active Directory (Azure AD) o la sicurezza di Active Directory.
- L'indicizzazione di contenuto rtf all'interno di colonne di database non è supportata. Esempi di contenuto di questo tipo sono HTML, JSON, XML, BLOB e analisi dei documenti presenti come collegamenti all'interno delle colonne del database.
