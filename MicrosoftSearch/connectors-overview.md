---
title: Panoramica dei connettori di Microsoft Graph
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Panoramica dei connettori di Microsoft Graph per Microsoft Search
ms.openlocfilehash: 2d49471c703b765f6e99324f39dbe730f6dea814
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031657"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="fe581-103">Panoramica dei connettori di Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="fe581-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="fe581-104">[Microsoft Search](./overview-microsoft-search.md) indicizza tutti i dati [di Microsoft 365](https://www.microsoft.com/microsoft-365) per renderli ricercabili per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="fe581-104">[Microsoft Search](./overview-microsoft-search.md) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="fe581-105">Con i connettori di Microsoft Graph, l'organizzazione può indicizzare i dati di terze parti in modo che appaino nei risultati di Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="fe581-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="fe581-106">Questa funzionalità espande i tipi di origini contenuto disponibili per la ricerca nelle app di produttività di Microsoft 365 e nell'ecosistema Microsoft più ampio.</span><span class="sxs-lookup"><span data-stu-id="fe581-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="fe581-107">I dati di terze parti possono essere ospitati in locale o nel cloud pubblico o privato.</span><span class="sxs-lookup"><span data-stu-id="fe581-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="fe581-108">Questo articolo ha lo scopo di aiutare gli amministratori di Microsoft 365 a individuare le risorse disponibili per rispondere alle domande seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe581-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="fe581-109">Quali origini dati possono essere connesse a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="fe581-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="fe581-110">Come si gestiscono le connessioni?</span><span class="sxs-lookup"><span data-stu-id="fe581-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="fe581-111">Quali sono i requisiti di licenza e le condizioni di utilizzo per i connettori Graph?</span><span class="sxs-lookup"><span data-stu-id="fe581-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="fe581-112">Quali sono le funzionalità di anteprima?</span><span class="sxs-lookup"><span data-stu-id="fe581-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="fe581-113">Come si personalizzano e si configurano i risultati della ricerca?</span><span class="sxs-lookup"><span data-stu-id="fe581-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="fe581-114">Come è possibile cercare i dati del connettore da un'applicazione personalizzata?</span><span class="sxs-lookup"><span data-stu-id="fe581-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)
* [<span data-ttu-id="fe581-115">Come si personalizzano i risultati della ricerca?</span><span class="sxs-lookup"><span data-stu-id="fe581-115">How do I customize search results?</span></span>](#how-do-i-customize-search-results)
* [<span data-ttu-id="fe581-116">Quali sono le limitazioni del connettore</span><span class="sxs-lookup"><span data-stu-id="fe581-116">What are the connector limitations</span></span>](#what-are-the-connector-limitations)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="fe581-117">I connettori di Microsoft Graph e le API di Microsoft Search sono ora disponibili in genere.</span><span class="sxs-lookup"><span data-stu-id="fe581-117">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="fe581-118">Le prime implementazioni saranno destinate ai clienti configurati per il rilascio mirato.</span><span class="sxs-lookup"><span data-stu-id="fe581-118">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="fe581-119">Se si desidera utilizzare un connettore Graph nel tenant, gli utenti e gli amministratori devono acconsentire esplicitamente [a Rilascio mirato.](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="fe581-119">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide).</span></span>

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](./overview-microsoft-search.md) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="fe581-120">Quali origini dati possono essere connesse a Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="fe581-120">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="fe581-121">Microsoft fornisce 9 connettori Graph e i partner dell'ecosistema hanno creato più di 100 connettori Graph.</span><span class="sxs-lookup"><span data-stu-id="fe581-121">Microsoft provides 9 Graph connectors and our ecosystem partners have created over 100 more Graph connectors.</span></span> <span data-ttu-id="fe581-122">È inoltre possibile creare un connettore Graph personalizzato.</span><span class="sxs-lookup"><span data-stu-id="fe581-122">You can also build your own Graph connector.</span></span>

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="fe581-123">Connettori di Graph Microsoft</span><span class="sxs-lookup"><span data-stu-id="fe581-123">Graph connectors by Microsoft</span></span>

<span data-ttu-id="fe581-124">È possibile connettersi alle origini dati seguenti utilizzando i connettori Graph creati da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="fe581-124">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="fe581-125">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="fe581-125">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="fe581-126">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="fe581-126">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="fe581-127">SQL di Azure e Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="fe581-127">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="fe581-128">Siti Web aziendali</span><span class="sxs-lookup"><span data-stu-id="fe581-128">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="fe581-129">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="fe581-129">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="fe581-130">Condivisione file</span><span class="sxs-lookup"><span data-stu-id="fe581-130">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="fe581-131">SQL Oracle (anteprima)</span><span class="sxs-lookup"><span data-stu-id="fe581-131">Oracle SQL (preview)</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="fe581-132">Salesforce (anteprima)</span><span class="sxs-lookup"><span data-stu-id="fe581-132">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="fe581-133">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="fe581-133">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="fe581-134">La [raccolta di connettori Graph](connectors-gallery.md) contiene una breve descrizione di ognuno di questi connettori Graph.</span><span class="sxs-lookup"><span data-stu-id="fe581-134">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="fe581-135">Se si è pronti per connettere una di queste origini dati [](configure-connector.md) al tenant, leggere la panoramica dell'installazione e gli altri articoli nella sezione Installazione dei connettori da parte di Microsoft che si applicano all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="fe581-135">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="fe581-136">Connettori grafici dei partner</span><span class="sxs-lookup"><span data-stu-id="fe581-136">Graph connectors by our partners</span></span>

<span data-ttu-id="fe581-137">La [raccolta di connettori di Microsoft Graph](connectors-gallery.md) include una breve descrizione di ognuno dei connettori Graph creati dai partner e un collegamento al sito Web di ogni partner.</span><span class="sxs-lookup"><span data-stu-id="fe581-137">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief description of each of the Graph connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="fe581-138">Per ulteriori informazioni, contattare direttamente ogni partner.</span><span class="sxs-lookup"><span data-stu-id="fe581-138">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="fe581-139">Creare un connettore Graph personalizzato</span><span class="sxs-lookup"><span data-stu-id="fe581-139">Build your own Graph connector</span></span>

<span data-ttu-id="fe581-140">Se si preferisce, è possibile creare un connettore Graph personalizzato.</span><span class="sxs-lookup"><span data-stu-id="fe581-140">You can build your own Graph connector if you prefer.</span></span> <span data-ttu-id="fe581-141">Per ulteriori informazioni sulla creazione di connettori Graph, vedere [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="fe581-141">For more information on building Graph connectors, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="fe581-142">Come si gestiscono le connessioni?</span><span class="sxs-lookup"><span data-stu-id="fe581-142">How do I manage my connections?</span></span>

<span data-ttu-id="fe581-143">È possibile gestire le connessioni dalla [scheda Connettori](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) nell'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="fe581-143">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="fe581-144">Per ulteriori informazioni sulla gestione delle connessioni, vedere: [Gestire le connessioni](manage-connector.md).</span><span class="sxs-lookup"><span data-stu-id="fe581-144">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="fe581-145">Quali sono i requisiti di licenza e le condizioni di utilizzo per i connettori Graph?</span><span class="sxs-lookup"><span data-stu-id="fe581-145">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="fe581-146">È necessaria una licenza valida di Microsoft 365 o Office 365 e una quota di connettori Graph sufficiente per consentire agli utenti dell'organizzazione di visualizzare i dati dei connettori nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="fe581-146">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="fe581-147">Per altre informazioni, vedi [Requisiti di licenza e prezzi](licensing.md) e Condizioni per [l'uso.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="fe581-147">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="fe581-148">Quali sono le funzionalità di anteprima?</span><span class="sxs-lookup"><span data-stu-id="fe581-148">What are the preview features?</span></span>

<span data-ttu-id="fe581-149">Anche se i connettori di Microsoft Graph e le API di Microsoft Search sono ora disponibili in genere, sono disponibili diverse funzionalità in anteprima.</span><span class="sxs-lookup"><span data-stu-id="fe581-149">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="fe581-150">L'insieme di connettori e funzionalità in anteprima include:</span><span class="sxs-lookup"><span data-stu-id="fe581-150">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="fe581-151">Connettore DevOps di Azure</span><span class="sxs-lookup"><span data-stu-id="fe581-151">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="fe581-152">Connettore Salesforce</span><span class="sxs-lookup"><span data-stu-id="fe581-152">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="fe581-153">[Connettore ServiceNow con](servicenow-connector.md) autorizzazioni di ricerca che utilizzano ACL di origine</span><span class="sxs-lookup"><span data-stu-id="fe581-153">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="fe581-154">Gestisci cluster dei risultati</span><span class="sxs-lookup"><span data-stu-id="fe581-154">Manage result cluster</span></span>](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="fe581-155">Come si personalizzano e si configurano i risultati della ricerca?</span><span class="sxs-lookup"><span data-stu-id="fe581-155">How do I customize and configure search results?</span></span>

<span data-ttu-id="fe581-156">Esistono molti modi per personalizzare e configurare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="fe581-156">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="fe581-157">Per ulteriori informazioni, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe581-157">See the following articles to learn more:</span></span>

* [<span data-ttu-id="fe581-158">Gestire le tipologie di verticali e i tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="fe581-158">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="fe581-159">Gestire i layout dei risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="fe581-159">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="fe581-160">Gestisci cluster dei risultati</span><span class="sxs-lookup"><span data-stu-id="fe581-160">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="fe581-161">Gestire filtri personalizzati</span><span class="sxs-lookup"><span data-stu-id="fe581-161">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="fe581-162">Come è possibile cercare i dati del connettore da un'applicazione personalizzata?</span><span class="sxs-lookup"><span data-stu-id="fe581-162">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="fe581-163">Dopo l'indicizzazione dei dati personalizzati, gli sviluppatori possono [eseguire query su tali dati.](/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="fe581-163">After custom data is indexed, developers can [query this data](/graph/search-concept-custom-types).</span></span> <span data-ttu-id="fe581-164">È possibile visualizzare i dati in qualsiasi applicazione.</span><span class="sxs-lookup"><span data-stu-id="fe581-164">You can view your data in any application.</span></span> <span data-ttu-id="fe581-165">Per ulteriori informazioni, vedere [Panoramica dell'API di Microsoft Search in Microsoft Graph.](/graph/search-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="fe581-165">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-customize-search-results"></a><span data-ttu-id="fe581-166">Come si personalizzano i risultati della ricerca?</span><span class="sxs-lookup"><span data-stu-id="fe581-166">How do I customize search results?</span></span>

<span data-ttu-id="fe581-167">Il passaggio successivo consiste nel personalizzare i risultati della ricerca come consigliato in questo articolo [Come personalizzare e configurare i risultati della ricerca?](#how-do-i-customize-and-configure-search-results).</span><span class="sxs-lookup"><span data-stu-id="fe581-167">The next step is to customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="fe581-168">Per ulteriori informazioni sulla personalizzazione dei risultati della ricerca, vedere [Customize the search results page](./configure-connector.md#next-steps-customize-the-search-results-page).</span><span class="sxs-lookup"><span data-stu-id="fe581-168">To learn more about customizing search results, see [Customize the search results page](./configure-connector.md#next-steps-customize-the-search-results-page).</span></span>

## <a name="what-are-the-connector-limitations"></a><span data-ttu-id="fe581-169">Quali sono le limitazioni del connettore?</span><span class="sxs-lookup"><span data-stu-id="fe581-169">What are the connector limitations?</span></span>

* <span data-ttu-id="fe581-170">Quando si **pubblica** un connettore creato da Microsoft, la creazione della connessione potrebbe richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="fe581-170">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="fe581-171">Durante questo periodo, lo stato della connessione verrà visualizzato come in sospeso.</span><span class="sxs-lookup"><span data-stu-id="fe581-171">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="fe581-172">L'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) non supporta la modifica dello schema di **ricerca** dopo la pubblicazione di una connessione.</span><span class="sxs-lookup"><span data-stu-id="fe581-172">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="fe581-173">Per modificare lo schema di ricerca, eliminare la connessione e crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="fe581-173">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="fe581-174">La velocità effettiva di inserimento è limitato a circa quattro elementi al secondo.</span><span class="sxs-lookup"><span data-stu-id="fe581-174">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="fe581-175">Non è disponibile alcun supporto per gli aggiornamenti dello schema.</span><span class="sxs-lookup"><span data-stu-id="fe581-175">There is no support for schema updates.</span></span> <span data-ttu-id="fe581-176">Dopo aver creato una configurazione di connessione, non è possibile aggiornare lo schema.</span><span class="sxs-lookup"><span data-stu-id="fe581-176">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="fe581-177">È possibile solo eliminare e creare di nuovo la connessione.</span><span class="sxs-lookup"><span data-stu-id="fe581-177">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="fe581-178">Esiste un limite di connessione.</span><span class="sxs-lookup"><span data-stu-id="fe581-178">There is a connection limit.</span></span> <span data-ttu-id="fe581-179">Ogni tenant può creare fino a 10 connessioni.</span><span class="sxs-lookup"><span data-stu-id="fe581-179">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="fe581-180">Il supporto della modifica per la connessione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="fe581-180">Edit support for connection is not available.</span></span> <span data-ttu-id="fe581-181">Dopo aver creato la connessione, non è possibile modificarla.</span><span class="sxs-lookup"><span data-stu-id="fe581-181">Once the connection has been created, you can't edit or change it.</span></span> <span data-ttu-id="fe581-182">Se è necessario modificare i dettagli, è necessario eliminare e ricreare la connessione.</span><span class="sxs-lookup"><span data-stu-id="fe581-182">If you need to change any details, you must delete and recreate the connection.</span></span>