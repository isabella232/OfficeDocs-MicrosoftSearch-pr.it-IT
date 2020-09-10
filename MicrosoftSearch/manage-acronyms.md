---
title: Gestire le risposte agli acronimi in Microsoft Search
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
description: Creare e aggiornare gli acronimi risposte in Microsoft Search
ms.openlocfilehash: e328ecb7604a144b51f3a1483eef1b1c3a7e0bcb
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422947"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="45adf-103">Gestire le risposte degli acronimi in Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="45adf-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="45adf-104">Gli utenti spesso incorrono in acronimi e abbreviazioni non familiari utilizzati dall'organizzazione o dal team.</span><span class="sxs-lookup"><span data-stu-id="45adf-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="45adf-105">Le condizioni specifiche per le organizzazioni o i team possono essere nuove per le persone che si spostano da un team all'altro, che lavorano con team partner interni o che sono nuove all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="45adf-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="45adf-106">Le organizzazioni non dispongono sempre di un singolo riferimento per la terminologia standard.</span><span class="sxs-lookup"><span data-stu-id="45adf-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="45adf-107">La mancanza di un singolo riferimento rende difficile trovare definizioni o espansioni per questi acronimi.</span><span class="sxs-lookup"><span data-stu-id="45adf-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="45adf-108">Microsoft Search risolve il problema con gli acronimi.</span><span class="sxs-lookup"><span data-stu-id="45adf-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="45adf-109">Esperienza degli utenti</span><span class="sxs-lookup"><span data-stu-id="45adf-109">What users experience</span></span>

<span data-ttu-id="45adf-110">Gli utenti di Microsoft Search possono ottenere definizioni con acronimi in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)e [Office 365](https://Office.com).</span><span class="sxs-lookup"><span data-stu-id="45adf-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="45adf-111">Nella casella di **ricerca** gli utenti immettono query come questi esempi:</span><span class="sxs-lookup"><span data-stu-id="45adf-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="45adf-112">*Che cos'è* DNN</span><span class="sxs-lookup"><span data-stu-id="45adf-112">*What is* DNN</span></span>
- <span data-ttu-id="45adf-113">*Definire* DNN</span><span class="sxs-lookup"><span data-stu-id="45adf-113">*Define* DNN</span></span>
- <span data-ttu-id="45adf-114">*Definizione* di DNN</span><span class="sxs-lookup"><span data-stu-id="45adf-114">DNN *definition*</span></span>
- <span data-ttu-id="45adf-115">*Espandi* DNN</span><span class="sxs-lookup"><span data-stu-id="45adf-115">*Expand* DNN</span></span>
- <span data-ttu-id="45adf-116">*Espansione* di DNN</span><span class="sxs-lookup"><span data-stu-id="45adf-116">DNN *expansion*</span></span>
- <span data-ttu-id="45adf-117">*Significato di* DNN</span><span class="sxs-lookup"><span data-stu-id="45adf-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="45adf-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="45adf-118">DNN *means*</span></span>

<span data-ttu-id="45adf-119">Il risultato include tutti i significati di DNN che sono presenti all'interno dell'organizzazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="45adf-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="45adf-120">Gli utenti devono immettere una query che includa le *parole chiave* specificate dall'acronimo per attivare le risposte corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="45adf-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="45adf-121">Le query di acronimo non sono case sensitive.</span><span class="sxs-lookup"><span data-stu-id="45adf-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="45adf-122">Configurare le risposte alle sigle</span><span class="sxs-lookup"><span data-stu-id="45adf-122">Set up Acronyms answers</span></span>

<span data-ttu-id="45adf-123">Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com), passare a [**acronimi**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), quindi selezionare **Aggiungi acronimo**.</span><span class="sxs-lookup"><span data-stu-id="45adf-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="45adf-124">Microsoft Search esegue una query su due origini dati per fornire agli acronimi risposte alle ricerche degli utenti:</span><span class="sxs-lookup"><span data-stu-id="45adf-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="45adf-125">**Acronimi editoriali**.</span><span class="sxs-lookup"><span data-stu-id="45adf-125">**Editorial acronyms**.</span></span> <span data-ttu-id="45adf-126">Fornite dagli amministratori IT nell'interfaccia di [Amministrazione](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span><span class="sxs-lookup"><span data-stu-id="45adf-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="45adf-127">**Acronimi estratti**.</span><span class="sxs-lookup"><span data-stu-id="45adf-127">**Mined acronyms**.</span></span> <span data-ttu-id="45adf-128">Estratto da Microsoft Search dalla posta elettronica personale e dai documenti personali dell'utente e dai dati disponibili pubblicamente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="45adf-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="45adf-129">Configurare gli acronimi editoriali</span><span class="sxs-lookup"><span data-stu-id="45adf-129">Set up editorial acronyms</span></span>

