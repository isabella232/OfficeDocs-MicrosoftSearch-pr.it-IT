---
title: Panoramica sui connettori
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Panoramica dei connettori di Microsoft Graph per Microsoft Search
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367524"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="f26d3-103">Panoramica dei connettori di Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="f26d3-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="f26d3-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indicizza tutti i dati di [Microsoft 365](https://www.microsoft.com/microsoft-365) per renderlo ricercabile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f26d3-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="f26d3-105">Con i connettori di Microsoft Graph, l'organizzazione può indicizzare i dati di terze parti in modo che vengano visualizzati nei risultati di ricerca di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f26d3-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="f26d3-106">Questo espande i tipi di origini di contenuto che possono essere ricercate nelle app per la produttività di Microsoft 365 e nel più vasto ecosistema di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f26d3-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="f26d3-107">I dati di terze parti possono essere ospitati in locale o in un cloud pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="f26d3-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="f26d3-108">Il resto di questo articolo è stato progettato per aiutare gli amministratori di Microsoft 365 a individuare le risorse disponibili per rispondere alle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="f26d3-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are avaiable to answer the following questions:</span></span>

* [<span data-ttu-id="f26d3-109">Quali origini dati possono essere connesse a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="f26d3-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="f26d3-110">Come si gestiscono le connessioni?</span><span class="sxs-lookup"><span data-stu-id="f26d3-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="f26d3-111">Quali sono i requisiti di licenza e i termini di utilizzo per i connettori grafico?</span><span class="sxs-lookup"><span data-stu-id="f26d3-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="f26d3-112">Come si personalizzano e configurano i risultati della ricerca?</span><span class="sxs-lookup"><span data-stu-id="f26d3-112">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="f26d3-113">Come eseguire la ricerca dei dati del connettore da un'applicazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="f26d3-113">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> <span data-ttu-id="f26d3-114">I connettori Microsoft Graph e le API di Microsoft Search sono ora generalmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="f26d3-114">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="f26d3-115">La prima graduali sarà rivolta ai clienti configurati per la versione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f26d3-115">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="f26d3-116">Se si desidera utilizzare un connettore grafico nel tenant, è necessario che gli utenti e gli amministratori optino per la [versione di destinazione](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="f26d3-116">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="f26d3-117">Quali origini dati possono essere connesse a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="f26d3-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="f26d3-118">Microsoft fornisce dieci connettori grafico e i nostri partner ecosistemici hanno creato oltre 100 connettori grafico aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="f26d3-118">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="f26d3-119">È inoltre possibile creare un connettore grafico personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f26d3-119">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="f26d3-120">Connettori del grafico da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f26d3-120">Graph connectors by Microsoft</span></span>

<span data-ttu-id="f26d3-121">È possibile connettersi alle origini dati seguenti utilizzando i connettori grafico creati da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="f26d3-121">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="f26d3-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="f26d3-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="f26d3-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="f26d3-123">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="f26d3-124">SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="f26d3-124">Azure SQL</span></span>
* [<span data-ttu-id="f26d3-125">Siti Web aziendali</span><span class="sxs-lookup"><span data-stu-id="f26d3-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="f26d3-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="f26d3-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="f26d3-127">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="f26d3-127">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="f26d3-128">Condivisione file</span><span class="sxs-lookup"><span data-stu-id="f26d3-128">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="f26d3-129">Oracle (anteprima)</span><span class="sxs-lookup"><span data-stu-id="f26d3-129">Oracle (preview)</span></span>
* [<span data-ttu-id="f26d3-130">Salesforce (anteprima)</span><span class="sxs-lookup"><span data-stu-id="f26d3-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="f26d3-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="f26d3-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="f26d3-132">La [raccolta dei connettori grafico](connectors-gallery.md) contiene una breve descrizione di ognuno di questi connettori grafico.</span><span class="sxs-lookup"><span data-stu-id="f26d3-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="f26d3-133">Se si è pronti per connettere una di queste origini dati al tenant, leggere la [Panoramica dell'installazione](configure-connector.md) e tutti gli altri articoli nella sezione Setup Connectors by Microsoft che si applicano all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="f26d3-133">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="f26d3-134">Connettori del grafico da parte dei partner</span><span class="sxs-lookup"><span data-stu-id="f26d3-134">Graph connectors by our partners</span></span>

<span data-ttu-id="f26d3-135">La [raccolta Microsoft Graph Connectors](connectors-gallery.md) include una breve descrizione di ognuno dei connettori grafico creati dai partner e un collegamento al sito Web di ogni partner.</span><span class="sxs-lookup"><span data-stu-id="f26d3-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="f26d3-136">Per ulteriori informazioni, contattare ogni partner direttamente.</span><span class="sxs-lookup"><span data-stu-id="f26d3-136">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="f26d3-137">Creare il proprio connettore grafico</span><span class="sxs-lookup"><span data-stu-id="f26d3-137">Build your own Graph connector</span></span>

<span data-ttu-id="f26d3-138">Se si prevede di creare un connettore grafico personalizzato, vedere la [Panoramica dell'API di Microsoft Search in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="f26d3-138">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="f26d3-139">Come si gestiscono le connessioni?</span><span class="sxs-lookup"><span data-stu-id="f26d3-139">How do I manage my connections?</span></span>

<span data-ttu-id="f26d3-140">È possibile gestire le connessioni dalla [scheda Connettori](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f26d3-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="f26d3-141">Per ulteriori informazioni, vedere [gestire le connessioni](manage-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="f26d3-141">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="f26d3-142">Quali sono i requisiti di licenza e i termini di utilizzo per i connettori grafico?</span><span class="sxs-lookup"><span data-stu-id="f26d3-142">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="f26d3-143">Per gli utenti dell'organizzazione è necessaria una licenza valida di Microsoft 365 o Office 365 e una quota sufficiente dei connettori del grafico per visualizzare i dati dei connettori nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="f26d3-143">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="f26d3-144">Per ulteriori informazioni, vedere [requisiti di licenza e prezzi](licensing.md) e [condizioni di utilizzo](terms-of-use.md).</span><span class="sxs-lookup"><span data-stu-id="f26d3-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="f26d3-145">Come si personalizzano e configurano i risultati della ricerca?</span><span class="sxs-lookup"><span data-stu-id="f26d3-145">How do I customize and configure search results?</span></span>

<span data-ttu-id="f26d3-146">Sono disponibili diversi modi per personalizzare e configurare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="f26d3-146">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="f26d3-147">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f26d3-147">See the following articles to learn more:</span></span>

* [<span data-ttu-id="f26d3-148">Gestire le tipologie di verticali e i tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="f26d3-148">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="f26d3-149">Gestire i layout dei risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="f26d3-149">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="f26d3-150">Gestire il cluster di risultati</span><span class="sxs-lookup"><span data-stu-id="f26d3-150">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="f26d3-151">Gestione di filtri personalizzati</span><span class="sxs-lookup"><span data-stu-id="f26d3-151">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="f26d3-152">Come eseguire la ricerca dei dati del connettore da un'applicazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="f26d3-152">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="f26d3-153">Dopo l'indicizzazione dei dati personalizzati, gli sviluppatori possono [eseguire query su tali dati](https://docs.microsoft.com/graph/search-concept-custom-types).</span><span class="sxs-lookup"><span data-stu-id="f26d3-153">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="f26d3-154">È possibile visualizzare i dati in qualsiasi applicazione.</span><span class="sxs-lookup"><span data-stu-id="f26d3-154">You can view your data in any application.</span></span> <span data-ttu-id="f26d3-155">Per ulteriori informazioni, vedere la [Panoramica dell'API di Microsoft Search in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="f26d3-155">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>
