---
title: Gestire le domande e risposte
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Trovare e aggiornare le risposte singolarmente oppure usare gli strumenti di Microsoft Search disponibili per modificarle tutte contemporaneamente
ms.openlocfilehash: 903aab52e8d51e45588a390b5ccdccbaae2cf04a
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626775"
---
# <a name="manage-qas"></a><span data-ttu-id="8c5b8-103">Gestire le domande e risposte</span><span class="sxs-lookup"><span data-stu-id="8c5b8-103">Manage Q&As</span></span>

<span data-ttu-id="8c5b8-104">Creare domande e risposte è simile alla creazione di segnalibri.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-104">Creating a Q&A is similar to creating bookmarks.</span></span> <span data-ttu-id="8c5b8-105">Le Domande e risposte consentono di rispondere alla domanda di un utente anziché limitarsi a fornire un collegamento a una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-105">Q&A allows you to answer the user's question instead of just providing a link to webpage.</span></span> <span data-ttu-id="8c5b8-106">È possibile formattare la risposta in testo RTF con gli strumenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-106">You can format the answer in rich text using the available tools.</span></span> <span data-ttu-id="8c5b8-107">Se un segnalibro e una domanda con risposta condividono la stessa parola chiave, il risultato del segnalibro viene visualizzato per primo.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-107">If a Bookmark and a Q&A share the same keyword, the Bookmark result is shown first.</span></span> <span data-ttu-id="8c5b8-108">Come per i segnalibri, l'indice delle domande e risposte verrà aggiornato immediatamente dopo che è stata aggiunta o modificata una domanda con risposta.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-108">Like Bookmarks, the Q&A index is refreshed immediately after a Q&A is added or changed.</span></span> 

## <a name="add-or-edit-a-single-qa"></a><span data-ttu-id="8c5b8-109">Aggiungere o modificare una singola domanda con risposta</span><span class="sxs-lookup"><span data-stu-id="8c5b8-109">Add or edit a single Q&A</span></span>
1. <span data-ttu-id="8c5b8-110">Passare all'**interfaccia di amministrazione di Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-110">Go to **Microsoft 365 admin center**.</span></span>
1. <span data-ttu-id="8c5b8-111">Nel riquadro di spostamento passare a **Impostazioni** e selezionare **Microsoft Search**.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-111">In the navigation pane, go to **Settings** and select **Microsoft Search**.</span></span>
1. <span data-ttu-id="8c5b8-112">Selezionare la scheda **Domande e risposte**. Per impostazione predefinita, è già selezionata la prima scheda (**Segnalibri**).</span><span class="sxs-lookup"><span data-stu-id="8c5b8-112">Select **Q&A** tab. By default, the first tab (**Bookmarks**) is selected.</span></span>
1. <span data-ttu-id="8c5b8-113">Per aggiungere una domanda con risposta, selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-113">To add a Q&A, select **Add new**.</span></span>
<span data-ttu-id="8c5b8-114">Per modificare una domanda con risposta, selezionarla nell'elenco di domande e risposte pertinente.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-114">To edit a Q&A, select the Q&A in the relevant Q&A list.</span></span>
1. <span data-ttu-id="8c5b8-115">Quando si aggiungono o modificano le informazioni, l'anteprima viene aggiornata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-115">As you add or edit the information, the preview automatically updates.</span></span>
1. <span data-ttu-id="8c5b8-116">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-116">Save your changes.</span></span>

