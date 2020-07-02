---
title: Gestire le posizioni
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 8ab9aa00-cd74-405f-8410-9a1c3cfacdb9
description: Nel corso del tempo, potrebbe essere necessario aggiornare lo stato e il contenuto di una posizione per fare in modo che rimanga pertinente.
ms.openlocfilehash: a5d3209e2b6e9269ff2e5986cf81de705ae1cc4d
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996068"
---
# <a name="manage-locations"></a><span data-ttu-id="65cf7-103">Gestire le posizioni</span><span class="sxs-lookup"><span data-stu-id="65cf7-103">Manage locations</span></span>

## <a name="location"></a><span data-ttu-id="65cf7-104">Posizione</span><span class="sxs-lookup"><span data-stu-id="65cf7-104">Location</span></span>

<span data-ttu-id="65cf7-105">Posizione consente agli utenti di trovare indirizzi e individuare gli edifici dell'organizzazione indicando la posizione precisa di uffici, campus ed edifici, oltre alle indicazioni di navigazione.</span><span class="sxs-lookup"><span data-stu-id="65cf7-105">Location helps your users find addresses and locate your organization's buildings by providing an accurate location for offices, campuses, and buildings, along with directions and navigation.</span></span> <span data-ttu-id="65cf7-106">Gli amministratori dovranno aggiungere tutte le posizioni importanti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65cf7-106">Administrators should add all important locations of your organization.</span></span> <span data-ttu-id="65cf7-107">A differenza dei segnalibri e delle domande e risposte, l'indice non verrà aggiornato immediatamente e la visualizzazione delle posizioni nuove o modificate nei risultati della ricerca può richiedere diverse ore.</span><span class="sxs-lookup"><span data-stu-id="65cf7-107">Unlike Bookmarks and Q&A, the index is not refreshed immediately, and it can take several hours for new or changed locations to appear in search results.</span></span>

### <a name="add-or-edit-a-single-location"></a><span data-ttu-id="65cf7-108">Aggiungere o modificare una singola posizione</span><span class="sxs-lookup"><span data-stu-id="65cf7-108">Add or edit a single location</span></span>

1. <span data-ttu-id="65cf7-109">Passare all'**interfaccia di amministrazione di Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="65cf7-109">Go to **Microsoft 365 admin center**.</span></span>
1. <span data-ttu-id="65cf7-110">Nel riquadro di spostamento, andare a **Impostazioni**  >  **Microsoft Search**  >  **Answers**  >  [**locations**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/locations)</span><span class="sxs-lookup"><span data-stu-id="65cf7-110">In the navigation pane, go to **Settings** > **Microsoft Search** > **Answers** > [**Locations**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/locations)</span></span>
1. <span data-ttu-id="65cf7-111">Per aggiungere una nuova posizione, fare clic su **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="65cf7-111">To add a new location, select **Add new**.</span></span>
1. <span data-ttu-id="65cf7-112">Per modificare una posizione, selezionarla nell'elenco di posizioni pertinenti.</span><span class="sxs-lookup"><span data-stu-id="65cf7-112">To edit a location, select the location in the relevant locations list.</span></span>
1. <span data-ttu-id="65cf7-113">Quando si aggiungono o modificano le informazioni, l'anteprima viene aggiornata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="65cf7-113">As you add or edit the information, the preview automatically updates.</span></span>
1. <span data-ttu-id="65cf7-114">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="65cf7-114">Save your changes.</span></span>

### <a name="bulk-add-or-edit-locations"></a><span data-ttu-id="65cf7-115">Aggiungere o modificare in blocco le posizioni</span><span class="sxs-lookup"><span data-stu-id="65cf7-115">Bulk add or edit locations</span></span>

<span data-ttu-id="65cf7-116">Gli amministratori possono usare le funzionalità di importazione o esportazione per aggiungere o modificare in blocco le posizioni.</span><span class="sxs-lookup"><span data-stu-id="65cf7-116">Administrators can use the Import or Export feature to bulk add or edit locations.</span></span>

<span data-ttu-id="65cf7-117">Usare la funzionalità di importazione/esportazione per:</span><span class="sxs-lookup"><span data-stu-id="65cf7-117">Use the import/export feature to:</span></span>

1. <span data-ttu-id="65cf7-118">Aggiungere posizioni in blocco: aggiungere i dettagli nel file modello delle posizioni e quindi importarlo.</span><span class="sxs-lookup"><span data-stu-id="65cf7-118">Bulk add location - Add details in the location template file, and then import it.</span></span>
1. <span data-ttu-id="65cf7-119">Modificare le posizioni in blocco: esportare le posizioni in un file CSV, quindi modificare i dettagli delle posizioni nel file CSV esportato e infine importare il file CSV aggiornato.</span><span class="sxs-lookup"><span data-stu-id="65cf7-119">Bulk edit locations - Export locations to a .csv file, then edit the location details in the exported .csv file, and then import the updated .csv file.</span></span>
1. <span data-ttu-id="65cf7-120">Percorsi di backup – esportare le posizioni esistenti in un file. csv.</span><span class="sxs-lookup"><span data-stu-id="65cf7-120">Backup locations – Export existing locations to a .csv file.</span></span>

