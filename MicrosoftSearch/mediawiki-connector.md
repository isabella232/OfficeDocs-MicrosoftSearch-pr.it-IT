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
ms.openlocfilehash: 7f6b34dcafc4b82ab3778ec1d7a4921383e44a44
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367641"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="61fd8-103">Connettore MediaWiki</span><span class="sxs-lookup"><span data-stu-id="61fd8-103">MediaWiki connector</span></span>

<span data-ttu-id="61fd8-104">Con il connettore MediaWiki, l'organizzazione può individuare e indicizzare i dati da un wiki creato usando il software MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="61fd8-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="61fd8-105">Questo connettore indicizza il contenuto specificato in Microsoft Search e supporta le ricerche per indicizzazione periodiche per mantenere l'indice aggiornato.</span><span class="sxs-lookup"><span data-stu-id="61fd8-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="61fd8-106">Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitorano un connettore MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="61fd8-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="61fd8-107">In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="61fd8-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="61fd8-108">Connettersi a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="61fd8-108">Connect to a data source</span></span>

<span data-ttu-id="61fd8-109">Immettere l'URL MediaWiki e le credenziali per l'autenticazione della connessione.</span><span class="sxs-lookup"><span data-stu-id="61fd8-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="61fd8-110">Sono necessarie le informazioni seguenti: **ID tenant**, ID **risorsa**, **ID client** e **segreto client**.</span><span class="sxs-lookup"><span data-stu-id="61fd8-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="61fd8-111">Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="61fd8-111">Manage search permissions</span></span>

<span data-ttu-id="61fd8-112">Il connettore MediaWiki supporta solo le autorizzazioni di ricerca visibili a **tutti**.</span><span class="sxs-lookup"><span data-stu-id="61fd8-112">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="61fd8-113">I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="61fd8-113">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="61fd8-114">Assegnare etichette delle proprietà</span><span class="sxs-lookup"><span data-stu-id="61fd8-114">Assign property labels</span></span>

<span data-ttu-id="61fd8-115">È possibile assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni.</span><span class="sxs-lookup"><span data-stu-id="61fd8-115">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="61fd8-116">Anche se questo passaggio non è obbligatorio, l'utilizzo di alcune etichette di proprietà migliorerà la pertinenza della ricerca e assicurerà risultati di ricerca più accurati per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="61fd8-116">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="61fd8-117">Gestione dello schema</span><span class="sxs-lookup"><span data-stu-id="61fd8-117">Manage schema</span></span>

<span data-ttu-id="61fd8-118">Nella schermata **Gestisci schema** è possibile modificare gli attributi dello schema (**Queryable**, **Searchable**, **Retrievable** e **per affinamento ricerca**) associati alle proprietà, aggiungere alias facoltativi e scegliere la proprietà **Content** .</span><span class="sxs-lookup"><span data-stu-id="61fd8-118">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="61fd8-119">Impostare la pianificazione di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="61fd8-119">Set the refresh schedule</span></span>

<span data-ttu-id="61fd8-120">Questa pianificazione consente di aggiornare i dati indicizzati, in modo che le modifiche apportate al wiki siano riflesse in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="61fd8-120">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="61fd8-121">Tutte le nuove pagine, le pagine eliminate, il contenuto della pagina o le modifiche dei metadati vengono visualizzati nei risultati della ricerca dopo l'intervallo di aggiornamento specificato.</span><span class="sxs-lookup"><span data-stu-id="61fd8-121">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="61fd8-122">Il tempo di ricerca per indicizzazione dipende dalle dimensioni del wiki.</span><span class="sxs-lookup"><span data-stu-id="61fd8-122">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="61fd8-123">Attualmente il connettore esegue la ricerca per indicizzazione a circa 50 pagine al minuto.</span><span class="sxs-lookup"><span data-stu-id="61fd8-123">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="61fd8-124">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="61fd8-124">Limitations</span></span>

<span data-ttu-id="61fd8-125">Il connettore MediaWiki ha queste limitazioni nella versione di anteprima:</span><span class="sxs-lookup"><span data-stu-id="61fd8-125">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="61fd8-126">Supporta solo wiki basati su cloud.</span><span class="sxs-lookup"><span data-stu-id="61fd8-126">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="61fd8-127">Supporta solo Basic o OAuth 2,0 con Azure Active Directory o l'autenticazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="61fd8-127">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="61fd8-128">Non supporta la selezione dello spazio dei nomi per l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="61fd8-128">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="61fd8-129">Indicizza solo gli spazi dei nomi **principale**, di **categoria** e di **file** .</span><span class="sxs-lookup"><span data-stu-id="61fd8-129">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="61fd8-130">Non supporta gli elenchi di controllo di accesso (ACL, Access Control List).</span><span class="sxs-lookup"><span data-stu-id="61fd8-130">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="61fd8-131">Di conseguenza, le pagine indicizzate sono visibili a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="61fd8-131">Thus, indexed pages are visible to all users in the organization.</span></span>
