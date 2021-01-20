---
title: Connettore MediaWiki per Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore MediaWiki per Microsoft Search
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905954"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="963b3-103">Connettore MediaWiki</span><span class="sxs-lookup"><span data-stu-id="963b3-103">MediaWiki connector</span></span>

<span data-ttu-id="963b3-104">Con il connettore MediaWiki, l'organizzazione può individuare e indicizzare i dati da un wiki creato usando il software MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="963b3-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="963b3-105">Questo connettore indicizza il contenuto specificato in Microsoft Search e supporta le ricerche per indicizzazione periodiche per mantenere l'indice aggiornato.</span><span class="sxs-lookup"><span data-stu-id="963b3-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="963b3-106">Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitorano un connettore grafico MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="963b3-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="963b3-107">Integra le istruzioni generali fornite nell'articolo [configurazione del connettore grafico](configure-connector.md) .</span><span class="sxs-lookup"><span data-stu-id="963b3-107">It supplements the general instructions provided in the [Set up your Graph connector](configure-connector.md) article.</span></span> <span data-ttu-id="963b3-108">Se non è stato ancora fatto, leggere l'articolo configurazione del connettore grafico completo per comprendere il processo di installazione generale.</span><span class="sxs-lookup"><span data-stu-id="963b3-108">If you have not already done so, read the entire Set up your Graph connector article to understand the general setup process.</span></span>

<span data-ttu-id="963b3-109">Ogni passaggio del processo di installazione è elencato di seguito insieme a una nota che indica che è necessario seguire le istruzioni generali per l'installazione o altre istruzioni che si applicano solo ai connettori del grafico MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="963b3-109">Each step in the setup process is listed below along with either a note that indicates you should follow the general setup instructions OR other instructions that apply to only MediaWiki Graph connectors.</span></span> <span data-ttu-id="963b3-110">Questo articolo include anche informazioni sulle [limitazioni](#limitations) per i connettori del grafico MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="963b3-110">This article also includes information about [Limitations](#limitations) for MediaWiki Graph connectors.</span></span> 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="963b3-111">Passaggio 1: aggiungere un connettore grafico nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="963b3-111">Step 1: Add a Graph connector in the Microsoft 365 admin center.</span></span>
<span data-ttu-id="963b3-112">Seguire le istruzioni generali per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="963b3-112">Follow the general setup instructions.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="963b3-113">Passaggio 2: denominare la connessione.</span><span class="sxs-lookup"><span data-stu-id="963b3-113">Step 2: Name the connection.</span></span>
<span data-ttu-id="963b3-114">Seguire le istruzioni generali per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="963b3-114">Follow the general setup instructions.</span></span>
 
## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="963b3-115">Passaggio 3: configurare le impostazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="963b3-115">Step 3: Configure the connection settings.</span></span>
<span data-ttu-id="963b3-116">Immettere l' **URL del wiki** e scegliere il **tipo di autenticazione** dal menu a discesa delle opzioni.</span><span class="sxs-lookup"><span data-stu-id="963b3-116">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="963b3-117">Le opzioni sono **None**, **Basic** e **OAuth 2,0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="963b3-117">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="963b3-118">Se si sceglie **Basic** come tipo di autenticazione, sarà necessario specificare il **nome utente** e la **password** per il wiki.</span><span class="sxs-lookup"><span data-stu-id="963b3-118">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="963b3-119">Se si sceglie **OAuth 2,0 AAD** come tipo di autenticazione, sarà necessario fornire l'ID della **risorsa** per l'installazione wiki.</span><span class="sxs-lookup"><span data-stu-id="963b3-119">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="963b3-120">Sarà inoltre necessario fornire l' **ID client** e il **segreto client** generati nella pagina di registrazione dell'applicazione AAD.</span><span class="sxs-lookup"><span data-stu-id="963b3-120">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span> 

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="963b3-121">Passaggio 4: gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="963b3-121">Step 4: Manage search permissions</span></span>
<span data-ttu-id="963b3-122">Il connettore MediaWiki supporta solo le autorizzazioni di ricerca visibili a **tutti**.</span><span class="sxs-lookup"><span data-stu-id="963b3-122">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="963b3-123">I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="963b3-123">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="963b3-124">Passaggio 5: assegnare etichette delle proprietà</span><span class="sxs-lookup"><span data-stu-id="963b3-124">Step 5: Assign property labels</span></span>
<span data-ttu-id="963b3-125">Seguire le istruzioni generali per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="963b3-125">Follow the general setup instructions.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="963b3-126">Passaggio 6: gestire lo schema</span><span class="sxs-lookup"><span data-stu-id="963b3-126">Step 6: Manage schema</span></span>
<span data-ttu-id="963b3-127">Seguire le istruzioni generali per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="963b3-127">Follow the general setup instructions.</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="963b3-128">Passaggio 7: scegliere Aggiorna impostazioni</span><span class="sxs-lookup"><span data-stu-id="963b3-128">Step 7: Choose refresh settings</span></span>
<span data-ttu-id="963b3-129">Seguire le istruzioni generali per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="963b3-129">Follow the general setup instructions.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="963b3-130">Passaggio 8: verifica della connessione</span><span class="sxs-lookup"><span data-stu-id="963b3-130">Step 8: Review connection</span></span>
<span data-ttu-id="963b3-131">Seguire le istruzioni generali per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="963b3-131">Follow the general setup instructions.</span></span>

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="963b3-132">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="963b3-132">Limitations</span></span>
<span data-ttu-id="963b3-133">Il connettore MediaWiki ha queste limitazioni nella versione di anteprima:</span><span class="sxs-lookup"><span data-stu-id="963b3-133">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="963b3-134">Supporta solo wiki basati su cloud.</span><span class="sxs-lookup"><span data-stu-id="963b3-134">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="963b3-135">Supporta solo Basic o OAuth 2,0 con Azure Active Directory o l'autenticazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="963b3-135">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="963b3-136">Non supporta la selezione dello spazio dei nomi per l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="963b3-136">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="963b3-137">Indicizza solo gli spazi dei nomi principale, di categoria e di file.</span><span class="sxs-lookup"><span data-stu-id="963b3-137">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="963b3-138">Non supporta gli elenchi di controllo di accesso (ACL, Access Control List).</span><span class="sxs-lookup"><span data-stu-id="963b3-138">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="963b3-139">Di conseguenza, le pagine indicizzate sono visibili a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="963b3-139">Thus, indexed pages are visible to all users in the organization.</span></span>
