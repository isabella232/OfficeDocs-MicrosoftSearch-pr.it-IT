---
title: Gestire le risposte degli acronimi in Microsoft Search
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Creare e aggiornare le risposte degli acronimi in Microsoft Search
ms.openlocfilehash: 45d3cc7b33f27d2f4e77d8099fbfa91e01aabcbb
ms.sourcegitcommit: ef94ffd6111acb929c8343f0f4f82ea109b68fb6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122157"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="0d30a-103">Gestire le risposte degli acronimi in Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="0d30a-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="0d30a-104">Gli utenti spesso si trovano in acronimi e abbreviazioni sconosciuti utilizzati dall'organizzazione o dal team.</span><span class="sxs-lookup"><span data-stu-id="0d30a-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="0d30a-105">I termini specifici per le organizzazioni o i team potrebbero essere nuovi per gli utenti che passano da un team all'altro, lavorano con i team partner interni o sono nuovi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d30a-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="0d30a-106">Le organizzazioni non hanno sempre un singolo riferimento per la terminologia standard.</span><span class="sxs-lookup"><span data-stu-id="0d30a-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="0d30a-107">La mancanza di un singolo riferimento rende difficile trovare definizioni o espansioni per questi acronimi.</span><span class="sxs-lookup"><span data-stu-id="0d30a-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="0d30a-108">Microsoft Search risolve il problema con gli acronimi.</span><span class="sxs-lookup"><span data-stu-id="0d30a-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="0d30a-109">Esperienza degli utenti</span><span class="sxs-lookup"><span data-stu-id="0d30a-109">What users experience</span></span>

