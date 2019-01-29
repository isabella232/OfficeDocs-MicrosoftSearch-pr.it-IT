---
title: Aggiungere una casella di ricerca al sito intranet
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
description: Ottenere suggerimenti per la ricerca pertinente e trovare più rapidamente i risultati di lavoro mediante l'aggiunta di una casella di ricerca Microsoft Search a un sito intranet o una pagina.
ms.openlocfilehash: 699cfd9c411c9b86f3a2f8742c425aaedef1ebc5
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612418"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Aggiungere una casella di ricerca al sito intranet

Per l'accesso rapido a suggerimenti per la ricerca pertinente e i risultati di lavoro, aggiungere una casella di ricerca Microsoft Search a qualsiasi sito intranet o una pagina.
  
## <a name="add-a-search-box-to-an-intranet-page"></a>Aggiungere una casella di ricerca a una pagina intranet

È necessario aggiungere due elementi alla pagina: per la casella di ricerca e lo script che si un contenitore.
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

In un sito SharePoint classico, aggiungere una Web Editor di Script Part e caduta lo script.
  
## <a name="enable-the-search-box-for-mobile"></a>Selezionare la casella di ricerca per dispositivi mobili

Per i siti intranet o pagine disponibili per gli utenti mobili, aggiungere isMobile: true per l'oggetto impostazioni:
  
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

## <a name="put-focus-on-the-search-box-by-default"></a>Rendere attiva la casella di ricerca per impostazione predefinita

Per consentire agli utenti di ricerca più veloce, quando i carichi di pagina o del sito posizionare il cursore nella casella di ricerca aggiungendo lo stato attivo: true per l'oggetto impostazioni:
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a>Utilizzare un iFrame per incorporare una casella di ricerca

Se incorporare uno script, non è un'opzione per il sito, utilizzare un iFrame per aggiungere la casella di ricerca:
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
