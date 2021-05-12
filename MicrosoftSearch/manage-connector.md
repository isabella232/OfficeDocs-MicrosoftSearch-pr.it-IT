---
title: Gestire i connettori di Microsoft Graph per Microsoft Search
ms.author: mecampos
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gestire i connettori di Microsoft Graph per Microsoft Search.
ms.openlocfilehash: 685b501f3afe25d75c13a1fe6cc2c1b5db8a3511
ms.sourcegitcommit: e5d695c40b68c2f1fa082fa9de20b9aa6d5b8050
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52325169"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="8a9ee-103">Monitorare le connessioni</span><span class="sxs-lookup"><span data-stu-id="8a9ee-103">Monitor your connections</span></span>

<span data-ttu-id="8a9ee-104">Per accedere e gestire i connettori, è necessario essere designati come amministratore della ricerca per il tenant.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="8a9ee-105">Contattare l'amministratore tenant per eseguire il provisioning del ruolo di amministratore della ricerca.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="8a9ee-106">Operazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="8a9ee-106">Connection Operations</span></span>

<span data-ttu-id="8a9ee-107">Passare alla scheda [Connettori nell'interfaccia](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) di amministrazione di [Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="8a9ee-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="8a9ee-108">Per ogni tipo di connettore, l'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) supporta le operazioni illustrate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="8a9ee-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="8a9ee-109">Operazione</span><span class="sxs-lookup"><span data-stu-id="8a9ee-109">Operation</span></span> | <span data-ttu-id="8a9ee-110">Connettori di Graph Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a9ee-110">Graph connectors by Microsoft</span></span> | <span data-ttu-id="8a9ee-111">Connettori partner o grafico</span><span class="sxs-lookup"><span data-stu-id="8a9ee-111">Partner or Graph connectors</span></span>
--- | --- | ---
<span data-ttu-id="8a9ee-112">Aggiungere una connessione</span><span class="sxs-lookup"><span data-stu-id="8a9ee-112">Add a connection</span></span> | :heavy_check_mark: <span data-ttu-id="8a9ee-113">(Vedere Panoramica [dell'installazione](configure-connector.md))</span><span class="sxs-lookup"><span data-stu-id="8a9ee-113">(See [Setup overview](configure-connector.md))</span></span> | :x: <span data-ttu-id="8a9ee-114">(Fare riferimento all'esperienza utente dell'amministratore del partner o del connettore personalizzato)</span><span class="sxs-lookup"><span data-stu-id="8a9ee-114">(Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="8a9ee-115">Eliminazione di una connessione</span><span class="sxs-lookup"><span data-stu-id="8a9ee-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="8a9ee-118">Modificare una connessione pubblicata</span><span class="sxs-lookup"><span data-stu-id="8a9ee-118">Edit a published connection</span></span> | :heavy_check_mark: <span data-ttu-id="8a9ee-119">Nome e descrizione</span><span class="sxs-lookup"><span data-stu-id="8a9ee-119">Name and Description</span></span><br></br> :heavy_check_mark: <span data-ttu-id="8a9ee-120">Impostazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="8a9ee-120">Connection settings</span></span><br></br> :heavy_check_mark: <span data-ttu-id="8a9ee-121">etichette di proprietà</span><span class="sxs-lookup"><span data-stu-id="8a9ee-121">Property labels</span></span><br></br> :heavy_check_mark: <span data-ttu-id="8a9ee-122">Schema</span><span class="sxs-lookup"><span data-stu-id="8a9ee-122">Schema</span></span><br></br> :heavy_check_mark: <span data-ttu-id="8a9ee-123">Pianificazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="8a9ee-123">Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="8a9ee-124">Name</span><span class="sxs-lookup"><span data-stu-id="8a9ee-124">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="8a9ee-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8a9ee-125">Description</span></span>
<span data-ttu-id="8a9ee-126">Modificare una bozza di connessione</span><span class="sxs-lookup"><span data-stu-id="8a9ee-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a><span data-ttu-id="8a9ee-129">Monitorare lo stato della connessione</span><span class="sxs-lookup"><span data-stu-id="8a9ee-129">Monitor your connection state</span></span>

<span data-ttu-id="8a9ee-130">Dopo aver creato una connessione, il numero di elementi elaborati viene visualizzato nella scheda **Connettori** della pagina **Microsoft Search.**</span><span class="sxs-lookup"><span data-stu-id="8a9ee-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="8a9ee-131">Al termine della ricerca per indicizzazione completa iniziale, viene visualizzato l'avanzamento delle ricerche per indicizzazione incrementali periodiche.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="8a9ee-132">In questa pagina vengono fornite informazioni sulle operazioni quotidiane del connettore e una panoramica dei registri e della cronologia degli errori.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="8a9ee-133">Nella colonna Stato vengono visualizzati cinque **stati** per ogni connessione:</span><span class="sxs-lookup"><span data-stu-id="8a9ee-133">Five states show up in the **State** column against each connection:</span></span>

* <span data-ttu-id="8a9ee-134">**Sincronizzazione di**.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-134">**Syncing**.</span></span> <span data-ttu-id="8a9ee-135">Il connettore esegue la ricerca per indicizzazione dei dati dall'origine per indicizzare gli elementi esistenti e apportare eventuali aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="8a9ee-136">**Pronto**: la connessione è pronta e non è in esecuzione alcuna ricerca per indicizzazione attiva.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-136">**Ready**: The connection is ready, and there's no active crawl running against it.</span></span> <span data-ttu-id="8a9ee-137">**L'ora dell'ultima** sincronizzazione indica quando si è verificata l'ultima ricerca per indicizzazione completata.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="8a9ee-138">La connessione è appena stata stabilita come l'ora dell'ultima sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="8a9ee-139">**Paused**.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-139">**Paused**.</span></span> <span data-ttu-id="8a9ee-140">Le ricerche per indicizzazione vengono sospese dagli amministratori tramite l'opzione di sospensione.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="8a9ee-141">La ricerca per indicizzazione successiva viene eseguita solo quando viene ripresa manualmente.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="8a9ee-142">Tuttavia, i dati di questa connessione continuano a essere ricercabili.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="8a9ee-143">**Operazione non riuscita.**</span><span class="sxs-lookup"><span data-stu-id="8a9ee-143">**Failed**.</span></span> <span data-ttu-id="8a9ee-144">Si è verificato un errore critico nella connessione.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-144">The connection had a critical failure.</span></span> <span data-ttu-id="8a9ee-145">Questo errore richiede un intervento manuale.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-145">This error requires manual intervention.</span></span> <span data-ttu-id="8a9ee-146">L'amministratore deve eseguire l'azione appropriata in base al messaggio di errore visualizzato.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="8a9ee-147">I dati indicizzati fino a quando non si è verificato l'errore sono ricercabili.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-147">Data that was indexed until the error occurred is searchable.</span></span>

* <span data-ttu-id="8a9ee-148">**Eliminazione non riuscita.**</span><span class="sxs-lookup"><span data-stu-id="8a9ee-148">**Delete Failed**.</span></span> <span data-ttu-id="8a9ee-149">L'eliminazione della connessione non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-149">The deletion of connection failed.</span></span> <span data-ttu-id="8a9ee-150">A seconda del motivo dell'errore, è possibile che i dati siano ancora indicizzati, che la quota degli elementi venga ancora utilizzata e che le ricerche per indicizzazione siano ancora in esecuzione per la connessione.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-150">Depending upon the failure reason, the data might still be indexed, item quota may still be consumed and crawls might still run for the connection.</span></span> <span data-ttu-id="8a9ee-151">Si consiglia di provare a eliminare di nuovo la connessione in questo stato.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-151">It is recommended to try deleting the connection again in this state.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="8a9ee-152">Monitorare l'utilizzo della quota di indice</span><span class="sxs-lookup"><span data-stu-id="8a9ee-152">Monitor your index quota utilization</span></span>

<span data-ttu-id="8a9ee-153">La quota di indice e l'utilizzo disponibili vengono visualizzati nella pagina di destinazione dei connettori.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-153">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![Barra di utilizzo quota indice](media/quota_utilization.png)
 
>[!NOTE]
><span data-ttu-id="8a9ee-155">Durante il periodo di anteprima, a ogni organizzazione che provava i connettori Graph è stata fornita una quota fissa gratuita di un massimo di 2 milioni di elementi in tutte le connessioni.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-155">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="8a9ee-156">Con la disponibilità generale dei connettori Graph, la quota gratuita scadrà il 1° aprile 2021 per le organizzazioni che hanno utilizzato i connettori Graph in anteprima.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-156">With Graph connectors being generally available, the free quota will expire on April 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="8a9ee-157">I connettori Microsoft Graph etichettati come ["Anteprima"](./connectors-overview.md) non verranno inclusi nella quota di indice totale addebitata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-157">Microsoft-built Graph connectors labeled as ["Preview"](./connectors-overview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="8a9ee-158">Tuttavia, verrà conteggiato per il numero massimo di 10 connessioni che è possibile configurare per l'organizzazione e il numero massimo di 7 milioni di elementi che l'organizzazione può indicizzare tra le connessioni. ogni connessione è limitata a 700.000 elementi.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-158">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="8a9ee-159">La barra di utilizzo delle quote indicherà diversi stati in base all'utilizzo della quota da parte dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="8a9ee-159">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="8a9ee-160">Stato</span><span class="sxs-lookup"><span data-stu-id="8a9ee-160">State</span></span> | <span data-ttu-id="8a9ee-161">Livelli di utilizzo delle quote</span><span class="sxs-lookup"><span data-stu-id="8a9ee-161">Quota utilization levels</span></span>
--- | --- 
<span data-ttu-id="8a9ee-162">Normale</span><span class="sxs-lookup"><span data-stu-id="8a9ee-162">Normal</span></span> | <span data-ttu-id="8a9ee-163">0-79%</span><span class="sxs-lookup"><span data-stu-id="8a9ee-163">0-79%</span></span>
<span data-ttu-id="8a9ee-164">Alta</span><span class="sxs-lookup"><span data-stu-id="8a9ee-164">High</span></span> | <span data-ttu-id="8a9ee-165">80-89%</span><span class="sxs-lookup"><span data-stu-id="8a9ee-165">80-89%</span></span>
<span data-ttu-id="8a9ee-166">Critico</span><span class="sxs-lookup"><span data-stu-id="8a9ee-166">Critical</span></span> | <span data-ttu-id="8a9ee-167">90%-99%</span><span class="sxs-lookup"><span data-stu-id="8a9ee-167">90%-99%</span></span>
<span data-ttu-id="8a9ee-168">Full</span><span class="sxs-lookup"><span data-stu-id="8a9ee-168">Full</span></span> | <span data-ttu-id="8a9ee-169">100%</span><span class="sxs-lookup"><span data-stu-id="8a9ee-169">100%</span></span>

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

<span data-ttu-id="8a9ee-170">Con ogni connessione verrà visualizzato anche il numero di elementi indicizzati.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-170">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="8a9ee-171">Il numero di elementi indicizzati da ogni connessione contribuisce alla quota totale disponibile per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-171">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="8a9ee-172">Quando viene superata la quota di indice per l'organizzazione, verranno influenzate tutte le connessioni attive e tali connessioni funzioneranno nello **stato limite superato.**</span><span class="sxs-lookup"><span data-stu-id="8a9ee-172">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="8a9ee-173">In questo stato, le connessioni attive</span><span class="sxs-lookup"><span data-stu-id="8a9ee-173">In this state, your active connections</span></span>  

* <span data-ttu-id="8a9ee-174">Non sarà possibile aggiungere nuovi elementi.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-174">Will not be able to add new items.</span></span>

* <span data-ttu-id="8a9ee-175">Sarà possibile aggiornare o eliminare elementi esistenti.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-175">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="8a9ee-176">Per risolvere il problema, è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8a9ee-176">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="8a9ee-177">Per informazioni su come acquistare la quota di indice per l'organizzazione, vedere [Requisiti di licenza e prezzi.](licensing.md)</span><span class="sxs-lookup"><span data-stu-id="8a9ee-177">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="8a9ee-178">Identificare le connessioni con troppo contenuto ingerito e aggiornarle in modo da indicizzare un numero minore di elementi per creare spazio per la quota.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-178">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="8a9ee-179">Per aggiornare la connessione, è necessario eliminare e creare una nuova connessione con un nuovo filtro di inserimento che comporta un numero minore di elementi.</span><span class="sxs-lookup"><span data-stu-id="8a9ee-179">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="8a9ee-180">Eliminare definitivamente una o più connessioni</span><span class="sxs-lookup"><span data-stu-id="8a9ee-180">Permanently delete one or more connections</span></span>