<span data-ttu-id="45adf-130">Gli amministratori della ricerca possono configurare gli acronimi editoriali nella [scheda acronimi](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) nell'interfaccia di  [amministrazione di Microsoft Search](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span><span class="sxs-lookup"><span data-stu-id="45adf-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="45adf-131">È possibile aggiungere acronimi da qualsiasi sito o repository interno all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="45adf-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="45adf-132">Gli acronimi editoriali possono essere aggiunti allo stato **Published** o **Draft** :</span><span class="sxs-lookup"><span data-stu-id="45adf-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="45adf-133">**Stato pubblicato**.</span><span class="sxs-lookup"><span data-stu-id="45adf-133">**Published state**.</span></span> <span data-ttu-id="45adf-134">Gli acronimi sono disponibili per i dipendenti dell'organizzazione tramite Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="45adf-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="45adf-135">Potrebbe essere necessario fino a tre giorni prima che gli acronimi siano stati aggiunti allo stato pubblicato per diventare disponibili in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="45adf-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="45adf-136">**Stato bozza**.</span><span class="sxs-lookup"><span data-stu-id="45adf-136">**Draft state**.</span></span> <span data-ttu-id="45adf-137">Se gli amministratori desiderano esaminare le risposte degli acronimi prima di renderli disponibili in Microsoft Search, possono aggiungere gli acronimi allo stato bozza.</span><span class="sxs-lookup"><span data-stu-id="45adf-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="45adf-138">Gli acronimi aggiunti allo stato bozza non sono disponibili in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="45adf-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="45adf-139">Gli amministratori devono aggiungere gli acronimi allo stato pubblicato per renderli disponibili.</span><span class="sxs-lookup"><span data-stu-id="45adf-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="45adf-140">Gli amministratori possono aggiungere gli acronimi singolarmente o in blocco per importarli in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="45adf-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="45adf-141">Caricare un file CSV con i campi illustrati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="45adf-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="45adf-142">Acronimo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="45adf-142">Acronym (mandatory)</span></span> | <span data-ttu-id="45adf-143">Espansione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="45adf-143">Expansion (mandatory)</span></span> | <span data-ttu-id="45adf-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45adf-144">Description</span></span>  | <span data-ttu-id="45adf-145">Origine</span><span class="sxs-lookup"><span data-stu-id="45adf-145">Source</span></span> | <span data-ttu-id="45adf-146">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="45adf-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="45adf-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="45adf-147">*XXX*</span></span> | <span data-ttu-id="45adf-148">*Abbreviazione disscritta*</span><span class="sxs-lookup"><span data-stu-id="45adf-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="45adf-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="45adf-149">*URL*</span></span> | <span data-ttu-id="45adf-150">*Pubblicazione o bozza*</span><span class="sxs-lookup"><span data-stu-id="45adf-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="45adf-151">Campi CSV</span><span class="sxs-lookup"><span data-stu-id="45adf-151">CSV fields</span></span>

