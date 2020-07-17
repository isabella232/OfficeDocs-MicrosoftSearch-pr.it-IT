---
title: Aggiungere una casella di ricerca al sito Intranet
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
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
description: Ottenere suggerimenti di ricerca pertinenti e trovare i risultati di lavoro più velocemente aggiungendo una casella di ricerca Microsoft Search a un sito Intranet o una pagina.
ms.openlocfilehash: af12ce4d17c2695e196f8e4d79ccd515f002f238
ms.sourcegitcommit: 92206ea179ec00b22496f6fd2866b5406449cf40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44798226"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="de962-103">Aggiungere una casella di ricerca al sito Intranet</span><span class="sxs-lookup"><span data-stu-id="de962-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="de962-104">Per consentire agli utenti di accedere facilmente ai risultati dell'organizzazione, aggiungere una casella di ricerca di Microsoft Search in Bing a qualsiasi sito o pagina Intranet.</span><span class="sxs-lookup"><span data-stu-id="de962-104">To provide your users with easy access to results from your organization, add a Microsoft Search in Bing search box to any intranet site or page.</span></span> <span data-ttu-id="de962-105">Di seguito sono illustrati alcuni dei vantaggi:</span><span class="sxs-lookup"><span data-stu-id="de962-105">These are some of the benefits:</span></span>

- <span data-ttu-id="de962-106">Una casella di ricerca nel portale di SharePoint o Intranet fornisce un punto di ingresso noto e attendibile per iniziare la ricerca</span><span class="sxs-lookup"><span data-stu-id="de962-106">A search box on your SharePoint or intranet portal provides a familiar, trusted entry point to start searching</span></span>
- <span data-ttu-id="de962-107">Supporta tutti i principali browser Web, tra cui Google Chrome e Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="de962-107">Supports all major web browsers, including Google Chrome and Microsoft Edge</span></span>
- <span data-ttu-id="de962-108">Vengono visualizzati solo i suggerimenti di ricerca dell'organizzazione, i suggerimenti Web non vengono mai inclusi</span><span class="sxs-lookup"><span data-stu-id="de962-108">Only search suggestions from your organization appear, web suggestions are never included</span></span>
- <span data-ttu-id="de962-109">Porta gli utenti a una pagina di ricerca di Microsoft nella pagina dei risultati di Bing, che esclude gli annunci e i risultati Web</span><span class="sxs-lookup"><span data-stu-id="de962-109">Takes users to a Microsoft Search in Bing work results page, which excludes ads and web results</span></span>
- <span data-ttu-id="de962-110">È possibile controllare l'aspetto e il comportamento della casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="de962-110">You control the appearance and behavior of the search box</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="de962-111">Aggiungere una casella di ricerca a una pagina Intranet</span><span class="sxs-lookup"><span data-stu-id="de962-111">Add a search box to an intranet page</span></span>

<span data-ttu-id="de962-112">È necessario aggiungere due elementi alla pagina: un contenitore per la casella di ricerca e lo script che la fa funzionare.</span><span class="sxs-lookup"><span data-stu-id="de962-112">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="de962-113">In un sito di SharePoint classico, aggiungere una Web part Editor di script e inserire lo script al suo interno.</span><span class="sxs-lookup"><span data-stu-id="de962-113">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="de962-114">Abilitare la casella di ricerca per i dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="de962-114">Enable the search box for mobile</span></span>

<span data-ttu-id="de962-115">Per i siti Intranet o le pagine disponibili per gli utenti mobili, aggiungere isMobile:true all'oggetto impostazioni:</span><span class="sxs-lookup"><span data-stu-id="de962-115">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="de962-116">Configurare lo stato attivo sulla casella di ricerca per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="de962-116">Put focus on the search box by default</span></span>

<span data-ttu-id="de962-117">Per consentire agli utenti di eseguire ricerche più velocemente, durante il caricamento della pagina o del sito posizionare il cursore nella casella di ricerca aggiungendo focus:true all'oggetto impostazioni:</span><span class="sxs-lookup"><span data-stu-id="de962-117">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="de962-118">Personalizzare l'aspetto della casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="de962-118">Customize the appearance of the search box</span></span> 

<span data-ttu-id="de962-119">Sono disponibili numerose opzioni di configurazione per adattare meglio la casella di ricerca allo stile della Intranet.</span><span class="sxs-lookup"><span data-stu-id="de962-119">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="de962-120">Combinare le opzioni in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="de962-120">Mix and match options to suit your needs.</span></span>

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
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="de962-121">Usare un iFrame per incorporare una casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="de962-121">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="de962-122">Se non è possibile incorporare uno script nel sito, usare un iFrame per aggiungere la casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="de962-122">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="de962-123">Non sarà però possibile personalizzare l'aspetto della casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="de962-123">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
