---
title: Connettore condivisione file
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore di condivisione file per Microsoft Search
ms.openlocfilehash: c11c407016315e638205adddddd17d90bbe6b33d
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367739"
---
# <a name="file-share-connector"></a><span data-ttu-id="ec479-103">Connettore condivisione file</span><span class="sxs-lookup"><span data-stu-id="ec479-103">File share connector</span></span>

<span data-ttu-id="ec479-104">Con il connettore grafico condivisione file, gli utenti dell'organizzazione possono eseguire ricerche in condivisioni file di Windows locali.</span><span class="sxs-lookup"><span data-stu-id="ec479-104">With the File share Graph connector, users in your organization can search on-premise Windows file shares.</span></span>

<span data-ttu-id="ec479-105">Questo articolo è per gli amministratori di Microsoft 365 o per tutti gli utenti che configurano, eseguono e monitora un connettore di condivisione file.</span><span class="sxs-lookup"><span data-stu-id="ec479-105">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a file share connector.</span></span> <span data-ttu-id="ec479-106">In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="ec479-106">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-graph-connector-agent"></a><span data-ttu-id="ec479-107">Installare l'agente del connettore grafico</span><span class="sxs-lookup"><span data-stu-id="ec479-107">Install Graph connector agent</span></span>

<span data-ttu-id="ec479-108">Per indicizzare le condivisioni di file di Windows, è necessario installare e registrare il software dell' [agente del connettore grafico](on-prem-agent.md) .</span><span class="sxs-lookup"><span data-stu-id="ec479-108">In order to index your Windows file shares, you must install and register [Graph connector agent](on-prem-agent.md) software.</span></span>

## <a name="content-requirements"></a><span data-ttu-id="ec479-109">Requisiti per il contenuto</span><span class="sxs-lookup"><span data-stu-id="ec479-109">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="ec479-110">Tipi di file</span><span class="sxs-lookup"><span data-stu-id="ec479-110">File types</span></span>

<span data-ttu-id="ec479-111">È possibile indicizzare e cercare il contenuto dei formati seguenti: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, xlb, xlc, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS e ZIP.</span><span class="sxs-lookup"><span data-stu-id="ec479-111">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="ec479-112">Solo il contenuto testuale di questi formati è indicizzato.</span><span class="sxs-lookup"><span data-stu-id="ec479-112">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="ec479-113">Tutto il contenuto multimediale viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="ec479-113">All multimedia content is ignored.</span></span> <span data-ttu-id="ec479-114">Per tutti i file che non appartengono a questo formato, solo i metadati vengono indicizzati.</span><span class="sxs-lookup"><span data-stu-id="ec479-114">For any file that does not belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="ec479-115">Limiti di dimensione dei file</span><span class="sxs-lookup"><span data-stu-id="ec479-115">File size limits</span></span>

<span data-ttu-id="ec479-116">La dimensione massima del file supportato è 100 MB.</span><span class="sxs-lookup"><span data-stu-id="ec479-116">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="ec479-117">I file che superano i 100 MB non vengono indicizzati.</span><span class="sxs-lookup"><span data-stu-id="ec479-117">Files that exceed 100 MB are not indexed.</span></span> <span data-ttu-id="ec479-118">Il limite massimo di dimensioni successive all'elaborazione è pari a 4 MB.</span><span class="sxs-lookup"><span data-stu-id="ec479-118">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="ec479-119">L'elaborazione si interrompe quando la dimensione di un file raggiunge i 4 MB.</span><span class="sxs-lookup"><span data-stu-id="ec479-119">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="ec479-120">Pertanto, alcune frasi presenti nel file potrebbero non funzionare per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec479-120">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="ec479-121">Connettersi a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="ec479-121">Connect to a data source</span></span>

<span data-ttu-id="ec479-122">Nella pagina **Connetti a origine dati** selezionare **condivisione file** e specificare il nome, l'ID di connessione e la descrizione.</span><span class="sxs-lookup"><span data-stu-id="ec479-122">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="ec479-123">Nella pagina successiva, specificare il percorso della condivisione file e selezionare l'agente del connettore grafico precedentemente installato.</span><span class="sxs-lookup"><span data-stu-id="ec479-123">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="ec479-124">Immettere le credenziali per un account utente di [Microsoft Windows](https://microsoft.com/windows) con accesso in lettura a tutti i file nella condivisione file.</span><span class="sxs-lookup"><span data-stu-id="ec479-124">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

## <a name="preserve-last-access-time"></a><span data-ttu-id="ec479-125">Mantieni l'ora dell'ultimo accesso</span><span class="sxs-lookup"><span data-stu-id="ec479-125">Preserve last access time</span></span>

<span data-ttu-id="ec479-126">Quando il connettore tenta di eseguire la ricerca per indicizzazione di un file, viene aggiornato il campo "tempo di accesso ultimo" nei metadati.</span><span class="sxs-lookup"><span data-stu-id="ec479-126">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="ec479-127">Se si dipendono da tale campo per qualsiasi soluzione di archiviazione e backup e non si desidera aggiornarlo quando il connettore lo accede, è possibile configurare questa opzione nella pagina **Impostazioni avanzate** .</span><span class="sxs-lookup"><span data-stu-id="ec479-127">If you depend on that field for any archiving and backup solutions and do not want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="ec479-128">Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="ec479-128">Manage search permissions</span></span>

<span data-ttu-id="ec479-129">È possibile limitare le autorizzazioni per la ricerca di qualsiasi file in base agli elenchi di controllo di accesso condiviso o ai nuovi accessi di controllo di accesso NTFS.</span><span class="sxs-lookup"><span data-stu-id="ec479-129">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="ec479-130">Se si desidera utilizzare gli elenchi di controllo di accesso di condivisione, selezionare l'opzione appropriata nella pagina **Impostazioni avanzate** .</span><span class="sxs-lookup"><span data-stu-id="ec479-130">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="ec479-131">Se si desidera utilizzare gli elenchi di controllo di accesso NTFS, selezionare l'opzione appropriata nella pagina **Gestisci autorizzazioni di ricerca** .</span><span class="sxs-lookup"><span data-stu-id="ec479-131">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="ec479-132">Assegnare etichette delle proprietà</span><span class="sxs-lookup"><span data-stu-id="ec479-132">Assign property labels</span></span>

<span data-ttu-id="ec479-133">È possibile assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni.</span><span class="sxs-lookup"><span data-stu-id="ec479-133">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="ec479-134">Anche se questo passaggio non è obbligatorio, l'utilizzo di alcune etichette di proprietà migliorerà la pertinenza della ricerca e assicurerà risultati di ricerca più accurati per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="ec479-134">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="ec479-135">Gestione dello schema</span><span class="sxs-lookup"><span data-stu-id="ec479-135">Manage schema</span></span>

<span data-ttu-id="ec479-136">Nella schermata **Gestisci schema** è possibile modificare gli attributi dello schema (**Queryable**, **Searchable**, **Retrievable** e **per affinamento ricerca**) associati alle proprietà, aggiungere alias facoltativi e scegliere la proprietà **Content** .</span><span class="sxs-lookup"><span data-stu-id="ec479-136">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="ec479-137">Impostare la pianificazione di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ec479-137">Set the refresh schedule</span></span>

<span data-ttu-id="ec479-138">L'intervallo di pianificazione di aggiornamento predefinito consigliato è 15 minuti, ma è possibile modificarlo in base alle preferenze.</span><span class="sxs-lookup"><span data-stu-id="ec479-138">The recommended default refresh schedule interval is 15 minutes, but you can change it based on your preferences.</span></span>
