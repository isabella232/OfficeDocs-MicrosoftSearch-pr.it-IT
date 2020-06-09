---
title: Anteprima connettori
ms.author: mounika.narayanan
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Informazioni sull'anteprima dei connettori Microsoft Graph per Microsoft Search.
ms.openlocfilehash: 4bcd8360957be69bc701e8b356cd222de32bfc5f
ms.sourcegitcommit: 64eea81f8c1db9ee955013462a7b51612fb7d0b7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "44604384"
---
# <a name="microsoft-graph-connectors-preview"></a><span data-ttu-id="d0c17-103">Anteprima connettori Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="d0c17-103">Microsoft Graph connectors preview</span></span>

<span data-ttu-id="d0c17-104">I connettori Microsoft Graph e le API di Microsoft Search (query e indice) sono attualmente in stato di anteprima.</span><span class="sxs-lookup"><span data-stu-id="d0c17-104">Microsoft Graph connectors and Microsoft Search APIs (query and index) are currently in preview status.</span></span> <span data-ttu-id="d0c17-105">Per accedere alla funzionalità dei connettori, è necessario abilitare l'opzione di rilascio di destinazione nel tenant.</span><span class="sxs-lookup"><span data-stu-id="d0c17-105">To gain access to connectors functionality, you must turn on the Targeted release option in your tenant.</span></span> <span data-ttu-id="d0c17-106">Si tratta di un'anteprima iniziale e non vi è alcuna garanzia a livello di servizio.</span><span class="sxs-lookup"><span data-stu-id="d0c17-106">This is an early preview, and there's no service level guarantee.</span></span> <span data-ttu-id="d0c17-107">Si consiglia ai clienti di provare la funzionalità dei connettori e fornire commenti e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="d0c17-107">We encourage customers to try connectors functionality and provide feedback.</span></span> <span data-ttu-id="d0c17-108">Non è consigliabile utilizzare i connettori per scopi di produzione durante il periodo di anteprima.</span><span class="sxs-lookup"><span data-stu-id="d0c17-108">We don’t recommend using connectors for production purposes during the preview period.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="d0c17-109">Configurare la versione di destinazione</span><span class="sxs-lookup"><span data-stu-id="d0c17-109">Set up Targeted release</span></span>

