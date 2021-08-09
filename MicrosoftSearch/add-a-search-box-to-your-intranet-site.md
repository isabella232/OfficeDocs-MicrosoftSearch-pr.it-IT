---
title: Aggiungere una casella di ricerca al sito Intranet
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: Ottenere suggerimenti di ricerca pertinenti e trovare risultati di lavoro più velocemente aggiungendo una Microsoft Search di ricerca al sito o alla pagina Intranet.
ms.openlocfilehash: f11fcbeee23346041e4ebc720e4256d3aba29d57bed9266ed04bb02ee31c2ada
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533394"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Aggiungere una casella di ricerca al sito Intranet

Per consentire agli utenti di accedere facilmente ai risultati dell'organizzazione, aggiungere un Microsoft Search nella Bing di ricerca a qualsiasi sito o pagina Intranet. Ecco alcuni dei vantaggi:

- Una casella di ricerca nel portale SharePoint intranet offre un punto di ingresso attendibile e familiare per iniziare la ricerca
- Supporta tutti i principali Web browser, tra cui Google Chrome e Microsoft Edge
- Vengono visualizzati solo i suggerimenti di ricerca dell'organizzazione, i suggerimenti Web non vengono mai inclusi
- Porta gli utenti a un Microsoft Search in Bing risultati di lavoro, che esclude annunci e risultati Web
- Puoi controllare l'aspetto e il comportamento della casella di ricerca, inclusa la possibilità di impostare gli utenti su un verticale predefinito o personalizzato che hai creato
  
## <a name="add-a-search-box-to-an-intranet-page"></a>Aggiungere una casella di ricerca a una pagina Intranet

È necessario aggiungere due elementi alla pagina: un contenitore per la casella di ricerca e lo script che la fa funzionare.
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

In un sito di SharePoint classico, aggiungere una Web part Editor di script e inserire lo script al suo interno.
  
## <a name="enable-the-search-box-for-mobile"></a>Abilitare la casella di ricerca per i dispositivi mobili

Per i siti Intranet o le pagine disponibili per gli utenti mobili, aggiungere isMobile:true all'oggetto impostazioni:
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox", 
        isMobile: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="put-focus-on-the-search-box-by-default"></a>Configurare lo stato attivo sulla casella di ricerca per impostazione predefinita

Per consentire agli utenti di eseguire ricerche più velocemente, durante il caricamento della pagina o del sito posizionare il cursore nella casella di ricerca aggiungendo focus:true all'oggetto impostazioni:
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        focus: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="customize-the-appearance-of-the-search-box"></a>Personalizzare l'aspetto della casella di ricerca 

Sono disponibili numerose opzioni di configurazione per adattare meglio la casella di ricerca allo stile della Intranet. Combinare le opzioni in base alle esigenze.

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: false
        iconColor: "#067FA6",                   // default: #067FA6
        title: "Search box",                    // default: "Search box"
        vertical: "Person-people",              // default: not specified, search box directs to the All vertical on the WORK results page
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="direct-users-to-a-default-or-custom-vertical"></a>Indirizzare gli utenti a un verticale predefinito o personalizzato

Per garantire una facile integrazione tra le app line-of-business o i siti Intranet e i risultati di lavoro, è anche possibile personalizzare la casella di ricerca specificando un verticale predefinito o personalizzato su cui gli utenti devono accedere quando fanno clic su un suggerimento di ricerca.

Utilizzare l'opzione verticale in bfbSearchBoxConfig per definire il verticale desiderato. Ad esempio, se si desidera che gli utenti atterrino sempre sul verticale Siti, uno dei verticali predefiniti, utilizzare il valore "Site-sites".

:::image type="content" alt-text="Screenshot of work results page on Microsoft Search in Bing showing the Sites vertical results and URL." source="media/sites-vertical-esb.png" lightbox="media/sites-vertical-esb.png":::

Per i verticali personalizzati, usa l'hash alla fine dell'URL. È possibile trovare questi valori eseguendo una ricerca dalla pagina di lavoro in Bing, facendo clic su un'etichetta verticale e copiando il valore dopo il simbolo del numero (#).

:::image type="content" alt-text="Screenshot della pagina dei risultati di lavoro Microsoft Search in Bing che mostra un URL e risultati verticali di presentazione personalizzati." source="media/custom-vertical-esb.png" lightbox="media/custom-vertical-esb.png":::

## <a name="use-an-iframe-to-embed-a-search-box"></a>Usare un iFrame per incorporare una casella di ricerca

Se non è possibile incorporare uno script nel sito, usare un iFrame per aggiungere la casella di ricerca. Non sarà possibile personalizzare la casella di ricerca.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```

## <a name="inprivate-mode-and-conditional-access"></a>Modalità InPrivate e Accesso condizionale

Una casella di ricerca incorporata verrà disabilitata se la pagina o il sito viene aperto in una finestra InPrivate. Inoltre, con il supporto dell'accesso condizionale di Azure AD in Microsoft Edge, Bing.com non supporta l'accesso AAD quando si usa la modalità InPrivate. Per ulteriori informazioni sull'accesso condizionale in Edge, vedere [Microsoft Edge e Accesso condizionale](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge). 
