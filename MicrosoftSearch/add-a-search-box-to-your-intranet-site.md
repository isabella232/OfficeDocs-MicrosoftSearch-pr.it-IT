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
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="82b1c-103">Aggiungere una casella di ricerca al sito intranet</span><span class="sxs-lookup"><span data-stu-id="82b1c-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="82b1c-104">Per l'accesso rapido a suggerimenti per la ricerca pertinente e i risultati di lavoro, aggiungere una casella di ricerca Microsoft Search a qualsiasi sito intranet o una pagina.</span><span class="sxs-lookup"><span data-stu-id="82b1c-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="82b1c-105">Aggiungere una casella di ricerca a una pagina intranet</span><span class="sxs-lookup"><span data-stu-id="82b1c-105">Add a search box to an intranet page</span></span>

<span data-ttu-id="82b1c-106">È necessario aggiungere due elementi alla pagina: per la casella di ricerca e lo script che si un contenitore.</span><span class="sxs-lookup"><span data-stu-id="82b1c-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="82b1c-107">In un sito SharePoint classico, aggiungere una Web Editor di Script Part e caduta lo script.</span><span class="sxs-lookup"><span data-stu-id="82b1c-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="82b1c-108">Selezionare la casella di ricerca per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="82b1c-108">Enable the search box for mobile</span></span>

<span data-ttu-id="82b1c-109">Per i siti intranet o pagine disponibili per gli utenti mobili, aggiungere isMobile: true per l'oggetto impostazioni:</span><span class="sxs-lookup"><span data-stu-id="82b1c-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="82b1c-110">Rendere attiva la casella di ricerca per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="82b1c-110">Put focus on the search box by default</span></span>

<span data-ttu-id="82b1c-111">Per consentire agli utenti di ricerca più veloce, quando i carichi di pagina o del sito posizionare il cursore nella casella di ricerca aggiungendo lo stato attivo: true per l'oggetto impostazioni:</span><span class="sxs-lookup"><span data-stu-id="82b1c-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="82b1c-112">Utilizzare un iFrame per incorporare una casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="82b1c-112">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="82b1c-113">Se incorporare uno script, non è un'opzione per il sito, utilizzare un iFrame per aggiungere la casella di ricerca:</span><span class="sxs-lookup"><span data-stu-id="82b1c-113">If embedding a script isn't an option for the site, use an iFrame to add the search box:</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
