---
title: Gestire le domande e risposte
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Trovare e aggiornare le risposte singolarmente o utilizzare gli strumenti di ricerca di Microsoft disponibili per modificare&come tutti insieme.
ms.openlocfilehash: 2ec06fb0940172621255946283290450c1f2e036
ms.sourcegitcommit: 7ad6f4b0ab6cd7b912862273a8b4d48a6507bc29
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2020
ms.locfileid: "44878234"
---
# <a name="manage-qas"></a><span data-ttu-id="ebc8b-103">Gestire le domande e risposte</span><span class="sxs-lookup"><span data-stu-id="ebc8b-103">Manage Q&As</span></span>

<span data-ttu-id="ebc8b-104">Creare domande e risposte è simile alla creazione di segnalibri.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-104">Creating a Q&A is similar to creating bookmarks.</span></span> <span data-ttu-id="ebc8b-105">Q&come consentono di rispondere alle domande dell'utente invece di fornire solo un collegamento a una pagina Web.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-105">Q&As allow you to answer the user's questions instead of just providing a link to a webpage.</span></span> <span data-ttu-id="ebc8b-106">È inoltre possibile formattare la risposta in testo RTF.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-106">You can also format the answer in rich text.</span></span> <span data-ttu-id="ebc8b-107">Se un segnalibro e un Q&condividono la stessa parola chiave, il risultato del segnalibro viene visualizzato per primo.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-107">If a bookmark and a Q&A share the same keyword, the bookmark result is shown first.</span></span> <span data-ttu-id="ebc8b-108">Analogamente ai segnalibri, la Q&un indice viene aggiornato subito dopo l'aggiunta o la modifica di una Q&A.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-108">Like bookmarks, the Q&A index is refreshed immediately after a Q&A is added or changed.</span></span>

## <a name="add-or-edit-a-single-qa"></a><span data-ttu-id="ebc8b-109">Aggiungere o modificare una singola domanda con risposta</span><span class="sxs-lookup"><span data-stu-id="ebc8b-109">Add or edit a single Q&A</span></span>

1. <span data-ttu-id="ebc8b-110">Passare all'**interfaccia di amministrazione di Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-110">Go to **Microsoft 365 admin center**.</span></span>
1. <span data-ttu-id="ebc8b-111">Nel riquadro di spostamento passare a **Impostazioni** e selezionare **Microsoft Search**.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-111">In the navigation pane, go to **Settings** and select **Microsoft Search**.</span></span>
1. <span data-ttu-id="ebc8b-112">Selezionare la scheda **Q&A** .</span><span class="sxs-lookup"><span data-stu-id="ebc8b-112">Select the **Q&A** tab.</span></span>
1. <span data-ttu-id="ebc8b-113">Per aggiungere una domanda con risposta, selezionare **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-113">To add a Q&A, select **Add new**.</span></span>
<span data-ttu-id="ebc8b-114">Per modificare una domanda con risposta, selezionarla nell'elenco di domande e risposte pertinente.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-114">To edit a Q&A, select the Q&A in the relevant Q&A list.</span></span> <span data-ttu-id="ebc8b-115">Quando si aggiungono o modificano le informazioni, l'anteprima viene aggiornata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-115">As you add or edit the information, the preview automatically updates.</span></span>
1. <span data-ttu-id="ebc8b-116">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-116">Save your changes.</span></span>

### <a name="supported-html-tags"></a><span data-ttu-id="ebc8b-117">Tag HTML supportati</span><span class="sxs-lookup"><span data-stu-id="ebc8b-117">Supported HTML tags</span></span>

<span data-ttu-id="ebc8b-118">È possibile usare contenuto HTML esistente o aggiungere tag HTML alla risposta (descrizione).</span><span class="sxs-lookup"><span data-stu-id="ebc8b-118">You can use existing HTML content or add HTML tags to your answer (description).</span></span> <span data-ttu-id="ebc8b-119">I tag non supportati vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-119">Unsupported tags are ignored.</span></span>

<span data-ttu-id="ebc8b-120">Sono supportati i tag HTML seguenti:</span><span class="sxs-lookup"><span data-stu-id="ebc8b-120">The following HTML tags are supported:</span></span>