<span data-ttu-id="0d30a-110">Gli utenti di Microsoft Search possono ottenere definizioni con acronimi in [Bing,](https://Bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)e [Office 365.](https://Office.com)</span><span class="sxs-lookup"><span data-stu-id="0d30a-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="0d30a-111">Nella casella **di ricerca** gli utenti immettono query come questi esempi:</span><span class="sxs-lookup"><span data-stu-id="0d30a-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="0d30a-112">*Che cos'è* DNN</span><span class="sxs-lookup"><span data-stu-id="0d30a-112">*What is* DNN</span></span>
- <span data-ttu-id="0d30a-113">*Definire* DNN</span><span class="sxs-lookup"><span data-stu-id="0d30a-113">*Define* DNN</span></span>
- <span data-ttu-id="0d30a-114">Definizione *DNN*</span><span class="sxs-lookup"><span data-stu-id="0d30a-114">DNN *definition*</span></span>
- <span data-ttu-id="0d30a-115">*Espandi* DNN</span><span class="sxs-lookup"><span data-stu-id="0d30a-115">*Expand* DNN</span></span>
- <span data-ttu-id="0d30a-116">Espansione *DNN*</span><span class="sxs-lookup"><span data-stu-id="0d30a-116">DNN *expansion*</span></span>
- <span data-ttu-id="0d30a-117">*Significato di* DNN</span><span class="sxs-lookup"><span data-stu-id="0d30a-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="0d30a-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="0d30a-118">DNN *means*</span></span>

<span data-ttu-id="0d30a-119">Il risultato include tutti i significati della DNN presenti all'interno dell'organizzazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0d30a-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="0d30a-120">Gli utenti devono immettere una query che includa le parole chiave specificate dall'acronimo *per* attivare le risposte corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="0d30a-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="0d30a-121">Le query con acronimo non supportano la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0d30a-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="0d30a-122">Configurare le risposte con acronimi</span><span class="sxs-lookup"><span data-stu-id="0d30a-122">Set up acronyms answers</span></span>

<span data-ttu-id="0d30a-123">Nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com)passare [**ad Acronimi**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)e quindi selezionare **Aggiungi acronimo.**</span><span class="sxs-lookup"><span data-stu-id="0d30a-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="0d30a-124">Microsoft Search esegue una query su due origini dati per fornire agli acronimi le risposte alle ricerche degli utenti:</span><span class="sxs-lookup"><span data-stu-id="0d30a-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="0d30a-125">**Curato dall'amministratore.**</span><span class="sxs-lookup"><span data-stu-id="0d30a-125">**Admin-curated**.</span></span> <span data-ttu-id="0d30a-126">Fornito dagli amministratori IT [nell'interfaccia di amministrazione.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)</span><span class="sxs-lookup"><span data-stu-id="0d30a-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="0d30a-127">**System-curated**.</span><span class="sxs-lookup"><span data-stu-id="0d30a-127">**System-curated**.</span></span> <span data-ttu-id="0d30a-128">Individuato da Microsoft Search dalla posta elettronica e dai documenti degli utenti e dai dati disponibili pubblicamente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d30a-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="0d30a-129">Configurare acronimi curati dall'amministratore</span><span class="sxs-lookup"><span data-stu-id="0d30a-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="0d30a-130">Gli amministratori della ricerca possono aggiungere acronimi nella [scheda Acronimi](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) nell'interfaccia [di amministrazione di Microsoft Search.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)</span><span class="sxs-lookup"><span data-stu-id="0d30a-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="0d30a-131">È possibile aggiungere acronimi da qualsiasi sito o archivio interno all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0d30a-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="0d30a-132">Questi acronimi possono essere aggiunti allo **stato Published** o **Draft:**</span><span class="sxs-lookup"><span data-stu-id="0d30a-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="0d30a-133">**Stato pubblicato.**</span><span class="sxs-lookup"><span data-stu-id="0d30a-133">**Published state**.</span></span> <span data-ttu-id="0d30a-134">Gli acronimi sono disponibili per gli utenti dell'organizzazione tramite Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="0d30a-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="0d30a-135">Potrebbero essere disponibili fino a tre giorni prima che gli acronimi aggiunti allo stato Published diventino disponibili in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="0d30a-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="0d30a-136">**Stato bozza.**</span><span class="sxs-lookup"><span data-stu-id="0d30a-136">**Draft state**.</span></span> <span data-ttu-id="0d30a-137">Se si desidera esaminare un acronimo prima di renderlo disponibile in Microsoft Search, è possibile aggiungere l'acronimo in uno stato Bozza.</span><span class="sxs-lookup"><span data-stu-id="0d30a-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="0d30a-138">Gli acronimi nello stato Bozza non verranno visualizzati nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="0d30a-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="0d30a-139">Sarà necessario spostare l'acronimo nello stato Published per renderlo visualizzato nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="0d30a-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="0d30a-140">È possibile aggiungere gli acronimi singolarmente o importarli in blocco in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="0d30a-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="0d30a-141">Caricare un file CSV con i campi mostrati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="0d30a-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="0d30a-142">Acronimo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="0d30a-142">Acronym (Mandatory)</span></span> | <span data-ttu-id="0d30a-143">Espansione (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="0d30a-143">Expansion (Mandatory)</span></span> | <span data-ttu-id="0d30a-144">URL</span><span class="sxs-lookup"><span data-stu-id="0d30a-144">Url</span></span> | <span data-ttu-id="0d30a-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d30a-145">Description</span></span>  | <span data-ttu-id="0d30a-146">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="0d30a-146">State (Mandatory)</span></span> | <span data-ttu-id="0d30a-147">Ultima modifica</span><span class="sxs-lookup"><span data-stu-id="0d30a-147">Last Modified</span></span> | <span data-ttu-id="0d30a-148">Data ultima modifica</span><span class="sxs-lookup"><span data-stu-id="0d30a-148">Last Modified By</span></span> | <span data-ttu-id="0d30a-149">Id</span><span class="sxs-lookup"><span data-stu-id="0d30a-149">Id</span></span> |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| <span data-ttu-id="0d30a-150">*XXX*</span><span class="sxs-lookup"><span data-stu-id="0d30a-150">*XXX*</span></span> | <span data-ttu-id="0d30a-151">*Abbreviazione con ortografia*</span><span class="sxs-lookup"><span data-stu-id="0d30a-151">*Spelled out abbreviation*</span></span> | <span data-ttu-id="0d30a-152">*Source*</span><span class="sxs-lookup"><span data-stu-id="0d30a-152">*Source*</span></span> |  | <span data-ttu-id="0d30a-153">*Published o Draft*</span><span class="sxs-lookup"><span data-stu-id="0d30a-153">*Published or Draft*</span></span> |  |  |  |

### <a name="csv-fields"></a><span data-ttu-id="0d30a-154">Campi CSV</span><span class="sxs-lookup"><span data-stu-id="0d30a-154">CSV fields</span></span>