<span data-ttu-id="45adf-152">**Acronimo**.</span><span class="sxs-lookup"><span data-stu-id="45adf-152">**Acronym**.</span></span> <span data-ttu-id="45adf-153">Contiene la forma breve o l'acronimo effettivo.</span><span class="sxs-lookup"><span data-stu-id="45adf-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="45adf-154">Un esempio è *DNN*.</span><span class="sxs-lookup"><span data-stu-id="45adf-154">An example is *DNN*.</span></span>

<span data-ttu-id="45adf-155">**Espansione**.</span><span class="sxs-lookup"><span data-stu-id="45adf-155">**Expansion**.</span></span> <span data-ttu-id="45adf-156">Contiene l'espansione dell'acronimo.</span><span class="sxs-lookup"><span data-stu-id="45adf-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="45adf-157">Un esempio è la *rete neurale profonda*.</span><span class="sxs-lookup"><span data-stu-id="45adf-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="45adf-158">**Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="45adf-158">**Description**.</span></span> <span data-ttu-id="45adf-159">Breve descrizione dell'acronimo che fornisce agli utenti altre informazioni sull'acronimo e sulla relativa espansione.</span><span class="sxs-lookup"><span data-stu-id="45adf-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="45adf-160">Ad esempio, *una rete neurale profonda è una rete neurale con un certo livello di complessità, una rete neurale con più di due layer*.</span><span class="sxs-lookup"><span data-stu-id="45adf-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="45adf-161">**Origine**.</span><span class="sxs-lookup"><span data-stu-id="45adf-161">**Source**.</span></span> <span data-ttu-id="45adf-162">URL della pagina o del sito Web in cui si desidera consentire agli utenti di accedere per ulteriori informazioni sull'acronimo.</span><span class="sxs-lookup"><span data-stu-id="45adf-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="45adf-163">**Stato**.</span><span class="sxs-lookup"><span data-stu-id="45adf-163">**State**.</span></span> <span data-ttu-id="45adf-164">Questo campo può assumere due valori:</span><span class="sxs-lookup"><span data-stu-id="45adf-164">This field can take two values:</span></span>

- <span data-ttu-id="45adf-165">**Bozza**.</span><span class="sxs-lookup"><span data-stu-id="45adf-165">**Draft**.</span></span> <span data-ttu-id="45adf-166">Aggiunge l'acronimo allo stato bozza.</span><span class="sxs-lookup"><span data-stu-id="45adf-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="45adf-167">**Pubblicati**.</span><span class="sxs-lookup"><span data-stu-id="45adf-167">**Published**.</span></span> <span data-ttu-id="45adf-168">Aggiunge l'acronimo allo stato pubblicato e lo rende disponibile in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="45adf-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="45adf-169">Acronimi estratti</span><span class="sxs-lookup"><span data-stu-id="45adf-169">Mined acronyms</span></span>

<span data-ttu-id="45adf-170">Potrebbe essere una sfida per gli amministratori aggiungere tutti gli acronimi utilizzati all'interno di un'organizzazione per rispondere alle risposte.</span><span class="sxs-lookup"><span data-stu-id="45adf-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="45adf-171">Questa funzionalità consente di trovare gli acronimi di cui gli amministratori della ricerca non sono ancora a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="45adf-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="45adf-172">Per eseguire tale operazione, Microsoft Search estrae anche gli acronimi di queste origini:</span><span class="sxs-lookup"><span data-stu-id="45adf-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="45adf-173">Messaggi di posta elettronica degli utenti.</span><span class="sxs-lookup"><span data-stu-id="45adf-173">Users’ emails.</span></span>
- <span data-ttu-id="45adf-174">Documenti in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/).</span><span class="sxs-lookup"><span data-stu-id="45adf-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/).</span></span>
- <span data-ttu-id="45adf-175">Documenti pubblici all'interno dell'organizzazione a cui gli utenti hanno accesso in SharePoint, OneDrive o OneNote.</span><span class="sxs-lookup"><span data-stu-id="45adf-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="45adf-176">Microsoft Search garantisce che solo gli utenti con accesso e le autorizzazioni per un documento possano visualizzare gli acronimi estratti da esso.</span><span class="sxs-lookup"><span data-stu-id="45adf-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="45adf-177">Quando si estrae un acronimo dalla cassetta postale di un utente, solo quell'utente può vedere quell'acronimo.</span><span class="sxs-lookup"><span data-stu-id="45adf-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="45adf-178">Non è necessaria alcuna configurazione per gli acronimi estratti.</span><span class="sxs-lookup"><span data-stu-id="45adf-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="45adf-179">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="45adf-179">Frequently asked questions</span></span>