- <span data-ttu-id="ebc8b-121">blockquote</span><span class="sxs-lookup"><span data-stu-id="ebc8b-121">blockquote</span></span>
- <span data-ttu-id="ebc8b-122">div</span><span class="sxs-lookup"><span data-stu-id="ebc8b-122">div</span></span>
- <span data-ttu-id="ebc8b-123">em</span><span class="sxs-lookup"><span data-stu-id="ebc8b-123">em</span></span>
- <span data-ttu-id="ebc8b-124">h1, h2, h3, and h4</span><span class="sxs-lookup"><span data-stu-id="ebc8b-124">h1, h2, h3, and h4</span></span>
- <span data-ttu-id="ebc8b-125">ol, ul, and li</span><span class="sxs-lookup"><span data-stu-id="ebc8b-125">ol, ul, and li</span></span>
- <span data-ttu-id="ebc8b-126">p</span><span class="sxs-lookup"><span data-stu-id="ebc8b-126">p</span></span>
- <span data-ttu-id="ebc8b-127">pre</span><span class="sxs-lookup"><span data-stu-id="ebc8b-127">pre</span></span>
- <span data-ttu-id="ebc8b-128">span</span><span class="sxs-lookup"><span data-stu-id="ebc8b-128">span</span></span>
- <span data-ttu-id="ebc8b-129">strong</span><span class="sxs-lookup"><span data-stu-id="ebc8b-129">strong</span></span>
- <span data-ttu-id="ebc8b-130">table, thead, tbody, tr, th, and td</span><span class="sxs-lookup"><span data-stu-id="ebc8b-130">table, thead, tbody, tr, th, and td</span></span>
- <span data-ttu-id="ebc8b-131">u</span><span class="sxs-lookup"><span data-stu-id="ebc8b-131">u</span></span>
- <span data-ttu-id="ebc8b-132">a</span><span class="sxs-lookup"><span data-stu-id="ebc8b-132">a</span></span>
- <span data-ttu-id="ebc8b-133">code</span><span class="sxs-lookup"><span data-stu-id="ebc8b-133">code</span></span>
- <span data-ttu-id="ebc8b-134">br</span><span class="sxs-lookup"><span data-stu-id="ebc8b-134">br</span></span>
- <span data-ttu-id="ebc8b-135">hr</span><span class="sxs-lookup"><span data-stu-id="ebc8b-135">hr</span></span>
- <span data-ttu-id="ebc8b-136">img</span><span class="sxs-lookup"><span data-stu-id="ebc8b-136">img</span></span>

## <a name="add-or-edit-qas-using-browser-extensions"></a><span data-ttu-id="ebc8b-137">Aggiungere o modificare la&Q come utilizzo delle estensioni del browser</span><span class="sxs-lookup"><span data-stu-id="ebc8b-137">Add or edit Q&As using browser extensions</span></span>

<span data-ttu-id="ebc8b-138">Gli amministratori della ricerca possono creare facilmente contenuti di ricerca usando le estensioni del browser.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-138">Search administrators can create search content easily by using browser extensions.</span></span> <span data-ttu-id="ebc8b-139">Installare l'estensione del browser, quindi passare al sito da cui si desidera generare una Q&A.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-139">Install the browser extension, and then go to the site from which you want to generate a Q&A.</span></span> <span data-ttu-id="ebc8b-140">È quindi possibile creare il&A e includere un collegamento al sito di origine.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-140">You can then create the Q&A and include a link to the source site.</span></span>

<span data-ttu-id="ebc8b-141">Attualmente, le estensioni del browser sono disponibili per Microsoft Edge e Chrome.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-141">Currently, browser extensions are available for Microsoft Edge and Chrome.</span></span>

- <span data-ttu-id="ebc8b-142">Per scaricare le estensioni per Edge (legacy), andare a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).</span><span class="sxs-lookup"><span data-stu-id="ebc8b-142">To download extensions for Edge (Legacy), go to [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).</span></span>
- <span data-ttu-id="ebc8b-143">Per scaricare le estensioni Chrome o Edge (cromo), passare a [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).</span><span class="sxs-lookup"><span data-stu-id="ebc8b-143">To download extensions Chrome or Edge (Chromium), go to the [Chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).</span></span>

## <a name="bulk-add-or-edit-qas"></a><span data-ttu-id="ebc8b-144">Aggiungere o modificare in blocco le domande e risposte</span><span class="sxs-lookup"><span data-stu-id="ebc8b-144">Bulk add or edit Q&As</span></span>

<span data-ttu-id="ebc8b-145">Gli amministratori possono utilizzare le funzionalità di importazione ed esportazione per creare o modificare in blocco Q&As.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-145">Administrators can use the Import and Export features to bulk create or edit Q&As.</span></span>

<span data-ttu-id="ebc8b-146">Utilizzare la caratteristica di importazione/esportazione per:</span><span class="sxs-lookup"><span data-stu-id="ebc8b-146">Use the Import/Export feature to:</span></span>

