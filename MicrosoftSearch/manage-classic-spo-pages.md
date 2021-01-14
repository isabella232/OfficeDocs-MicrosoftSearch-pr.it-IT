---
title: Pagine classiche in SharePoint Online e Microsoft Search
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Utilizzo di Microsoft Search nelle pagine di SharePoint classiche
ms.openlocfilehash: 9a5aeb2e683297faccfb55d3407653c1791b3961
ms.sourcegitcommit: 7133d46ca9c3a5216ee9159db781febd17e5a831
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "49863175"
---
# <a name="classic-pages-and-microsoft-search"></a><span data-ttu-id="3efe8-103">Pagine classiche e Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="3efe8-103">Classic pages and Microsoft Search</span></span>

<span data-ttu-id="3efe8-104">I siti di SharePoint creati prima dei siti moderni utilizzano una casella di ricerca classica e un'esperienza di risultati della ricerca classica.</span><span class="sxs-lookup"><span data-stu-id="3efe8-104">SharePoint sites created prior to modern sites use a classic search box and classic search results experience.</span></span> <span data-ttu-id="3efe8-105">Verrà implementata una funzionalità che utilizzerà le pagine classiche predefinite per iniziare a utilizzare l'esperienza di ricerca moderna che utilizza Microsoft Search, che fornisce risultati personalizzati con maggiore rilevanza.</span><span class="sxs-lookup"><span data-stu-id="3efe8-105">We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.</span></span>

<span data-ttu-id="3efe8-106">L'utilizzo di Microsoft Search è consigliato per tutti i siti, tra cui quello classico, ma se i siti classici utilizzano pagine master personalizzate e/o se sono state personalizzate le classiche esperienze dei risultati di ricerca, verranno rilevate automaticamente queste personalizzazioni e non si passerà a Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="3efe8-106">Using Microsoft Search is recommended for all sites, including classic, but if your classic sites use custom master pages and/or you have customized your classic search results experience, we will auto-detect these customizations and not switch to Microsoft Search.</span></span>

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a><span data-ttu-id="3efe8-107">Siti classici che passano automaticamente a Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="3efe8-107">Classic sites that will automatically switch to Microsoft Search</span></span>

<span data-ttu-id="3efe8-108">I siti classici inizieranno a utilizzare Microsoft Search se sono soddisfatte tutte le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="3efe8-108">Classic sites will start using Microsoft Search if all of the following are true:</span></span>

