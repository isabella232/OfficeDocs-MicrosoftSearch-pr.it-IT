---
title: Integrazione di Power Apps
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
description: Includere le app basate su browser nei risultati dei segnalibri per Microsoft Search
ms.openlocfilehash: 7d3dd21758c63da14bbd3896ece1ce67a19c80a2
ms.sourcegitcommit: f4cb37fdf85b895337caee827fb72b5b7fcaa8ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2019
ms.locfileid: "39995024"
---
# <a name="integrate-power-apps-in-microsoft-search-bookmarks"></a><span data-ttu-id="d078f-103">Integrare le app Power nei segnalibri di Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="d078f-103">Integrate Power Apps in Microsoft Search bookmarks</span></span>
   
<span data-ttu-id="d078f-104">Aiutare gli utenti a completare le attività, ad esempio il tempo di ferie o le spese per le relazioni, integrando le [applicazioni Microsoft Power](https://products.office.com/business/microsoft-powerapps) esistenti nei segnalibri di Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="d078f-104">Help your users complete tasks, like entering vacation time or reporting expenses, by integrating existing [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) into your Microsoft Search bookmarks.</span></span> <span data-ttu-id="d078f-105">Le app Power integrate vengono visualizzate all'interno di un risultato di segnalibro, eliminando la necessità di accedere a un altro sito o di aprire uno strumento separato, che consente di risparmiare tempo e fatica.</span><span class="sxs-lookup"><span data-stu-id="d078f-105">Integrated Power Apps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-power-apps"></a><span data-ttu-id="d078f-106">Che cos'è Power Apps?</span><span class="sxs-lookup"><span data-stu-id="d078f-106">What are Power Apps?</span></span>

<span data-ttu-id="d078f-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) è un servizio che consente di creare app aziendali che vengono eseguite in un browser o su un telefono o tablet senza che sia necessaria alcuna esperienza di codifica.</span><span class="sxs-lookup"><span data-stu-id="d078f-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="d078f-108">Ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="d078f-108">Learn more:</span></span>
  
- [<span data-ttu-id="d078f-109">Formazione guidata</span><span class="sxs-lookup"><span data-stu-id="d078f-109">Guided Learning</span></span>](https://docs.microsoft.com/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="d078f-110">Documentazione</span><span class="sxs-lookup"><span data-stu-id="d078f-110">Documentation</span></span>](https://docs.microsoft.com/powerapps/)
    
## <a name="add-a-power-app-to-a-bookmark"></a><span data-ttu-id="d078f-111">Aggiungere un'app Power a un segnalibro</span><span class="sxs-lookup"><span data-stu-id="d078f-111">Add a Power App to a bookmark</span></span>

<span data-ttu-id="d078f-112">[Power Apps (https://products.office.com/business/microsoft-powerapps) funziona in qualsiasi browser e su qualsiasi dispositivo e impiega meno di un minuto per aggiungere.</span><span class="sxs-lookup"><span data-stu-id="d078f-112">[Power Apps(https://products.office.com/business/microsoft-powerapps) work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="d078f-113">[Individuare l'ID app per l'app Power](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) che si desidera integrare.</span><span class="sxs-lookup"><span data-stu-id="d078f-113">[Find the App ID for the Power App](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate.</span></span>
    
2. <span data-ttu-id="d078f-114">Nell'interfaccia di [Amministrazione](https://admin.microsoft.com)di Microsoft 365, andare a **segnalibri**.</span><span class="sxs-lookup"><span data-stu-id="d078f-114">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Bookmarks**.</span></span>
    
3. <span data-ttu-id="d078f-115">Aggiungere un segnalibro o individuare un segnalibro esistente a cui si desidera aggiungere un'applicazione di alimentazione.</span><span class="sxs-lookup"><span data-stu-id="d078f-115">Add a bookmark or find an existing bookmark that you want to add a Power App to.</span></span>
    
4. <span data-ttu-id="d078f-116">Nelle impostazioni dei segnalibri, selezionare **Power app**, quindi selezionare **Aggiungi un'applicazione di alimentazione**.</span><span class="sxs-lookup"><span data-stu-id="d078f-116">In the bookmark settings, select **Power App**, and then select **Add a Power App**.</span></span>
    
5. <span data-ttu-id="d078f-117">Immettere o incollare l'ID dell’app.</span><span class="sxs-lookup"><span data-stu-id="d078f-117">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="d078f-118">L'altezza e la larghezza vengono aggiunte automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d078f-118">The height and width are automatically added.</span></span> <span data-ttu-id="d078f-119">I segnalibri possono supportare orientamento orizzontale e verticale, ma attualmente non è possibile modificare le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="d078f-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="d078f-120">L'anteprima del segnalibro illustra la modalità di visualizzazione dell'app Power nel risultato del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="d078f-120">The bookmark preview shows how the Power App will appear in the bookmark result.</span></span>
    
    <span data-ttu-id="d078f-121">L'app Power nell'anteprima è completamente funzionante per semplificare la verifica e l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="d078f-121">The Power App in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="d078f-122">Selezionare **pubblica**.</span><span class="sxs-lookup"><span data-stu-id="d078f-122">Select **Publish**.</span></span>
    
<span data-ttu-id="d078f-123">Quando un utente di Microsoft Search autorizzato esegue una ricerca su [Bing](https://Bing.com) per qualsiasi parola chiave o parola chiave riservata del segnalibro, il Power app verrà visualizzato nel risultato del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="d078f-123">When an authorized Microsoft Search user searches on [Bing](https://Bing.com) for any of the bookmark's keywords or reserved keywords, the Power App will appear in the bookmark result.</span></span>