- <span data-ttu-id="ebc8b-147">Aggiungere in blocco&come aggiungere i dettagli in Q&un file modello e quindi importarlo.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-147">Bulk add Q&As - Add details in the Q&A template file, and then import it.</span></span>
- <span data-ttu-id="ebc8b-148">Modifica in blocco Q&As-Export Q&come in un file. csv, modificare la&di un dettaglio nel file esportato e quindi importare il file.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-148">Bulk edit Q&As - Export Q&As to a .csv file, edit the Q&A details in the exported file, and then import the file.</span></span>
- <span data-ttu-id="ebc8b-149">Eseguire il backup di Q&come-Export Q&come in un file. csv.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-149">Back up Q&As - Export Q&As to a .csv file.</span></span>

<span data-ttu-id="ebc8b-150">Per importare o esportare Q&come:</span><span class="sxs-lookup"><span data-stu-id="ebc8b-150">To import or export Q&As:</span></span>

1. <span data-ttu-id="ebc8b-151">In alto a destra della scheda Domande e risposte, selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-151">In the upper-right corner of the Q&A tab, select **Import**.</span></span>
<span data-ttu-id="ebc8b-152">Selezionare **Esporta** per scaricare tutte le&Q esistenti come in un file. csv.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-152">Select **Export** to download all the existing Q&As in a .csv file.</span></span>
1. <span data-ttu-id="ebc8b-153">Nel riquadro destro selezionare l'opzione da importare utilizzando un file. csv.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-153">In the right pane, select the option to import by using a .csv file.</span></span> <span data-ttu-id="ebc8b-154">Scaricare il file modello per ottenere un elenco di campi e dettagli necessari.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-154">Download the template file to get a list of the required fields and details.</span></span>
1. <span data-ttu-id="ebc8b-155">Aggiungere o modificare Q&un dettaglio nel file modello e salvarlo nel computer.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-155">Add or edit Q&A details in the template file, and save it on your computer.</span></span>
1. <span data-ttu-id="ebc8b-156">Nel riquadro **Importa Q&a** , selezionare **Sfoglia**e quindi selezionare il file. csv che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-156">In the **Import Q&A** pane, select **Browse**, and then select the .csv file that you want to import.</span></span>
1. <span data-ttu-id="ebc8b-157">Selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-157">Select **Import**.</span></span>

<span data-ttu-id="ebc8b-158">Suggerimenti importanti per i file del modello:</span><span class="sxs-lookup"><span data-stu-id="ebc8b-158">Important template file tips:</span></span>

- <span data-ttu-id="ebc8b-159">Non modificare i dati in questi campi: **Id**, **Data ultima modifica** e **Autore ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="ebc8b-159">Never edit data in these fields: **Id**, **Last Modified**, and **Last Modified By**</span></span>
- <span data-ttu-id="ebc8b-160">Se si include l'**Id** di un segnalibro esistente, verrà sostituito con le informazioni presenti nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-160">If you include the **Id** of an existing bookmark, it will be replaced with the information in the import file.</span></span>
- <span data-ttu-id="ebc8b-161">Se è presente un segnalibro esistente con lo stesso titolo o URL, il segnalibro verrà aggiornato con le informazioni contenute nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-161">If there's an existing bookmark that has the same title or URL, the bookmark will be updated with information in the import file.</span></span>
- <span data-ttu-id="ebc8b-162">Non tutti i campi del file modello sono obbligatori e i campi richiesti variano a seconda dello stato del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-162">Not all fields in the template file are required, and the required fields vary depending on the bookmark state.</span></span>
- <span data-ttu-id="ebc8b-163">In base al campo **dello stato** , i segnalibri vengono salvati come *bozza*, *suggerita*o *pianificata*oppure vengono pubblicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-163">Based on the **State** field, bookmarks are saved as *draft*, *suggested*, or *scheduled*, or they are published automatically.</span></span>
- <span data-ttu-id="ebc8b-164">Per i partner che gestiscono più organizzazioni: è possibile esportare i segnalibri da un'organizzazione e importarli in un altro.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-164">For partners who manage multiple organizations: You can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="ebc8b-165">È tuttavia necessario rimuovere i dati dalla colonna **Id** prima di importarli.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-165">But you must remove the data in the **Id** column before you import.</span></span>

> [!NOTE]
> <span data-ttu-id="ebc8b-166">Non è possibile importare la&Q come se si verificassero errori nel file modello.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-166">You can't import Q&As if there are any errors in the template file.</span></span> <span data-ttu-id="ebc8b-167">Per evitare errori, verificare che il file di importazione sia formattato correttamente e includere tutte le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="ebc8b-167">To prevent errors, make sure your import file is properly formatted, and include all the required information.</span></span>

<span data-ttu-id="ebc8b-168">Per ulteriori informazioni sull'evitare errori, vedere [prevenire gli errori di importazione](manage-bookmarks.md#prevent-import-errors).</span><span class="sxs-lookup"><span data-stu-id="ebc8b-168">For more information about avoiding errors, see [Prevent import errors](manage-bookmarks.md#prevent-import-errors).</span></span>
