---
title: Integrare PowerApps
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
ROBOTS: NOINDEX
description: Includere app basate sul browser nei risultati di segnalibri per Microsoft Search
ms.openlocfilehash: 1f4cf7512ee176015537be2fbe2f59429cde6578
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727970"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="5bd23-103">Integrare PowerApps</span><span class="sxs-lookup"><span data-stu-id="5bd23-103">Integrate PowerApps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5bd23-104">Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="5bd23-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="5bd23-105">Stiamo trasferendo il portale nell’interfaccia di amministrazione di Microsoft 365, e lo stesso sarà poi rimosso.</span><span class="sxs-lookup"><span data-stu-id="5bd23-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="5bd23-106">Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5bd23-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="5bd23-107">[Panoramica di Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="5bd23-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="5bd23-108">Aiutare gli utenti a completare le attività, ad esempio immettere ferie o segnalare le spese integrando le PowerApp esistenti con i segnalibri.</span><span class="sxs-lookup"><span data-stu-id="5bd23-108">Help your users complete tasks, such as entering vacation time or reporting expenses, by adding existing PowerApps to your bookmarks.</span></span> <span data-ttu-id="5bd23-109">Le PowerApp integrate sono visualizzate all’interno di un risultato di segnalibri, senza dover passare a un altro sito o aprire un altro strumento, evitando di perdere tempo e risorse.</span><span class="sxs-lookup"><span data-stu-id="5bd23-109">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="5bd23-110">Cosa sono le PowerApp?</span><span class="sxs-lookup"><span data-stu-id="5bd23-110">What are PowerApps?</span></span>

<span data-ttu-id="5bd23-111">PowerApps è un servizio che consente di creare applicazioni aziendali che vengono eseguite in un browser o in un telefono o tablet senza richiedere esperienza di programmazione.</span><span class="sxs-lookup"><span data-stu-id="5bd23-111">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="5bd23-112">Altre informazioni:</span><span class="sxs-lookup"><span data-stu-id="5bd23-112">Learn more:</span></span>
  
- <span data-ttu-id="5bd23-113">
  [Formazione guidata](https://docs.microsoft.com/it-IT/learn/browse/?products=powerapps)</span><span class="sxs-lookup"><span data-stu-id="5bd23-113">[Guided Learning](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)</span></span>
    
- <span data-ttu-id="5bd23-114">
  [Documentazione](https://docs.microsoft.com/it-IT/powerapps/)</span><span class="sxs-lookup"><span data-stu-id="5bd23-114">[Documentation](https://docs.microsoft.com/en-us/powerapps/)</span></span>
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="5bd23-115">Aggiungere una PowerApp a un segnalibro</span><span class="sxs-lookup"><span data-stu-id="5bd23-115">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="5bd23-116">PowerApps funziona con qualsiasi browser e su qualsiasi dispositivo e l'aggiunta richiede meno di un minuto.</span><span class="sxs-lookup"><span data-stu-id="5bd23-116">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="5bd23-117">
  [Trovare l'ID di applicazione per la PowerApp](https://docs.microsoft.com/it-IT/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) da integrare</span><span class="sxs-lookup"><span data-stu-id="5bd23-117">Find the [App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) that you want to add.</span></span> 
    
2. <span data-ttu-id="5bd23-118">Nel portale di amministrazione di Microsoft Search passare a **Segnalibri**</span><span class="sxs-lookup"><span data-stu-id="5bd23-118">In the Microsoft Search Admin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="5bd23-119">Aggiungere un segnalibro o trovare un segnalibro esistente a cui si vuole aggiungere una PowerApp</span><span class="sxs-lookup"><span data-stu-id="5bd23-119">Add a bookmark or find an existing bookmark that you want to add a PowerApp to.</span></span>
    
4. <span data-ttu-id="5bd23-120">In Impostazioni segnalibro fare clic su **Power App** e quindi su **Aggiungi Power App**</span><span class="sxs-lookup"><span data-stu-id="5bd23-120">In Bookmark settings, select Power App, and then Add a Power App.</span></span>
    
5. <span data-ttu-id="5bd23-121">Immettere o incollare l'ID dell’app</span><span class="sxs-lookup"><span data-stu-id="5bd23-121">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="5bd23-122">Vengono aggiunte automaticamente l'altezza e la larghezza.</span><span class="sxs-lookup"><span data-stu-id="5bd23-122">The height and width are automatically adjusted.</span></span> <span data-ttu-id="5bd23-123">I segnalibri possono supportare orientamento orizzontale e verticale, ma attualmente non è possibile modificare le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="5bd23-123">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="5bd23-124">L'anteprima del segnalibro mostra come apparirà la PowerApp nel risultato del segnalibro</span><span class="sxs-lookup"><span data-stu-id="5bd23-124">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="5bd23-125">La PowerApp nel riquadro di anteprima è completamente funzionante, per renderla semplice da testare e da usare.</span><span class="sxs-lookup"><span data-stu-id="5bd23-125">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="5bd23-126">Fare clic su **Pubblica**</span><span class="sxs-lookup"><span data-stu-id="5bd23-126">Click **Publish**.</span></span>
    
<span data-ttu-id="5bd23-127">Quando un utente di Microsoft Search autorizzato cerca in Bing le parole chiave o le parole chiave riservate del segnalibro, la PowerApp verrà visualizzata nel risultato del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="5bd23-127">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

