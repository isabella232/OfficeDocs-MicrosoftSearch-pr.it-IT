---
title: Personalizzare la Microsoft Search pagina
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Aggiungere verticali di ricerca e personalizzare i risultati della ricerca
ms.openlocfilehash: 1ca436a2617e32e285715e4fffd622dc7a571ca1
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702175"
---
# <a name="customize-the-search-results-page"></a>Personalizzare la pagina dei risultati della ricerca

È possibile *creare* verticali di ricerca e tipi di risultati per personalizzare i risultati di ricerca visualizzati dagli utenti durante la ricerca in Microsoft [SharePoint,](https://sharepoint.com/)Microsoft Office e [Microsoft Search](https://office.com)in [Bing](https://bing.com).  I verticali facilitano agli utenti l'individuazione delle informazioni che sono autorizzati a visualizzare.

Ad esempio, è possibile creare un verticale di ricerca per i dati di analisi di marketing da software di terze parti per gli utenti del reparto marketing. È inoltre possibile definire tipi di risultati e personalizzare il layout per questi dati.

## <a name="about-search-verticals"></a>Informazioni sui verticali di ricerca

C'è una riga di schede nella parte superiore della pagina dei Microsoft Search risultati. Si tratta di verticali di ricerca. Un verticale di ricerca mostra solo i risultati di un determinato tipo o di un determinato set di contenuti. Esempi sono **File** o **Notizie.** Per impostazione predefinita, Microsoft Search i verticali **All,** **People,** **Files,** **Sites** e **News.**  

È possibile aggiungere verticali di ricerca rilevanti per l'organizzazione. Questi elementi verranno visualizzati nella pagina Microsoft Search risultati SharePoint, Office e Bing. Ad esempio, è possibile creare un verticale per il contenuto correlato al marketing e un altro per le vendite, in base al tipo di informazioni necessarie per ogni reparto. È possibile aggiungere verticali per visualizzare i risultati solo dal contenuto indicizzato tramite connettori.

È possibile creare verticali e tipi di risultati a due livelli:

- **Livello** dell'organizzazione: un verticale creato a livello di organizzazione viene visualizzato nella pagina dei risultati di ricerca quando gli utenti esere in una ricerca dalla pagina iniziale di [SharePoint,](https://sharepoint.com/) [Office](https://office.com)o [Bing](https://bing.com).
- **Livello di** sito: ad esempio, è possibile consentire ai dipendenti del servizio clienti di cercare gli eventi imprevisti di *gravità 1* direttamente dal sito di SharePoint del loro reparto.

### <a name="multiple-connections-in-a-vertical"></a>Più connessioni in verticale

Un verticale di ricerca può visualizzare i risultati da più origini connettore. Questa opzione offre flessibilità nella progettazione della pagina dei risultati di ricerca. Il processo di configurazione verticale consente agli amministratori di selezionare più connessioni nel passaggio "Origine contenuto".

Se nomini in modo accurato il maggior numero possibile di *etichette semantiche,* questa esperienza è migliorata. È possibile aggiungere etichette semantiche al punto di definizione e inserimento dello schema. [Vedi altre informazioni su come creare e gestire le etichette semantiche.](configure-connector.md#step-6-assign-property-labels)
[Ecco](configure-connector.md#step-6-assign-property-labels) altre informazioni su come creare e gestire le etichette semantiche.

> [!NOTE]
> Le connessioni multiple in una funzionalità verticale sono attualmente in anteprima. Per ulteriori informazioni, vedere [Funzionalità di anteprima dei connettori.](connectors-overview.md#what-are-the-preview-features)

È possibile aggiungere una connessione come origine contenuto in un'unica verticale. Non è possibile utilizzare connessioni in più verticali.

Per impostare una query per un verticale di ricerca in cui sono state aggiunte più origini di connessione, utilizzare proprietà di origine comuni per creare la query.

### <a name="before-you-create-verticals-and-result-types"></a>Prima di creare verticali e tipi di risultati

Prendere in considerazione questi fattori:

- Assicurarsi che il connettore sia stato indicizzato. Questa operazione può richiedere fino a 48 ore, a seconda delle dimensioni del file.

- Non è possibile creare un verticale per il contenuto che si trova in SharePoint.

Ecco i passaggi per implementare un verticale:

1. Creare il verticale. In questo passaggio viene definito il nome, l'origine di contenuto e l'ambito del contenuto in cui eseguire la ricerca.
2. Definire l'aspetto dei risultati per questo verticale.  
3. Abilita il verticale (da visualizzare) dalla pagina elenco verticale.

## <a name="step-1-create-the-search-vertical"></a>Passaggio 1: Creare il verticale di ricerca

Dopo aver avviato la procedura guidata, vengono descritti i passaggi per definire il nome, l'origine di contenuto e l'ambito del contenuto verticale in cui eseguire la ricerca.

>[!Note]
>I verticali vengono creati in uno stato disabilitato. Puoi abilitarli per renderli visualizzabili.

È possibile utilizzare un set limitato di linguaggio [KQL (Keyword Query Language)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) per restringere l'ambito. Le proprietà che è possibile utilizzare sono descritte più avanti in questo articolo. È consigliabile usare parole chiave a testo libero e restrizioni di proprietà con operatori booleani. KQL supporta anche variabili [di query di profilo](#profile-query-variables) per ottimizzare i risultati sotto il verticale.

### <a name="create-a-vertical-at-the-organization-level"></a>Creare un verticale a livello di organizzazione

Per creare un verticale Microsoft Search in SharePoint home, Office o Bing, attenersi alla seguente procedura:

1. Nella finestra [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com), andare a [**Verticali**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Seleziona **Aggiungi** per iniziare.  

### <a name="create-a-vertical-at-the-site-level"></a>Creare un verticale a livello di sito

1. Nel sito [SharePoint](https://sharepoint.com/) in cui si desidera visualizzare il verticale, passare a **Impostazioni**.
2. Selezionare **Informazioni sito** e quindi Selezionare Visualizza tutte le impostazioni del **sito.**
3. Individuare la **Microsoft Search** e quindi selezionare Configura Microsoft Search **per questa raccolta siti.**
4. Nel riquadro di spostamento passare a **Esperienza personalizzata** e quindi selezionare la **scheda** Verticali.
5. Per aggiungere un verticale, selezionare **Aggiungi**. Oppure per modificare un verticale, selezionarlo dall'elenco.

## <a name="step-2-create-result-types"></a>Passaggio 2: Creare tipi di risultati

È possibile utilizzare *i tipi di* risultati per definire la modalità di visualizzazione dei risultati in verticale. Il layout dei risultati ti consente di mostrare informazioni importanti direttamente nei risultati della ricerca, in modo che gli utenti non devono selezionare ogni risultato per vedere se hanno trovato quello che stanno cercando.

### <a name="default-search-result-layout"></a>Layout dei risultati di ricerca predefinito

Se le etichette e le proprietà del  contenuto  sono state mappate correttamente alle proprietà di origine al momento della configurazione del connettore, verrà visualizzato un layout dei risultati di ricerca predefinito per il contenuto del connettore. *L'etichetta* del titolo è l'etichetta più importante. È *consigliabile* assegnare una proprietà a questa etichetta per utilizzare il layout dei risultati di ricerca predefinito.

### <a name="create-your-own-result-type"></a>Creare un tipo di risultato personalizzato

Per creare un layout dei risultati di ricerca personalizzato ed eseguire l'override del layout dei risultati di ricerca predefinito, creare un *tipo di risultato*. Un tipo di risultati di ricerca è una regola che determina la visualizzazione di tipi di risultati di ricerca diversi in modi differenti. È costituito da:

- **Una o più condizioni con** cui confrontare ogni risultato della ricerca, ad esempio l'origine contenuto del risultato della ricerca.  
- Layout **dei risultati da** utilizzare per i risultati della ricerca che soddisfano le condizioni. Il layout risultante controlla l'aspetto e il comportamento dei risultati che soddisfano le condizioni in una pagina dei risultati di ricerca.

*Se non si fa un mapping appropriato per visualizzare il layout dei risultati di ricerca predefinito, è necessario creare almeno un tipo di risultato per la visualizzazione dei risultati sul verticale.* 

È possibile creare più tipi di risultati per ogni verticale, che consente di utilizzare layout diversi per diversi tipi di risultati. Ad esempio, è possibile personalizzare gli eventi imprevisti di *gravità 1* in modo da avere colori più prominenti e un tipo di carattere più grande rispetto agli eventi imprevisti *di gravità 3.*

Dopo aver avviato la procedura guidata, vengono descritti i passaggi per definire il nome, l'origine di contenuto e le condizioni per il tipo di risultato. È possibile definire la priorità del tipo di risultato dalla visualizzazione elenco.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Creare un tipo di risultato a livello di organizzazione

1. Nella finestra [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com), passare a [**Tipi di risultati**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).
2. Per aggiungere un tipo di risultato, selezionare **Aggiungi**. Per modificare un tipo di risultato, selezionare il tipo di risultato nell'elenco pertinente.

### <a name="create-a-result-type-at-the-site-level"></a>Creare un tipo di risultato a livello di sito

1. Nel sito [SharePoint](https://sharepoint.com/) in cui si desidera il tipo di risultato, passare a **Impostazioni**.
2. Selezionare **Informazioni sito** e quindi Selezionare Visualizza tutte le impostazioni del **sito.**
3. Cercare la sezione **Microsoft Search** e quindi selezionare Configura Microsoft Search **per questa raccolta siti.**
4. Nel riquadro di spostamento passare a **Esperienza personalizzata** e selezionare la scheda **Tipo di** risultato.
5. Per aggiungere un tipo di risultato, selezionare **Aggiungi**.  In caso contrario, per modificare un tipo di risultato, selezionare il tipo di risultato nell'elenco.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>Passaggio 3: visualizzare il verticale dopo che è stato abilitato

Dopo aver abilitato il verticale, si verifica un ritardo di alcune ore prima di poterlo visualizzare. Tuttavia, puoi aggiungere `cacheClear=true` all'URL in SharePoint e Office per visualizzare immediatamente il verticale. Ad Bing, `&features=uncachedVerticals` accoda `Work vertical URL` all'oggetto per visualizzare immediatamente il verticale.

> [!NOTE]
> I verticali aggiunti non sono visibili SharePoint]( https://sharepoint.com/) e [Office](https://office.com) visualizzati dai Web browser per dispositivi mobili.

## <a name="profile-query-variables"></a>Variabili di query dei profili

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
| 2  | MyProperty:{Profile.emails}   |    {Profile.emails} Questa operazione non verrà risolta perché *i messaggi di posta* elettronica sono un oggetto.|
| 3     | {? MyProperty:{Profile.emails}}  |  Questa operazione non verrà risolta perché *i messaggi di posta* elettronica sono un oggetto. Il "?" l'operatore ignora le variabili di query che non vengono risolte. Questa variabile verrà rimossa quando viene passata più avanti nello stack di query.   |
| 4  | {&#124;MyProperty: {Profile.emails.source.Type}}    |  ((MyProperty:"official") o (MyProperty:"non-official") o (MyProperty:"personal"))    |

> [!NOTE]
>
> - Le variabili di query profilo sono supportate solo per verticali personalizzati che utilizzano un [connettore](connectors-overview.md) come origine di contenuto.
> - Le variabili di query dei profili sono definite nella sezione "Query" del processo [di installazione verticale.](customize-search-page.md#step-1-create-the-search-vertical)
> - La funzionalità delle variabili di query dei profili è attualmente in anteprima. Per ulteriori informazioni sull'anteprima, vedere [Funzionalità di anteprima dei connettori.](connectors-overview.md#what-are-the-preview-features)

## <a name="troubleshooting"></a>Risoluzione dei problemi

Ecco un elenco dei problemi comuni che potresti riscontrare e delle azioni per risolverli.

|Problema  |Azione  |
|---------|---------|
| Viene visualizzato un messaggio di errore "Si è verificato un problema" sulla verticale. | Per completare l'installazione sono necessari sia i tipi di risultati che verticali. Assicurarsi di aver creato entrambi per la stessa origine di contenuto. |
| Il layout dei risultati non è visualizzato, anche se ne è stato creato uno. | Potrebbe verificarsi un ritardo di alcuni minuti perché queste impostazioni vengono memorizzate nella cache. Attendere alcuni minuti e riprovare.        |
| Non viene visualizzata alcuna origine di contenuto nella pagina verticale o tipo di risultato. | Assicurarsi di aver configurato i connettori e i dati indicizzati.   |

## <a name="next-steps"></a>Passaggi successivi

[Personalizzare il layout dei risultati](customize-results-layout.md)
