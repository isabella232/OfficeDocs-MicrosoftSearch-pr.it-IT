---
title: Gestire i verticali di ricerca
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Gestire i verticali di ricerca nella pagina dei risultati
ms.openlocfilehash: 89887b6ce5391d2473692504efa3c0eb35407b48
ms.sourcegitcommit: 967a02ee932f8a6cee70cfd78bb0c8b1b78d07c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127789"
---
# <a name="manage-search-verticals"></a>Gestire i verticali di ricerca

I verticali di ricerca sono schede nella pagina dei risultati della ricerca che mostrano i risultati di un tipo specifico o da origini selezionate. Ad esempio, il verticale File mostra i risultati classificati come file e semplifica la ricerca di documenti per gli utenti. È possibile personalizzare i verticali in Microsoft Search per soddisfare le esigenze dell'organizzazione o dei singoli reparti.

È possibile gestire i verticali a due livelli:

- **Livello** dell'organizzazione: nella pagina dei risultati di ricerca viene visualizzato un verticale a livello di organizzazione quando gli utenti esere esere in cerca dalla pagina iniziale di [SharePoint,](https://sharepoint.com/) [Microsoft Office](https://office.com)e Microsoft Search in [Bing](https://bing.com)
- **Livello di sito:** un verticale a livello di sito viene visualizzato nella pagina dei risultati di ricerca quando gli utenti eseere in un SharePoint sito. Ad esempio, è possibile consentire ai dipendenti del servizio clienti di cercare gli eventi imprevisti di gravità 1 direttamente dal sito SharePoint del loro reparto.

## <a name="understanding-search-verticals"></a>Informazioni sui verticali di ricerca

Microsoft Search ha due tipi di verticali, predefiniti e verticali personalizzati. I verticali predefinito, ad esempio Tutti, File e Persone, creano un facile accesso ai risultati di ricerca usati più di frequente.

Ulteriori opzioni di configurazione sono disponibili su verticali personalizzati e possono essere usate per creare l'esperienza migliore per gli utenti.

È possibile aggiungere verticali di ricerca rilevanti per l'organizzazione. Ad esempio, è possibile creare un verticale per il contenuto correlato al marketing e un altro per le vendite, in base al tipo di informazioni necessarie per ogni reparto. È possibile aggiungere verticali per visualizzare i risultati del contenuto indicizzato da connettori Graph [,](connectors-overview.md)ma non è possibile creare un verticale per il contenuto che risiede in SharePoint.

## <a name="create-search-verticals"></a>Creare verticali di ricerca

L'esperienza di gestione verticale è guidata da una procedura guidata, in cui vengono descritti i passaggi per definire il nome, l'origine di contenuto e l'ambito del contenuto verticale in cui eseguire la ricerca. È possibile utilizzare un set limitato di linguaggio [KQL (Keyword Query Language)](#keyword-query-language-kql) per definire l'ambito della ricerca verticale per una determinata origine di contenuto.

