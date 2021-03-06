---
title: Connettore Graph per la condivisione file per Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurare il connettore Grafico condivisione file per Microsoft Search
ms.openlocfilehash: cd3f28356e41d24182e2da712d476ce2223b39b2
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508788"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="ebd69-103">Connettore Grafico condivisione file</span><span class="sxs-lookup"><span data-stu-id="ebd69-103">File share Graph connector</span></span>

<span data-ttu-id="ebd69-104">Il connettore Grafico condivisione file consente agli utenti dell'organizzazione di cercare condivisioni file di Windows locali.</span><span class="sxs-lookup"><span data-stu-id="ebd69-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="ebd69-105">Leggere [**l'articolo setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup process.</span><span class="sxs-lookup"><span data-stu-id="ebd69-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="ebd69-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ebd69-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="ebd69-107">Installare l'agente connettore Graph</span><span class="sxs-lookup"><span data-stu-id="ebd69-107">Install the Graph connector agent</span></span>

<span data-ttu-id="ebd69-108">Per indicizzare le condivisioni file di Windows, è necessario installare e registrare l'agente connettore Graph.</span><span class="sxs-lookup"><span data-stu-id="ebd69-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="ebd69-109">Per [ulteriori informazioni, vedere Install the Graph connector agent.](on-prem-agent.md)</span><span class="sxs-lookup"><span data-stu-id="ebd69-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="ebd69-110">Requisiti per il contenuto</span><span class="sxs-lookup"><span data-stu-id="ebd69-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="ebd69-111">Tipi di file</span><span class="sxs-lookup"><span data-stu-id="ebd69-111">File types</span></span>

<span data-ttu-id="ebd69-112">È possibile indicizzare e cercare il contenuto dei formati seguenti: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS e ZIP.</span><span class="sxs-lookup"><span data-stu-id="ebd69-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="ebd69-113">Viene indicizzato solo il contenuto testuale di questi formati.</span><span class="sxs-lookup"><span data-stu-id="ebd69-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="ebd69-114">Tutto il contenuto multimediale viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="ebd69-114">All multimedia content is ignored.</span></span> <span data-ttu-id="ebd69-115">Per qualsiasi file che non appartiene a questo formato, solo i metadati vengono indicizzati.</span><span class="sxs-lookup"><span data-stu-id="ebd69-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="ebd69-116">Limiti di dimensione dei file</span><span class="sxs-lookup"><span data-stu-id="ebd69-116">File size limits</span></span>

<span data-ttu-id="ebd69-117">La dimensione massima supportata per i file è 100 MB.</span><span class="sxs-lookup"><span data-stu-id="ebd69-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="ebd69-118">I file che superano i 100 MB non vengono indicizzati.</span><span class="sxs-lookup"><span data-stu-id="ebd69-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="ebd69-119">Il limite massimo per le dimensioni post-elaborazione è 4 MB.</span><span class="sxs-lookup"><span data-stu-id="ebd69-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="ebd69-120">L'elaborazione viene interrotta quando le dimensioni di un file raggiungono i 4 MB.</span><span class="sxs-lookup"><span data-stu-id="ebd69-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="ebd69-121">È pertanto possibile che alcune frasi presenti nel file non funzionino per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ebd69-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ebd69-122">Passaggio 1: Aggiungere un connettore Graph nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ebd69-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="ebd69-123">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ebd69-123">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="ebd69-124">Passaggio 2: assegnare un nome alla connessione</span><span class="sxs-lookup"><span data-stu-id="ebd69-124">Step 2: Name the connection</span></span>

<span data-ttu-id="ebd69-125">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ebd69-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="ebd69-126">Passaggio 3: Configurare le impostazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="ebd69-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="ebd69-127">Nella pagina **Connetti all'origine** dati selezionare **Condivisione file** e specificare il nome, l'ID di connessione e la descrizione.</span><span class="sxs-lookup"><span data-stu-id="ebd69-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="ebd69-128">Nella pagina successiva, specificare il percorso della condivisione file e selezionare l'agente connettore Graph installato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ebd69-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="ebd69-129">Immettere le credenziali per un account utente [di Microsoft Windows](https://microsoft.com/windows) con accesso in lettura a tutti i file nella condivisione file.</span><span class="sxs-lookup"><span data-stu-id="ebd69-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="ebd69-130">Mantieni ora ultimo accesso</span><span class="sxs-lookup"><span data-stu-id="ebd69-130">Preserve last access time</span></span>