### <a name="supported-html-tags"></a><span data-ttu-id="8c5b8-117">Tag HTML supportati</span><span class="sxs-lookup"><span data-stu-id="8c5b8-117">Supported HTML tags</span></span>
<span data-ttu-id="8c5b8-118">È possibile usare contenuto HTML esistente o aggiungere tag HTML alla risposta (descrizione).</span><span class="sxs-lookup"><span data-stu-id="8c5b8-118">You can use existing HTML content or add HTML tags to your answer (description).</span></span> <span data-ttu-id="8c5b8-119">I tag non supportati vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-119">Unsupported tags are ignored.</span></span>  
<span data-ttu-id="8c5b8-120">Sono supportati i tag HTML seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c5b8-120">The following HTML tags are supported:</span></span>
- <span data-ttu-id="8c5b8-121">blockquote</span><span class="sxs-lookup"><span data-stu-id="8c5b8-121">blockquote</span></span>
- <span data-ttu-id="8c5b8-122">div</span><span class="sxs-lookup"><span data-stu-id="8c5b8-122">div</span></span>
- <span data-ttu-id="8c5b8-123">em</span><span class="sxs-lookup"><span data-stu-id="8c5b8-123">em</span></span>
- <span data-ttu-id="8c5b8-124">h1, h2, h3, and h4</span><span class="sxs-lookup"><span data-stu-id="8c5b8-124">h1, h2, h3, and h4</span></span>
- <span data-ttu-id="8c5b8-125">ol, ul, and li</span><span class="sxs-lookup"><span data-stu-id="8c5b8-125">ol, ul, and li</span></span>
- <span data-ttu-id="8c5b8-126">p</span><span class="sxs-lookup"><span data-stu-id="8c5b8-126">p</span></span>
- <span data-ttu-id="8c5b8-127">pre</span><span class="sxs-lookup"><span data-stu-id="8c5b8-127">pre</span></span>
- <span data-ttu-id="8c5b8-128">span</span><span class="sxs-lookup"><span data-stu-id="8c5b8-128">span</span></span>
- <span data-ttu-id="8c5b8-129">strong</span><span class="sxs-lookup"><span data-stu-id="8c5b8-129">strong</span></span>
- <span data-ttu-id="8c5b8-130">table, thead, tbody, tr, th, and td</span><span class="sxs-lookup"><span data-stu-id="8c5b8-130">table, thead, tbody, tr, th, and td</span></span>
- <span data-ttu-id="8c5b8-131">u</span><span class="sxs-lookup"><span data-stu-id="8c5b8-131">u</span></span>
- <span data-ttu-id="8c5b8-132">a</span><span class="sxs-lookup"><span data-stu-id="8c5b8-132">a</span></span>
- <span data-ttu-id="8c5b8-133">code</span><span class="sxs-lookup"><span data-stu-id="8c5b8-133">code</span></span>
- <span data-ttu-id="8c5b8-134">br</span><span class="sxs-lookup"><span data-stu-id="8c5b8-134">br</span></span>
- <span data-ttu-id="8c5b8-135">hr</span><span class="sxs-lookup"><span data-stu-id="8c5b8-135">hr</span></span>
- <span data-ttu-id="8c5b8-136">img</span><span class="sxs-lookup"><span data-stu-id="8c5b8-136">img</span></span>

## <a name="bulk-add-or-edit-qas"></a><span data-ttu-id="8c5b8-137">Aggiungere o modificare in blocco le domande e risposte</span><span class="sxs-lookup"><span data-stu-id="8c5b8-137">Bulk add or edit Q&As</span></span>
<span data-ttu-id="8c5b8-138">Gli amministratori possono usare le funzionalità di importazione o esportazione per creare o modificare in blocco le domande e risposte.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-138">Administrators can use the Import and Export features to bulk create or edit Q&A.</span></span> <span data-ttu-id="8c5b8-139">È una funzionalità utile quando gli amministratori devono aggiungere o modificare un numero elevato di domande e risposte.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-139">This is a useful feature when administrators need to add or edit a large number of Q&A.</span></span> 

<span data-ttu-id="8c5b8-140">Usare la funzionalità di importazione/esportazione per:</span><span class="sxs-lookup"><span data-stu-id="8c5b8-140">Use the import/export feature to:</span></span>
1. <span data-ttu-id="8c5b8-141">Aggiungere domande e risposte in blocco: aggiungere i dettagli nel file modello delle domande e risposte e quindi importarlo.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-141">Bulk add Q&A - Add details in the Q&A template file, and then import it.</span></span>
1. <span data-ttu-id="8c5b8-142">Modificare domande e risposte in blocco: esportare le domande e risposte in un file CSV, quindi modificare i relativi dettagli nel file CSV esportato e infine importare il file CSV aggiornato.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-142">Bulk edit Q&A - Export Q&A to a .csv file, then edit the Q&A details in the exported .csv file, and then import the .csv file.</span></span>
1. <span data-ttu-id="8c5b8-143">Eseguire il backup di domande e risposte: esportare le domande e risposte in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-143">Backup Q&A - Export Q&A to a .csv file.</span></span>

