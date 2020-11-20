---
title: Mapping delle identità AAD
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Passaggi su come eseguire il mapping delle identità AAD
ms.openlocfilehash: db0378e596c560edebd2ceb942e6327b47a5286b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367704"
---
# <a name="map-your-azure-ad-identities"></a><span data-ttu-id="e169d-103">Mappare le identità di Azure AD</span><span class="sxs-lookup"><span data-stu-id="e169d-103">Map your Azure AD Identities</span></span>  

<span data-ttu-id="e169d-104">In questo articolo vengono illustrati i passaggi per la mappatura delle identità di Azure AD un identificatore univoco per l'origine dati (identità non Azure AD), in modo che gli utenti nell'elenco di controllo di accesso (ACL) con identità non Azure AD siano in grado di visualizzare i risultati della ricerca dei connettori con ambito.</span><span class="sxs-lookup"><span data-stu-id="e169d-104">This article walks you through the steps of mapping your Azure AD identities to a unique identifier for your data source (non-Azure AD identity) so that people in your Access Control List (ACL) with non-Azure AD identities can see connector search results scoped to them.</span></span>

<span data-ttu-id="e169d-105">Questi passaggi sono rilevanti solo per gli amministratori della ricerca che stanno configurando un connettore [Salesforce](salesforce-connector.md) da Microsoft con le autorizzazioni di ricerca per "solo gli utenti con accesso a questa origine dati" e il tipo di identità "AAD".</span><span class="sxs-lookup"><span data-stu-id="e169d-105">These steps are only relevant to search administrators who are setting up a [Salesforce](salesforce-connector.md) connector by Microsoft with search permissions for "Only people with access to this data source" and identity type "AAD."</span></span> <span data-ttu-id="e169d-106">Nei passaggi seguenti viene illustrato come eseguire il mapping delle proprietà degli utenti di Azure AD agli **ID di Federazione** degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e169d-106">The following steps walk you through how to map your Azure AD user properties to your users' **Federation IDs**.</span></span>

>[!NOTE]
><span data-ttu-id="e169d-107">Se si sta impostando un [connettore Salesforce](salesforce-connector.md) e si selezionano **solo gli utenti con accesso a questa origine dati** e il tipo di identità **non AAD** nella schermata autorizzazioni di ricerca, fare riferimento all'articolo [Map Your non-Azure ad](map-non-aad.md) identitys per i passaggi su come eseguire il mapping delle identità di Active Directory non Azure.</span><span class="sxs-lookup"><span data-stu-id="e169d-107">If you are setting up a [Salesforce connector](salesforce-connector.md) and select **Only people with access to this data source** and identity type **non-AAD** on the search permissions screen, refer to the [Map your non-Azure AD Identities](map-non-aad.md) article for steps on how to map non-Azure AD identities.</span></span>  

## <a name="steps-for-mapping-your-azure-ad-properties"></a><span data-ttu-id="e169d-108">Passaggi per il mapping delle proprietà di Azure AD</span><span class="sxs-lookup"><span data-stu-id="e169d-108">Steps for mapping your Azure AD properties</span></span>

### <a name="1-select-azure-ad-user-properties-to-map"></a><span data-ttu-id="e169d-109">1. Selezionare le proprietà degli utenti di Azure Active Directory da mappare</span><span class="sxs-lookup"><span data-stu-id="e169d-109">1. Select Azure AD user properties to map</span></span>

<span data-ttu-id="e169d-110">È possibile selezionare le proprietà di Azure AD che è necessario mappare all'ID federativo.</span><span class="sxs-lookup"><span data-stu-id="e169d-110">You can select the Azure AD properties you need to map to the Federation ID.</span></span>

<span data-ttu-id="e169d-111">È possibile selezionare una proprietà utente di Azure AD dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="e169d-111">You can select an Azure AD user property from the dropdown.</span></span> <span data-ttu-id="e169d-112">È inoltre possibile aggiungere tutte le proprietà degli utenti di Azure AD come si desidera se queste proprietà sono necessarie per creare il mapping dell'ID federativo per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e169d-112">You can also add as many Azure AD user properties as you would like if these properties are necessary to create the Federation ID mapping for your organization.</span></span>

### <a name="2-create-formula-to-complete-mapping"></a><span data-ttu-id="e169d-113">2. creare la formula per completare il mapping</span><span class="sxs-lookup"><span data-stu-id="e169d-113">2. Create formula to complete mapping</span></span>

<span data-ttu-id="e169d-114">È possibile combinare i valori delle proprietà degli utenti di Azure AD per formare l'ID di federazione univoco.</span><span class="sxs-lookup"><span data-stu-id="e169d-114">You can combine the values of the Azure AD user properties to form the unique Federation ID.</span></span>

<span data-ttu-id="e169d-115">Nella casella formula, " {0} " corrisponde alla *prima* proprietà di Azure ad selezionata.</span><span class="sxs-lookup"><span data-stu-id="e169d-115">In the formula box, "{0}" corresponds to the *first* Azure AD property you selected.</span></span> <span data-ttu-id="e169d-116">" {1} " corrisponde alla *seconda* proprietà di Azure ad selezionata.</span><span class="sxs-lookup"><span data-stu-id="e169d-116">"{1}" corresponds to the *second* Azure AD property you selected.</span></span> <span data-ttu-id="e169d-117">" {2} " corrisponde alla *terza* proprietà di Azure ad e così via.</span><span class="sxs-lookup"><span data-stu-id="e169d-117">"{2}" corresponds to the *third* Azure AD property, and so on.</span></span>  

<span data-ttu-id="e169d-118">Di seguito sono riportati alcuni esempi di formule con gli output di espressioni regolari di esempio e gli output delle formule:</span><span class="sxs-lookup"><span data-stu-id="e169d-118">Below are some examples of formulas with sample regular expression outputs and formula outputs:</span></span>

