---
title: Personalizzare la pagina di ricerca di Microsoft
ms.author: jypal6
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
description: Aggiungere verticali di ricerca e personalizzare i risultati di ricerca
ms.openlocfilehash: 97a43e057297712baef3bf91ac8b3b2fa80975ac
ms.sourcegitcommit: c22e8c3dcc53857da677db98a1a2b7d5ca2c6170
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41721769"
---
# <a name="customize-the-search-results-page"></a>Personalizzare la pagina dei risultati di ricerca

Se si creano i tipi di risultati e verticali di ricerca, è possibile personalizzare i risultati della ricerca visualizzati dagli utenti quando eseguono una ricerca in [SharePoint](http://sharepoint.com/), [Microsoft Office](https://Office.com)e Microsoft Search in [Bing](https://Bing.com). Per gli utenti è più facile trovare le informazioni che sono autorizzate a visualizzare. Ad esempio, è possibile creare un verticale di ricerca per i dati di analisi di marketing da software di terze parti per gli utenti del reparto marketing. È inoltre possibile definire i tipi di risultati e personalizzare il layout per tali dati.  

È possibile creare verticali e tipi di risultati a questi livelli:

- **Livello di organizzazione** : quando si aggiunge un verticale a livello dell'organizzazione, viene visualizzato nella pagina dei risultati della ricerca quando gli utenti eseguono una ricerca dalla pagina iniziale di [SharePoint](http://sharepoint.com/) , in [Office](https://Office.com)e su [Bing](https://Bing.com).
- **Livello di sito** , ad esempio, è possibile consentire ai dipendenti del servizio clienti di cercare gli incidenti di **gravità 1** direttamente dal sito di SharePoint del reparto.

## <a name="search-verticals-explained"></a>Spiegazioni verticali di ricerca

Nella parte superiore della pagina dei risultati di ricerca Microsoft è presente una riga di schede che rappresentano i verticali di ricerca. Un verticale di ricerca Visualizza solo i risultati di un determinato tipo o di un determinato contenuto. Un esempio è solo file o notizie. Per impostazione predefinita, Microsoft Search Visualizza **tutte**le verticali, **persone**, **file**, **siti**e **notizie**.  

È possibile aggiungere verticali di ricerca rilevanti per l'organizzazione. Questi verranno visualizzati nella pagina dei risultati della ricerca di Microsoft in [SharePoint](http://sharepoint.com/), [Office](https://Office.com)e [Bing](https://Bing.com). Ad esempio, è possibile creare un verticale per il contenuto relativo al marketing e un altro per le vendite, in base al tipo di informazioni che ogni gruppo vorrebbe avere. È possibile aggiungere verticali per visualizzare i risultati solo dal contenuto indicizzato tramite connettori.  

**Dichiarazione di non responsabilità:** I tipi di verticali e di risultati sono attualmente in anteprima come parte dell'anteprima dei connettori di Microsoft Graph. Non è possibile creare un verticale per il contenuto che risiede in [SharePoint](http://sharepoint.com/) o dal contenuto indicizzato dal [connettore di condivisione file](file-share-connector.md). Per ulteriori informazioni sull'anteprima, vedere l' [anteprima dei connettori](connectors-preview.md). Per partecipare all'anteprima, è necessario prima di tutto inviare il [modulo di iscrizione all'anteprima dei connettori Microsoft Graph](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).

## <a name="things-to-consider"></a>Osservazioni

Prima di iniziare, verificare che il connettore sia stato indicizzato. È possibile richiedere fino a 48 ore, a seconda delle dimensioni del file.

Non è possibile creare un verticale per il contenuto che risiede in [SharePoint](http://sharepoint.com/) o dal contenuto indicizzato dal [connettore di condivisione file](file-share-connector.md). Informazioni su come [indicizzare il contenuto](configure-connector.md).

A livello elevato, sono disponibili tre passaggi principali per l'aggiunta di un verticale:

1. Creare la verticale. In questo passaggio viene definito il nome, l'origine di contenuto e l'ambito del contenuto verticale da cercare.
2. Definire l'aspetto dei risultati per questo verticale.  
3. Abilitare la verticale (da visualizzare) dalla pagina dell'elenco verticale.

## <a name="step-1-create-the-search-vertical"></a>PASSAGGIO 1: creare il verticale di ricerca

Dopo aver avviato la procedura guidata, è possibile eseguire la procedura per definire il nome, l'origine di contenuto e l'ambito del contenuto verticale per la ricerca. La verticale viene creata in uno stato disabilitato. La verticale verrà abilitata in un secondo momento.

È possibile utilizzare un insieme limitato di [KQL (Keyword Query Language)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) per restringere l'ambito e la pagina elenca le proprietà disponibili. È consigliabile utilizzare parole chiave di testo e restrizioni di proprietà gratuite con operatori booleani per la creazione di KQL.

### <a name="create-a-vertical-at-the-organization-level"></a>Creare un verticale a livello dell'organizzazione

Per creare la verticale in Microsoft Search in [SharePoint](http://sharepoint.com/) Home, [Office](https://Office.com)o [Bing](https://Bing.com), eseguire la procedura seguente:

1. Nell'interfaccia di [Amministrazione](https://admin.microsoft.com)di Microsoft 365, passare **a impostazioni** >**verticali**di **ricerca** > di Microsoft.
1. Selezionare **Aggiungi** per iniziare.  

### <a name="create-a-vertical-at-the-site-level"></a>Creare un verticale a livello di sito

1. Nel sito di [SharePoint](http://sharepoint.com/) in cui si desidera creare la verticale, passare a **Impostazioni**.
1. Selezionare **informazioni sito** e quindi **tutte le impostazioni del sito**.
1. Cercare la sezione **Microsoft Search** e quindi fare clic su **configura Microsoft Search per la raccolta siti**.
1. Nel riquadro di spostamento, passare a **Custom Experience**, quindi selezionare la scheda **verticale** .
1. Per aggiungere un verticale, selezionare **Aggiungi**.  
OPPURE  
Per modificare un verticale, selezionarlo nell'elenco.

Tenere presente che i verticali vengono creati in uno stato disabilitato. È comunque necessario abilitarli prima che gli utenti possano visualizzare le verticali.

## <a name="step-2-create-the-result-types"></a>PASSAGGIO 2: creare i tipi di risultati

È possibile definire la modalità di visualizzazione dei risultati in verticale progettando il layout utilizzando i tipi di risultati. Il layout dei risultati consente di visualizzare informazioni importanti direttamente nei risultati di ricerca, in modo che gli utenti non debbano selezionare ogni risultato per vedere se hanno trovato ciò che stanno cercando.

Un tipo di risultati di ricerca è una regola che determina la visualizzazione di tipi di risultati di ricerca diversi in modi differenti. È costituito dai seguenti elementi:

- **Una o più condizioni** per confrontare ogni risultato di ricerca, ad esempio l'origine di contenuto del risultato della ricerca.  
- Un **layout** di risultati da utilizzare per i risultati di ricerca che soddisfano le condizioni. Il layout dei risultati controlla il modo in cui vengono visualizzati tutti i risultati che soddisfano le condizioni e si comportano in una pagina dei risultati della ricerca.

**È necessario creare almeno un tipo di risultato per visualizzare i risultati in verticale.** È possibile creare più tipi di risultati per ogni verticale, che consente di utilizzare layout diversi per diversi tipi di risultati. Ad esempio, è possibile personalizzare gli eventi di **gravità 1** per avere colori più prominenti e un tipo di carattere più grande rispetto a **gravità 3** incidenti.

Dopo aver avviato la procedura guidata, è possibile eseguire la procedura per definire il nome, l'origine di contenuto e le condizioni per il tipo di risultato. È possibile definire la priorità del tipo di risultati dalla visualizzazione elenco.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Creare un tipo di risultato a livello di organizzazione

1. Nell'interfaccia di [Amministrazione](https://admin.microsoft.com), andare a **impostare** > **Microsoft Search**, quindi selezionare **tipo di risultati**.
1. Per aggiungere un **tipo di risultati**, selezionare **Aggiungi**. Per modificare un tipo di risultati, selezionare il tipo di risultato nell'elenco pertinente.

### <a name="create-a-results-type-at-the-site-level"></a>Creare un tipo di risultati a livello di sito

1. Nel sito di [SharePoint](http://sharepoint.com/) in cui si desidera creare il tipo di risultati, passare a **Impostazioni**.
1. Selezionare **informazioni sito** e quindi **tutte le impostazioni del sito**.
1. Cercare la sezione Microsoft Search e quindi fare clic su **configura Microsoft Search per la raccolta siti**.
1. Nel riquadro di spostamento, passare a **Custom Experience**, quindi selezionare la scheda **tipo di risultato** .
1. Per aggiungere un tipo di risultati, selezionare **Aggiungi**.  
OPPURE  
Per modificare un tipo di risultati, selezionare il tipo di risultato nell'elenco.

### <a name="view-the-vertical-after-enabling"></a>Visualizzazione verticale dopo l'abilitazione

Dopo aver abilitato la verticale, potrebbe essere necessario un po' di tempo prima che sia possibile visualizzarla.
Se non si desidera attendere dopo l'abilitazione, è possibile aggiungere **cacheClear = true** all'URL in [SharePoint](http://sharepoint.com/) e [Office](https://Office.com) per visualizzare immediatamente il verticale.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Di seguito è visualizzato un elenco di problemi comuni che potrebbero verificarsi e le azioni per correggerli.

|Errore  |Azione  |
|---------|---------|
|Viene visualizzato un errore *errato* sulla verticale. |   Per completare il programma di installazione sono necessari sia i tipi verticali che quelli dei risultati. Assicurarsi di aver creato entrambi per la stessa origine di contenuto.      |
|Perché non viene visualizzato il layout dei risultati, anche se ne è stato creato uno? | Sono necessari alcuni minuti per l'utilizzo dei tipi di risultati poiché queste impostazioni vengono in genere memorizzate nella cache. Attendere qualche minuto e riprovare.        |
|Non vengono visualizzate origini di contenuto nella pagina tipo di risultato o verticale.     |      Assicurarsi di aver configurato i connettori e i dati indicizzati.   |

## <a name="next-steps"></a>Passaggi successivi

[PASSAGGIO 3: personalizzare il layout dei risultati](customize-results-layout.md)
