---
title: Gestire le risposte agli acronimi in Microsoft Search
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
description: Creare e aggiornare gli acronimi risposte in Microsoft Search
ms.openlocfilehash: ff79e3d741e10d401873c29d86739e61c9f53329
ms.sourcegitcommit: e6ceb07cae208648dadd5452a077414ab5a4513f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2020
ms.locfileid: "49728007"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="c2598-103">Gestire le risposte degli acronimi in Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="c2598-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="c2598-104">Gli utenti spesso incorrono in acronimi e abbreviazioni non familiari utilizzati dall'organizzazione o dal team.</span><span class="sxs-lookup"><span data-stu-id="c2598-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="c2598-105">Le condizioni specifiche per le organizzazioni o i team possono essere nuove per le persone che si spostano da un team all'altro, che lavorano con team partner interni o che sono nuove all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2598-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="c2598-106">Le organizzazioni non dispongono sempre di un singolo riferimento per la terminologia standard.</span><span class="sxs-lookup"><span data-stu-id="c2598-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="c2598-107">La mancanza di un singolo riferimento rende difficile trovare definizioni o espansioni per questi acronimi.</span><span class="sxs-lookup"><span data-stu-id="c2598-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="c2598-108">Microsoft Search risolve il problema con gli acronimi.</span><span class="sxs-lookup"><span data-stu-id="c2598-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="c2598-109">Esperienza degli utenti</span><span class="sxs-lookup"><span data-stu-id="c2598-109">What users experience</span></span>

