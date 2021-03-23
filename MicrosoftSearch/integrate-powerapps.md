---
title: Integrare Power Apps
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
description: Includere app basate su browser nei risultati dei segnalibri per Microsoft Search
ms.openlocfilehash: 52fa78c54ab6db74ef1e3679d3d32151a3f5ac10
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031702"
---
# <a name="integrate-power-apps-in-microsoft-search-bookmarks"></a><span data-ttu-id="6f28c-103">Integrare Power Apps nei segnalibri di Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="6f28c-103">Integrate Power Apps in Microsoft Search bookmarks</span></span>
   
<span data-ttu-id="6f28c-104">Aiuta gli utenti a completare attività, come l'immissione di periodi di ferie o le spese di reporting, integrando [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) esistenti nei segnalibri di Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="6f28c-104">Help your users complete tasks, like entering vacation time or reporting expenses, by integrating existing [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) into your Microsoft Search bookmarks.</span></span> <span data-ttu-id="6f28c-105">Le app power integrate vengono visualizzate all'interno di un risultato di segnalibro, eliminando la necessità di passare a un sito diverso o aprire uno strumento separato, risparmiando tempi e fatica.</span><span class="sxs-lookup"><span data-stu-id="6f28c-105">Integrated Power Apps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-power-apps"></a><span data-ttu-id="6f28c-106">Che cos'è Power Apps?</span><span class="sxs-lookup"><span data-stu-id="6f28c-106">What are Power Apps?</span></span>

<span data-ttu-id="6f28c-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) è un servizio che consente di creare app aziendali che vengono eseguite in un browser o in un telefono o un tablet senza alcuna esperienza di codifica necessaria.</span><span class="sxs-lookup"><span data-stu-id="6f28c-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="6f28c-108">Ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="6f28c-108">Learn more:</span></span>
  
- [<span data-ttu-id="6f28c-109">Formazione guidata</span><span class="sxs-lookup"><span data-stu-id="6f28c-109">Guided Learning</span></span>](/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="6f28c-110">Documentazione</span><span class="sxs-lookup"><span data-stu-id="6f28c-110">Documentation</span></span>](/powerapps/)
    
## <a name="add-a-power-app-to-a-bookmark"></a><span data-ttu-id="6f28c-111">Aggiungere un'app Power a un segnalibro</span><span class="sxs-lookup"><span data-stu-id="6f28c-111">Add a Power App to a bookmark</span></span>

<span data-ttu-id="6f28c-112">[Power Apps( funziona in qualsiasi browser e in qualsiasi dispositivo e richiede meno di https://products.office.com/business/microsoft-powerapps) un minuto per l'aggiunta.</span><span class="sxs-lookup"><span data-stu-id="6f28c-112">[Power Apps(https://products.office.com/business/microsoft-powerapps) work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="6f28c-113">[Trova l'ID app per l'app Power Che](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) vuoi integrare.</span><span class="sxs-lookup"><span data-stu-id="6f28c-113">[Find the App ID for the Power App](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate.</span></span>
    
2. <span data-ttu-id="6f28c-114">Nell'interfaccia di amministrazione [](https://admin.microsoft.com)di Microsoft 365 passare a **Segnalibri**.</span><span class="sxs-lookup"><span data-stu-id="6f28c-114">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Bookmarks**.</span></span>
    
3. <span data-ttu-id="6f28c-115">Aggiungi un segnalibro o trova un segnalibro esistente a cui vuoi aggiungere un'app Power.</span><span class="sxs-lookup"><span data-stu-id="6f28c-115">Add a bookmark or find an existing bookmark that you want to add a Power App to.</span></span>
    
4. <span data-ttu-id="6f28c-116">Nelle impostazioni dei segnalibri seleziona **Power App** e quindi **aggiungi un'app Power.**</span><span class="sxs-lookup"><span data-stu-id="6f28c-116">In the bookmark settings, select **Power App**, and then select **Add a Power App**.</span></span>
    
5. <span data-ttu-id="6f28c-117">Immettere o incollare l'ID dell’app.</span><span class="sxs-lookup"><span data-stu-id="6f28c-117">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="6f28c-118">L'altezza e la larghezza vengono aggiunte automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6f28c-118">The height and width are automatically added.</span></span> <span data-ttu-id="6f28c-119">I segnalibri possono supportare orientamento orizzontale e verticale, ma attualmente non è possibile modificare le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="6f28c-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="6f28c-120">L'anteprima dei segnalibri mostra come l'app Power App verrà visualizzata nel risultato del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="6f28c-120">The bookmark preview shows how the Power App will appear in the bookmark result.</span></span>
    
    <span data-ttu-id="6f28c-121">L'app Power Nell'anteprima è completamente funzionante per semplificare il test e l'uso.</span><span class="sxs-lookup"><span data-stu-id="6f28c-121">The Power App in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="6f28c-122">Selezionare **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="6f28c-122">Select **Publish**.</span></span>
    
<span data-ttu-id="6f28c-123">Quando un utente autorizzato di Microsoft Search cerca in [Bing](https://Bing.com) le parole chiave del segnalibro o le parole chiave riservate, l'app Power app verrà visualizzata nel risultato del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="6f28c-123">When an authorized Microsoft Search user searches on [Bing](https://Bing.com) for any of the bookmark's keywords or reserved keywords, the Power App will appear in the bookmark result.</span></span>