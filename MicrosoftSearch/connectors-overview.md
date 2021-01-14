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
ms.openlocfilehash: 677c91f121185faa6dc96f80c517917f429a3ab0
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847520"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="3db92-103">Panoramica dei connettori di Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="3db92-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="3db92-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indicizza tutti i dati di [Microsoft 365](https://www.microsoft.com/microsoft-365) per renderlo ricercabile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3db92-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="3db92-105">Con i connettori di Microsoft Graph, l'organizzazione può indicizzare i dati di terze parti in modo che vengano visualizzati nei risultati di ricerca di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3db92-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="3db92-106">Questo espande i tipi di origini di contenuto che possono essere ricercate nelle app per la produttività di Microsoft 365 e nel più vasto ecosistema di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3db92-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="3db92-107">I dati di terze parti possono essere ospitati in locale o in un cloud pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="3db92-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="3db92-108">Il resto di questo articolo è stato progettato per aiutare gli amministratori di Microsoft 365 a individuare le risorse disponibili per rispondere alle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="3db92-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="3db92-109">Quali origini dati possono essere connesse a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="3db92-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="3db92-110">Come si gestiscono le connessioni?</span><span class="sxs-lookup"><span data-stu-id="3db92-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="3db92-111">Quali sono i requisiti di licenza e i termini di utilizzo per i connettori grafico?</span><span class="sxs-lookup"><span data-stu-id="3db92-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="3db92-112">Come si personalizzano e configurano i risultati della ricerca?</span><span class="sxs-lookup"><span data-stu-id="3db92-112">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="3db92-113">Come eseguire la ricerca dei dati del connettore da un'applicazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="3db92-113">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> <span data-ttu-id="3db92-114">I connettori Microsoft Graph e le API di Microsoft Search sono ora generalmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="3db92-114">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="3db92-115">La prima graduali sarà rivolta ai clienti configurati per la versione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3db92-115">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="3db92-116">Se si desidera utilizzare un connettore grafico nel tenant, è necessario che gli utenti e gli amministratori optino per la [versione di destinazione](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="3db92-116">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="3db92-117">Quali origini dati possono essere connesse a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="3db92-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="3db92-118">Microsoft fornisce dieci connettori grafico e i nostri partner ecosistemici hanno creato oltre 100 connettori grafico aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="3db92-118">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="3db92-119">È inoltre possibile creare un connettore grafico personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3db92-119">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="3db92-120">Connettori di Graph Microsoft</span><span class="sxs-lookup"><span data-stu-id="3db92-120">Graph connectors by Microsoft</span></span>