* <span data-ttu-id="3efe8-109">Il sito è basato sul modello di sito del team (come STS # 0 e STS # 1).</span><span class="sxs-lookup"><span data-stu-id="3efe8-109">The site is based on the team site template (like STS#0 and STS#1).</span></span>
* <span data-ttu-id="3efe8-110">Al sito non è attivata la caratteristica di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="3efe8-110">The site does not have the publishing feature turned on.</span></span>
* <span data-ttu-id="3efe8-111">Il sito non utilizza una pagina master personalizzata (una pagina master diversa da Oslo. master o Seattle. master).</span><span class="sxs-lookup"><span data-stu-id="3efe8-111">The site does not use a custom master page (a different master page than oslo.master or seattle.master).</span></span>
* <span data-ttu-id="3efe8-112">Non vi sono regole di query attive diverse da quelle che aggiungono risultati alzati di valore per il sito, la raccolta siti o il tenant nell'origine dei risultati predefinita.</span><span class="sxs-lookup"><span data-stu-id="3efe8-112">There are no active query rules other than those adding promoted results for the site, site collection or tenant on the default result source.</span></span>
* <span data-ttu-id="3efe8-113">Non sono disponibili tipi di risultati personalizzati per il sito o la raccolta siti nell'origine dei risultati predefinita.</span><span class="sxs-lookup"><span data-stu-id="3efe8-113">There are no custom result types for the site or the site collection on the default result source.</span></span>
* <span data-ttu-id="3efe8-114">Il sito o la raccolta siti non viene disattivata tramite l'impostazione *SearchBoxInNavBar* descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="3efe8-114">The site or the site collection is not opted out of the switch using the *SearchBoxInNavBar* setting described below.</span></span>

<span data-ttu-id="3efe8-115">Dopo il passaggio a Microsoft Search, le pagine classiche del sito inizieranno a visualizzare la casella di ricerca nella barra di spostamento della famiglia e rimuovere la casella di ricerca classica dalla pagina.</span><span class="sxs-lookup"><span data-stu-id="3efe8-115">After the switch to Microsoft Search, classic pages in the site will start to show the search box in the suite navigation bar and remove the classic search box from the page.</span></span> <span data-ttu-id="3efe8-116">Successivamente, quando un utente cerca un termine, i risultati verranno visualizzati utilizzando l'esperienza di ricerca moderna di Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="3efe8-116">Then, when a user searches for a term, the results will be displayed using the modern search experience of Microsoft Search.</span></span>

## <a name="staying-with-the-classic-search-experience"></a><span data-ttu-id="3efe8-117">Rimanere con l'esperienza di ricerca classica</span><span class="sxs-lookup"><span data-stu-id="3efe8-117">Staying with the classic search experience</span></span>

<span data-ttu-id="3efe8-118">Se il sito soddisfa i criteri elencati in questo argomento, ma non si desidera che passi all'esperienza di ricerca di Microsoft, è possibile escludere l'utilizzo dei comandi seguenti, come proprietario del sito o della raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="3efe8-118">If your site meets the criteria listed above, but you do not want it to switch to the Microsoft Search experience, you can opt out using the following commands, as the site or site collection owner.</span></span>

<span data-ttu-id="3efe8-119">È possibile utilizzare questo comando in qualsiasi momento, prima o dopo l'operazione, per cui è facile tornare all'esperienza di ricerca precedentemente eseguita.</span><span class="sxs-lookup"><span data-stu-id="3efe8-119">You can use this command at any time, before or after the switch happens, so it is easy to go back to the search experience you had previously.</span></span>

<span data-ttu-id="3efe8-120">Per eseguire i comandi riportati di seguito, si utilizzerà PowerShell con le estensioni di PowerShell di SharePoint PnP.</span><span class="sxs-lookup"><span data-stu-id="3efe8-120">To run the commands below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="3efe8-121">È possibile installare e scoprire altre informazioni su come [iniziare.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="3efe8-121">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="3efe8-122">Si eseguirà l'accesso al sito o alla raccolta siti utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3efe8-122">You will sign in to your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

<span data-ttu-id="3efe8-123">Per rimanere con l'esperienza di ricerca classica per un sito, eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="3efe8-123">To stay with classic search experience for a site, run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

<span data-ttu-id="3efe8-124">In alternativa, se si desidera impostarlo per tutti i siti di una raccolta siti, è possibile utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="3efe8-124">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a><span data-ttu-id="3efe8-125">Scelta di Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="3efe8-125">Opting into Microsoft Search</span></span>

<span data-ttu-id="3efe8-126">Per i siti che non soddisfano i criteri sopra elencati o per siti specifici di una raccolta siti che hanno scelto di rimanere in modalità classica, è possibile abilitare manualmente l'esperienza di ricerca di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3efe8-126">For those sites that do not meet the criteria listed above, or for specific sites in a site collection that opted to stay in classic, you can manually enable the Microsoft Search experience.</span></span>

<span data-ttu-id="3efe8-127">Per modificare questa impostazione per un sito specifico, è possibile utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="3efe8-127">To change this setting for a specific site, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

<span data-ttu-id="3efe8-128">Se si desidera impostarla per tutti i siti di una raccolta siti, è possibile utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="3efe8-128">If you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> <span data-ttu-id="3efe8-129">È possibile abilitare manualmente la ricerca di Microsoft solo per un sito del team o un sito di pubblicazione (ID modello che contengono "STS", "CMSPUBLISHING", "BLANKINTERNET" e "GROUP").</span><span class="sxs-lookup"><span data-stu-id="3efe8-129">You can manually enable Microsoft Search only for a Team Site or Publishing Site (template ids that contain "STS", "CMSPUBLISHING", "BLANKINTERNET" and "GROUP").</span></span>