<span data-ttu-id="c2598-110">Gli utenti di Microsoft Search possono ottenere definizioni con acronimi in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)e [Office 365](https://Office.com).</span><span class="sxs-lookup"><span data-stu-id="c2598-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="c2598-111">Nella casella di **ricerca** gli utenti immettono query come questi esempi:</span><span class="sxs-lookup"><span data-stu-id="c2598-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="c2598-112">*Che cos'è* DNN</span><span class="sxs-lookup"><span data-stu-id="c2598-112">*What is* DNN</span></span>
- <span data-ttu-id="c2598-113">*Definire* DNN</span><span class="sxs-lookup"><span data-stu-id="c2598-113">*Define* DNN</span></span>
- <span data-ttu-id="c2598-114">*Definizione* di DNN</span><span class="sxs-lookup"><span data-stu-id="c2598-114">DNN *definition*</span></span>
- <span data-ttu-id="c2598-115">*Espandi* DNN</span><span class="sxs-lookup"><span data-stu-id="c2598-115">*Expand* DNN</span></span>
- <span data-ttu-id="c2598-116">*Espansione* di DNN</span><span class="sxs-lookup"><span data-stu-id="c2598-116">DNN *expansion*</span></span>
- <span data-ttu-id="c2598-117">*Significato di* DNN</span><span class="sxs-lookup"><span data-stu-id="c2598-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="c2598-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="c2598-118">DNN *means*</span></span>

<span data-ttu-id="c2598-119">Il risultato include tutti i significati di DNN che sono presenti all'interno dell'organizzazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c2598-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="c2598-120">Gli utenti devono immettere una query che includa le *parole chiave* specificate dall'acronimo per attivare le risposte corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c2598-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="c2598-121">Le query di acronimo non sono case sensitive.</span><span class="sxs-lookup"><span data-stu-id="c2598-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="c2598-122">Configurare le risposte alle sigle</span><span class="sxs-lookup"><span data-stu-id="c2598-122">Set up acronyms answers</span></span>

<span data-ttu-id="c2598-123">Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com), passare a [**acronimi**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), quindi selezionare **Aggiungi acronimo**.</span><span class="sxs-lookup"><span data-stu-id="c2598-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="c2598-124">Microsoft Search esegue una query su due origini dati per fornire agli acronimi risposte alle ricerche degli utenti:</span><span class="sxs-lookup"><span data-stu-id="c2598-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="c2598-125">**A cura di amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c2598-125">**Admin-curated**.</span></span> <span data-ttu-id="c2598-126">Fornite dagli amministratori IT nell'interfaccia di [Amministrazione](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span><span class="sxs-lookup"><span data-stu-id="c2598-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="c2598-127">**System-curato**.</span><span class="sxs-lookup"><span data-stu-id="c2598-127">**System-curated**.</span></span> <span data-ttu-id="c2598-128">Scoperta da Microsoft Search dalla posta elettronica e dai documenti degli utenti e dati disponibili pubblicamente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2598-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="c2598-129">Configurare gli acronimi a cura di amministratore</span><span class="sxs-lookup"><span data-stu-id="c2598-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="c2598-130">Gli amministratori della ricerca possono aggiungere gli acronimi nella [scheda acronimi](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) nell'interfaccia di  [amministrazione di Microsoft Search](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span><span class="sxs-lookup"><span data-stu-id="c2598-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="c2598-131">È possibile aggiungere acronimi da qualsiasi sito o repository interno all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="c2598-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="c2598-132">È possibile aggiungere tali acronimi allo stato **Published** o **Draft** :</span><span class="sxs-lookup"><span data-stu-id="c2598-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="c2598-133">**Stato pubblicato**.</span><span class="sxs-lookup"><span data-stu-id="c2598-133">**Published state**.</span></span> <span data-ttu-id="c2598-134">Gli acronimi sono disponibili per gli utenti dell'organizzazione tramite Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="c2598-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="c2598-135">Potrebbe essere necessario fino a tre giorni prima che gli acronimi siano stati aggiunti allo stato pubblicato per diventare disponibili in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="c2598-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="c2598-136">**Stato bozza**.</span><span class="sxs-lookup"><span data-stu-id="c2598-136">**Draft state**.</span></span> <span data-ttu-id="c2598-137">Se si desidera esaminare un acronimo prima di renderlo disponibile in Microsoft Search, è possibile aggiungere l'acronimo in uno stato bozza.</span><span class="sxs-lookup"><span data-stu-id="c2598-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="c2598-138">Gli acronimi nello stato bozza non verranno visualizzati nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="c2598-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="c2598-139">Sarà necessario spostare l'acronimo allo stato pubblicato in modo che venga visualizzato nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="c2598-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="c2598-140">È possibile aggiungere gli acronimi singolarmente o importarli in blocco in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="c2598-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="c2598-141">Caricare un file CSV con i campi illustrati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="c2598-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="c2598-142">Acronimo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="c2598-142">Acronym (mandatory)</span></span> | <span data-ttu-id="c2598-143">Espansione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="c2598-143">Expansion (mandatory)</span></span> | <span data-ttu-id="c2598-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2598-144">Description</span></span>  | <span data-ttu-id="c2598-145">Origine</span><span class="sxs-lookup"><span data-stu-id="c2598-145">Source</span></span> | <span data-ttu-id="c2598-146">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="c2598-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="c2598-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="c2598-147">*XXX*</span></span> | <span data-ttu-id="c2598-148">*Abbreviazione disscritta*</span><span class="sxs-lookup"><span data-stu-id="c2598-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="c2598-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="c2598-149">*URL*</span></span> | <span data-ttu-id="c2598-150">*Pubblicazione o bozza*</span><span class="sxs-lookup"><span data-stu-id="c2598-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="c2598-151">Campi CSV</span><span class="sxs-lookup"><span data-stu-id="c2598-151">CSV fields</span></span>

<span data-ttu-id="c2598-152">**Acronimo**.</span><span class="sxs-lookup"><span data-stu-id="c2598-152">**Acronym**.</span></span> <span data-ttu-id="c2598-153">Contiene la forma breve o l'acronimo effettivo.</span><span class="sxs-lookup"><span data-stu-id="c2598-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="c2598-154">Un esempio è *DNN*.</span><span class="sxs-lookup"><span data-stu-id="c2598-154">An example is *DNN*.</span></span>

