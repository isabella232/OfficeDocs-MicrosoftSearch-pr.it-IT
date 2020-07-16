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
ms.openlocfilehash: bbdd27b00be323db8d80994fe9ff6ab7fac17416
ms.sourcegitcommit: b5142052ed17cd430b4c193b67d8f3d90d94ba6e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2020
ms.locfileid: "45143866"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="3b7c4-103">Gestire le risposte degli acronimi in Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="3b7c4-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="3b7c4-104">Gli utenti spesso incorrono in acronimi e abbreviazioni non familiari utilizzati dall'organizzazione o dal team.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="3b7c4-105">Le condizioni specifiche per le organizzazioni o i team possono essere nuove per le persone che si spostano da un team all'altro, che lavorano con team partner interni o che sono nuove all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="3b7c4-106">Le organizzazioni non dispongono sempre di un singolo riferimento per la terminologia standard.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="3b7c4-107">La mancanza di un singolo riferimento rende difficile trovare definizioni o espansioni per questi acronimi.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="3b7c4-108">Microsoft Search risolve il problema con gli acronimi.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="3b7c4-109">Esperienza degli utenti</span><span class="sxs-lookup"><span data-stu-id="3b7c4-109">What users experience</span></span>

<span data-ttu-id="3b7c4-110">Gli utenti di Microsoft Search possono ottenere definizioni con acronimi in [Bing](https://Bing.com) e [SharePoint](https://products.office.com/sharepoint/collaboration).</span><span class="sxs-lookup"><span data-stu-id="3b7c4-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com) and [SharePoint](https://products.office.com/sharepoint/collaboration).</span></span> <span data-ttu-id="3b7c4-111">Nella casella di **ricerca** gli utenti immettono query come questi esempi:</span><span class="sxs-lookup"><span data-stu-id="3b7c4-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="3b7c4-112">*Che cos'è* DNN</span><span class="sxs-lookup"><span data-stu-id="3b7c4-112">*What is* DNN</span></span>
- <span data-ttu-id="3b7c4-113">*Definire* DNN</span><span class="sxs-lookup"><span data-stu-id="3b7c4-113">*Define* DNN</span></span>
- <span data-ttu-id="3b7c4-114">*Definizione* di DNN</span><span class="sxs-lookup"><span data-stu-id="3b7c4-114">DNN *definition*</span></span>
- <span data-ttu-id="3b7c4-115">*Espandi* DNN</span><span class="sxs-lookup"><span data-stu-id="3b7c4-115">*Expand* DNN</span></span>
- <span data-ttu-id="3b7c4-116">*Espansione* di DNN</span><span class="sxs-lookup"><span data-stu-id="3b7c4-116">DNN *expansion*</span></span>
- <span data-ttu-id="3b7c4-117">*Significato di* DNN</span><span class="sxs-lookup"><span data-stu-id="3b7c4-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="3b7c4-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="3b7c4-118">DNN *means*</span></span>

<span data-ttu-id="3b7c4-119">Il risultato include tutti i significati di DNN che sono presenti all'interno dell'organizzazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="3b7c4-120">Gli utenti devono immettere una query che includa le *parole chiave* specificate dall'acronimo per attivare le risposte corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="3b7c4-121">Le query di acronimo non sono case sensitive.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="3b7c4-122">Configurare le risposte alle sigle</span><span class="sxs-lookup"><span data-stu-id="3b7c4-122">Set up Acronyms answers</span></span>

<span data-ttu-id="3b7c4-123">Nell'interfaccia di [Amministrazione](https://admin.microsoft.com)di Microsoft 365, andare a **Impostazioni**  >  **Microsoft Search**  >  **Answers**  >  [**acronimi**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), quindi selezionare **Aggiungi acronimi**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-123">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** > **Answers** > [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronyms**.</span></span>

<span data-ttu-id="3b7c4-124">Microsoft Search esegue una query su due origini dati per fornire agli acronimi risposte alle ricerche degli utenti:</span><span class="sxs-lookup"><span data-stu-id="3b7c4-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="3b7c4-125">**Acronimi editoriali**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-125">**Editorial acronyms**.</span></span> <span data-ttu-id="3b7c4-126">Fornite dagli amministratori IT nell'interfaccia di [Amministrazione](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span><span class="sxs-lookup"><span data-stu-id="3b7c4-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="3b7c4-127">**Acronimi estratti**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-127">**Mined acronyms**.</span></span> <span data-ttu-id="3b7c4-128">Estratto da Microsoft Search dalla posta elettronica personale e dai documenti personali dell'utente e dai dati disponibili pubblicamente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="3b7c4-129">Configurare gli acronimi editoriali</span><span class="sxs-lookup"><span data-stu-id="3b7c4-129">Set up editorial acronyms</span></span>

<span data-ttu-id="3b7c4-130">Gli amministratori della ricerca possono configurare gli acronimi editoriali nella [scheda acronimi](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) nell'interfaccia di [amministrazione di Microsoft Search](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span><span class="sxs-lookup"><span data-stu-id="3b7c4-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="3b7c4-131">È possibile aggiungere acronimi da qualsiasi sito o repository interno all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="3b7c4-132">Gli acronimi editoriali possono essere aggiunti allo stato **Published** o **Draft** :</span><span class="sxs-lookup"><span data-stu-id="3b7c4-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="3b7c4-133">**Stato pubblicato**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-133">**Published state**.</span></span> <span data-ttu-id="3b7c4-134">Gli acronimi sono disponibili per i dipendenti dell'organizzazione tramite Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="3b7c4-135">Potrebbe essere necessario fino a tre giorni prima che gli acronimi siano stati aggiunti allo stato pubblicato per diventare disponibili in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="3b7c4-136">**Stato bozza**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-136">**Draft state**.</span></span> <span data-ttu-id="3b7c4-137">Se gli amministratori desiderano esaminare le risposte degli acronimi prima di renderli disponibili in Microsoft Search, possono aggiungere gli acronimi allo stato bozza.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="3b7c4-138">Gli acronimi aggiunti allo stato bozza non sono disponibili in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="3b7c4-139">Gli amministratori devono aggiungere gli acronimi allo stato pubblicato per renderli disponibili.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="3b7c4-140">Gli amministratori possono aggiungere gli acronimi singolarmente o in blocco per importarli in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="3b7c4-141">Caricare un file CSV con i campi illustrati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="3b7c4-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="3b7c4-142">Acronimo (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="3b7c4-142">Acronym (mandatory)</span></span> | <span data-ttu-id="3b7c4-143">Espansione (obbligatoria)</span><span class="sxs-lookup"><span data-stu-id="3b7c4-143">Expansion (mandatory)</span></span> | <span data-ttu-id="3b7c4-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3b7c4-144">Description</span></span>  | <span data-ttu-id="3b7c4-145">Origine</span><span class="sxs-lookup"><span data-stu-id="3b7c4-145">Source</span></span> | <span data-ttu-id="3b7c4-146">Stato (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="3b7c4-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="3b7c4-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="3b7c4-147">*XXX*</span></span> | <span data-ttu-id="3b7c4-148">*Abbreviazione disscritta*</span><span class="sxs-lookup"><span data-stu-id="3b7c4-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="3b7c4-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="3b7c4-149">*URL*</span></span> | <span data-ttu-id="3b7c4-150">*Pubblicazione o bozza*</span><span class="sxs-lookup"><span data-stu-id="3b7c4-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="3b7c4-151">Campi CSV</span><span class="sxs-lookup"><span data-stu-id="3b7c4-151">CSV fields</span></span>

<span data-ttu-id="3b7c4-152">**Acronimo**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-152">**Acronym**.</span></span> <span data-ttu-id="3b7c4-153">Contiene la forma breve o l'acronimo effettivo.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="3b7c4-154">Un esempio è *DNN*.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-154">An example is *DNN*.</span></span>

<span data-ttu-id="3b7c4-155">**Espansione**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-155">**Expansion**.</span></span> <span data-ttu-id="3b7c4-156">Contiene l'espansione dell'acronimo.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="3b7c4-157">Un esempio è la *rete neurale profonda*.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="3b7c4-158">**Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-158">**Description**.</span></span> <span data-ttu-id="3b7c4-159">Breve descrizione dell'acronimo che fornisce agli utenti altre informazioni sull'acronimo e sulla relativa espansione.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="3b7c4-160">Ad esempio, *una rete neurale profonda è una rete neurale con un certo livello di complessità, una rete neurale con più di due layer*.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="3b7c4-161">**Origine**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-161">**Source**.</span></span> <span data-ttu-id="3b7c4-162">URL della pagina o del sito Web in cui si desidera consentire agli utenti di accedere per ulteriori informazioni sull'acronimo.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="3b7c4-163">**Stato**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-163">**State**.</span></span> <span data-ttu-id="3b7c4-164">Questo campo può assumere due valori:</span><span class="sxs-lookup"><span data-stu-id="3b7c4-164">This field can take two values:</span></span>

- <span data-ttu-id="3b7c4-165">**Bozza**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-165">**Draft**.</span></span> <span data-ttu-id="3b7c4-166">Aggiunge l'acronimo allo stato bozza.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="3b7c4-167">**Pubblicati**.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-167">**Published**.</span></span> <span data-ttu-id="3b7c4-168">Aggiunge l'acronimo allo stato pubblicato e lo rende disponibile in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="3b7c4-169">Acronimi estratti</span><span class="sxs-lookup"><span data-stu-id="3b7c4-169">Mined acronyms</span></span>

<span data-ttu-id="3b7c4-170">Potrebbe essere una sfida per gli amministratori aggiungere tutti gli acronimi utilizzati all'interno di un'organizzazione per rispondere alle risposte.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="3b7c4-171">Questa funzionalità consente di trovare gli acronimi di cui gli amministratori della ricerca non sono ancora a conoscenza.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="3b7c4-172">Per eseguire tale operazione, Microsoft Search estrae anche gli acronimi di queste origini:</span><span class="sxs-lookup"><span data-stu-id="3b7c4-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="3b7c4-173">Messaggi di posta elettronica degli utenti.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-173">Users’ emails.</span></span>
- <span data-ttu-id="3b7c4-174">Documenti in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/).</span><span class="sxs-lookup"><span data-stu-id="3b7c4-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/).</span></span>
- <span data-ttu-id="3b7c4-175">Documenti pubblici all'interno dell'organizzazione a cui gli utenti hanno accesso in SharePoint, OneDrive o OneNote.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="3b7c4-176">Microsoft Search garantisce che solo gli utenti con accesso e le autorizzazioni per un documento possano visualizzare gli acronimi estratti da esso.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="3b7c4-177">Quando si estrae un acronimo dalla cassetta postale di un utente, solo quell'utente può vedere quell'acronimo.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="3b7c4-178">Non è necessaria alcuna configurazione per gli acronimi estratti.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="3b7c4-179">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="3b7c4-179">Frequently asked questions</span></span>

<span data-ttu-id="3b7c4-180">**D: in che modo vengono classificati i dati editoriali e estratti?**</span><span class="sxs-lookup"><span data-stu-id="3b7c4-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="3b7c4-181">**A:** La caratteristica attualmente classifica gli acronimi editoriali sopra gli acronimi estratti.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="3b7c4-182">**D: quanto tempo occorre per rendere visibili gli acronimi editoriali in Microsoft Search dopo che sono stati pubblicati?**</span><span class="sxs-lookup"><span data-stu-id="3b7c4-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="3b7c4-183">**A:**  Sono necessari fino a tre giorni per gli acronimi aggiunti allo stato pubblicato per renderli disponibili in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="3b7c4-184">**D: in che modo gli utenti attivano le risposte alle sigle?**</span><span class="sxs-lookup"><span data-stu-id="3b7c4-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="3b7c4-185">**A: per**ottenere risposte agli acronimi, gli utenti devono immettere modelli di query specifici in una casella di **ricerca** [Bing](https://bing.com) o [SharePoint](https://products.office.com/sharepoint/collaboration) .</span><span class="sxs-lookup"><span data-stu-id="3b7c4-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com) or [SharePoint](https://products.office.com/sharepoint/collaboration) **Search** box.</span></span> <span data-ttu-id="3b7c4-186">Attualmente, le risposte all'acronimo non sono disponibili in [Office 365](https://Office.com).</span><span class="sxs-lookup"><span data-stu-id="3b7c4-186">Currently, Acronym answers aren't available in [Office 365](https://Office.com).</span></span>

<span data-ttu-id="3b7c4-187">**D: quanto tempo è necessario per visualizzare gli acronimi estratti dopo aver ricevuto o inviato un nuovo messaggio di posta elettronica o documento?**</span><span class="sxs-lookup"><span data-stu-id="3b7c4-187">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="3b7c4-188">**A:** Gli acronimi estratti da un nuovo messaggio di posta elettronica o documento richiedono fino a sette giorni per essere visualizzati nei risultati della ricerca di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-188">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="3b7c4-189">**D: i documenti devono essere in un formato specifico per l'estrazione delle informazioni?**</span><span class="sxs-lookup"><span data-stu-id="3b7c4-189">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="3b7c4-190">**A:** No.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-190">**A:** No.</span></span> <span data-ttu-id="3b7c4-191">Sono supportati tutti i tipi di file, ad eccezione dell'immagine, delle cartelle e dei file zip.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-191">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="3b7c4-192">**D: gli acronimi di Microsoft mine verranno da documenti in tutte le lingue?**</span><span class="sxs-lookup"><span data-stu-id="3b7c4-192">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="3b7c4-193">**A**: Microsoft supporta solo le attività minerarie dai documenti in inglese.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-193">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="3b7c4-194">Il supporto per altre lingue verrà aggiunto nelle fasi.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-194">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="3b7c4-195">**D: che cosa accade se la mia organizzazione non vuole visualizzare gli acronimi estratti? È possibile interrompere la visualizzazione degli acronimi estratti nei risultati della ricerca?**</span><span class="sxs-lookup"><span data-stu-id="3b7c4-195">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="3b7c4-196">**A: per**disattivare la visualizzazione degli acronimi estratti nei risultati della ricerca, creare un ticket di supporto clienti attenendosi alle istruzioni riportate in [Contact Support for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span><span class="sxs-lookup"><span data-stu-id="3b7c4-196">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="3b7c4-197">Dopo aver creato un ticket di supporto, sono necessarie fino a 48 ore per evitare che gli acronimi estratti vengano visualizzati nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-197">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>

<span data-ttu-id="3b7c4-198">**D: quando vengono visualizzate le risposte agli acronimi in [Office 365](https://Office.com)?**</span><span class="sxs-lookup"><span data-stu-id="3b7c4-198">**Q: When will I see Acronyms answers in [Office 365](https://Office.com)?**</span></span>

<span data-ttu-id="3b7c4-199">**A**: gli acronimi Answers in Office 365 fanno parte della nostra roadmap del prodotto, ma al momento non è possibile fornire una data o un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="3b7c4-199">**A**: Acronyms answers in Office 365 are part of our product roadmap, but we're currently unable to provide a date or timeframe.</span></span>
