---
title: Connettore SQL e Microsoft SQL Server Graph Azure per Microsoft Search
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
description: Configurare il connettore SQL Azure e Microsoft SQL Graph per Microsoft Search.
ms.openlocfilehash: ae953d55de4a4f5e8afc32cc6b55f6e0b32e2811
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375883"
---
<!---Previous ms.author: vivg --->

# <a name="azure-sql-and-microsoft-sql-server-graph-connectors"></a>Connettori SQL e Microsoft SQL Server Graph Azure

Il connettore di Microsoft SQL Server o azure SQL Graph consente all'organizzazione di individuare e indicizzare i dati da un database SQL Server locale o da un database ospitato nell'istanza di Azure SQL nel cloud.
Il connettore Graph indicizza il contenuto specificato Microsoft Search. Per mantenere aggiornato l'indice con i dati di origine, supporta ricerche per indicizzazione periodiche complete e incrementali. Con questi SQL, è anche possibile limitare l'accesso ai risultati della ricerca per determinati utenti.

> [!NOTE]
> Leggere [**l'articolo Setup your Graph connector**](configure-connector.md) to understand the general Graph connectors setup instructions.

Questo articolo è per tutti coloro che configurano, esere e monitorano un connettore SQL Azure e Microsoft SQL server Graph. Integra il processo di installazione generale e mostra le istruzioni valide solo per il connettore SQL Azure e Microsoft SQL server Graph. Questo articolo include anche informazioni [sulle limitazioni](#limitations) per il server Microsoft SQL e i connettori SQL Azure.

## <a name="before-you-get-started"></a>Prima di iniziare

### <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a>Installare l'Graph connettore (necessario solo per il connettore Microsoft SQL Server locale)

Per accedere ai dati di terze parti locali, è necessario installare e configurare l'agente Graph connettore. Per [ulteriori informazioni, vedere Install the Graph connector agent.](graph-connector-agent.md)

>[!NOTE]
>Se si utilizza l'autenticazione Windows durante la configurazione del connettore Microsoft SQL Server Graph, l'utente con cui si sta tentando di accedere deve disporre dei diritti di accesso interattivo per il computer Graph cui è installato l'agente connettore. Fare riferimento alla documentazione relativa [alla gestione dei criteri di accesso](/windows/security/threat-protection/security-policy-settings/allow-log-on-locally#policy-management) per controllare i diritti di accesso.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nella interfaccia di amministrazione di Microsoft 365

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Passaggio 2: assegnare un nome alla connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: Configurare le impostazioni di connessione

### <a name="register-an-app-for-azure-sql-connector-only"></a>Registrare un'app (solo per il connettore SQL Azure)

Per il connettore SQL Azure, è necessario registrare un'app in Azure Active Directory per consentire Microsoft Search'app di accedere ai dati per l'indicizzazione. Per altre informazioni sulla registrazione di un'app, fai riferimento alla documentazione di Microsoft Graph su come [registrare un'app.](/graph/auth-register-app-v2)

Dopo aver completato la registrazione dell'app e aver preso nota del nome dell'app, dell'ID dell'applicazione (client) e dell'ID tenant, devi generare [un nuovo segreto client.](/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret) Il segreto client verrà visualizzato una sola volta. Ricordarsi di & il segreto client in modo sicuro. Usa l'ID client e il segreto client durante la configurazione di una nuova connessione in Microsoft Search.

Per aggiungere l'app registrata al database SQL di Azure, devi:

- Accedere al database di Azure SQL
- Aprire una nuova finestra di query
- Creare un nuovo utente eseguendo il comando 'CREATE USER [nome app] FROM EXTERNAL PROVIDER'
- Aggiungere l'utente al ruolo eseguendo il comando 'exec sp_addrolemember 'db_datareader', [nome app]' o 'ALTER ROLE db_datareader ADD MEMBER [nome app]'

>[!NOTE]
>Per revocare l'accesso a qualsiasi app registrata in Azure Active Directory, fare riferimento alla documentazione di Azure [sulla rimozione di un'app registrata.](/azure/active-directory/develop/quickstart-remove-app)

### <a name="connection-settings"></a>Impostazioni di connessione

Per connettere il connettore Microsoft SQL Server a un'origine dati, è necessario configurare il server di database di cui si desidera eseguire la ricerca per indicizzazione e l'agente locale. È quindi possibile connettersi al database con il metodo di autenticazione richiesto.

> [!NOTE]
> - Il database deve essere SQL Server versione 2008 o successiva perché il connettore Microsoft SQL Server sia in grado di connettersi.
> - Il connettore SQL grafico di Azure consente solo l'inserimento da un'istanza di Azure SQL nello stesso [tenant](/azure/active-directory/develop/quickstart-create-new-tenant) di Microsoft 365. Il flusso di dati tra tenant non è supportato.

Per il connettore SQL Azure, è necessario specificare solo il nome del server o l'indirizzo IP a cui si desidera connettersi. Il connettore SQL Azure supporta solo l Azure Active Directory'autenticazione Open ID connect (OIDC) per connettersi al database.

Per una sicurezza aggiunta, è possibile configurare le regole del firewall IP per il SQL Server o il database di Azure. Per ulteriori informazioni sulla configurazione delle regole del firewall IP, fare riferimento alla documentazione relativa alle [regole del firewall IP.](/azure/azure-sql/database/firewall-configure) Aggiungere i seguenti intervalli IP client nelle impostazioni del firewall.

| Area geografica | Intervallo IP |
| ------------ | ------------ |
| NAM | 52.250.92.252/30, 52.224.250.216/30 |
| EUR | 20.54.41.208/30, 51.105.159.88/30 |
| APC | 52.139.188.212/30, 20.43.146.44/30 |

Per eseguire ricerche nel contenuto del database, è necessario specificare SQL query quando si configura il connettore. Queste SQL devono assegnare un nome a tutte le colonne di database che si desidera indicizzare, ovvero le proprietà di origine, inclusi gli eventuali join SQL che devono essere eseguiti per ottenere tutte le colonne. Per limitare l'accesso ai risultati della ricerca, è necessario specificare gli elenchi di controllo di accesso (ACL) all'interno SQL query quando si configura il connettore.

## <a name="step-3a-full-crawl-required"></a>Passaggio 3a: ricerca per indicizzazione completa (obbligatorio)

In questo passaggio viene configurata la query SQL che esegue una ricerca per indicizzazione completa del database. La ricerca per indicizzazione completa seleziona tutte le colonne o le proprietà in cui si desidera selezionare le opzioni **Query**, **Cerca** o **Recupera**. È inoltre possibile specificare colonne ACL per limitare l'accesso dei risultati della ricerca a utenti o gruppi specifici.

> [!Tip]
> Per ottenere tutte le colonne necessarie, è possibile unire più tabelle.

![Script che mostra OrderTable e AclTable con proprietà di esempio.](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Selezionare colonne di dati (obbligatorie) e colonne ACL (facoltativo)

Nell'esempio viene illustrata una selezione di cinque colonne di dati che contengono i dati per la ricerca: OrderId, OrderTitle, OrderDesc, CreatedDateTime e IsDeleted. Per impostare le autorizzazioni di visualizzazione per ogni riga di dati, è possibile selezionare le colonne ACL seguenti: AllowedUsers, AllowedGroups, DeniedUsers e DeniedGroups. Tutte queste colonne di dati dispongono inoltre delle opzioni **Query,** **Ricerca** o **Recupera.**

Selezionare le colonne di dati come illustrato in questa query di esempio: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Si noti che i SQL non consentono nomi di colonna con caratteri non alfanumerici nella clausola SELECT. Rimuovere eventuali caratteri non alfanumerici dai nomi di colonna utilizzando un alias. Esempio: SELECT *column_name* AS *columnName*

Per gestire l'accesso ai risultati della ricerca, è possibile specificare una o più colonne ACL nella query. Il SQL consente di controllare l'accesso a livello di record. È possibile scegliere di disporre dello stesso controllo di accesso per tutti i record di una tabella. Se le informazioni ACL sono archiviate in una tabella separata, potrebbe essere necessario eseguire un join con tali tabelle nella query.

L'utilizzo di ogni colonna ACL nella query precedente è descritto di seguito. Nell'elenco seguente vengono illustrati i quattro **meccanismi di controllo di accesso**.

- **AllowedUsers**: Questa colonna specifica l'elenco degli ID utente che possono accedere ai risultati della ricerca. Nell'esempio seguente, l'elenco degli utenti: john@contoso.com, keith@contoso.com e lisa@contoso.com avrebbe accesso solo a un record con OrderId = 12.
- **AllowedGroups**: Questa colonna specifica il gruppo di utenti che potranno accedere ai risultati della ricerca. Nell'esempio seguente, i gruppi sales-team@contoso.com possono accedere solo al record con OrderId = 12.
- **DeniedUsers**: Questa colonna specifica l'elenco di utenti che **non** hanno accesso ai risultati della ricerca. Nell'esempio seguente, gli utenti john@contoso.com e keith@contoso.com non hanno accesso al record con OrderId = 13, mentre tutti gli altri utenti hanno accesso a questo record.
- **DeniedGroups**: Questa colonna specifica il gruppo di utenti che **non** hanno accesso ai risultati della ricerca. Nell'esempio seguente i gruppi engg-team@contoso.com e pm-team@contoso.com non hanno accesso al record con OrderId = 15, mentre tutti gli altri utenti hanno accesso a questo record.  

![Dati di esempio che mostrano OrderTable e AclTable con proprietà di esempio.](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Tipi di dati supportati

Nella tabella seguente sono riepilogati SQL tipi di dati supportati nei connettori di SQL Ms e Azure SQL. La tabella riepiloga inoltre il tipo di dati di indicizzazione per il tipo di dati SQL supportato. Per ulteriori informazioni sui tipi di dati supportati Graph microsoft Graph per l'indicizzazione, fare riferimento alla documentazione relativa ai [tipi di risorse delle proprietà.](/graph/api/resources/property?preserve-view=true&view=graph-rest-beta#properties)

| Categoria | Tipo di dati di origine | Tipo di dati di indicizzazione |
| ------------ | ------------ | ------------ |
| Data e ora | data <br> datetime <br> datetime2 <br> smalldatetime | datetime |
| Numero esatto | bigint <br> int <br> smallint <br> tinyint | int64 |
| Numero esatto | bit | booleano |
| Numero approssimativo | float <br> real | double |
| Stringa di caratteri | char <br> varchar <br> text | stringa |
| Stringhe di caratteri Unicode | nchar <br> nvarchar <br> ntext | stringa |
| Altri tipi di dati | uniqueidentifier | stringa |

Per qualsiasi altro tipo di dati attualmente non supportato direttamente, è necessario eseguire in modo esplicito il cast della colonna a un tipo di dati supportato.

### <a name="watermark-required"></a>Filigrana (obbligatorio)

Per evitare l'sovraccarico del database, il connettore esegue in batch e riprende le query di ricerca per indicizzazione completa con una colonna filigrana di ricerca per indicizzazione completa. Utilizzando il valore della colonna watermark, ogni batch successivo viene recuperato e l'esecuzione di query viene ripresa dall'ultimo checkpoint. Essenzialmente, questo meccanismo controlla l'aggiornamento dei dati per le ricerche per indicizzazione complete.

Creare frammenti di codice di query per filigrane come illustrato negli esempi seguenti:

- `WHERE (CreatedDateTime > @watermark)`. Cita il nome della colonna della filigrana con la parola chiave riservata `@watermark` . Se l'ordinamento della colonna della filigrana è crescente, utilizzare `>` ; in caso contrario, utilizzare `<` .
- `ORDER BY CreatedDateTime ASC`. Ordinare in base alla colonna della filigrana in ordine crescente o decrescente.

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

- **Nome entità utente (UPN):** un nome dell'entità utente (UPN) è il nome di un utente di sistema in un formato di indirizzo di posta elettronica. Un UPN (ad esempio: john.doe@domain.com) è costituito dal nome utente (nome di accesso), dal separatore (simbolo @) e dal nome di dominio (suffisso UPN).
- **Azure Active Directory (AAD):** in Azure AD, ogni utente o gruppo ha un ID oggetto simile a 'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b'.
- ID di sicurezza di **Active Directory (AD):** in un'installazione di Active Directory locale, ogni utente e gruppo dispone di un identificatore di sicurezza univoco non modificabile simile a 'S-1-5-21-3878594291-2115959936-132693609-65242'.

![Impostazioni delle autorizzazioni di ricerca per configurare gli elenchi di controllo di accesso.](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Passaggio 3b: ricerca per indicizzazione incrementale (facoltativo)

In questo passaggio facoltativo, fornire una SQL query per eseguire una ricerca per indicizzazione incrementale del database. Con questa query, il connettore SQL determina eventuali modifiche apportate ai dati dopo l'ultima ricerca per indicizzazione incrementale. Come nella ricerca per indicizzazione completa, selezionare tutte le colonne in cui si desidera selezionare le opzioni **Query**, **Cerca** o **Recupera**. Specificare lo stesso set di colonne ACL specificato nella query di ricerca per indicizzazione completa.

I componenti nell'immagine seguente sono simili ai componenti di ricerca per indicizzazione completa con un'eccezione. In questo caso, "ModifiedDateTime" è la colonna della filigrana selezionata. Esaminare i [passaggi completi della ricerca per](#step-3a-full-crawl-required) indicizzazione per informazioni su come scrivere la query di ricerca per indicizzazione incrementale e vedere l'immagine seguente come esempio.

![Script di ricerca per indicizzazione incrementale che mostra le proprietà OrderTable, AclTable e di esempio che possono essere utilizzate.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Passaggio 4: Assegnare etichette di proprietà

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-5-manage-schema"></a>Passaggio 5: Gestire lo schema

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-6-manage-search-permissions"></a>Passaggio 6: Gestire le autorizzazioni di ricerca

È possibile scegliere di utilizzare gli [elenchi di](#full-crawl-manage-search-permissions) controllo di accesso specificati nella schermata di ricerca per indicizzazione completa oppure di ignorarli per rendere visibile il contenuto a tutti gli utenti.

## <a name="step-7-choose-refresh-settings"></a>Passaggio 7: Scegliere le impostazioni di aggiornamento

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-8-review-connection"></a>Passaggio 8: verificare la connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).-->

## <a name="troubleshooting"></a>Risoluzione dei problemi

Di seguito è riportato un errore comune rilevato durante la configurazione del connettore e il relativo possibile motivo.

| Passaggio di configurazione | Messaggio di errore | Possibili motivi |
| ------------ | ------------ | ------------ |
| Ricerca per indicizzazione completa | `Error from database server: A transport level error has occurred when receiving results from the server.` | Questo errore si verifica a causa di problemi di rete. È consigliabile controllare i registri di rete utilizzando [Network Monitor Microsoft](https://www.microsoft.com/download/details.aspx?id=4865) e contattare il supporto tecnico Microsoft. |
| Ricerca per indicizzazione completa | `Column column_name returned from full crawl SQL query contains non-alphanumeric character` | I caratteri non alfanumerici ,come i caratteri di sottolineatura, non sono consentiti nei nomi di colonna nella clausola SELECT. Utilizzare alias per rinominare le colonne e rimuovere caratteri non alfanumerici (esempio: SELECT column_name AS columnName). |

## <a name="limitations"></a>Limitazioni

I SQL connettori hanno queste limitazioni nella versione di anteprima:

- Microsoft SQL Server connettore: il database locale deve essere SQL Server versione 2008 o successiva.
- La Microsoft 365 e la sottoscrizione di Azure (che ospita il database di Azure SQL) devono trovarsi nello stesso Azure Active Directory.
- Gli ACL sono supportati solo tramite un nome dell'entità utente (UPN), Azure Active Directory (Azure AD) o la sicurezza di Active Directory.
- L'indicizzazione di contenuto rtf all'interno di colonne di database non è supportata. Esempi di questo tipo di contenuto sono HTML, JSON, XML, BLOB e analisi di documenti presenti come collegamenti all'interno delle colonne del database.
