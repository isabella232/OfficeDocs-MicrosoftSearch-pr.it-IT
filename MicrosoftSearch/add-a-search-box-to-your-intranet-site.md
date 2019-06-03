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
ROBOTS: NoIndex
description: Ottenere suggerimenti di ricerca pertinenti e trovare i risultati di lavoro più velocemente aggiungendo una casella di ricerca Microsoft Search a un sito Intranet o una pagina.
ms.openlocfilehash: 867282393c7a4bffa63363a3455e4f1543c7f8a1
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "34590694"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="ea2e1-103">Aggiungere una casella di ricerca al sito intranet</span><span class="sxs-lookup"><span data-stu-id="ea2e1-103">Add a search box to your intranet site</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea2e1-104">Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="ea2e1-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="ea2e1-105">Stiamo trasferendo il portale nell’interfaccia di amministrazione di Microsoft 365, e lo stesso sarà poi rimosso.</span><span class="sxs-lookup"><span data-stu-id="ea2e1-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="ea2e1-106">Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea2e1-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="ea2e1-107">[Panoramica di Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="ea2e1-107">Overview of Microsoft Search</span></span>

<span data-ttu-id="ea2e1-108">Aggiungere una casella di ricerca Microsoft Search a qualsiasi pagina o sito Intranet per accedere rapidamente a suggerimenti di ricerca e risultati di lavoro pertinenti.</span><span class="sxs-lookup"><span data-stu-id="ea2e1-108">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="ea2e1-109">Aggiungere una casella di ricerca a una pagina Intranet</span><span class="sxs-lookup"><span data-stu-id="ea2e1-109">Add a search box to an intranet page</span></span>

<span data-ttu-id="ea2e1-110">È necessario aggiungere due elementi alla pagina: un contenitore per la casella di ricerca e lo script che la fa funzionare.</span><span class="sxs-lookup"><span data-stu-id="ea2e1-110">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="ea2e1-111">In un sito di SharePoint classico, aggiungere una Web part Editor di script e inserire lo script al suo interno.</span><span class="sxs-lookup"><span data-stu-id="ea2e1-111">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="ea2e1-112">Abilitare la casella di ricerca per i dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="ea2e1-112">Enable the search box for mobile</span></span>

<span data-ttu-id="ea2e1-113">Per i siti Intranet o le pagine disponibili per gli utenti mobili, aggiungere isMobile:true all'oggetto impostazioni:</span><span class="sxs-lookup"><span data-stu-id="ea2e1-113">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="ea2e1-114">Configurare lo stato attivo sulla casella di ricerca per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="ea2e1-114">Put focus on the search box by default</span></span>

<span data-ttu-id="ea2e1-115">Per consentire agli utenti di eseguire ricerche più velocemente, durante il caricamento della pagina o del sito posizionare il cursore nella casella di ricerca aggiungendo focus:true all'oggetto impostazioni:</span><span class="sxs-lookup"><span data-stu-id="ea2e1-115">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="ea2e1-116">Personalizzare l'aspetto della casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="ea2e1-116">Customize the appearance of the search box</span></span> 

<span data-ttu-id="ea2e1-117">Sono disponibili numerose opzioni di configurazione per adattare meglio la casella di ricerca allo stile della Intranet.</span><span class="sxs-lookup"><span data-stu-id="ea2e1-117">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="ea2e1-118">Combinare le opzioni in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ea2e1-118">Mix and match options to suit your needs.</span></span>

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

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="ea2e1-119">Usare un iFrame per incorporare una casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="ea2e1-119">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="ea2e1-120">Se non è possibile incorporare uno script nel sito, usare un iFrame per aggiungere la casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ea2e1-120">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="ea2e1-121">Non sarà però possibile personalizzare l'aspetto della casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ea2e1-121">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```