<span data-ttu-id="0d30a-155">**Acronimo**.</span><span class="sxs-lookup"><span data-stu-id="0d30a-155">**Acronym**.</span></span> <span data-ttu-id="0d30a-156">Contiene il formato breve o l'acronimo effettivo.</span><span class="sxs-lookup"><span data-stu-id="0d30a-156">Contains the actual short form or acronym.</span></span> <span data-ttu-id="0d30a-157">Un esempio è *DNN.*</span><span class="sxs-lookup"><span data-stu-id="0d30a-157">An example is *DNN*.</span></span>

<span data-ttu-id="0d30a-158">**Espansione**.</span><span class="sxs-lookup"><span data-stu-id="0d30a-158">**Expansion**.</span></span> <span data-ttu-id="0d30a-159">Contiene l'espansione dell'acronimo.</span><span class="sxs-lookup"><span data-stu-id="0d30a-159">Contains the expansion of the acronym.</span></span> <span data-ttu-id="0d30a-160">Un esempio è *Deep Neural Network.*</span><span class="sxs-lookup"><span data-stu-id="0d30a-160">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="0d30a-161">**Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="0d30a-161">**Description**.</span></span> <span data-ttu-id="0d30a-162">Breve descrizione dell'acronimo che fornisce agli utenti altre informazioni sull'acronimo e sulla relativa espansione.</span><span class="sxs-lookup"><span data-stu-id="0d30a-162">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="0d30a-163">Ad esempio, *una rete deep-neurale* è una rete di tipo neurale con un determinato livello di complessità, una rete di reti di tipo neurale con più di due livelli.</span><span class="sxs-lookup"><span data-stu-id="0d30a-163">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="0d30a-164">**Origine**.</span><span class="sxs-lookup"><span data-stu-id="0d30a-164">**Source**.</span></span> <span data-ttu-id="0d30a-165">URL della pagina o del sito Web in cui si desidera che gli utenti vadano per ulteriori informazioni sull'acronimo.</span><span class="sxs-lookup"><span data-stu-id="0d30a-165">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="0d30a-166">**Stato**.</span><span class="sxs-lookup"><span data-stu-id="0d30a-166">**State**.</span></span> <span data-ttu-id="0d30a-167">Questo campo può assumere due valori:</span><span class="sxs-lookup"><span data-stu-id="0d30a-167">This field can take two values:</span></span>

- <span data-ttu-id="0d30a-168">**Bozza.**</span><span class="sxs-lookup"><span data-stu-id="0d30a-168">**Draft**.</span></span> <span data-ttu-id="0d30a-169">Aggiunge l'acronimo allo stato Bozza.</span><span class="sxs-lookup"><span data-stu-id="0d30a-169">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="0d30a-170">**Published**.</span><span class="sxs-lookup"><span data-stu-id="0d30a-170">**Published**.</span></span> <span data-ttu-id="0d30a-171">Aggiunge l'acronimo allo stato Published e lo rende disponibile in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="0d30a-171">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="0d30a-172">Acronimi curati dal sistema</span><span class="sxs-lookup"><span data-stu-id="0d30a-172">System-curated acronyms</span></span>