<span data-ttu-id="3db92-121">È possibile connettersi alle origini dati seguenti utilizzando i connettori grafico creati da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="3db92-121">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="3db92-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="3db92-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="3db92-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="3db92-123">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="3db92-124">SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="3db92-124">Azure SQL</span></span>
* [<span data-ttu-id="3db92-125">Siti Web aziendali</span><span class="sxs-lookup"><span data-stu-id="3db92-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="3db92-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="3db92-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="3db92-127">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="3db92-127">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="3db92-128">Condivisione file</span><span class="sxs-lookup"><span data-stu-id="3db92-128">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="3db92-129">Oracle (anteprima)</span><span class="sxs-lookup"><span data-stu-id="3db92-129">Oracle (preview)</span></span>
* [<span data-ttu-id="3db92-130">Salesforce (anteprima)</span><span class="sxs-lookup"><span data-stu-id="3db92-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="3db92-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="3db92-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="3db92-132">La [raccolta dei connettori grafico](connectors-gallery.md) contiene una breve descrizione di ognuno di questi connettori grafico.</span><span class="sxs-lookup"><span data-stu-id="3db92-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="3db92-133">Se si è pronti per connettere una di queste origini dati al tenant, leggere la [Panoramica dell'installazione](configure-connector.md) e tutti gli altri articoli nella sezione Setup Connectors by Microsoft che si applicano all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3db92-133">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="3db92-134">Connettori del grafico da parte dei partner</span><span class="sxs-lookup"><span data-stu-id="3db92-134">Graph connectors by our partners</span></span>

<span data-ttu-id="3db92-135">La [raccolta Microsoft Graph Connectors](connectors-gallery.md) include una breve descrizione di ognuno dei connettori grafico creati dai partner e un collegamento al sito Web di ogni partner.</span><span class="sxs-lookup"><span data-stu-id="3db92-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="3db92-136">Per ulteriori informazioni, contattare ogni partner direttamente.</span><span class="sxs-lookup"><span data-stu-id="3db92-136">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="3db92-137">Creare il proprio connettore grafico</span><span class="sxs-lookup"><span data-stu-id="3db92-137">Build your own Graph connector</span></span>

<span data-ttu-id="3db92-138">Se si prevede di creare un connettore grafico personalizzato, vedere la [Panoramica dell'API di Microsoft Search in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="3db92-138">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="3db92-139">Come si gestiscono le connessioni?</span><span class="sxs-lookup"><span data-stu-id="3db92-139">How do I manage my connections?</span></span>

<span data-ttu-id="3db92-140">È possibile gestire le connessioni dalla [scheda Connettori](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="3db92-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="3db92-141">Per ulteriori informazioni, vedere [gestire le connessioni](manage-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="3db92-141">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="3db92-142">Quali sono i requisiti di licenza e i termini di utilizzo per i connettori grafico?</span><span class="sxs-lookup"><span data-stu-id="3db92-142">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="3db92-143">Per gli utenti dell'organizzazione è necessaria una licenza valida di Microsoft 365 o Office 365 e una quota sufficiente dei connettori del grafico per visualizzare i dati dei connettori nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="3db92-143">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="3db92-144">Per ulteriori informazioni, vedere [requisiti di licenza e prezzi](licensing.md) e [condizioni di utilizzo](terms-of-use.md).</span><span class="sxs-lookup"><span data-stu-id="3db92-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="3db92-145">Come si personalizzano e configurano i risultati della ricerca?</span><span class="sxs-lookup"><span data-stu-id="3db92-145">How do I customize and configure search results?</span></span>

<span data-ttu-id="3db92-146">Sono disponibili diversi modi per personalizzare e configurare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="3db92-146">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="3db92-147">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="3db92-147">See the following articles to learn more:</span></span>

* [<span data-ttu-id="3db92-148">Gestire le tipologie di verticali e i tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="3db92-148">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="3db92-149">Gestire i layout dei risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="3db92-149">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="3db92-150">Gestisci cluster dei risultati</span><span class="sxs-lookup"><span data-stu-id="3db92-150">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="3db92-151">Gestire filtri personalizzati</span><span class="sxs-lookup"><span data-stu-id="3db92-151">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="3db92-152">Come eseguire la ricerca dei dati del connettore da un'applicazione personalizzata</span><span class="sxs-lookup"><span data-stu-id="3db92-152">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="3db92-153">Dopo l'indicizzazione dei dati personalizzati, gli sviluppatori possono [eseguire query su tali dati](https://docs.microsoft.com/graph/search-concept-custom-types).</span><span class="sxs-lookup"><span data-stu-id="3db92-153">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="3db92-154">È possibile visualizzare i dati in qualsiasi applicazione.</span><span class="sxs-lookup"><span data-stu-id="3db92-154">You can view your data in any application.</span></span> <span data-ttu-id="3db92-155">Per ulteriori informazioni, vedere la [Panoramica dell'API di Microsoft Search in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="3db92-155">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="limitations"></a><span data-ttu-id="3db92-156">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="3db92-156">Limitations</span></span>

* <span data-ttu-id="3db92-157">Quando si **pubblica** un connettore basato su Microsoft, potrebbero essere necessari alcuni minuti per la creazione della connessione.</span><span class="sxs-lookup"><span data-stu-id="3db92-157">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="3db92-158">Durante tale periodo, la connessione mostrerà lo stato in sospeso.</span><span class="sxs-lookup"><span data-stu-id="3db92-158">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="3db92-159">L'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) non supporta la modifica dello **schema di ricerca** dopo la pubblicazione di una connessione.</span><span class="sxs-lookup"><span data-stu-id="3db92-159">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="3db92-160">Per modificare lo schema di ricerca, eliminare la connessione e crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="3db92-160">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="3db92-161">La velocità effettiva di ingestione viene limitata a circa quattro elementi al secondo.</span><span class="sxs-lookup"><span data-stu-id="3db92-161">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="3db92-162">Non è disponibile alcun supporto per gli aggiornamenti dello schema.</span><span class="sxs-lookup"><span data-stu-id="3db92-162">There is no support for schema updates.</span></span> <span data-ttu-id="3db92-163">Dopo aver creato una configurazione di connessione, non è possibile aggiornare lo schema.</span><span class="sxs-lookup"><span data-stu-id="3db92-163">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="3db92-164">È possibile eliminare e ricreare la connessione solo.</span><span class="sxs-lookup"><span data-stu-id="3db92-164">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="3db92-165">Esiste un limite per le connessioni.</span><span class="sxs-lookup"><span data-stu-id="3db92-165">There is a connections limit.</span></span> <span data-ttu-id="3db92-166">Ogni tenant è in grado di creare fino a 10 connessioni.</span><span class="sxs-lookup"><span data-stu-id="3db92-166">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="3db92-167">La modifica del supporto per la connessione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="3db92-167">Edit support for connection is not available.</span></span> <span data-ttu-id="3db92-168">Dopo aver creato la connessione, non è possibile modificarla o modificarla.</span><span class="sxs-lookup"><span data-stu-id="3db92-168">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="3db92-169">Se è necessario modificare i dettagli, è necessario eliminare e ricreare la connessione.</span><span class="sxs-lookup"><span data-stu-id="3db92-169">If you need to change any details, you must delete and recreate the connection.</span></span>