<span data-ttu-id="8c5b8-144">Per importare o esportare domande e risposte:</span><span class="sxs-lookup"><span data-stu-id="8c5b8-144">To import or export Q&A:</span></span>
1. <span data-ttu-id="8c5b8-145">In alto a destra della scheda Domande e risposte, selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-145">In the upper-right corner of the Q&A tab, select **Import**.</span></span> <span data-ttu-id="8c5b8-146">Selezionare **Esporta** per scaricare tutte le domande e risposte esistenti in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-146">Select **Export** to download all the existing Q&A in a .csv file.</span></span>
1. <span data-ttu-id="8c5b8-147">Nel riquadro destro, scegliere l'opzione per importare con un file CSV.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-147">In the right pane, choose the option to import using a .csv file.</span></span>
<span data-ttu-id="8c5b8-148">Scaricare il file modello per un elenco di campi obbligatori e i dettagli.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-148">Download the template file for a list of the required fields and details.</span></span> 
1. <span data-ttu-id="8c5b8-149">Aggiungere o modificare i dettagli delle domande e risposte nel file modello e salvarlo nel computer.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-149">Add or edit Q&A details in the template file and save it on your computer.</span></span> 
1. <span data-ttu-id="8c5b8-150">Nel riquadro di **importazione domande e risposte**, selezionare **Sfoglia** e quindi il file CSV da importare.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-150">In the **Import Q&A** pane, select **Browse**, and then the .csv file that you want to import.</span></span>
1. <span data-ttu-id="8c5b8-151">Selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-151">Select **Import**.</span></span>

<span data-ttu-id="8c5b8-152">Ecco alcuni punti importanti riguardanti il file modello:</span><span class="sxs-lookup"><span data-stu-id="8c5b8-152">Here are some important points regarding the template file:</span></span>
- <span data-ttu-id="8c5b8-153">Non modificare i dati in questi campi: *Id*, *Data ultima modifica* e *Autore ultima modifica*</span><span class="sxs-lookup"><span data-stu-id="8c5b8-153">Never edit data in these fields: *Id*, *Last Modified*, and *Last Modified By*</span></span>
- <span data-ttu-id="8c5b8-154">Se si include l'*Id* di un segnalibro esistente, verrà sostituito con le informazioni presenti nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-154">If you include the *Id* of an existing bookmark, it will be replaced with the information in the import file.</span></span>
- <span data-ttu-id="8c5b8-155">Se esiste un segnalibro con lo stesso titolo o URL, il segnalibro verrà aggiornato con le informazioni nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-155">If there is an existing bookmark with the same title or URL, the bookmark will be updated with information in the import file.</span></span>
- <span data-ttu-id="8c5b8-156">Non tutti i campi sono obbligatori nel file modello e i campi obbligatori variano in base allo stato del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-156">Not all fields in the template file are required and required fields vary depending on the bookmark state.</span></span>
- <span data-ttu-id="8c5b8-157">In base al campo Stato, i segnalibri saranno salvati come bozza, suggeriti o pianificati, oppure saranno pubblicati direttamente.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-157">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>
- <span data-ttu-id="8c5b8-158">Per i partner che gestiscono più organizzazioni, è possibile esportare i segnalibri da un'organizzazione e importarli in un altro.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-158">For partners who manage multiple organizations, you can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="8c5b8-159">È tuttavia necessario rimuovere i dati dalla colonna *Id* prima di importarli.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-159">But you must remove the data in the *Id* column before you import.</span></span>

<span data-ttu-id="8c5b8-160">**Nota:** non è possibile importare domande e risposte se sono presenti errori nel file modello.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-160">**Note:** You cannot import Q&A if there are any errors in the template file.</span></span> <span data-ttu-id="8c5b8-161">Per evitare errori, verificare che il file di importazione sia formattato correttamente e che includa tutte le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="8c5b8-161">To prevent errors, make sure your import file is properly formatted and include all the required information.</span></span> 

<span data-ttu-id="8c5b8-162">Per altre informazioni su come evitare errori, vedere [Evitare gli errori di importazione](manage-bookmarks.md#prevent-import-errors).</span><span class="sxs-lookup"><span data-stu-id="8c5b8-162">For more information on how to prevent error, see [Prevent import errors](manage-bookmarks.md#prevent-import-errors).</span></span>