<span data-ttu-id="65cf7-121">Per esportare o importare posizioni:</span><span class="sxs-lookup"><span data-stu-id="65cf7-121">To export or import locations:</span></span>

1. <span data-ttu-id="65cf7-122">In alto a destra della scheda **Posizioni**, selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="65cf7-122">In the upper-right corner of the **Locations** tab, select **Import**.</span></span>
<span data-ttu-id="65cf7-123">Selezionare **Esporta** per scaricare le posizioni esistenti in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="65cf7-123">Select **Export** to download the existing locations in a .csv file.</span></span>
1. <span data-ttu-id="65cf7-124">Nel riquadro destro, scegliere l'opzione per importare con un file CSV.</span><span class="sxs-lookup"><span data-stu-id="65cf7-124">In the right pane, choose the option to import using a .csv file.</span></span>
<span data-ttu-id="65cf7-125">Scaricare il file modello per un elenco di campi obbligatori e i dettagli.</span><span class="sxs-lookup"><span data-stu-id="65cf7-125">Download the template file for a list of the required fields and details.</span></span>
1. <span data-ttu-id="65cf7-126">Aggiungere o modificare i dettagli della posizione nel file modello e quindi salvarlo nel computer.</span><span class="sxs-lookup"><span data-stu-id="65cf7-126">Add or edit location details in the template file, and then save it on your computer.</span></span>
1. <span data-ttu-id="65cf7-127">Nel riquadro **Importa** posizioni, selezionare **Sfoglia** e quindi il file CSV da importare.</span><span class="sxs-lookup"><span data-stu-id="65cf7-127">In the **Import** locations pane, select **Browse**, and then the .csv file that you want to import.</span></span>
1. <span data-ttu-id="65cf7-128">Selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="65cf7-128">Select **Import**.</span></span>

<span data-ttu-id="65cf7-129">Ecco alcuni punti importanti riguardanti il file modello:</span><span class="sxs-lookup"><span data-stu-id="65cf7-129">Here are some important points regarding the template file:</span></span>

- <span data-ttu-id="65cf7-130">Non modificare i dati in questi campi: *Id*, *Data ultima modifica* e *Autore ultima modifica*</span><span class="sxs-lookup"><span data-stu-id="65cf7-130">Never edit data in these fields: *Id*, *Last Modified*, and *Last Modified By*</span></span>
- <span data-ttu-id="65cf7-131">Se si include l' *ID* di un percorso esistente, verrà sostituito con le informazioni contenute nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="65cf7-131">If you include the *Id* of an existing location, it will be replaced with the information in the import file.</span></span>
- <span data-ttu-id="65cf7-132">Se esiste un percorso esistente con lo stesso nome, il percorso verrà aggiornato con le informazioni contenute nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="65cf7-132">If there is an existing location with the same name, the location will be updated with information in the import file.</span></span>
- <span data-ttu-id="65cf7-133">Non tutti i campi nel file modello sono obbligatori e i campi obbligatori variano a seconda dello stato del percorso.</span><span class="sxs-lookup"><span data-stu-id="65cf7-133">Not all fields in the template file are required and required fields vary depending on the location state.</span></span>
- <span data-ttu-id="65cf7-134">In base al campo *dello stato* , i percorsi verranno salvati come bozza, suggeriti, pianificati o verranno pubblicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="65cf7-134">Based on the *State* field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>
- <span data-ttu-id="65cf7-135">Per i partner che gestiscono più organizzazioni, è possibile esportare i percorsi da un org e importarli in un altro.</span><span class="sxs-lookup"><span data-stu-id="65cf7-135">For partners who manage multiple organizations, you can export your locations from one org and import them into another.</span></span> <span data-ttu-id="65cf7-136">È tuttavia necessario rimuovere i dati dalla colonna *Id* prima di importarli.</span><span class="sxs-lookup"><span data-stu-id="65cf7-136">But you must remove the data in the *Id* column before you import.</span></span>

> [!NOTE]
> <span data-ttu-id="65cf7-137">Non è possibile importare percorsi se sono presenti errori nel file modello.</span><span class="sxs-lookup"><span data-stu-id="65cf7-137">You cannot import Locations if there are any errors in the template file.</span></span> <span data-ttu-id="65cf7-138">Per evitare errori, verificare che il file di importazione sia formattato correttamente e che includa tutte le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="65cf7-138">To prevent errors, make sure your import file is properly formatted and include all the required information.</span></span>

<span data-ttu-id="65cf7-139">Per altre informazioni su come evitare errori, vedere [Evitare gli errori di importazione](manage-bookmarks.md#prevent-import-errors).</span><span class="sxs-lookup"><span data-stu-id="65cf7-139">For more information on how to prevent error, see [Prevent import errors](manage-bookmarks.md#prevent-import-errors).</span></span>