| <span data-ttu-id="e169d-119">Formula di esempio</span><span class="sxs-lookup"><span data-stu-id="e169d-119">Sample formula</span></span>                  | <span data-ttu-id="e169d-120">Valore della proprietà {0} per un utente di esempio</span><span class="sxs-lookup"><span data-stu-id="e169d-120">Value of property {0} for a sample user</span></span>                 | <span data-ttu-id="e169d-121">Valore della proprietà {1} per un utente di esempio</span><span class="sxs-lookup"><span data-stu-id="e169d-121">Value of property {1} for a sample user</span></span>           | <span data-ttu-id="e169d-122">Output della formula</span><span class="sxs-lookup"><span data-stu-id="e169d-122">Output of formula</span></span>                  |
| :------------------- | :------------------- |:---------------|:---------------|
| <span data-ttu-id="e169d-123">{0}.{1} @contoso. com</span><span class="sxs-lookup"><span data-stu-id="e169d-123">{0}.{1}@contoso.com</span></span>  | <span data-ttu-id="e169d-124">FirstName</span><span class="sxs-lookup"><span data-stu-id="e169d-124">firstname</span></span> | <span data-ttu-id="e169d-125">LastName</span><span class="sxs-lookup"><span data-stu-id="e169d-125">lastname</span></span> |<span data-ttu-id="e169d-126">firstname.lastname@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e169d-126">firstname.lastname@contoso.com</span></span>
| <span data-ttu-id="e169d-127">{0}@domain. com</span><span class="sxs-lookup"><span data-stu-id="e169d-127">{0}@domain.com</span></span>                 | <span data-ttu-id="e169d-128">UserID</span><span class="sxs-lookup"><span data-stu-id="e169d-128">userid</span></span>                 |             |<span data-ttu-id="e169d-129">userid@domain.com</span><span class="sxs-lookup"><span data-stu-id="e169d-129">userid@domain.com</span></span>

<span data-ttu-id="e169d-130">Dopo aver fornito la formula, è possibile fare clic su **Anteprima** per visualizzare un'anteprima di 5 utenti casuali dall'origine dati con i rispettivi mapping utente applicati.</span><span class="sxs-lookup"><span data-stu-id="e169d-130">After you provide your formula, you can optionally click **Preview** to see a preview of 5 random users from your data source with their respective user mappings applied.</span></span> <span data-ttu-id="e169d-131">L'output dell'anteprima include il valore delle proprietà dell'utente di Azure AD selezionate nel passaggio 1 per gli utenti e l'output della formula finale fornita nel passaggio 2 per tale utente.</span><span class="sxs-lookup"><span data-stu-id="e169d-131">The output of the preview includes the value of the Azure AD user properties selected in step 1 for those users and the output of the final formula provided in step 2 for that user.</span></span> <span data-ttu-id="e169d-132">Indica anche se l'output della formula può essere risolto in un utente di Azure AD nel tenant tramite un'icona "riuscita" o "non riuscita".</span><span class="sxs-lookup"><span data-stu-id="e169d-132">It also indicates whether the output of the formula could be resolved to an Azure AD user in your tenant via a "Success" or "Failed" icon.</span></span>  

>[!NOTE]
><span data-ttu-id="e169d-133">È comunque possibile continuare a creare la connessione se uno o più mapping degli utenti hanno uno stato "non riuscito" dopo aver fatto clic su **Anteprima**.</span><span class="sxs-lookup"><span data-stu-id="e169d-133">You can still proceed with creating your connection if one or more user mappings have a "Failed" status after you click **Preview**.</span></span> <span data-ttu-id="e169d-134">Nell'anteprima vengono visualizzati 5 utenti casuali e i relativi mapping dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e169d-134">The preview shows 5 random users and their mappings from your data source.</span></span> <span data-ttu-id="e169d-135">Se il mapping specificato non esegue il mapping di tutti gli utenti, è possibile che si verifichi questo caso.</span><span class="sxs-lookup"><span data-stu-id="e169d-135">If the mapping you provide does not map all users, you may experience this case.</span></span>

## <a name="sample-azure-ad-mapping"></a><span data-ttu-id="e169d-136">Mapping di Azure AD di esempio</span><span class="sxs-lookup"><span data-stu-id="e169d-136">Sample Azure AD mapping</span></span>

<span data-ttu-id="e169d-137">Vedere lo snapshot seguente per un esempio di mapping di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e169d-137">See the snapshot below for a sample Azure AD mapping.</span></span>

![Snapshot di esempio su come compilare la pagina di mapping di Azure AD](media/aad-mapping.png)

## <a name="limitations"></a><span data-ttu-id="e169d-139">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="e169d-139">Limitations</span></span>  

- <span data-ttu-id="e169d-140">Solo un mapping è supportato per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e169d-140">Only one mapping is supported for all users.</span></span> <span data-ttu-id="e169d-141">I mapping condizionali non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="e169d-141">Conditional mappings are not supported.</span></span>  

- <span data-ttu-id="e169d-142">Non è possibile modificare il mapping dopo la pubblicazione della connessione.</span><span class="sxs-lookup"><span data-stu-id="e169d-142">You cannot change your mapping once the connection is published.</span></span>  

- <span data-ttu-id="e169d-143">Le espressioni basate su Regex rispetto alle proprietà degli utenti di Azure AD non sono supportate per la trasformazione dell'ID di Federazione di Azure ad.</span><span class="sxs-lookup"><span data-stu-id="e169d-143">Regex-based expressions against the Azure AD user properties are not supported for the Azure AD to Federation ID transformation.</span></span>