<span data-ttu-id="0d30a-173">L'aggiunta di tutti gli acronimi utilizzati all'interno di un'organizzazione a Answers potrebbe essere una sfida per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="0d30a-173">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="0d30a-174">Questa funzionalità può trovare acronimi di cui gli amministratori della ricerca non sono nemmeno a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="0d30a-174">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="0d30a-175">A tale scopo, Microsoft Search individua e cura anche gli acronimi da queste origini:</span><span class="sxs-lookup"><span data-stu-id="0d30a-175">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="0d30a-176">Messaggi di posta elettronica degli utenti</span><span class="sxs-lookup"><span data-stu-id="0d30a-176">Users’ emails</span></span>
- <span data-ttu-id="0d30a-177">Documenti in [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="0d30a-177">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="0d30a-178">Documenti pubblici all'interno dell'organizzazione a cui gli utenti hanno accesso in SharePoint, OneDrive o OneNote</span><span class="sxs-lookup"><span data-stu-id="0d30a-178">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="0d30a-179">Microsoft Search garantisce che solo gli utenti con accesso e autorizzazioni per un documento possano visualizzare gli acronimi individuati da tale documento.</span><span class="sxs-lookup"><span data-stu-id="0d30a-179">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="0d30a-180">Quando viene trovato un acronimo nella cassetta postale di un utente, solo tale utente può vedere tale acronimo.</span><span class="sxs-lookup"><span data-stu-id="0d30a-180">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="0d30a-181">Non è necessaria alcuna configurazione per gli acronimi curati dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="0d30a-181">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="0d30a-182">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="0d30a-182">Frequently asked questions</span></span>

<span data-ttu-id="0d30a-183">**D: In che modo vengono classificati i dati curati dall'amministratore e curati dal sistema?**</span><span class="sxs-lookup"><span data-stu-id="0d30a-183">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="0d30a-184">**A:** La classificazione dei risultati può variare da persona a persona in quanto i risultati sono personalizzati per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="0d30a-184">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="0d30a-185">Nessuna di queste categorie avrà sempre la precedenza sull'altra.</span><span class="sxs-lookup"><span data-stu-id="0d30a-185">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="0d30a-186">**D: Quanto tempo è necessario perché gli acronimi curati dall'amministratore siano visibili in Microsoft Search dopo la pubblicazione?**</span><span class="sxs-lookup"><span data-stu-id="0d30a-186">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="0d30a-187">**A:**  Sono necessari fino a tre giorni prima che gli acronimi aggiunti allo stato Published diventino disponibili in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="0d30a-187">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="0d30a-188">**D: In che modo gli utenti attivano le risposte agli acronimi?**</span><span class="sxs-lookup"><span data-stu-id="0d30a-188">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="0d30a-189">**A:** Per ottenere risposte con acronimi, gli utenti devono immettere modelli di query specifici in una casella di ricerca di [Bing,](https://bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)o [Office 365.](https://Office.com) </span><span class="sxs-lookup"><span data-stu-id="0d30a-189">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="0d30a-190">**D: Quanto tempo è necessario per visualizzare gli acronimi curati dal sistema dopo aver ricevuto o inviato un nuovo messaggio di posta elettronica o documento?**</span><span class="sxs-lookup"><span data-stu-id="0d30a-190">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="0d30a-191">**A:** Gli acronimi trovati in un nuovo messaggio di posta elettronica o documento possono richiedere fino a sette giorni per essere visualizzati nei risultati di Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="0d30a-191">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="0d30a-192">**D: I documenti devono essere in un formato specifico per poter essere selezionati dal data mining?**</span><span class="sxs-lookup"><span data-stu-id="0d30a-192">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="0d30a-193">**A:** No.</span><span class="sxs-lookup"><span data-stu-id="0d30a-193">**A:** No.</span></span> <span data-ttu-id="0d30a-194">Sono supportati tutti i tipi di file, ad eccezione dei file immagine, cartelle e zip.</span><span class="sxs-lookup"><span data-stu-id="0d30a-194">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="0d30a-195">**D: Microsoft scoprirà gli acronimi dai documenti in tutte le lingue?**</span><span class="sxs-lookup"><span data-stu-id="0d30a-195">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="0d30a-196">**A:** Microsoft supporta solo il mining da documenti in inglese.</span><span class="sxs-lookup"><span data-stu-id="0d30a-196">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="0d30a-197">Il supporto per altre lingue verrà aggiunto in più fasi.</span><span class="sxs-lookup"><span data-stu-id="0d30a-197">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="0d30a-198">**D: Cosa succede se l'organizzazione non vuole mostrare acronimi curati dal sistema? È possibile interrompere la visualizzazione di questo tipo di acronimo nei risultati della ricerca?**</span><span class="sxs-lookup"><span data-stu-id="0d30a-198">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="0d30a-199">**A:** Per disattivare la visualizzazione degli acronimi curati dal sistema nei risultati della ricerca, creare un ticket di supporto clienti seguendo le istruzioni in Contattare il supporto per [i prodotti aziendali.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)</span><span class="sxs-lookup"><span data-stu-id="0d30a-199">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products).</span></span>
<span data-ttu-id="0d30a-200">Dopo aver creato un ticket di supporto, sono necessari fino a 48 ore prima che gli acronimi curati dal sistema non appaiano più nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="0d30a-200">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