<span data-ttu-id="c2598-155">**Espansione**.</span><span class="sxs-lookup"><span data-stu-id="c2598-155">**Expansion**.</span></span> <span data-ttu-id="c2598-156">Contiene l'espansione dell'acronimo.</span><span class="sxs-lookup"><span data-stu-id="c2598-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="c2598-157">Un esempio è la *rete neurale profonda*.</span><span class="sxs-lookup"><span data-stu-id="c2598-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="c2598-158">**Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="c2598-158">**Description**.</span></span> <span data-ttu-id="c2598-159">Breve descrizione dell'acronimo che fornisce agli utenti altre informazioni sull'acronimo e sulla relativa espansione.</span><span class="sxs-lookup"><span data-stu-id="c2598-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="c2598-160">Ad esempio, *una rete neurale profonda è una rete neurale con un certo livello di complessità, una rete neurale con più di due layer*.</span><span class="sxs-lookup"><span data-stu-id="c2598-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="c2598-161">**Origine**.</span><span class="sxs-lookup"><span data-stu-id="c2598-161">**Source**.</span></span> <span data-ttu-id="c2598-162">URL della pagina o del sito Web in cui si desidera consentire agli utenti di accedere per ulteriori informazioni sull'acronimo.</span><span class="sxs-lookup"><span data-stu-id="c2598-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="c2598-163">**Stato**.</span><span class="sxs-lookup"><span data-stu-id="c2598-163">**State**.</span></span> <span data-ttu-id="c2598-164">Questo campo può assumere due valori:</span><span class="sxs-lookup"><span data-stu-id="c2598-164">This field can take two values:</span></span>

- <span data-ttu-id="c2598-165">**Bozza**.</span><span class="sxs-lookup"><span data-stu-id="c2598-165">**Draft**.</span></span> <span data-ttu-id="c2598-166">Aggiunge l'acronimo allo stato bozza.</span><span class="sxs-lookup"><span data-stu-id="c2598-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="c2598-167">**Pubblicati**.</span><span class="sxs-lookup"><span data-stu-id="c2598-167">**Published**.</span></span> <span data-ttu-id="c2598-168">Aggiunge l'acronimo allo stato pubblicato e lo rende disponibile in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="c2598-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="c2598-169">Acronimi a cura di sistema</span><span class="sxs-lookup"><span data-stu-id="c2598-169">System-curated acronyms</span></span>

<span data-ttu-id="c2598-170">Potrebbe essere una sfida per gli amministratori aggiungere tutti gli acronimi utilizzati all'interno di un'organizzazione per rispondere alle risposte.</span><span class="sxs-lookup"><span data-stu-id="c2598-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="c2598-171">Questa funzionalità consente di trovare gli acronimi di cui gli amministratori della ricerca non sono ancora a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="c2598-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="c2598-172">Per eseguire tale operazione, Microsoft Search consente inoltre di individuare e curare gli acronimi da queste origini:</span><span class="sxs-lookup"><span data-stu-id="c2598-172">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="c2598-173">Messaggi di posta elettronica degli utenti</span><span class="sxs-lookup"><span data-stu-id="c2598-173">Users’ emails</span></span>
- <span data-ttu-id="c2598-174">Documenti in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="c2598-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="c2598-175">Documenti pubblici all'interno dell'organizzazione a cui gli utenti hanno accesso in SharePoint, OneDrive o OneNote</span><span class="sxs-lookup"><span data-stu-id="c2598-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="c2598-176">Microsoft Search garantisce che solo gli utenti con accesso e le autorizzazioni per un documento possano visualizzare gli acronimi da esso individuati.</span><span class="sxs-lookup"><span data-stu-id="c2598-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="c2598-177">Quando si trova un acronimo nella cassetta postale di un utente, solo quell'utente può vedere quell'acronimo.</span><span class="sxs-lookup"><span data-stu-id="c2598-177">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="c2598-178">Non è necessaria alcuna configurazione per gli acronimi a cura di amministratore.</span><span class="sxs-lookup"><span data-stu-id="c2598-178">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c2598-179">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="c2598-179">Frequently asked questions</span></span>

