---
title: Cluster di risultati dei connettori
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Dettagli dell'esperienza del cluster di risultati dei connettori
ms.openlocfilehash: ae5528f2e12c9e331b66e821f2a9c03947d788df
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031774"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="08b53-103">Cluster di risultati dei connettori grafici</span><span class="sxs-lookup"><span data-stu-id="08b53-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="08b53-104">Panoramica del cluster di risultati dei connettori graph (anteprima)</span><span class="sxs-lookup"><span data-stu-id="08b53-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="08b53-105">Con i cluster di risultati dei connettori Graph, le aziende possono cercare contenuto da origini dati di terze parti nella visualizzazione predefinita, la scheda **Tutti,** in SharePoint, Office.com e Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="08b53-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="08b53-106">I cluster di risultati consentono agli utenti di individuare tutto il contenuto di terze parti in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="08b53-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="08b53-107">I risultati visualizzati in un cluster di risultati sono raggruppati in base alla configurazione verticale di ricerca.</span><span class="sxs-lookup"><span data-stu-id="08b53-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="08b53-108">Modalità di selezione e visualizzazione dei risultati del connettore</span><span class="sxs-lookup"><span data-stu-id="08b53-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="08b53-109">I risultati dei connettori forniti nel cluster di risultati derivano da singoli verticali di ricerca con contenuto del connettore.</span><span class="sxs-lookup"><span data-stu-id="08b53-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="08b53-110">Ogni verticale di ricerca fornisce un set di risultati pertinenti che diventa un cluster di risultati candidato.</span><span class="sxs-lookup"><span data-stu-id="08b53-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="08b53-111">I risultati pertinenti vengono scelti in base alla proprietà "title" e alla proprietà "content" di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="08b53-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="08b53-112">La proprietà content è contrassegnata *come isContent=true* nello schema.</span><span class="sxs-lookup"><span data-stu-id="08b53-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="08b53-113">Per garantire l'individuazione del contenuto dai verticali di ricerca, ti consigliamo di fornire titoli significativi per gli elementi.</span><span class="sxs-lookup"><span data-stu-id="08b53-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="08b53-114">Ciò influisce positivamente sull'arbitraggio dei candidati del cluster di risultati e sulla probabilità che il contenuto sia visualizzato in un cluster di risultati.</span><span class="sxs-lookup"><span data-stu-id="08b53-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="08b53-115">Ad esempio, evita l'uso di ID come valori per la proprietà "title" a meno che gli utenti non utilizzino gli ID per cercare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="08b53-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="08b53-116">La frequenza di visualizzazione di un cluster di risultati varia in base a fattori quali il numero di verticali di ricerca da configurare e il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="08b53-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="08b53-117">Interagendo o ignorando un cluster di risultati, gli utenti forniranno implicitamente suggerimenti che ne modificano l'attivazione nel tempo.</span><span class="sxs-lookup"><span data-stu-id="08b53-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="08b53-118">L'esperienza dei risultati della ricerca per gli elementi dei connettori mostrati nel cluster di risultati [utilizza](./customize-search-page.md#create-your-own-result-type) i tipi di risultati definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="08b53-118">The search result experience for connector items shown in your result cluster uses [result types](./customize-search-page.md#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="08b53-119">Se non è configurato alcun tipo di risultato, viene [utilizzato un layout generato](./customize-search-page.md#default-search-result-layout) dal sistema.</span><span class="sxs-lookup"><span data-stu-id="08b53-119">If no result type is configured, a [system generated layout](./customize-search-page.md#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="08b53-120">È consigliabile utilizzare la proprietà "title" come titolo del risultato della ricerca e la proprietà "content" come descrizione della ricerca.</span><span class="sxs-lookup"><span data-stu-id="08b53-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="08b53-121">In questo modo gli utenti potranno ottenere la migliore esperienza attivando in modo accurato il cluster di risultati e i risultati più rilevanti nel cluster.</span><span class="sxs-lookup"><span data-stu-id="08b53-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="08b53-122">Abilitare i cluster di risultati</span><span class="sxs-lookup"><span data-stu-id="08b53-122">Enable result clusters</span></span>
  
<span data-ttu-id="08b53-123">L'esperienza del cluster di risultati è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="08b53-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="08b53-124">Seguire questa procedura per attivare l'esperienza a livello di organizzazione:</span><span class="sxs-lookup"><span data-stu-id="08b53-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="08b53-125">Nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com)passare a [**Verticali.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)</span><span class="sxs-lookup"><span data-stu-id="08b53-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="08b53-126">Selezionare il **verticale Tutti,** quindi abilitare **Mostra risultati connettore**.</span><span class="sxs-lookup"><span data-stu-id="08b53-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="08b53-127">Seguire questa procedura per attivare l'esperienza a livello di sito di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="08b53-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="08b53-128">Nel sito di SharePoint in cui si desidera ottenere l'esperienza del cluster di risultati, passare a **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="08b53-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="08b53-129">Vai a **Informazioni sito** Visualizza tutte le impostazioni > **del sito.**</span><span class="sxs-lookup"><span data-stu-id="08b53-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="08b53-130">Passare alla sezione Microsoft Search, quindi selezionare **Configura Microsoft Search per questa raccolta siti.**</span><span class="sxs-lookup"><span data-stu-id="08b53-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="08b53-131">Nel riquadro di spostamento passare a **Esperienza personalizzata,** quindi selezionare **Verticali.**</span><span class="sxs-lookup"><span data-stu-id="08b53-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="08b53-132">Selezionare il **verticale Tutti,** quindi abilitare **Mostra risultati connettore**.</span><span class="sxs-lookup"><span data-stu-id="08b53-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="08b53-133">Visualizzare l'esperienza del cluster di risultati dopo che è stato abilitato</span><span class="sxs-lookup"><span data-stu-id="08b53-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="08b53-134">Una volta attivata l'esperienza del cluster di risultati, possono essere necessario fino a 12 ore prima di poterla visualizzare.</span><span class="sxs-lookup"><span data-stu-id="08b53-134">After you turn on the result cluster experience, it can take up to 12 hours before you can view it.</span></span> <span data-ttu-id="08b53-135">Se si desidera che l'esperienza sia immediata, è possibile aggiungere *cacheClear=true* all'URL in SharePoint e Office.</span><span class="sxs-lookup"><span data-stu-id="08b53-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>