<span data-ttu-id="ebd69-131">Quando il connettore tenta di eseguire la ricerca per indicizzazione di un file, il campo "Ora ultimo accesso" nei metadati viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="ebd69-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="ebd69-132">Se si dipende da tale campo per qualsiasi soluzione di archiviazione e backup e non si desidera aggiornarlo quando il connettore vi accede, è possibile configurare questa opzione nella pagina **Impostazioni** avanzate.</span><span class="sxs-lookup"><span data-stu-id="ebd69-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="ebd69-133">Passaggio 4: Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="ebd69-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="ebd69-134">È possibile limitare l'autorizzazione per la ricerca di qualsiasi file basato sugli elenchi di controllo di accesso condivisi o sugli elenchi di controllo di accesso NTFS (New Technology File System) selezionando l'opzione desiderata nella pagina Gestisci autorizzazioni **di** ricerca.</span><span class="sxs-lookup"><span data-stu-id="ebd69-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists, by selecting the desired option in **Manage search permissions** page.</span></span> <span data-ttu-id="ebd69-135">Gli account utente e i gruppi forniti in questi elenchi di controllo di accesso devono essere gestiti da Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="ebd69-135">The user accounts and groups provided in these Access Control Lists must be managed by Active Directory (AD).</span></span> <span data-ttu-id="ebd69-136">Se si utilizza qualsiasi altro sistema per la gestione degli account utente, è possibile selezionare l'opzione "tutti", che consente agli utenti di cercare tutti i file senza restrizioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="ebd69-136">If you are using any other system for user accounts management, you can select 'everyone' option, which lets users search for all the files without any access restrictions.</span></span> <span data-ttu-id="ebd69-137">Tuttavia, quando gli utenti tentano di aprire il file, vengono applicati i controlli di accesso impostati nell'origine.</span><span class="sxs-lookup"><span data-stu-id="ebd69-137">However, when users try to open the file, access controls set at the source apply.</span></span>

<span data-ttu-id="ebd69-138">Tieni presente che le finestre per impostazione predefinita forniscono l'autorizzazione "Lettura" a "Tutti" negli elenchi ACL di condivisione quando una cartella viene condivisa in rete.</span><span class="sxs-lookup"><span data-stu-id="ebd69-138">Note that windows by default provides 'Read' permission to 'Everyone' in Share ACLs when a folder is shared on network.</span></span> <span data-ttu-id="ebd69-139">Per estensione, se si sceglie Condividi ACL in **Gestisci** autorizzazioni di ricerca, gli utenti saranno in grado di cercare tutti i file.</span><span class="sxs-lookup"><span data-stu-id="ebd69-139">By extension, if you are choosing Share ACLs in **Manage search permissions**, users will be able to search for all the files.</span></span> <span data-ttu-id="ebd69-140">Se si desidera limitare l'accesso, rimuovere l'accesso "Lettura" per "Tutti" nelle condivisioni file e fornire l'accesso solo agli utenti e ai gruppi desiderati.</span><span class="sxs-lookup"><span data-stu-id="ebd69-140">If you want to restrict access, remove 'Read' access for 'Everyone' in file shares and provide access only to the desired users and groups.</span></span> <span data-ttu-id="ebd69-141">Il connettore legge quindi queste restrizioni di accesso e le applica alla ricerca.</span><span class="sxs-lookup"><span data-stu-id="ebd69-141">The connector then reads these access restrictions and applies them to search.</span></span>

<span data-ttu-id="ebd69-142">È possibile scegliere Gli ACL di condivisione solo se il percorso di condivisione specificato segue il formato di percorso UNC.</span><span class="sxs-lookup"><span data-stu-id="ebd69-142">You can choose Share ACLs only if the share path you provided follows UNC path format.</span></span> <span data-ttu-id="ebd69-143">È possibile creare un percorso in formato UNC selezionando "Condivisione avanzata" nell'opzione "Condivisione".</span><span class="sxs-lookup"><span data-stu-id="ebd69-143">You can create a path in UNC format by going to 'Advanced Sharing' under 'Sharing' option.</span></span>

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="ebd69-145">Passaggio 5: Assegnare etichette di proprietà</span><span class="sxs-lookup"><span data-stu-id="ebd69-145">Step 5: Assign property labels</span></span>

<span data-ttu-id="ebd69-146">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ebd69-146">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="ebd69-147">Passaggio 6: Gestire lo schema</span><span class="sxs-lookup"><span data-stu-id="ebd69-147">Step 6: Manage schema</span></span>

<span data-ttu-id="ebd69-148">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ebd69-148">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="ebd69-149">Passaggio 7: Scegliere le impostazioni di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ebd69-149">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="ebd69-150">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ebd69-150">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="ebd69-151">Passaggio 8: esaminare la connessione</span><span class="sxs-lookup"><span data-stu-id="ebd69-151">Step 8: Review connection</span></span>

<span data-ttu-id="ebd69-152">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ebd69-152">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
