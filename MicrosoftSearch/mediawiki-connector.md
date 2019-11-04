---
title: Connettore MediaWiki per Microsoft Search
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore MediaWiki per Microsoft Search
ms.openlocfilehash: 281d270a47051e20cb1cfd44540bd51371557c13
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949889"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="94645-103">Connettore MediaWiki</span><span class="sxs-lookup"><span data-stu-id="94645-103">MediaWiki connector</span></span>

<span data-ttu-id="94645-104">Con il connettore MediaWiki, l'organizzazione può individuare e indicizzare i dati da un wiki creato usando il software MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="94645-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="94645-105">Questo connettore indicizza il contenuto specificato in Microsoft Search e supporta le ricerche per indicizzazione periodiche per mantenere l'indice aggiornato.</span><span class="sxs-lookup"><span data-stu-id="94645-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="94645-106">Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitorano un connettore MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="94645-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="94645-107">In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="94645-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="94645-108">Connettersi a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="94645-108">Connect to a data source</span></span>
<span data-ttu-id="94645-109">Immettere l'URL MediaWiki e le credenziali per l'autenticazione della connessione.</span><span class="sxs-lookup"><span data-stu-id="94645-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="94645-110">Sono necessarie le informazioni seguenti: **ID tenant**, ID **risorsa**, **ID client**e **segreto client**.</span><span class="sxs-lookup"><span data-stu-id="94645-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-the-search-schema"></a><span data-ttu-id="94645-111">Gestire lo schema di ricerca</span><span class="sxs-lookup"><span data-stu-id="94645-111">Manage the search schema</span></span>
<span data-ttu-id="94645-112">Dopo la connessione completata, configurare il mapping dello schema di ricerca.</span><span class="sxs-lookup"><span data-stu-id="94645-112">After successful connection, configure the search schema mapping.</span></span> <span data-ttu-id="94645-113">È possibile scegliere quali proprietà rendere **querybili** **, reperibili e** **recuperabili**.</span><span class="sxs-lookup"><span data-stu-id="94645-113">You can choose which properties to make **queryable**, **searchable**, and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="94645-114">Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="94645-114">Manage search permissions</span></span>
<span data-ttu-id="94645-115">Il connettore MediaWiki supporta solo le autorizzazioni di ricerca visibili a **tutti**.</span><span class="sxs-lookup"><span data-stu-id="94645-115">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="94645-116">I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94645-116">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="94645-117">Impostare la pianificazione di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="94645-117">Set the refresh schedule</span></span> 
<span data-ttu-id="94645-118">Questa pianificazione consente di aggiornare i dati indicizzati, in modo che le modifiche apportate al wiki siano riflesse in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="94645-118">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="94645-119">Tutte le nuove pagine, le pagine eliminate, il contenuto della pagina o le modifiche dei metadati vengono visualizzati nei risultati della ricerca dopo l'intervallo di aggiornamento specificato.</span><span class="sxs-lookup"><span data-stu-id="94645-119">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="94645-120">Il tempo di ricerca per indicizzazione dipende dalle dimensioni del wiki.</span><span class="sxs-lookup"><span data-stu-id="94645-120">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="94645-121">Attualmente il connettore esegue la ricerca per indicizzazione a circa 50 pagine al minuto.</span><span class="sxs-lookup"><span data-stu-id="94645-121">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="94645-122">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="94645-122">Limitations</span></span> 
<span data-ttu-id="94645-123">Il connettore MediaWiki ha queste limitazioni nella versione di anteprima:</span><span class="sxs-lookup"><span data-stu-id="94645-123">The MediaWiki connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="94645-124">Supporta solo wiki basati su cloud.</span><span class="sxs-lookup"><span data-stu-id="94645-124">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="94645-125">Supporta solo Basic o OAuth 2,0 con Azure Active Directory o l'autenticazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="94645-125">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="94645-126">Non supporta la selezione dello spazio dei nomi per l'indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="94645-126">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="94645-127">Indicizza solo gli spazi dei nomi **principale**, di **categoria**e di **file** .</span><span class="sxs-lookup"><span data-stu-id="94645-127">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="94645-128">Non supporta gli elenchi di controllo di accesso (ACL, Access Control List).</span><span class="sxs-lookup"><span data-stu-id="94645-128">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="94645-129">Di conseguenza, le pagine indicizzate sono visibili a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="94645-129">Thus, indexed pages are visible to all users in the organization.</span></span>
