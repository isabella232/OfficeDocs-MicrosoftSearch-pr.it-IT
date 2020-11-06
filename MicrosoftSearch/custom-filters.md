---
title: Gestione di filtri personalizzati
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gestione di filtri personalizzati
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927383"
---
# <a name="create-custom-filters"></a><span data-ttu-id="5331f-103">Creare filtri personalizzati</span><span class="sxs-lookup"><span data-stu-id="5331f-103">Create custom Filters</span></span>

<span data-ttu-id="5331f-104">È possibile creare filtri per personalizzare l'esperienza di ricerca che gli utenti visualizzano quando eseguono la ricerca in Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com)e Microsoft Search in [Bing](https://bing.com).</span><span class="sxs-lookup"><span data-stu-id="5331f-104">You can create filters to customize the search experience that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="5331f-105">I filtri consentono agli utenti di affinare rapidamente il set di risultati della query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5331f-105">Filters lets users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="5331f-106">Un filtro personalizzato può essere creato all'interno di un verticale in base a una proprietà di connessione.</span><span class="sxs-lookup"><span data-stu-id="5331f-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="5331f-107">Ad esempio, è possibile creare un filtro **pubblicato su** per la connessione ServiceNow all'interno di un verticale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5331f-107">For example, you can create a **Published On** filter for ServiceNow connection inside a custom vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="5331f-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5331f-108">Things to consider</span></span>

1. <span data-ttu-id="5331f-109">Per la creazione di un filtro personalizzato sull'origine di contenuto della connessione, vengono fornite alcune funzionalità aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="5331f-109">For creating custom filter on connection content source, some additional capabilities are provided:</span></span>
- <span data-ttu-id="5331f-110">È inoltre possibile creare un filtro su un alias per le proprietà dell'origine del connettore</span><span class="sxs-lookup"><span data-stu-id="5331f-110">You can also create filter on an alias to connector source properties</span></span>
- <span data-ttu-id="5331f-111">Nel caso in cui la verticale disponga di più connessioni, è possibile creare un filtro comune tra queste connessioni.</span><span class="sxs-lookup"><span data-stu-id="5331f-111">In case your vertical has multiple connections then you can create a common filter across these connections.</span></span> <span data-ttu-id="5331f-112">A tale scopo, è possibile creare il filtro su un alias comune che consente di alias le proprietà di origine tra diverse connessioni.</span><span class="sxs-lookup"><span data-stu-id="5331f-112">This can be done by creating the filter on an common alias which aliases source properties across across different connections.</span></span> <span data-ttu-id="5331f-113">Ad esempio, è possibile creare un filtro **autore** in una ServiceNow & una connessione JIRA creando alias come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5331f-113">For example you can create an **Author** filter across a ServiceNow & a Jira connection by creating aliases as follows:</span></span>

| <span data-ttu-id="5331f-114">Connessione</span><span class="sxs-lookup"><span data-stu-id="5331f-114">Connection</span></span> | <span data-ttu-id="5331f-115">Proprietà</span><span class="sxs-lookup"><span data-stu-id="5331f-115">Property</span></span> | <span data-ttu-id="5331f-116">Alias</span><span class="sxs-lookup"><span data-stu-id="5331f-116">Alias</span></span> |
| --- | --- | --- |
| <span data-ttu-id="5331f-117">Servizio ora</span><span class="sxs-lookup"><span data-stu-id="5331f-117">Service Now</span></span> | <span data-ttu-id="5331f-118">Proprietario</span><span class="sxs-lookup"><span data-stu-id="5331f-118">Owner</span></span> | <span data-ttu-id="5331f-119">Author</span><span class="sxs-lookup"><span data-stu-id="5331f-119">Author</span></span> |
| <span data-ttu-id="5331f-120">JIRA</span><span class="sxs-lookup"><span data-stu-id="5331f-120">Jira</span></span> | <span data-ttu-id="5331f-121">Publisher</span><span class="sxs-lookup"><span data-stu-id="5331f-121">Publisher</span></span> | <span data-ttu-id="5331f-122">Author</span><span class="sxs-lookup"><span data-stu-id="5331f-122">Author</span></span> |

2. <span data-ttu-id="5331f-123">I filtri sono presenti nell'ambito della verticale.</span><span class="sxs-lookup"><span data-stu-id="5331f-123">Filters exist within the scope of the vertical.</span></span> <span data-ttu-id="5331f-124">Quindi</span><span class="sxs-lookup"><span data-stu-id="5331f-124">Hence,</span></span>  
- <span data-ttu-id="5331f-125">Se un filtro viene creato in un verticale a livello organizzativo, il filtro verrebbe visualizzato solo a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5331f-125">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
- <span data-ttu-id="5331f-126">Se un filtro viene creato in un verticale a livello di sito, il filtro verrebbe visualizzato solo a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="5331f-126">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="steps-to-create-custom-filter"></a><span data-ttu-id="5331f-127">Procedura per la creazione di un filtro personalizzato</span><span class="sxs-lookup"><span data-stu-id="5331f-127">Steps to Create custom filter</span></span>

### <a name="create-filter-in-organizational-level-vertical"></a><span data-ttu-id="5331f-128">Creare un filtro in verticale a livello organizzativo:</span><span class="sxs-lookup"><span data-stu-id="5331f-128">Create filter in organizational level vertical:</span></span>

<span data-ttu-id="5331f-129">Per creare un filtro in Microsoft Search, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="5331f-129">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="5331f-130">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina [verticali](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) .</span><span class="sxs-lookup"><span data-stu-id="5331f-130">In the Microsoft 365 admin center, go to the [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) page.</span></span>
2. <span data-ttu-id="5331f-131">Creare/modificare la verticale in cui si desidera creare il filtro</span><span class="sxs-lookup"><span data-stu-id="5331f-131">Create/Edit the vertical in which you want to create the filter</span></span>
3. <span data-ttu-id="5331f-132">Passare al passaggio ' filters ' nella procedura guidata</span><span class="sxs-lookup"><span data-stu-id="5331f-132">Navigate to the 'Filters' step in the wizard</span></span>
4. <span data-ttu-id="5331f-133">Fare clic su' Aggiungi filtro ' e iniziare dopo l'aggiunta dei filtri, è possibile rivedere e salvare la verticale.</span><span class="sxs-lookup"><span data-stu-id="5331f-133">Click on 'Add Filter' and get started After adding filters, you can review and save the vertical.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5331f-134">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="5331f-134">Known Limitations</span></span>

1. <span data-ttu-id="5331f-135">È attualmente possibile creare filtri solo sulla stringa & proprietà gestite tipo di data.</span><span class="sxs-lookup"><span data-stu-id="5331f-135">You can currently create filters only on String & Date type managed properties.</span></span>
2. <span data-ttu-id="5331f-136">Non è possibile creare filtri gerarchici</span><span class="sxs-lookup"><span data-stu-id="5331f-136">You cannot create hierarchical filters</span></span>

## <a name="resources"></a><span data-ttu-id="5331f-137">Risorse</span><span class="sxs-lookup"><span data-stu-id="5331f-137">Resources</span></span>

[<span data-ttu-id="5331f-138">Personalizzare la pagina dei risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="5331f-138">Customize search result page</span></span>](customize-search-page.md)