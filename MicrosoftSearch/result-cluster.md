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
ms.openlocfilehash: fa6ac2dc720ed43e40454b952526734accd45ea4
ms.sourcegitcommit: a328b9764abf5cd0c1c0a8c7def0c6e334da9a1d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477114"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="b0cb3-103">Cluster di risultati dei connettori del grafico</span><span class="sxs-lookup"><span data-stu-id="b0cb3-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="b0cb3-104">Panoramica del cluster di risultati dei connettori del grafico (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b0cb3-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="b0cb3-105">Con i cluster di risultati dei connettori grafico, le aziende possono cercare contenuto da origini dati di terze parti nella visualizzazione predefinita (la scheda tutti) in SharePoint e Office.com.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view (the All tab) in SharePoint and Office.com.</span></span>

<span data-ttu-id="b0cb3-106">I cluster di risultati aiutano gli utenti a individuare tutti i contenuti di terze parti (previoulsy collegato a un singolo connettore e verticale) in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-106">Result clusters help users discover all third party content (previoulsy tied to a single connector and vertical) in one place.</span></span> <span data-ttu-id="b0cb3-107">I risultati mostrati in un cluster di risultati vengono raggruppati in base al modo in cui l'amministratore tenant le configura in un verticale di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-107">The results shown in a result cluster are grouped together based on how the tenant administrator configures them in a search vertical.</span></span>  

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="b0cb3-108">Modalità di selezione e visualizzazione dei risultati del connettore</span><span class="sxs-lookup"><span data-stu-id="b0cb3-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="b0cb3-109">I risultati del connettore forniti nel cluster di risultati sono derivati da singoli verticali di ricerca con contenuto del connettore.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="b0cb3-110">Ogni verticale di ricerca fornisce una serie di risultati rilevanti che diventeranno un cluster di risultati candidato.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="b0cb3-111">I risultati rilevanti vengono scelti in base alla proprietà "title", al frammento di risultati e al componente contenuto di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-111">Relevant results are chosen based on the "title" property, result snippet, and content component of each item.</span></span>

<span data-ttu-id="b0cb3-112">Per garantire l'individuazione del contenuto dai verticali di ricerca, è consigliabile fornire titoli significativi per gli elementi.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-112">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="b0cb3-113">Questo incide positivamente sull'arbitrato dei candidati del cluster di risultati e sulla probabilità che il contenuto venga visualizzato in un cluster di risultati.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-113">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="b0cb3-114">Ad esempio, evitare l'utilizzo di ID come valori per la proprietà "title" a meno che gli utenti non utilizzino gli ID per cercare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-114">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="b0cb3-115">La frequenza con cui viene visualizzato un cluster di risultati varia in base a fattori quali il numero di verticali di ricerca configurati e il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-115">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="b0cb3-116">Se si seleziona o si ignorano i risultati dei cluster di risultati, verranno forniti implicitamente suggerimenti che consentiranno di regolare l'attivazione di cluster di risultati nel tempo.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-116">By either selecting or ignoring result cluster results, you will implicitly provide hints that will adjust the triggering of result clusters over time.</span></span>

<span data-ttu-id="b0cb3-117">L'esperienza dei risultati di ricerca per gli elementi del connettore mostrati nel cluster di risultati è generata dal sistema e non utilizza layout dei risultati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-117">The search result experience for connector items shown in your result cluster is system generated and does not use custom result layouts.</span></span> <span data-ttu-id="b0cb3-118">Se si desidera che i risultati vengano visualizzati nel cluster di risultati, è necessario dichiarare la proprietà "title" e il contenuto dell'elemento durante la registrazione della connessione.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-118">You must declare the "title" property and item content during connection registration if you want results to appear in your result cluster.</span></span>

## <a name="enable-result-clusters"></a><span data-ttu-id="b0cb3-119">Abilitare i cluster di risultati</span><span class="sxs-lookup"><span data-stu-id="b0cb3-119">Enable result clusters</span></span>
  
<span data-ttu-id="b0cb3-120">L'esperienza del cluster di risultati è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-120">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="b0cb3-121">Seguire questa procedura per abilitare l'esperienza a livello dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="b0cb3-121">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="b0cb3-122">Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/)passare a **Impostazioni** di  >  **ricerca &**  >  verticale di **personalizzazione** dell'Intelligence  >  **Verticals**.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-122">In the [Microsoft 365 admin center](https://admin.microsoft.com/), go to **Settings** > **Search & intelligence** > **Customization** > **Verticals**.</span></span>  
2. <span data-ttu-id="b0cb3-123">Selezionare la verticale **tutto** , quindi Abilita **Mostra risultati connettore**.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-123">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="b0cb3-124">Seguire questa procedura per abilitare l'esperienza a livello di sito:</span><span class="sxs-lookup"><span data-stu-id="b0cb3-124">Follow these steps to turn on the experience at the site level:</span></span>

1. <span data-ttu-id="b0cb3-125">Nel sito di SharePoint in cui si desidera utilizzare il cluster di risultati, passare a **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-125">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="b0cb3-126">Vai a **informazioni sito** > **Visualizza tutte le impostazioni del sito**.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-126">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="b0cb3-127">Andare alla sezione ricerca di Microsoft, quindi selezionare **configura Microsoft Search per la raccolta siti**.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-127">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="b0cb3-128">Nel riquadro di spostamento, passare a **esperienza personalizzata**, quindi selezionare **verticali**.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-128">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="b0cb3-129">Selezionare la verticale **tutto** , quindi Abilita **Mostra risultati connettore**.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-129">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="b0cb3-130">Visualizzare l'esperienza del cluster di risultati dopo che è stata abilitata</span><span class="sxs-lookup"><span data-stu-id="b0cb3-130">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="b0cb3-131">Dopo aver attivato l'esperienza del cluster di risultati, potrebbero essere necessari alcuni minuti prima che sia possibile visualizzarla.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-131">After you turn on the result cluster experience, it might take a few minutes before you can view it.</span></span> <span data-ttu-id="b0cb3-132">Se si desidera che l'esperienza venga immediatamente configurata, è possibile aggiungere *cacheClear = true* all'URL in SharePoint e Office.</span><span class="sxs-lookup"><span data-stu-id="b0cb3-132">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
