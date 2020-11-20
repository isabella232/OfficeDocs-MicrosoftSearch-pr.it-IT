---
title: Personalizzare la pagina di ricerca di Microsoft
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
description: Aggiungere verticali di ricerca e personalizzare i risultati di ricerca
ms.openlocfilehash: 8522a6daf05b718ee6a066272da181be6e95905e
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367488"
---
# <a name="customize-the-search-results-page"></a>Personalizzare la pagina dei risultati di ricerca

È possibile creare verticali di ricerca e tipi di risultati per personalizzare i risultati della ricerca visualizzati dagli utenti quando eseguono la ricerca in Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com)e Microsoft Search in [Bing](https://bing.com). Per gli utenti è più facile trovare le informazioni che dispongono dell'autorizzazione per l'accesso. Ad esempio, è possibile creare un verticale di ricerca per i dati di analisi di marketing da software di terze parti per gli utenti del reparto marketing. È inoltre possibile definire i tipi di risultati e personalizzare il layout per tali dati.  

È possibile creare verticali e tipi di risultati a questi livelli:

- **Livello di organizzazione** : quando si aggiunge un verticale a livello di organizzazione, viene visualizzato nella pagina dei risultati della ricerca quando gli utenti eseguono una ricerca dalla pagina iniziale di [SharePoint](https://sharepoint.com/) , in [Office](https://office.com)o su [Bing](https://bing.com).
- **Livello di sito** , ad esempio, potrebbe essere necessario consentire ai dipendenti del servizio clienti di cercare gli incidenti di *gravità 1* direttamente dal sito di SharePoint del reparto.

## <a name="search-verticals-explained"></a>Spiegazioni verticali di ricerca

Nella parte superiore della pagina dei risultati di ricerca Microsoft è presente una riga di tabulazioni. Questi sono i verticali di ricerca. Un verticale di ricerca Visualizza solo i risultati di un determinato tipo o di un determinato contenuto. Esempi sono **file** o **notizie**. Per impostazione predefinita, Microsoft Search Visualizza **tutte** le verticali, **persone**, **file**, **siti** e **notizie**.  

È possibile aggiungere verticali di ricerca rilevanti per l'organizzazione. Questi verranno visualizzati nella pagina dei risultati della ricerca di Microsoft in [SharePoint](https://sharepoint.com/), [Office](https://Office.com)e [Bing](https://bing.com). Ad esempio, è possibile creare un verticale per il contenuto relativo al marketing e un altro per le vendite, in base al tipo di informazioni necessarie per ciascun gruppo. È possibile aggiungere verticali per visualizzare i risultati solo dal contenuto indicizzato tramite connettori.  

### <a name="multiple-connections-in-a-vertical"></a>Più connessioni in un verticale

Un verticale di ricerca può ora riportare i risultati da più origini del connettore. Questo garantisce una maggiore flessibilità nella progettazione della pagina dei risultati di ricerca. L'esperienza amministrativa esistente per il programma di installazione verticale consente di selezionare più connessioni nel passaggio "origine di contenuto".
Se si nominano con precisione il numero di etichette semantiche possibili, questa esperienza verrà migliorata. È possibile aggiungere etichette semantiche sulla definizione dello schema e sull'ingestione.

Di [seguito](#configure-connector-step-5-assign-property-labels) vengono fornite ulteriori informazioni su come creare e gestire le etichette semantiche.

### <a name="things-you-should-know"></a>Aspetti da conoscere

1. È possibile aggiungere una connessione come origine di contenuto solo in una verticale. Non è consentito riutilizzare le connessioni in più verticali.
2. Se è necessario impostare una query per un verticale di ricerca in cui sono state aggiunte più origini di connessione, è consigliabile utilizzare proprietà di origine comuni per creare una query di questo tipo.

## <a name="things-to-consider"></a>Osservazioni

Prima di iniziare, verificare che il connettore sia stato indicizzato. Questo può richiedere fino a 48 ore, a seconda delle dimensioni del file.

Non è possibile creare un verticale per il contenuto che risiede in [SharePoint](https://sharepoint.com/).

Sono disponibili tre passaggi di base per aggiungere una verticale:

1. Creare la verticale. In questo passaggio viene definito il nome, l'origine di contenuto e l'ambito del contenuto verticale da cercare.
2. Definire l'aspetto dei risultati per questo verticale.  
3. Abilitare la verticale (da visualizzare) dalla pagina dell'elenco verticale.

## <a name="step-1-create-the-search-vertical"></a>PASSAGGIO 1: creare il verticale di ricerca

Dopo aver avviato la procedura guidata, è possibile eseguire le operazioni seguenti per definire il nome, l'origine di contenuto e l'ambito del contenuto in cui eseguire la ricerca. La verticale viene creata in uno stato disabilitato. Sarà possibile attivarlo in un secondo momento.

È possibile utilizzare un insieme limitato di [KQL (Keyword Query Language)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) per limitare l'ambito. In questa pagina sono elencate le proprietà disponibili. È consigliabile utilizzare le parole chiave FREETEXT e le restrizioni delle proprietà con gli operatori booleani per la creazione del KQL.

### <a name="create-a-vertical-at-the-organization-level"></a>Creare un verticale a livello dell'organizzazione

Per creare la verticale in Microsoft Search in [SharePoint](https://sharepoint.com/) Home, [Office](https://office.com)o [Bing](https://bing.com), eseguire la procedura seguente:

1. Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com), andare a [**verticali**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Selezionare **Aggiungi** per iniziare.  

### <a name="create-a-vertical-at-the-site-level"></a>Creare un verticale a livello di sito

1. Nel sito di [SharePoint](https://sharepoint.com/) in cui si desidera eseguire la verticale, passare a **Impostazioni**.
2. Selezionare **informazioni sito** e quindi **tutte le impostazioni del sito**.
3. Cercare la sezione **Microsoft Search** e quindi fare clic su **configura Microsoft Search per la raccolta siti**.
4. Nel riquadro di spostamento, passare a **Custom Experience**, quindi selezionare la scheda **verticale** .
5. Per aggiungere un verticale, selezionare **Aggiungi**.
  In alternativa, per modificare un verticale, selezionarlo nell'elenco.

Tenere presente che i verticali vengono creati in uno stato disabilitato. Devono essere abilitati prima che gli utenti possano visualizzarli.

## <a name="step-2-create-the-result-types"></a>PASSAGGIO 2: creare i tipi di risultati

È possibile definire la modalità di visualizzazione dei risultati in verticale progettando il layout utilizzando i tipi di risultati. Il layout dei risultati consente di visualizzare informazioni importanti direttamente nei risultati di ricerca, in modo che gli utenti non debbano selezionare ogni risultato per vedere se hanno trovato ciò che stanno cercando.

### <a name="default-search-result-layout"></a>Layout dei risultati di ricerca predefinito

Un layout dei risultati di ricerca predefinito verrà visualizzato per il contenuto del connettore se le **etichette** e la proprietà di **contenuto** sono state mappate correttamente alle proprietà di origine al momento della configurazione del connettore. Il **titolo** dell'etichetta è l'etichetta più importante. È **consigliabile** disporre di una proprietà assegnata a questa etichetta per utilizzare il layout dei risultati di ricerca predefinito.

### <a name="create-your-own-result-type"></a>Creare un tipo di risultato personalizzato

È possibile decidere di creare un layout dei risultati di ricerca personalizzato ed eseguire l'override del layout dei risultati di ricerca predefinito creando un **tipo di risultato**. Un tipo di risultati di ricerca è una regola che determina la visualizzazione di tipi di risultati di ricerca diversi in modi differenti. È costituito dai seguenti elementi:

- **Una o più condizioni** per confrontare ogni risultato di ricerca, ad esempio l'origine di contenuto del risultato della ricerca.  
- Un **layout** di risultati da utilizzare per i risultati di ricerca che soddisfano le condizioni. Il layout dei risultati controlla il modo in cui tutti i risultati che soddisfano le condizioni vengono visualizzati e si comportano in una pagina dei risultati di ricerca.

**Se non è possibile eseguire il mapping appropriato per visualizzare il layout dei risultati di ricerca predefinito, Ehi deve creare almeno un tipo di risultati per visualizzare i risultati in verticale.** È possibile creare più tipi di risultati per ogni verticale, che consente di utilizzare layout diversi per diversi tipi di risultati. Ad esempio, è possibile personalizzare gli eventi di *gravità 1* per avere colori più prominenti e un tipo di carattere più grande rispetto a *gravità 3* incidenti.

Dopo aver avviato la procedura guidata, è possibile eseguire la procedura per definire il nome, l'origine di contenuto e le condizioni per il tipo di risultato. È possibile definire la priorità del tipo di risultati dalla visualizzazione elenco.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Creare un tipo di risultato a livello di organizzazione

1. Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com)passare ai [**tipi di risultati**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).
2. Per aggiungere un **tipo di risultati**, selezionare **Aggiungi**. Per modificare un tipo di risultati, selezionare il tipo di risultato nell'elenco pertinente.

### <a name="create-a-results-type-at-the-site-level"></a>Creare un tipo di risultati a livello di sito

1. Nel sito di [SharePoint](https://sharepoint.com/) in cui si desidera creare il tipo di risultati, passare a **Impostazioni**.
2. Selezionare **informazioni sito** e quindi **tutte le impostazioni del sito**.
3. Cercare la sezione Microsoft Search e quindi fare clic su **configura Microsoft Search per la raccolta siti**.
4. Nel riquadro di spostamento, passare a **esperienza personalizzata** e selezionare la scheda **tipo di risultato** .
5. Per aggiungere un tipo di risultati, selezionare **Aggiungi**.  In alternativa, per modificare un tipo di risultati, selezionare il tipo di risultato nell'elenco.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>PASSAGGIO 3: visualizzare la verticale dopo che è stata abilitata

Dopo aver abilitato la verticale, potrebbe essere necessario un po' di tempo prima che sia possibile visualizzarla. Se non si desidera attendere dopo l'abilitazione, è possibile aggiungere **cacheClear = true** all'URL in [SharePoint](https://sharepoint.com/) e [Office](https://office.com) per visualizzare immediatamente il verticale.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Di seguito è visualizzato un elenco di problemi comuni che potrebbero verificarsi e le azioni da risolvere.

|Error  |Azione  |
|---------|---------|
| Viene visualizzato un messaggio di errore "qualcosa è andato storto" sul verticale. | Per completare l'installazione, sono necessari sia i tipi verticale che quelli dei risultati. Assicurarsi di aver creato entrambi per la stessa origine di contenuto. |
| Non viene visualizzato il layout dei risultati, anche se ne è stato creato uno. | Sono necessari alcuni minuti perché queste impostazioni vengono in genere memorizzate nella cache. Attendere qualche minuto e riprovare.        |
| Non vengono visualizzate origini di contenuto nella pagina tipo di risultato o verticale. | Assicurarsi di aver configurato i connettori e i dati indicizzati.   |

## <a name="next-steps"></a>Passaggi successivi

[PASSAGGIO 3: personalizzare il layout dei risultati](customize-results-layout.md)
