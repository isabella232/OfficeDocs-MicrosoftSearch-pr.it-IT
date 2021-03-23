---
title: Personalizzare la pagina Microsoft Search
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Aggiungere verticali di ricerca e personalizzare i risultati della ricerca
ms.openlocfilehash: 75dd6193308f52e7bfbb787d8f8dc27def834751
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031648"
---
# <a name="customize-the-search-results-page"></a>Personalizzare la pagina dei risultati della ricerca

È possibile creare verticali di ricerca e tipi di risultati per personalizzare i risultati della ricerca visualizzati dagli utenti durante la ricerca in Microsoft [SharePoint,](https://sharepoint.com/) [Microsoft Office](https://office.com)e Microsoft Search in [Bing.](https://bing.com) I verticali facilitano agli utenti l'individuazione delle informazioni di cui dispongono dell'autorizzazione per la visualizzazione. Ad esempio, è possibile creare un verticale di ricerca per i dati di analisi di marketing da software di terze parti per gli utenti del reparto marketing. È inoltre possibile definire tipi di risultati e personalizzare il layout per questi dati.  

È possibile creare verticali e tipi di risultati a questi livelli:

- **Livello** dell'organizzazione: quando si aggiunge un verticale a livello di organizzazione, questo viene visualizzato nella pagina dei risultati di ricerca quando gli utenti esere esere in una ricerca dalla pagina iniziale di [SharePoint,](https://sharepoint.com/) in [Office](https://office.com)o [in Bing.](https://bing.com)
- **Livello di** sito: ad esempio, è possibile consentire ai dipendenti del servizio clienti di cercare eventi imprevisti di *gravità 1* direttamente dal sito di SharePoint del proprio reparto.

## <a name="search-verticals-explained"></a>Verticali di ricerca spiegati

Nella parte superiore della pagina dei risultati di Microsoft Search è presente una riga di schede. Questi sono i verticali di ricerca. Un verticale di ricerca mostra solo i risultati di un determinato tipo o di determinati contenuti. Esempi sono **File** o **Notizie.** Per impostazione predefinita, Microsoft Search mostra i verticali **All,** **People,** **Files,** **Sites** e **News.**  

È possibile aggiungere verticali di ricerca rilevanti per l'organizzazione. Questi elementi verranno visualizzati nella pagina dei risultati di Microsoft Search in [SharePoint,](https://sharepoint.com/) [Office](https://Office.com)e [Bing.](https://bing.com) Ad esempio, è possibile creare un verticale per il contenuto correlato al marketing e un altro per le vendite, in base al tipo di informazioni necessarie per ogni gruppo. È possibile aggiungere verticali per visualizzare i risultati solo dal contenuto indicizzato tramite connettori.  

### <a name="multiple-connections-in-a-vertical"></a>Più connessioni in verticale

Un verticale di ricerca può ora visualizzare i risultati da più origini connettore. In questo modo si garantisce una maggiore flessibilità nella progettazione della pagina dei risultati di ricerca. L'esperienza amministrativa esistente della configurazione verticale consente di selezionare più connessioni nel passaggio "Origine contenuto".
Se nomini in modo accurato il maggior numero possibile di etichette semantiche, questa esperienza sarà migliorata. È possibile aggiungere etichette semantiche al momento della definizione e dell'inserimento dello schema.

[Ecco](configure-connector.md#step-5-assign-property-labels) altre informazioni su come creare e gestire le etichette semantiche.

### <a name="things-you-should-know"></a>Aspetti da conoscere

1. Una connessione può essere aggiunta come origine contenuto solo in un verticale. Il riutilizzo delle connessioni in più verticali non è consentito.
2. Se è necessario configurare una query per un verticale di ricerca in cui sono state aggiunte più origini di connessione, è necessario utilizzare proprietà di origine comuni per creare una query di questo tipo.

## <a name="things-to-consider"></a>Osservazioni

Prima di iniziare, verificare che il connettore sia stato indicizzato. Questa operazione può richiedere fino a 48 ore, a seconda delle dimensioni del file.

Non è possibile creare un verticale per il contenuto che si trova in [SharePoint.](https://sharepoint.com/)

Per aggiungere un verticale, è necessario eseguire tre passaggi di base:

1. Creare il verticale. In questo passaggio viene definito il nome, l'origine di contenuto e l'ambito del contenuto in cui eseguire la ricerca.
2. Definire l'aspetto dei risultati per questo verticale.  
3. Abilita il verticale (da visualizzare) dalla pagina elenco verticale.

## <a name="step-1-create-the-search-vertical"></a>PASSAGGIO 1: Creare il verticale di ricerca

Dopo aver avviato la procedura guidata, vengono descritti i passaggi per definire il nome, l'origine di contenuto e l'ambito del contenuto verticale in cui eseguire la ricerca. Il verticale viene creato in uno stato disabilitato. Lo abiliterai in un secondo momento.

È possibile utilizzare un set limitato di linguaggio [KQL (Keyword Query Language)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) per restringere l'ambito. In questa pagina sono elencate le proprietà disponibili. Ti consigliamo di usare parole chiave a testo libero e restrizioni di proprietà con operatori booleani per la creazione di KQL.

### <a name="create-a-vertical-at-the-organization-level"></a>Creare un verticale a livello di organizzazione

Per creare il verticale in Microsoft Search in [SharePoint](https://sharepoint.com/) Home, [Office](https://office.com)o [Bing,](https://bing.com)attenersi alla seguente procedura:

1. Nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com)passare a [**Verticali.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Seleziona **Aggiungi** per iniziare.  

### <a name="create-a-vertical-at-the-site-level"></a>Creare un verticale a livello di sito

1. Nel sito [di SharePoint](https://sharepoint.com/) in cui si desidera visualizzare il verticale, passare a **Impostazioni**.
2. Selezionare **Informazioni sito** e quindi Visualizza tutte le impostazioni del **sito.**
3. Cercare la **sezione Microsoft Search** e quindi selezionare Configura Microsoft Search per questa raccolta **siti.**
4. Nel riquadro di spostamento passare a **Esperienza personalizzata** e quindi selezionare la **scheda** Verticali.
5. Per aggiungere una verticale, selezionare **Aggiungi**.
  In caso contrario, per modificare un verticale, selezionarlo nell'elenco.

Tenere presente che i verticali vengono creati in uno stato disabilitato. Devono essere abilitati prima che gli utenti possano vederli.

## <a name="step-2-create-the-result-types"></a>PASSAGGIO 2: Creare i tipi di risultati

Puoi definire la modalità di visualizzazione dei risultati nel verticale progettando il layout usando i tipi di risultati. Il layout dei risultati ti consente di mostrare informazioni importanti direttamente nei risultati della ricerca, in modo che gli utenti non devono selezionare ogni risultato per vedere se hanno trovato quello che stanno cercando.

### <a name="default-search-result-layout"></a>Layout dei risultati di ricerca predefinito

Se le etichette e la proprietà  del  contenuto sono state mappate correttamente alle proprietà di origine al momento della configurazione del connettore, verrà visualizzato un layout dei risultati di ricerca predefinito per il contenuto del connettore. Il titolo **dell'etichetta** è l'etichetta più importante. È **consigliabile assegnare** una proprietà a questa etichetta per utilizzare il layout dei risultati di ricerca predefinito.

### <a name="create-your-own-result-type"></a>Creare un tipo di risultato personalizzato

È possibile decidere di creare un layout dei risultati di ricerca personalizzato ed eseguire l'override del layout dei risultati di ricerca predefinito creando un **tipo di risultato**. Un tipo di risultati di ricerca è una regola che determina la visualizzazione di tipi di risultati di ricerca diversi in modi differenti. È costituito dai seguenti elementi:

- **Una o più condizioni con** cui confrontare ogni risultato della ricerca, ad esempio l'origine contenuto del risultato della ricerca.  
- Layout **dei risultati da** utilizzare per i risultati della ricerca che soddisfano le condizioni. Il layout dei risultati controlla il modo in cui tutti i risultati che soddisfano le condizioni vengono visualizzati e si comportano in una pagina dei risultati di ricerca.

**Se non viene eseguito un mapping appropriato per visualizzare il layout dei risultati di ricerca predefinito, è necessario creare almeno un tipo di risultato per la visualizzazione dei risultati sul verticale.** È possibile creare più tipi di risultati per ogni verticale, che consente di utilizzare layout diversi per diversi tipi di risultati. Ad esempio, è possibile personalizzare gli eventi imprevisti di *gravità 1* in modo da avere colori più prominenti e un tipo di carattere più grande rispetto agli eventi imprevisti *di gravità 3.*

Dopo aver avviato la procedura guidata, vengono descritti i passaggi per definire il nome, l'origine di contenuto e le condizioni per il tipo di risultato. È possibile definire la priorità del tipo di risultato dalla visualizzazione elenco.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Creare un tipo di risultato a livello di organizzazione

1. Nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com)passare a [**Tipi di risultati**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).
2. Per aggiungere un **tipo di risultato,** selezionare **Aggiungi**. Per modificare un tipo di risultato, selezionare il tipo di risultato nell'elenco pertinente.

### <a name="create-a-results-type-at-the-site-level"></a>Creare un tipo di risultati a livello di sito

1. Nel sito [di SharePoint](https://sharepoint.com/) in cui si desidera creare il tipo di risultato passare a **Impostazioni**.
2. Selezionare **Informazioni sito** e quindi Visualizza tutte le impostazioni del **sito.**
3. Cercare la sezione Microsoft Search e quindi selezionare **Configura Microsoft Search per questa raccolta siti.**
4. Nel riquadro di spostamento passare a **Esperienza personalizzata** e selezionare scheda **Tipo di** risultato.
5. Per aggiungere un tipo di risultato, selezionare **Aggiungi**.  In caso contrario, per modificare un tipo di risultato, selezionare il tipo di risultato nell'elenco.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>PASSAGGIO 3: Visualizzare il verticale dopo che è stato abilitato

Dopo aver abilitato il verticale, potrebbe essere necessario un po' di tempo prima di poterlo visualizzare. Se non si desidera attendere dopo l'abilitazione, è possibile aggiungere **cacheClear=true** all'URL in [SharePoint](https://sharepoint.com/) e [Office](https://office.com) per visualizzare immediatamente il verticale. Per [Bing,](https://bing.com) **aggiungi&features=uncachedVerticals** all'URL verticale di lavoro per visualizzare immediatamente i verticali.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Ecco un elenco dei problemi comuni che potresti riscontrare e delle azioni per risolverli.

|Errore  |Azione  |
|---------|---------|
| Viene visualizzato un messaggio di errore "Si è verificato un problema" sulla verticale. | Per completare l'installazione sono necessari sia i tipi verticali che i tipi di risultati. Assicurarsi di aver creato entrambi per la stessa origine di contenuto. |
| Il layout dei risultati non è visualizzato, anche se ne è stato creato uno. | L'operazione richiede alcuni minuti perché queste impostazioni vengono in genere memorizzate nella cache. Attendere alcuni minuti e riprovare.        |
| Non viene visualizzata alcuna origine di contenuto nella pagina del tipo di risultato o verticale. | Assicurarsi di aver configurato i connettori e i dati indicizzati.   |

## <a name="next-steps"></a>Passaggi successivi

[Personalizzare il layout dei risultati](customize-results-layout.md)