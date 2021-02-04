---
title: Connettore Graph per la condivisione file per Microsoft Search
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
ROBOTS: NoIndex
description: Configurare il connettore di Graph per la condivisione file per Microsoft Search
ms.openlocfilehash: e8a68a1c6b9c2c8a8592fb915fe9bf846a758e77
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097422"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="3cca2-103">Connettore Grafico condivisione file</span><span class="sxs-lookup"><span data-stu-id="3cca2-103">File share Graph connector</span></span>

<span data-ttu-id="3cca2-104">Il connettore Grafico condivisione file consente agli utenti dell'organizzazione di eseguire ricerche nelle condivisioni file di Windows locali.</span><span class="sxs-lookup"><span data-stu-id="3cca2-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="3cca2-105">Leggere [**l'articolo setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup process.</span><span class="sxs-lookup"><span data-stu-id="3cca2-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="3cca2-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3cca2-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="3cca2-107">Installare l'agente connettore Graph</span><span class="sxs-lookup"><span data-stu-id="3cca2-107">Install the Graph connector agent</span></span>

<span data-ttu-id="3cca2-108">Per indicizzare le condivisioni file di Windows, è necessario installare e registrare l'agente connettore Graph.</span><span class="sxs-lookup"><span data-stu-id="3cca2-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="3cca2-109">Per ulteriori informazioni, vedere Install [the Graph connector agent.](on-prem-agent.md)</span><span class="sxs-lookup"><span data-stu-id="3cca2-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="3cca2-110">Requisiti per il contenuto</span><span class="sxs-lookup"><span data-stu-id="3cca2-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="3cca2-111">Tipi di file</span><span class="sxs-lookup"><span data-stu-id="3cca2-111">File types</span></span>

<span data-ttu-id="3cca2-112">È possibile indicizzare e cercare il contenuto dei formati seguenti: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS e ZIP.</span><span class="sxs-lookup"><span data-stu-id="3cca2-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="3cca2-113">Viene indicizzato solo il contenuto testuale di questi formati.</span><span class="sxs-lookup"><span data-stu-id="3cca2-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="3cca2-114">Tutto il contenuto multimediale viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="3cca2-114">All multimedia content is ignored.</span></span> <span data-ttu-id="3cca2-115">Per qualsiasi file che non appartiene a questo formato, i metadati vengono indicizzati.</span><span class="sxs-lookup"><span data-stu-id="3cca2-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="3cca2-116">Limiti di dimensione dei file</span><span class="sxs-lookup"><span data-stu-id="3cca2-116">File size limits</span></span>

<span data-ttu-id="3cca2-117">La dimensione massima supportata per i file è 100 MB.</span><span class="sxs-lookup"><span data-stu-id="3cca2-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="3cca2-118">I file che superano i 100 MB non vengono indicizzati.</span><span class="sxs-lookup"><span data-stu-id="3cca2-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="3cca2-119">Il limite massimo per le dimensioni post-elaborazione è 4 MB.</span><span class="sxs-lookup"><span data-stu-id="3cca2-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="3cca2-120">L'elaborazione viene interrotta quando le dimensioni di un file raggiungono i 4 MB.</span><span class="sxs-lookup"><span data-stu-id="3cca2-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="3cca2-121">È pertanto possibile che alcune frasi presenti nel file non funzionino per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="3cca2-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="3cca2-122">Passaggio 1: Aggiungere un connettore Graph nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cca2-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="3cca2-123">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="3cca2-123">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="3cca2-124">Passaggio 2: Assegnare un nome alla connessione</span><span class="sxs-lookup"><span data-stu-id="3cca2-124">Step 2: Name the connection</span></span>

<span data-ttu-id="3cca2-125">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="3cca2-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="3cca2-126">Passaggio 3: Configurare le impostazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="3cca2-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="3cca2-127">Nella pagina **Connetti all'origine dati** selezionare **Condivisione file** e specificare il nome, l'ID di connessione e la descrizione.</span><span class="sxs-lookup"><span data-stu-id="3cca2-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="3cca2-128">Nella pagina successiva, specificare il percorso della condivisione file e selezionare l'agente connettore Graph installato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3cca2-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="3cca2-129">Immettere le credenziali per un account utente [di Microsoft Windows](https://microsoft.com/windows) con accesso in lettura a tutti i file nella condivisione file.</span><span class="sxs-lookup"><span data-stu-id="3cca2-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="3cca2-130">Mantieni ora ultimo accesso</span><span class="sxs-lookup"><span data-stu-id="3cca2-130">Preserve last access time</span></span>

<span data-ttu-id="3cca2-131">Quando il connettore tenta di eseguire la ricerca per indicizzazione di un file, il campo "Ora ultimo accesso" nei metadati viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="3cca2-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="3cca2-132">Se si dipende da tale campo per qualsiasi soluzione di archiviazione e backup e non si desidera aggiornarlo quando il connettore vi accede, è possibile configurare questa opzione nella pagina **Impostazioni** avanzate.</span><span class="sxs-lookup"><span data-stu-id="3cca2-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="3cca2-133">Passaggio 4: Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="3cca2-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="3cca2-134">È possibile limitare l'autorizzazione per la ricerca di qualsiasi file basato sugli elenchi di controllo di accesso condivisi o sugli elenchi di controllo di accesso NTFS (New Technology File System).</span><span class="sxs-lookup"><span data-stu-id="3cca2-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="3cca2-135">Se si desidera utilizzare gli elenchi di controllo di accesso condivisi, selezionare l'opzione appropriata nella **pagina Impostazioni** avanzate.</span><span class="sxs-lookup"><span data-stu-id="3cca2-135">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="3cca2-136">Se si desidera utilizzare gli elenchi di controllo di accesso NTFS, selezionare l'opzione appropriata nella **pagina Gestisci autorizzazioni di** ricerca.</span><span class="sxs-lookup"><span data-stu-id="3cca2-136">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="3cca2-137">Passaggio 5: Assegnare etichette di proprietà</span><span class="sxs-lookup"><span data-stu-id="3cca2-137">Step 5: Assign property labels</span></span>

<span data-ttu-id="3cca2-138">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="3cca2-138">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="3cca2-139">Passaggio 6: Gestire lo schema</span><span class="sxs-lookup"><span data-stu-id="3cca2-139">Step 6: Manage schema</span></span>

<span data-ttu-id="3cca2-140">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="3cca2-140">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="3cca2-141">Passaggio 7: Scegliere le impostazioni di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="3cca2-141">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="3cca2-142">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="3cca2-142">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="3cca2-143">Passaggio 8: esaminare la connessione</span><span class="sxs-lookup"><span data-stu-id="3cca2-143">Step 8: Review connection</span></span>

<span data-ttu-id="3cca2-144">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="3cca2-144">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