<span data-ttu-id="d0c17-110">Per provare i connettori, è necessario che l'opzione di **rilascio di destinazione** sia impostata per tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d0c17-110">To try connectors, you must have the **Targeted release** option set for all users in your organization.</span></span> <span data-ttu-id="d0c17-111">Per ulteriori informazioni sull'opzione di rilascio mirato e su come impostarla, vedere [configurare le opzioni di rilascio standard o di destinazione in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="d0c17-111">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

## <a name="choose-a-preview-environment"></a><span data-ttu-id="d0c17-112">Scegliere un ambiente di anteprima</span><span class="sxs-lookup"><span data-stu-id="d0c17-112">Choose a preview environment</span></span>

<span data-ttu-id="d0c17-113">Per provare connettori, API di indicizzazione e API di ricerca, è consigliabile utilizzare i due metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0c17-113">To try connectors, indexing APIs, and search APIs, we recommend these two methods:</span></span>

1. <span data-ttu-id="d0c17-114">**Tenant di testing**.</span><span class="sxs-lookup"><span data-stu-id="d0c17-114">**Test tenant**.</span></span>  <span data-ttu-id="d0c17-115">Si consiglia di utilizzare un tenant di test per provare l'anteprima dei connettori di Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="d0c17-115">We encourage you to use a test tenant to try the Microsoft Graph connectors preview.</span></span>

2. <span data-ttu-id="d0c17-116">**Raccolta siti di test**.</span><span class="sxs-lookup"><span data-stu-id="d0c17-116">**Test site collection**.</span></span> <span data-ttu-id="d0c17-117">Se non si dispone di un tenant di prova, è possibile creare una raccolta siti di prova per provare la funzionalità di connettori.</span><span class="sxs-lookup"><span data-stu-id="d0c17-117">If you don't have a test tenant, you can create a test site collection to try out connectors functionality.</span></span> <span data-ttu-id="d0c17-118">Per visualizzare i risultati dei connettori senza influire sulle pagine di ricerca in nessun'altra parte dell'organizzazione, personalizzare l'esperienza di ricerca solo per la raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="d0c17-118">To show results from connectors without impacting the search pages anywhere else in your organization, customize the search experience of only that site collection.</span></span>

## <a name="preview-limitations"></a><span data-ttu-id="d0c17-119">Limitazioni relative all'anteprima</span><span class="sxs-lookup"><span data-stu-id="d0c17-119">Preview limitations</span></span>

<span data-ttu-id="d0c17-120">La versione di anteprima presenta le limitazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0c17-120">The preview release has the following limitations:</span></span>

* <span data-ttu-id="d0c17-121">La velocità effettiva di ingestione viene limitata a circa quattro elementi al secondo.</span><span class="sxs-lookup"><span data-stu-id="d0c17-121">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="d0c17-122">Non è disponibile alcun supporto per gli aggiornamenti dello schema.</span><span class="sxs-lookup"><span data-stu-id="d0c17-122">There's no support for schema updates.</span></span> <span data-ttu-id="d0c17-123">Dopo aver creato una configurazione di connessione, non è possibile aggiornare lo schema.</span><span class="sxs-lookup"><span data-stu-id="d0c17-123">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="d0c17-124">È possibile eliminare e ricreare la connessione solo.</span><span class="sxs-lookup"><span data-stu-id="d0c17-124">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="d0c17-125">Il contenuto indicizzato viene visualizzato solo nella pagina dei risultati di ricerca in un verticale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d0c17-125">Indexed content only shows up in the search results page under a custom vertical.</span></span> <span data-ttu-id="d0c17-126">Questa restrizione si applica al contenuto con tipi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d0c17-126">This restriction applies to content with custom types.</span></span>

* <span data-ttu-id="d0c17-127">Potrebbe essere necessario eliminare e ricreare qualsiasi connessione configurata durante il periodo di anteprima.</span><span class="sxs-lookup"><span data-stu-id="d0c17-127">Any connection you set up during the preview period might need to be deleted and re-created.</span></span> <span data-ttu-id="d0c17-128">Tali connessioni non funzioneranno più se non sono compatibili con le modifiche apportate per migliorare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="d0c17-128">Those connections won't work anymore if they're incompatible with changes made to improve the product.</span></span>

* <span data-ttu-id="d0c17-129">Esiste un limite per le connessioni.</span><span class="sxs-lookup"><span data-stu-id="d0c17-129">There's a connections limit.</span></span> <span data-ttu-id="d0c17-130">Ogni tenant è in grado di creare fino a 10 connessioni.</span><span class="sxs-lookup"><span data-stu-id="d0c17-130">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="d0c17-131">Dimensione del repository di origine.</span><span class="sxs-lookup"><span data-stu-id="d0c17-131">Source repository size.</span></span> <span data-ttu-id="d0c17-132">Si consiglia di visualizzare in anteprima i connettori con un repository di origine di circa 200.000 elementi, in quanto questo è il limite della scala di ricerca testato.</span><span class="sxs-lookup"><span data-stu-id="d0c17-132">We recommend that you preview connectors with a source repository of about 200,000 items as this is our tested search scale limit.</span></span> <span data-ttu-id="d0c17-133">Stiamo lavorando per migliorare le prestazioni della ricerca e si prevede di supportare le dimensioni dei repository più grandi nel prossimo futuro.</span><span class="sxs-lookup"><span data-stu-id="d0c17-133">We are working on improving the performance of search, and we expect to support for larger repository sizes in the near future.</span></span>

* <span data-ttu-id="d0c17-134">La modifica del supporto per la connessione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="d0c17-134">Edit support for connection is not available.</span></span> <span data-ttu-id="d0c17-135">Dopo aver creato la connessione, non è possibile modificarla o modificarla.</span><span class="sxs-lookup"><span data-stu-id="d0c17-135">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="d0c17-136">Se è necessario modificare i dettagli, è necessario eliminare e ricreare la connessione.</span><span class="sxs-lookup"><span data-stu-id="d0c17-136">If you need to change any details, you must delete and recreate the connection.</span></span>

* <span data-ttu-id="d0c17-137">È possibile cercare il contenuto del connettore solo su verticale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d0c17-137">Connector content can only be searched on custom verticals.</span></span>

* <span data-ttu-id="d0c17-138">Il contenuto del connettore da una sola connessione può essere visualizzato in ogni verticale personalizzato e richiede la creazione del tipo di risultato.</span><span class="sxs-lookup"><span data-stu-id="d0c17-138">Connector content from only one connection can be displayed in each custom vertical and requires result type creation.</span></span>
