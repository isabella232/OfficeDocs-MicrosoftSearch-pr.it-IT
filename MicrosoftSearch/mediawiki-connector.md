---
title: Connettore MediaWiki Graph per Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore MediaWiki Graph per Microsoft Search
ms.openlocfilehash: 9d9d7a1ef9aeaba079f8cccef1ec4a4836768e8d
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084984"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a><span data-ttu-id="f7da1-103">Connettore Grafico MediaWiki</span><span class="sxs-lookup"><span data-stu-id="f7da1-103">MediaWiki Graph connector</span></span>

<span data-ttu-id="f7da1-104">Il connettore Grafico MediaWiki consente all'organizzazione di individuare e indicizzare i dati da un wiki creato utilizzando il software MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="f7da1-104">The MediaWiki Graph connector allows your organization to discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="f7da1-105">Questo connettore indicizza il contenuto specificato in Microsoft Search e supporta ricerche per indicizzazione periodiche per mantenere aggiornato l'indice.</span><span class="sxs-lookup"><span data-stu-id="f7da1-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

> [!NOTE]
> <span data-ttu-id="f7da1-106">Leggere [**l'articolo setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup process.</span><span class="sxs-lookup"><span data-stu-id="f7da1-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="f7da1-107">Questo articolo è per tutti gli utenti che configurano, eseguiti e monitorano un connettore ServiceNow Graph.</span><span class="sxs-lookup"><span data-stu-id="f7da1-107">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="f7da1-108">Integra il processo di configurazione generale e mostra le istruzioni che si applicano solo al connettore MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="f7da1-108">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span> <span data-ttu-id="f7da1-109">In questo articolo sono inoltre incluse informazioni [sulle limitazioni.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="f7da1-109">This article also includes information about [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f7da1-110">Passaggio 1: Aggiungere un connettore Graph nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f7da1-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="f7da1-111">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="f7da1-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="f7da1-112">Passaggio 2: Assegnare un nome alla connessione</span><span class="sxs-lookup"><span data-stu-id="f7da1-112">Step 2: Name the connection</span></span>

<span data-ttu-id="f7da1-113">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="f7da1-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="f7da1-114">Passaggio 3: Configurare le impostazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="f7da1-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="f7da1-115">Immetti **l'URL wiki** e scegli **il tipo di** autenticazione dal menu a discesa delle opzioni.</span><span class="sxs-lookup"><span data-stu-id="f7da1-115">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="f7da1-116">Le opzioni sono **None,** **Basic** e **OAuth 2.0 AAD.**</span><span class="sxs-lookup"><span data-stu-id="f7da1-116">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="f7da1-117">Se si sceglie **Di base** come tipo di autenticazione, sarà necessario specificare il nome **utente** e la **password** per il wiki.</span><span class="sxs-lookup"><span data-stu-id="f7da1-117">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="f7da1-118">Se si sceglie **OAuth 2.0 AAD** come tipo di autenticazione, sarà necessario fornire l'ID **risorsa** dell'installazione wiki.</span><span class="sxs-lookup"><span data-stu-id="f7da1-118">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="f7da1-119">Dovrai anche fornire **l'ID client** e il **segreto client** generati nella pagina di registrazione dell'applicazione AAD.</span><span class="sxs-lookup"><span data-stu-id="f7da1-119">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="f7da1-120">Passaggio 4: Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="f7da1-120">Step 4: Manage search permissions</span></span>

<span data-ttu-id="f7da1-121">Il connettore MediaWiki supporta solo le autorizzazioni di ricerca visibili a **Tutti.**</span><span class="sxs-lookup"><span data-stu-id="f7da1-121">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="f7da1-122">I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f7da1-122">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="f7da1-123">Passaggio 5: Assegnare etichette di proprietà</span><span class="sxs-lookup"><span data-stu-id="f7da1-123">Step 5: Assign property labels</span></span>

<span data-ttu-id="f7da1-124">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="f7da1-124">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="f7da1-125">Passaggio 6: Gestire lo schema</span><span class="sxs-lookup"><span data-stu-id="f7da1-125">Step 6: Manage schema</span></span>

<span data-ttu-id="f7da1-126">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="f7da1-126">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="f7da1-127">Passaggio 7: Scegliere le impostazioni di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="f7da1-127">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="f7da1-128">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="f7da1-128">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="f7da1-129">Passaggio 8: esaminare la connessione</span><span class="sxs-lookup"><span data-stu-id="f7da1-129">Step 8: Review connection</span></span>

<span data-ttu-id="f7da1-130">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="f7da1-130">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="f7da1-131">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="f7da1-131">Limitations</span></span>

<span data-ttu-id="f7da1-132">Il connettore MediaWiki presenta queste limitazioni nella versione di anteprima:</span><span class="sxs-lookup"><span data-stu-id="f7da1-132">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="f7da1-133">Supporta solo wiki basati sul cloud.</span><span class="sxs-lookup"><span data-stu-id="f7da1-133">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="f7da1-134">Supporta solo Basic o OAuth 2.0 con l'autenticazione di Azure Active Directory o Azure.</span><span class="sxs-lookup"><span data-stu-id="f7da1-134">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="f7da1-135">Non supporta la selezione dello spazio dei nomi per l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="f7da1-135">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="f7da1-136">Indicizza solo gli spazi dei nomi Main, Category e File.</span><span class="sxs-lookup"><span data-stu-id="f7da1-136">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="f7da1-137">Non supporta gli elenchi di controllo di accesso (ACL).</span><span class="sxs-lookup"><span data-stu-id="f7da1-137">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="f7da1-138">Pertanto, le pagine indicizzate sono visibili a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f7da1-138">Thus, indexed pages are visible to all users in the organization.</span></span>