Di seguito sono riportati i passaggi per creare i verticali personalizzati Microsoft Search in [SharePoint home,](https://sharepoint.com/) [Office](https://office.com/)o [Bing](https://bing.com/).  

### <a name="manage-organization-level-verticals"></a>Gestire verticali a livello di organizzazione

1. Nel [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com), passare alla [**pagina Verticali**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) nella sezione **Personalizzazione.**
1. Fare **clic su** Aggiungi per creare un nuovo verticale.
1. Dopo aver seguito i passaggi di configurazione, è possibile esaminare e salvare il verticale.  

### <a name="manage-site-level-verticals"></a>Gestire verticali a livello di sito

1. Nel sito SharePoint in cui vuoi gestire i verticali, apri il pannello delle impostazioni facendo clic sull'ingranaggio.
1. Selezionare **Informazioni sito** e quindi Selezionare Visualizza tutte le impostazioni del **sito.**  
1. Cercare la sezione Microsoft Search e quindi selezionare **Configura impostazioni di ricerca**.
1. Nel riquadro di spostamento passare a Esperienza personalizzata e quindi selezionare **Verticali.**
1. Fare **clic su** Aggiungi per creare un nuovo verticale.
1. Dopo aver impostato la configurazione, è possibile esaminare e salvare il verticale.  

## <a name="view-the-vertical-in-search-results"></a>Visualizzare il verticale nei risultati della ricerca

È [necessario un layout dei risultati](manage-result-types.md) di ricerca per Graph dei risultati del connettore di ricerca per il rendering nella pagina verticale di ricerca. Verificando che sia presente il layout dei risultati appropriato, puoi abilitare il verticale di ricerca. Dopo aver abilitato un verticale, si verifica un ritardo di alcune ore prima di poterlo visualizzare. Puoi aggiungere cacheClear=true all'URL in SharePoint e Office per visualizzare immediatamente il verticale. In Bing aggiungi &features=uncachedVerticals all'URL verticale di lavoro per visualizzare immediatamente il verticale.

> [!NOTE]
> I verticali aggiunti non sono visibili SharePoint [e](https://sharepoint.com/) [Office](https://office.com) visualizzati dai Web browser per dispositivi mobili.

## <a name="advanced-configuration-options"></a>Opzioni di configurazione avanzate

### <a name="multiple-connections-in-a-vertical"></a>Più connessioni in verticale

Un verticale di ricerca può visualizzare i risultati da più origini connettore. Questa opzione offre flessibilità nella progettazione della pagina dei risultati di ricerca. Il processo di configurazione verticale consente agli amministratori di selezionare più connessioni nel passaggio "Origine contenuto".

Se nomini in modo accurato il maggior numero possibile di *etichette semantiche,* questa esperienza è migliorata. È possibile aggiungere etichette semantiche al punto di definizione e inserimento dello schema. [Vedi altre informazioni su come creare e gestire le etichette semantiche.](configure-connector.md#step-6-assign-property-labels)
[Ecco](configure-connector.md#step-6-assign-property-labels) altre informazioni su come creare e gestire le etichette semantiche.

> [!NOTE]
> - Le connessioni multiple in una funzionalità verticale sono attualmente in anteprima. Per ulteriori informazioni, vedere [Funzionalità di anteprima dei connettori.](connectors-overview.md#what-are-the-preview-features)
> - È possibile aggiungere una connessione come origine contenuto in un'unica verticale. Non è possibile usare connessioni in più verticali.

Per impostare una query per un verticale di ricerca in cui sono state aggiunte più origini di connessione, utilizzare proprietà di origine comuni per creare la query.

### <a name="keyword-query-language-kql"></a>Keyword Query Language (KQL)

È possibile aggiungere una query a un verticale per limitare i risultati visualizzati sul verticale di ricerca utilizzando [Keyword Query Language (KQL) (supporto](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) limitato). In questa pagina sono elencate le proprietà disponibili. Ti consigliamo di usare parole chiave a testo libero e restrizioni di proprietà con operatori booleani per la creazione di KQL. Gli operatori di classificazione dinamici come XRANK, gli operatori di prossimità e le parole non sono supportati.

Ecco alcune query di esempio.

|Scenario         | Query   |  
| --------- | ------ |
|Esclusione dei risultati dai siti di archiviazione           |NOT (percorso:http//contoso.sharepoint.com/archive OR path:http//contoso.sharepoint.com/CompanyArchive)|
| Esclusione dei risultati in base alla proprietà del tipo di file | NOT(FileType:htm)|  

#### <a name="profile-query-variables"></a>Variabili di query dei profili

Utilizzare variabili nella sezione query KQL di un verticale per fornire dati dinamici come input per la query di un verticale. È possibile utilizzare variabili di query di profilo per rendere contestuali i risultati della ricerca all'utente connesso. Le variabili di query dei profili recuperano i valori dal profilo dell'utente [connesso.](/graph/api/resources/profile)

Ad esempio, per creare un verticale "Ticket" per l'utente per trovare i ticket di supporto assegnati, è possibile specificare la query seguente nella sezione "Query" durante la creazione verticale nella pagina di amministrazione:  

`AssignedTo:{Profile.accounts.userPrincipalName}`

Questa lingua restringe i risultati della ricerca per visualizzare solo gli elementi per i quali l'assegnatare è l'utente che esegue la ricerca.

[La risorsa profilo](/graph/api/resources/profile) espone le proprietà come raccolte. Ad esempio, le informazioni relative agli indirizzi di posta elettronica vengono esposte tramite la raccolta di posta elettronica, le posizioni lavorative come raccolta posizioni e così via. Tutte le proprietà disponibili nel profilo utente, che hanno AAD come tipo di origine, vengono esposte come variabili di query.

Considerare un utente che ha tre indirizzi di posta elettronica disponibili nella raccolta di posta elettronica, come illustrato di seguito:

```json
"emails": [{ 

        "address": "Megan.Bowen@contoso.com",
        "id": "xyz", 
        "source": { 
            "CreatedBy": "xyz", 
            "CreatedOn": "2222", 
            "Type": "official" 
        },
        "type": "main" 
    }, { 
        "address": "meganb@hotmail.com",
        "id": "abc", 
        "source": { 
            "CreatedBy": "abc",
            "CreatedOn": "3333", 
            "Type": "non-official",
        },
        "type": "work"
    }, { 
        "address": "meganb@outlook.com",
        "id": "pqr", 
        "source": { 
            "CreatedBy": "pqr", 
            "CreatedOn": "4444", 
            "Type": "personal" 
        },
        "type": "personal" 
    } 
] 
```

- La query `MyProperty: {Profile.emails.address}` verrà risolta *in MyProperty: "Megan.Bowen@contoso.com"*.  

- Per risolvere tutti i valori dell'attributo address, utilizzare la sintassi di espansione multivalore. La query verrà risolta in `{|MyProperty:{Profile.emails.address}}` *((MyProperty:"Megan.Bowen@contoso \. com")* o *(MyProperty: "meganb@hotmail \. com")* o *(MyProperty:"meganb@outlook \. com")).*

Utilizzare l'operatore "|" per risolvere variabili multivalore. Vedi la tabella seguente per altri esempi di espansione dei profili.

| #         | Sintassi |  Valore restituito  |
| --------- | ------ | --- |
| 1    | MyProperty:{Profile.emails.address}  |   "Megan \. Bowen@contoso.com"  |
| 2 | MyProperty:{Profile.emails}   |    {Profile.emails} Questa operazione non verrà risolta perché *i messaggi di posta* elettronica sono un oggetto.|
| 3     | {? MyProperty:{Profile.emails}}  |  Questa operazione non verrà risolta perché *i messaggi di posta* elettronica sono un oggetto. Il "?" l'operatore ignora le variabili di query che non vengono risolte. Questa variabile verrà rimossa quando viene passata più avanti nello stack di query.   |
| 4  | {&#124;MyProperty: {Profile.emails.source.Type}}    |  ((MyProperty:"official") o (MyProperty:"non-official") o (MyProperty:"personal"))    |

> [!NOTE]
>
> - Le variabili di query profilo sono supportate solo per verticali personalizzati che utilizzano un [connettore](connectors-overview.md) come origine di contenuto.
> - La funzionalità delle variabili di query dei profili è attualmente in anteprima. Per ulteriori informazioni sull'anteprima, vedere [Funzionalità di anteprima dei connettori.](connectors-overview.md#what-are-the-preview-features)

## <a name="troubleshooting"></a>Risoluzione dei problemi

Ecco un elenco dei problemi comuni che potresti riscontrare e delle azioni per risolverli.

|Problema  |Azione  |
|---------|---------|
| Viene visualizzato un messaggio di errore "Si è verificato un problema" sulla verticale. | Per completare l'installazione sono necessari sia i tipi di risultati che verticali. Assicurarsi che entrambi siano impostati per l'origine di contenuto. |
| Non viene visualizzata alcuna origine di contenuto nella pagina verticale. | Assicurarsi di aver configurato i connettori e i dati indicizzati.   |
