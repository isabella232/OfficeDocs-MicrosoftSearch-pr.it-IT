---
title: Connettore Azure Data Lake Graph per Microsoft Search
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
description: Configurare il connettore Azure Data Lake Storage Gen2 Graph per Microsoft Search
ms.openlocfilehash: da508694929d3c83a456c664aa4613b09a1b14a3
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084858"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a><span data-ttu-id="ce961-103">Connettore grafico Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="ce961-103">Azure Data Lake Storage Gen2 Graph connector</span></span>

<span data-ttu-id="ce961-104">Il connettore Azure Data Lake Storage Gen2 Graph consente agli utenti dell'organizzazione di cercare i file archiviati negli account di archiviazione BLOB di [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e azure [Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="ce961-104">The Azure Data Lake Storage Gen2 Graph connector allows users in your organization to search for files stored in [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="ce961-105">Leggere [**l'articolo configurazione del connettore Graph**](configure-connector.md) per comprendere il processo generale di configurazione dei connettori di Graph.</span><span class="sxs-lookup"><span data-stu-id="ce961-105">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="ce961-106">Questo articolo è per tutti gli utenti che configurano, eseguiti e monitorano un connettore Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="ce961-106">This article is for anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="ce961-107">Integra il processo di configurazione generale e mostra le istruzioni che si applicano solo al connettore Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="ce961-107">It supplements the general setup process, and shows instructions that apply only for the Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="ce961-108">In questo articolo sono inoltre incluse informazioni [sulle limitazioni.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="ce961-108">This article also includes information about [Limitations](#limitations).</span></span>

<span data-ttu-id="ce961-109">Nell'articolo viene utilizzato *Archiviazione di Azure* come termine generico per Archiviazione BLOB di [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e Archiviazione Azure Data Lake [Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="ce961-109">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ce961-110">Passaggio 1: Aggiungere un connettore Graph nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ce961-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="ce961-111">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ce961-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="ce961-112">Passaggio 2: Assegnare un nome alla connessione</span><span class="sxs-lookup"><span data-stu-id="ce961-112">Step 2: Name the connection</span></span>

<span data-ttu-id="ce961-113">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ce961-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="ce961-114">Passaggio 3: Configurare le impostazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="ce961-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="ce961-115">Immettere la stringa di connessione di archiviazione principale.</span><span class="sxs-lookup"><span data-stu-id="ce961-115">Enter your Primary storage connection String.</span></span> <span data-ttu-id="ce961-116">Questa stringa è necessaria per consentire l'accesso all'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ce961-116">This string is required to allow access to your storage account.</span></span> <span data-ttu-id="ce961-117">Per trovare la stringa di connessione, passare al portale [di Azure](https://ms.portal.azure.com/#home) e passare alla **sezione** Chiavi dell'account di archiviazione di Azure pertinente.</span><span class="sxs-lookup"><span data-stu-id="ce961-117">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span>

<span data-ttu-id="ce961-118">Se si preferisce non fornire **AccountKey** (un parametro nella stringa di connessione di archiviazione principale), concedere l'accesso al servizio connettori Graph per i ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce961-118">If you prefer not to provide the **AccountKey** (a parameter in the primary storage connection string), grant access to our Graph Connectors Service for the following roles:</span></span>

* <span data-ttu-id="ce961-119">Lettore dati BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="ce961-119">Storage Blob Data Reader</span></span>
* <span data-ttu-id="ce961-120">Collaboratore dati coda di archiviazione</span><span class="sxs-lookup"><span data-stu-id="ce961-120">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="ce961-121">Delegatore BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="ce961-121">Storage Blob Delegator</span></span>

<span data-ttu-id="ce961-122">Passare alla scheda **Controllo di accesso** dell'account di archiviazione di Azure e seguire le istruzioni per concedere l'accesso all'app seguente:</span><span class="sxs-lookup"><span data-stu-id="ce961-122">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="ce961-123">ID app di prima **parte:** 56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="ce961-123">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="ce961-124">**Nome app di prima parte:** Servizio connettore grafico</span><span class="sxs-lookup"><span data-stu-id="ce961-124">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="ce961-125">Notifiche sull'account di archiviazione e sulla coda (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="ce961-125">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="ce961-126">Il supporto per elaborare le modifiche in tempo reale nel servizio connettori graph potrebbe essere aggiunto in futuro.</span><span class="sxs-lookup"><span data-stu-id="ce961-126">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="ce961-127">In tal caso, verranno monitorate le notifiche di modifica di Archiviazione di Azure archiviate in una coda.</span><span class="sxs-lookup"><span data-stu-id="ce961-127">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="ce961-128">Dovrai creare una coda nello stesso account dell'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="ce961-128">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="ce961-129">Dopo aver creato una coda, passare alla scheda **Eventi** nella pagina della coda per configurare la **sottoscrizione di evento.**</span><span class="sxs-lookup"><span data-stu-id="ce961-129">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="ce961-130">Scegliere tutti gli eventi BLOB che la coda riceverà e connettere la coda all'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="ce961-130">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="ce961-131">Passaggio 4: Assegnare etichette di proprietà</span><span class="sxs-lookup"><span data-stu-id="ce961-131">Step 4: Assign property labels</span></span>

<span data-ttu-id="ce961-132">Puoi assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni.</span><span class="sxs-lookup"><span data-stu-id="ce961-132">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="ce961-133">Anche se questo passaggio non è obbligatorio, la presenza di alcune etichette di proprietà migliorerà la pertinenza della ricerca e garantirà risultati di ricerca migliori per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="ce961-133">While this step isn't mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="ce961-134">Passaggio 5: Gestire lo schema</span><span class="sxs-lookup"><span data-stu-id="ce961-134">Step 5: Manage schema</span></span>

<span data-ttu-id="ce961-135">Nella schermata **Gestisci schema** è possibile modificare gli attributi dello schema associati alle proprietà, le opzioni disponibili sono **Query,** **Ricerca,** **Recupera** e **Affinamento.**</span><span class="sxs-lookup"><span data-stu-id="ce961-135">On the **Manage Schema** screen, you can change the schema attributes associated with the properties, the options are **Query**, **Search**, **Retrieve**, and **Refine**.</span></span> <span data-ttu-id="ce961-136">È inoltre possibile aggiungere alias facoltativi e scegliere la **proprietà Content.**</span><span class="sxs-lookup"><span data-stu-id="ce961-136">You also can add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="ce961-137">Passaggio 6: Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="ce961-137">Step 6: Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="ce961-138">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="ce961-138">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="ce961-139">È possibile scegliere di inserire gli elenchi di controllo di accesso (ACL) dall'account di archiviazione [di Azure Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="ce961-139">You can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="ce961-140">Quando queste autorizzazioni di ricerca sono impostate, il contenuto della ricerca viene tagliato in base alle autorizzazioni dell'utente che ha effettuato l'accesso in [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="ce961-140">When these search permissions are set, search content is trimmed based on the permissions of the user signed in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/).</span></span> <span data-ttu-id="ce961-141">In alternativa, è possibile scegliere di rendere tutto il contenuto indicizzato dall'account di archiviazione visibile a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ce961-141">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="ce961-142">In questo caso, tutti gli utenti dell'organizzazione avranno accesso a tutti i dati nell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ce961-142">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

<span data-ttu-id="ce961-143">Il connettore Graph di Azure Data Lake Storage Gen2 supporta le autorizzazioni di ricerca visibili per **tutti** gli utenti o solo per gli utenti con **accesso a questa origine dati.**</span><span class="sxs-lookup"><span data-stu-id="ce961-143">The Azure Data Lake Storage Gen2 Graph connector supports search permissions visible to **Everyone**, or **Only people with access to this data source**.</span></span> <span data-ttu-id="ce961-144">I dati indicizzati visualizzati nei risultati della ricerca potrebbero essere visibili agli utenti dell'organizzazione che hanno accesso a ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="ce961-144">Indexed data that appears in the search results could be visible to users in the organization who have access to each item.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="ce961-145">Archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="ce961-145">Azure Blob Storage</span></span>

<span data-ttu-id="ce961-146">Per una connessione [all'archiviazione BLOB di Azure,](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)tutto il contenuto indicizzato dall'origine configurata è visibile a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ce961-146">For a connection to [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="ce961-147">Gli elenchi di controllo di accesso non sono supportati a livello di BLOB in Archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="ce961-147">Access control lists aren't supported at Blob level in Azure Blob Storage.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="ce961-148">Passaggio 7: Impostare la pianificazione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ce961-148">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="ce961-149">Nella schermata **Impostazioni aggiornamento è** possibile impostare l'intervallo di ricerca per indicizzazione incrementale e l'intervallo di ricerca per indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="ce961-149">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="ce961-150">Gli intervalli predefiniti per il connettore Azure Data Lake Storage Gen2 sono di 15 minuti per una ricerca per indicizzazione incrementale e di una settimana per una ricerca per indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="ce961-150">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="ce961-151">Passaggio 8: esaminare la connessione</span><span class="sxs-lookup"><span data-stu-id="ce961-151">Step 8: Review connection</span></span>

<span data-ttu-id="ce961-152">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ce961-152">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="ce961-153">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="ce961-153">Limitations</span></span>

<span data-ttu-id="ce961-154">Una connessione pubblicata per l'archiviazione BLOB di Azure non può essere riconfigurata per l'origine di Azure Data Lake Storage Gen2 e al contrario.</span><span class="sxs-lookup"><span data-stu-id="ce961-154">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and the other way around.</span></span> <span data-ttu-id="ce961-155">In questi scenari, è consigliabile configurare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="ce961-155">In such scenarios, it's recommended to configure a new connection.</span></span>

<span data-ttu-id="ce961-156">Inoltre, le dimensioni dei file devono essere inferiori o pari a 4 MB per poter essere sottoposti a ricerca per indicizzazione.</span><span class="sxs-lookup"><span data-stu-id="ce961-156">Also, the size of the files needs to be 4 MB or less for it to be crawled.</span></span> <span data-ttu-id="ce961-157">I tipi di file attualmente supportati sono:</span><span class="sxs-lookup"><span data-stu-id="ce961-157">File types currently supported are:</span></span>

* <span data-ttu-id="ce961-158">Word (docx, docm, dotx, dotm)</span><span class="sxs-lookup"><span data-stu-id="ce961-158">Word (docx, .docm, .dotx, .dotm)</span></span>
* <span data-ttu-id="ce961-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span><span class="sxs-lookup"><span data-stu-id="ce961-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span></span>
* <span data-ttu-id="ce961-160">Excel (.xlsx, .xlsm)</span><span class="sxs-lookup"><span data-stu-id="ce961-160">Excel (.xlsx, .xlsm)</span></span>
* <span data-ttu-id="ce961-161">Formati di Office legacy (.doc, .dot e così via)</span><span class="sxs-lookup"><span data-stu-id="ce961-161">Legacy Office formats (.doc, .dot, etc.)</span></span>
* <span data-ttu-id="ce961-162">Testo (.txt)</span><span class="sxs-lookup"><span data-stu-id="ce961-162">Text (.txt)</span></span>
* <span data-ttu-id="ce961-163">HTML</span><span class="sxs-lookup"><span data-stu-id="ce961-163">HTML</span></span>
* <span data-ttu-id="ce961-164">PDF</span><span class="sxs-lookup"><span data-stu-id="ce961-164">PDF</span></span>

<span data-ttu-id="ce961-165">I file binari come immagini (jpg, bmp e così via) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="ce961-165">Binary files like images (.jpg, .bmp, etc.) are not supported.</span></span> <span data-ttu-id="ce961-166">Ad esempio, se un file docx contiene solo immagini, potrebbe essere ignorato perché non ha restituito alcun contenuto.</span><span class="sxs-lookup"><span data-stu-id="ce961-166">For example, if a .docx file contains only images, it might be skipped because it didn't return any content.</span></span>