<span data-ttu-id="c2598-180">**D: in che modo vengono classificati i dati curati dall'amministratore e dal sistema?**</span><span class="sxs-lookup"><span data-stu-id="c2598-180">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="c2598-181">**A:** La classificazione dei risultati può variare da persona a persona poiché i risultati sono personalizzati per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="c2598-181">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="c2598-182">Nessuna di queste categorie avrà sempre la precedenza sull'altra.</span><span class="sxs-lookup"><span data-stu-id="c2598-182">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="c2598-183">**D: quanto tempo è necessario per rendere visibili gli acronimi curati dall'amministratore in Microsoft Search dopo che sono stati pubblicati?**</span><span class="sxs-lookup"><span data-stu-id="c2598-183">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="c2598-184">**A:**  Sono necessari fino a tre giorni per gli acronimi aggiunti allo stato pubblicato per renderli disponibili in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="c2598-184">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="c2598-185">**D: in che modo gli utenti attivano le risposte alle sigle?**</span><span class="sxs-lookup"><span data-stu-id="c2598-185">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="c2598-186">**A: per** ottenere risposte agli acronimi, gli utenti devono immettere modelli di query specifici in una casella di **ricerca** [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)o [Office 365](https://Office.com) .</span><span class="sxs-lookup"><span data-stu-id="c2598-186">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="c2598-187">**D: quanto tempo occorre per visualizzare gli acronimi curati dal sistema dopo aver ricevuto o inviato un nuovo messaggio di posta elettronica o documento?**</span><span class="sxs-lookup"><span data-stu-id="c2598-187">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="c2598-188">**A:** Gli acronimi trovati in un nuovo messaggio di posta elettronica o documento richiedono fino a sette giorni per essere visualizzati nei risultati della ricerca di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c2598-188">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="c2598-189">**D: i documenti devono essere in un formato specifico per l'estrazione delle informazioni?**</span><span class="sxs-lookup"><span data-stu-id="c2598-189">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="c2598-190">**A:** No.</span><span class="sxs-lookup"><span data-stu-id="c2598-190">**A:** No.</span></span> <span data-ttu-id="c2598-191">Sono supportati tutti i tipi di file, ad eccezione dell'immagine, delle cartelle e dei file zip.</span><span class="sxs-lookup"><span data-stu-id="c2598-191">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="c2598-192">**D: Microsoft scoprirà gli acronimi dei documenti in tutte le lingue?**</span><span class="sxs-lookup"><span data-stu-id="c2598-192">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="c2598-193">**A**: Microsoft supporta solo le attività minerarie dai documenti in inglese.</span><span class="sxs-lookup"><span data-stu-id="c2598-193">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="c2598-194">Il supporto per altre lingue verrà aggiunto nelle fasi.</span><span class="sxs-lookup"><span data-stu-id="c2598-194">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="c2598-195">**D: che cosa accade se l'organizzazione non desidera visualizzare gli acronimi a cura di sistema? È possibile interrompere la visualizzazione di questo tipo di acronimo nei risultati della ricerca?**</span><span class="sxs-lookup"><span data-stu-id="c2598-195">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="c2598-196">**A: per** disattivare la visualizzazione degli acronimi curati dal sistema nei risultati della ricerca, creare un ticket di supporto tecnico seguendo le istruzioni riportate in [Contact Support for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span><span class="sxs-lookup"><span data-stu-id="c2598-196">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="c2598-197">Dopo aver creato un ticket di supporto, sono necessarie fino a 48 ore affinché gli acronimi a cura di sistema smettano di essere visualizzati nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="c2598-197">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
