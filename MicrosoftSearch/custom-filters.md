---
title: Gestire filtri personalizzati
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
description: Gestire filtri personalizzati
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790335"
---
# <a name="manage-custom-filters"></a><span data-ttu-id="791da-103">Gestire filtri personalizzati</span><span class="sxs-lookup"><span data-stu-id="791da-103">Manage custom filters</span></span>

<span data-ttu-id="791da-104">È possibile utilizzare i filtri per personalizzare l'esperienza di ricerca di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="791da-104">You can use filters to customize the Microsoft Search experience.</span></span> <span data-ttu-id="791da-105">I filtri consentono agli utenti di affinare rapidamente il set di risultati della query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="791da-105">Filters let users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="791da-106">Un filtro personalizzato può essere creato all'interno di un verticale in base a una proprietà di connessione.</span><span class="sxs-lookup"><span data-stu-id="791da-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="791da-107">Ad esempio, è possibile creare un filtro **pubblicato su** per la connessione ServiceNow all'interno di un verticale.</span><span class="sxs-lookup"><span data-stu-id="791da-107">For example, you can create a **Published On** filter for ServiceNow connection inside a vertical.</span></span>

## <a name="create-a-filter-in-an-organizational-level-vertical"></a><span data-ttu-id="791da-108">Creare un filtro in un livello di organizzazione verticale</span><span class="sxs-lookup"><span data-stu-id="791da-108">Create a filter in an organizational level vertical</span></span>

<span data-ttu-id="791da-109">Per creare un filtro in Microsoft Search, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="791da-109">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="791da-110">Nell'interfaccia di amministrazione di Microsoft 365, andare a [verticali](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="791da-110">In the Microsoft 365 admin center, go to [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
1. <span data-ttu-id="791da-111">Creare/modificare la verticale in cui si desidera creare il filtro</span><span class="sxs-lookup"><span data-stu-id="791da-111">Create/Edit the vertical in which you want to create the filter</span></span>
1. <span data-ttu-id="791da-112">Passare al passaggio ' filters ' nella procedura guidata</span><span class="sxs-lookup"><span data-stu-id="791da-112">Navigate to the 'Filters' step in the wizard</span></span>
1. <span data-ttu-id="791da-113">Fare clic su' Aggiungi filtro ' e iniziare</span><span class="sxs-lookup"><span data-stu-id="791da-113">Click on 'Add Filter' and get started</span></span>
1. <span data-ttu-id="791da-114">Dopo aver aggiunto i filtri, è possibile rivedere e salvare il verticale.</span><span class="sxs-lookup"><span data-stu-id="791da-114">After adding filters, you can review and save the vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="791da-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="791da-115">Things to consider</span></span>

1. <span data-ttu-id="791da-116">Sono disponibili ulteriori funzionalità di filtro per il contenuto della connessione.</span><span class="sxs-lookup"><span data-stu-id="791da-116">Additional filter capabilities exist on connection content.</span></span>

    - <span data-ttu-id="791da-117">È inoltre possibile creare un filtro su un alias per le proprietà dell'origine del connettore</span><span class="sxs-lookup"><span data-stu-id="791da-117">You can also create filter on an alias to connector source properties</span></span>
    - <span data-ttu-id="791da-118">Se un verticale dispone di più connessioni, è possibile creare un filtro comune tra queste connessioni.</span><span class="sxs-lookup"><span data-stu-id="791da-118">If a vertical has multiple connections, you can create a common filter across these connections.</span></span> <span data-ttu-id="791da-119">A tale scopo, è possibile creare il filtro su un alias comune che consente di alias le proprietà di origine in tutte le diverse connessioni.</span><span class="sxs-lookup"><span data-stu-id="791da-119">This can be done by creating the filter on an common alias which aliases source properties across across the different connections.</span></span> <span data-ttu-id="791da-120">Ad esempio, è possibile creare un filtro **autore** tra ServiceNow e una connessione JIRA creando alias come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="791da-120">For example you can create an **Author** filter across a ServiceNow and a Jira connection by creating aliases as follows:</span></span>

    | <span data-ttu-id="791da-121">Connessione</span><span class="sxs-lookup"><span data-stu-id="791da-121">Connection</span></span> | <span data-ttu-id="791da-122">Proprietà</span><span class="sxs-lookup"><span data-stu-id="791da-122">Property</span></span> | <span data-ttu-id="791da-123">Alias</span><span class="sxs-lookup"><span data-stu-id="791da-123">Alias</span></span> |
    | --- | --- | --- |
    | <span data-ttu-id="791da-124">Servizio ora</span><span class="sxs-lookup"><span data-stu-id="791da-124">Service Now</span></span> | <span data-ttu-id="791da-125">Proprietario</span><span class="sxs-lookup"><span data-stu-id="791da-125">Owner</span></span> | <span data-ttu-id="791da-126">Author</span><span class="sxs-lookup"><span data-stu-id="791da-126">Author</span></span> |
    | <span data-ttu-id="791da-127">JIRA</span><span class="sxs-lookup"><span data-stu-id="791da-127">Jira</span></span> | <span data-ttu-id="791da-128">Publisher</span><span class="sxs-lookup"><span data-stu-id="791da-128">Publisher</span></span> | <span data-ttu-id="791da-129">Author</span><span class="sxs-lookup"><span data-stu-id="791da-129">Author</span></span> |

1. <span data-ttu-id="791da-130">I filtri esistono nell'ambito di un verticale.</span><span class="sxs-lookup"><span data-stu-id="791da-130">Filters exist within the scope of a vertical.</span></span>

    - <span data-ttu-id="791da-131">Se un filtro viene creato in un verticale a livello organizzativo, il filtro verrebbe visualizzato solo a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="791da-131">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
    - <span data-ttu-id="791da-132">Se un filtro viene creato in un verticale a livello di sito, il filtro verrebbe visualizzato solo a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="791da-132">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="791da-133">Limitazioni note</span><span class="sxs-lookup"><span data-stu-id="791da-133">Known Limitations</span></span>

1. <span data-ttu-id="791da-134">È attualmente possibile creare filtri solo sulla stringa & proprietà gestite tipo di data.</span><span class="sxs-lookup"><span data-stu-id="791da-134">You can currently create filters only on string & date type managed properties.</span></span>
1. <span data-ttu-id="791da-135">Non è possibile creare filtri gerarchici.</span><span class="sxs-lookup"><span data-stu-id="791da-135">You cannot create hierarchical filters.</span></span>

## <a name="resources"></a><span data-ttu-id="791da-136">Risorse</span><span class="sxs-lookup"><span data-stu-id="791da-136">Resources</span></span>

[<span data-ttu-id="791da-137">Gestire le tipologie di verticali e i tipi di risultati</span><span class="sxs-lookup"><span data-stu-id="791da-137">Manage verticals and result types</span></span>](customize-search-page.md)
