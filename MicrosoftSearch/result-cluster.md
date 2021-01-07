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
description: Informazioni dettagliate sull'esperienza del cluster di risultati dei connettori
ms.openlocfilehash: f2355213a0b1821968c801153841c274e539d72e
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773028"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="b5a96-103">Cluster di risultati dei connettori del grafico</span><span class="sxs-lookup"><span data-stu-id="b5a96-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="b5a96-104">Panoramica del cluster di risultati dei connettori del grafico (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b5a96-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="b5a96-105">Con i cluster di risultati dei connettori grafico, le aziende possono cercare contenuto da origini dati di terze parti nella visualizzazione predefinita, la scheda **tutti** , in SharePoint, Office.com e Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="b5a96-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="b5a96-106">I cluster di risultati aiutano gli utenti a individuare tutti i contenuti di terze parti in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="b5a96-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="b5a96-107">I risultati mostrati in un cluster di risultati vengono raggruppati in base alla configurazione verticale della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b5a96-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="b5a96-108">Modalità di selezione e visualizzazione dei risultati del connettore</span><span class="sxs-lookup"><span data-stu-id="b5a96-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="b5a96-109">I risultati del connettore forniti nel cluster di risultati sono derivati da singoli verticali di ricerca con contenuto del connettore.</span><span class="sxs-lookup"><span data-stu-id="b5a96-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="b5a96-110">Ogni verticale di ricerca fornisce una serie di risultati rilevanti che diventeranno un cluster di risultati candidato.</span><span class="sxs-lookup"><span data-stu-id="b5a96-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="b5a96-111">I risultati rilevanti vengono scelti in base alla proprietà "title" e alla proprietà "Content" di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="b5a96-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="b5a96-112">La proprietà Content è contrassegnata come *incontent = true* nello schema.</span><span class="sxs-lookup"><span data-stu-id="b5a96-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="b5a96-113">Per garantire l'individuazione del contenuto dai verticali di ricerca, è consigliabile fornire titoli significativi per gli elementi.</span><span class="sxs-lookup"><span data-stu-id="b5a96-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="b5a96-114">Questo incide positivamente sull'arbitrato dei candidati del cluster di risultati e sulla probabilità che il contenuto venga visualizzato in un cluster di risultati.</span><span class="sxs-lookup"><span data-stu-id="b5a96-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="b5a96-115">Ad esempio, evitare l'utilizzo di ID come valori per la proprietà "title" a meno che gli utenti non utilizzino gli ID per cercare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b5a96-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="b5a96-116">La frequenza con cui viene visualizzato un cluster di risultati varia in base a fattori quali il numero di verticali di ricerca configurati e il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b5a96-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="b5a96-117">Interagendo o ignorando un cluster di risultati, gli utenti forniranno implicitamente suggerimenti che ne modificheranno l'attivazione nel tempo.</span><span class="sxs-lookup"><span data-stu-id="b5a96-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="b5a96-118">L'esperienza dei risultati di ricerca per gli elementi del connettore mostrati nel cluster di risultati utilizza i [tipi di risultati](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b5a96-118">The search result experience for connector items shown in your result cluster uses [result types](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="b5a96-119">Se non è stato configurato alcun tipo di risultato, viene utilizzato un [layout generato dal sistema](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) .</span><span class="sxs-lookup"><span data-stu-id="b5a96-119">If no result type is configured, a [system generated layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="b5a96-120">È consigliabile utilizzare la proprietà "title" come titolo del risultato della ricerca e la proprietà "Content" come descrizione della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b5a96-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="b5a96-121">In questo modo si otterrà la migliore esperienza per gli utenti tramite l'attivazione accurata del cluster di risultati e la maggior parte dei risultati rilevanti nel cluster.</span><span class="sxs-lookup"><span data-stu-id="b5a96-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="b5a96-122">Abilitare i cluster di risultati</span><span class="sxs-lookup"><span data-stu-id="b5a96-122">Enable result clusters</span></span>
  
<span data-ttu-id="b5a96-123">L'esperienza del cluster di risultati è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b5a96-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="b5a96-124">Seguire questa procedura per abilitare l'esperienza a livello dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="b5a96-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="b5a96-125">Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com), andare a [**verticali**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="b5a96-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="b5a96-126">Selezionare la verticale **tutto** , quindi Abilita **Mostra risultati connettore**.</span><span class="sxs-lookup"><span data-stu-id="b5a96-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="b5a96-127">Seguire questa procedura per abilitare l'esperienza a livello di sito di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="b5a96-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="b5a96-128">Nel sito di SharePoint in cui si desidera utilizzare il cluster di risultati, passare a **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="b5a96-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="b5a96-129">Vai a **informazioni sito** > **Visualizza tutte le impostazioni del sito**.</span><span class="sxs-lookup"><span data-stu-id="b5a96-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="b5a96-130">Andare alla sezione ricerca di Microsoft, quindi selezionare **configura Microsoft Search per la raccolta siti**.</span><span class="sxs-lookup"><span data-stu-id="b5a96-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="b5a96-131">Nel riquadro di spostamento, passare a **esperienza personalizzata**, quindi selezionare **verticali**.</span><span class="sxs-lookup"><span data-stu-id="b5a96-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="b5a96-132">Selezionare la verticale **tutto** , quindi Abilita **Mostra risultati connettore**.</span><span class="sxs-lookup"><span data-stu-id="b5a96-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="b5a96-133">Visualizzare l'esperienza del cluster di risultati dopo che è stata abilitata</span><span class="sxs-lookup"><span data-stu-id="b5a96-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="b5a96-134">Dopo aver attivato l'esperienza del cluster di risultati, potrebbero essere necessari alcuni minuti prima che sia possibile visualizzarla.</span><span class="sxs-lookup"><span data-stu-id="b5a96-134">After you turn on the result cluster experience, it might take a few minutes before you can view it.</span></span> <span data-ttu-id="b5a96-135">Se si desidera che l'esperienza venga immediatamente configurata, è possibile aggiungere *cacheClear = true* all'URL in SharePoint e Office.</span><span class="sxs-lookup"><span data-stu-id="b5a96-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