<span data-ttu-id="45adf-180">**D: in che modo vengono classificati i dati editoriali e estratti?**</span><span class="sxs-lookup"><span data-stu-id="45adf-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="45adf-181">**A:** La caratteristica attualmente classifica gli acronimi editoriali sopra gli acronimi estratti.</span><span class="sxs-lookup"><span data-stu-id="45adf-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="45adf-182">**D: quanto tempo occorre per rendere visibili gli acronimi editoriali in Microsoft Search dopo che sono stati pubblicati?**</span><span class="sxs-lookup"><span data-stu-id="45adf-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="45adf-183">**A:**  Sono necessari fino a tre giorni per gli acronimi aggiunti allo stato pubblicato per renderli disponibili in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="45adf-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="45adf-184">**D: in che modo gli utenti attivano le risposte alle sigle?**</span><span class="sxs-lookup"><span data-stu-id="45adf-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="45adf-185">**A: per**ottenere risposte agli acronimi, gli utenti devono immettere modelli di query specifici in una casella di **ricerca** [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)o [Office 365](https://Office.com) .</span><span class="sxs-lookup"><span data-stu-id="45adf-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="45adf-186">**D: quanto tempo è necessario per visualizzare gli acronimi estratti dopo aver ricevuto o inviato un nuovo messaggio di posta elettronica o documento?**</span><span class="sxs-lookup"><span data-stu-id="45adf-186">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="45adf-187">**A:** Gli acronimi estratti da un nuovo messaggio di posta elettronica o documento richiedono fino a sette giorni per essere visualizzati nei risultati della ricerca di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="45adf-187">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="45adf-188">**D: i documenti devono essere in un formato specifico per l'estrazione delle informazioni?**</span><span class="sxs-lookup"><span data-stu-id="45adf-188">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="45adf-189">**A:** No.</span><span class="sxs-lookup"><span data-stu-id="45adf-189">**A:** No.</span></span> <span data-ttu-id="45adf-190">Sono supportati tutti i tipi di file, ad eccezione dell'immagine, delle cartelle e dei file zip.</span><span class="sxs-lookup"><span data-stu-id="45adf-190">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="45adf-191">**D: gli acronimi di Microsoft mine verranno da documenti in tutte le lingue?**</span><span class="sxs-lookup"><span data-stu-id="45adf-191">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="45adf-192">**A**: Microsoft supporta solo le attività minerarie dai documenti in inglese.</span><span class="sxs-lookup"><span data-stu-id="45adf-192">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="45adf-193">Il supporto per altre lingue verrà aggiunto nelle fasi.</span><span class="sxs-lookup"><span data-stu-id="45adf-193">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="45adf-194">**D: che cosa accade se la mia organizzazione non vuole visualizzare gli acronimi estratti? È possibile interrompere la visualizzazione degli acronimi estratti nei risultati della ricerca?**</span><span class="sxs-lookup"><span data-stu-id="45adf-194">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="45adf-195">**A: per**disattivare la visualizzazione degli acronimi estratti nei risultati della ricerca, creare un ticket di supporto clienti attenendosi alle istruzioni riportate in [Contact Support for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span><span class="sxs-lookup"><span data-stu-id="45adf-195">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="45adf-196">Dopo aver creato un ticket di supporto, sono necessarie fino a 48 ore per evitare che gli acronimi estratti vengano visualizzati nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="45adf-196">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>
