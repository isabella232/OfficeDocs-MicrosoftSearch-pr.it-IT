---
title: Aggiungere una casella di ricerca al sito Intranet
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
description: Ottenere suggerimenti di ricerca pertinenti e trovare i risultati di lavoro più velocemente aggiungendo una casella di ricerca Microsoft Search a un sito Intranet o una pagina.
ms.openlocfilehash: a66c0cea71cf637209d298f49542864755e92ec9
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508522"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Aggiungere una casella di ricerca al sito Intranet

Aggiungere una casella di ricerca Microsoft Search a qualsiasi pagina o sito Intranet per accedere rapidamente a suggerimenti di ricerca e risultati di lavoro pertinenti.
  
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
        dropShadow: true,                       // default: true
        iconColor: "#067FA6",                   // default: #067FA6
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work and the web"
                                                // when specified, text will be "Search the web and [Contoso]"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a>Usare un iFrame per incorporare una casella di ricerca

Se non è possibile incorporare uno script nel sito, usare un iFrame per aggiungere la casella di ricerca. Non sarà però possibile personalizzare l'aspetto della casella di ricerca.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```