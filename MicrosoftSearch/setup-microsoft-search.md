---
title: Configurare Microsoft Search
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
description: Configurare Microsoft Search per la prima volta.
ms.openlocfilehash: 94ee7ece8a56d599778b151d5b836240d8832762
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626910"
---
# <a name="set-up-microsoft-search"></a><span data-ttu-id="ef515-103">Configurare Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="ef515-103">Set up Microsoft Search</span></span>

<span data-ttu-id="ef515-104">Microsoft Search offre un'interfaccia semplice da usare per consentire agli utenti di trovare informazioni, ad esempio file e documenti, siti interni e strumenti aziendali, persone e gruppi, località e indicazioni stradali, conversazioni e risposte, con un accesso sicuro a tutte le origini dati, inclusi i messaggi di posta elettronica, i file, i file di SharePoint, i contenuti di OneDrive e altre risorse condivise, ad esempio Internet nell'organizzazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ef515-104">Microsoft Search provides a user-friendly interface to help users find information, like files and documents, internal sites and business tools, people and groups, locations and directions, conversations and answers by securely accessing all data sources, including emails, files, SharePoint files, OneDrive content, and other shared resources as well as the internet in the user’s organization.</span></span>

<span data-ttu-id="ef515-105">Per altre informazioni sulle funzionalità di Microsoft Search, vedere [Panoramica di Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="ef515-105">To learn more about Microsoft Search features, see [Microsoft Search Overview](overview-microsoft-search.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="ef515-106">Introduzione</span><span class="sxs-lookup"><span data-stu-id="ef515-106">Get Started</span></span>

<span data-ttu-id="ef515-107">Microsoft Search viene attivato per impostazione predefinita in Microsoft 365 per tutte le app Microsoft che lo supportano.</span><span class="sxs-lookup"><span data-stu-id="ef515-107">Microsoft Search is turned on by default for all Microsoft apps that supports it, as a part of Microsoft 365.</span></span> <span data-ttu-id="ef515-108">Non è necessaria alcuna configurazione, ma è possibile migliorare l'esperienza complessiva di ricerca di Microsoft tramite alcune attività amministrative di base.</span><span class="sxs-lookup"><span data-stu-id="ef515-108">There is no setup required,but you can improve the overall Microsoft Search experience through some basic administrative tasks.</span></span>

<span data-ttu-id="ef515-109">È possibile gestire Microsoft Search dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef515-109">You manage Microsoft Search from Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="ef515-110">Nell'interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** > **Microsoft Search**.</span><span class="sxs-lookup"><span data-stu-id="ef515-110">In Microsoft 365 admin center, go to **Settings** > **Microsoft Search**.</span></span>

<span data-ttu-id="ef515-111">**Nota:** se NON viene visualizzato Microsoft Search in **Impostazioni**, attivare l'opzione **Prova l'anteprima** nell'angolo in alto a destra di qualsiasi pagina dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="ef515-111">**Note:** If you are NOT seeing Microsoft Search under **Settings**, turn on the **Try the preview** switch in the right top corner of any admin center page.</span></span>

<span data-ttu-id="ef515-112">Gli amministratori devono considerare alcuni aspetti che possono rendere l'esperienza di Microsoft Search più efficiente e intuitiva nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ef515-112">As an admin you should consider a few things that can make the Microsoft Search experience efficient and user friendly in your organization.</span></span>

## <a name="step-1-assign-search-admin-and-search-editor"></a><span data-ttu-id="ef515-113">Passaggio 1: assegnare l'amministratore della ricerca e l'editor di ricerca</span><span class="sxs-lookup"><span data-stu-id="ef515-113">Step 1: Assign Search admin and Search editor</span></span>

<span data-ttu-id="ef515-114">In Microsoft Search è possibile gestire i contenuti e le impostazioni di ricerca dell'organizzazione attribuendo questi ruoli agli utenti:</span><span class="sxs-lookup"><span data-stu-id="ef515-114">In Microsoft Search, you can manage your organization’s search settings and content by assigning these roles to users:</span></span>

1. <span data-ttu-id="ef515-115">**Amministratore della ricerca:** questo ruolo può creare e gestire i contenuti dei risultati della ricerca e definire le impostazioni query per migliorare i risultati all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ef515-115">**Search admin:** This role can create and manage search result content and define query settings for improved search results within the organization.</span></span> <span data-ttu-id="ef515-116">L'amministratore della ricerca gestisce la configurazione di Microsoft Search ed è in grado di eseguire tutte le attività di gestione del contenuto che possono essere eseguite dall'editor della ricerca.</span><span class="sxs-lookup"><span data-stu-id="ef515-116">Search admin manages the Microsoft Search configuration and can perform all of the content-management tasks a Search editor can.</span></span>
2. <span data-ttu-id="ef515-117">**Editor della ricerca:** crea, gestisce ed elimina i contenuti per Microsoft Search nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef515-117">**Search editor:** Creates, manages, and deletes content for Microsoft Search in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ef515-118">Questo ruolo può creare e gestire contenuti editoriali, ad esempio domande frequenti, luoghi e località importanti, siti e app cercati e usati di frequente.</span><span class="sxs-lookup"><span data-stu-id="ef515-118">This role can create and manage editorial content, such as frequently asked questions and answers, important places and locations, frequently searched and used sites and apps.</span></span>

<span data-ttu-id="ef515-119">Attualmente, i ruoli di amministratore della ricerca e di editor della ricerca devono essere assegnati da un amministratore globale. Per altre informazioni, vedere [Assegnare ruoli di amministrazione](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="ef515-119">Currently, the Search admin and Search editor roles must be assigned by a global admin. For more information, see [Assign admin roles](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>

<span data-ttu-id="ef515-120">Gli amministratori della ricerca influiscono direttamente sull'esperienza di ricerca per gli utenti finali,</span><span class="sxs-lookup"><span data-stu-id="ef515-120">Search administrators directly influence the search experience for end users.</span></span> <span data-ttu-id="ef515-121">ad esempio scegliendo i tipi di risultati che gli utenti possono visualizzare.</span><span class="sxs-lookup"><span data-stu-id="ef515-121">This includes choosing the types of results you want to surface to your users.</span></span> <span data-ttu-id="ef515-122">Può risultare difficile scegliere e creare contenuti rilevanti nei numerosi argomenti diversi che gli utenti cercano in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ef515-122">It may be difficult for one person to choose and create authoritative content on many different topics that users search for in an organization.</span></span> <span data-ttu-id="ef515-123">È consigliabile sfruttare le competenze e le conoscenze degli SME (Subject Matter Expert) e di altri utenti aggiungendoli come editor della ricerca.</span><span class="sxs-lookup"><span data-stu-id="ef515-123">We recommend that you leverage the expertise and knowledge of subject matter experts (SME) and other users by adding them as Search editors.</span></span>

## <a name="step-2-create-answers"></a><span data-ttu-id="ef515-124">Passaggio 2: creare risposte</span><span class="sxs-lookup"><span data-stu-id="ef515-124">Step 2: Create answers</span></span>

<span data-ttu-id="ef515-125">Microsoft Search offre agli amministratori strumenti utili per creare un'esperienza di ricerca solida per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ef515-125">Microsoft Search provides administrators with tools that they can use to build a robust search experience for their users.</span></span> <span data-ttu-id="ef515-126">In Microsoft Search gli amministratori hanno tre diversi contenuti di ricerca che possono creare per una migliore esperienza di ricerca e per migliorare la "reperibilità" del contenuto:</span><span class="sxs-lookup"><span data-stu-id="ef515-126">In Microsoft Search, administrators have three different search contents that they can create for a better search experience and to improve the "findability" of content:</span></span>

<span data-ttu-id="ef515-127">I segnalibri sono il tipo di risposta più comunemente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="ef515-127">Bookmarks are the most commonly used answer type.</span></span> <span data-ttu-id="ef515-128">Essi promuovono i migliori risultati possibili per le query degli utenti all'inizio dei risultati della ricerca e consentono agli utenti di trovare facilmente quello che stanno cercando.</span><span class="sxs-lookup"><span data-stu-id="ef515-128">They promote the best possible results for your users’ queries to the top of the search results and make it easy for your users to find what they are looking for.</span></span>
<span data-ttu-id="ef515-129">Contenuto informativo disponibile per tutti; ad esempio, informazioni sull'azienda, assistenza per le app di Windows e di Office e così via. Contenuto che gli utenti dell'organizzazione cercano in genere nel loro lavoro quotidiano.</span><span class="sxs-lookup"><span data-stu-id="ef515-129">Informational content that is available for everyone; for example, information about the company, help for Windows and Office apps, etc. Content that people in the organization generally search for in their day-to-day work.</span></span> <span data-ttu-id="ef515-130">Le ricerche correlate al lavoro includono benefit dei dipendenti, report su orari e spese, invio di ordini di acquisto e assistenza dei servizi IT.</span><span class="sxs-lookup"><span data-stu-id="ef515-130">Common work-related searches include employee benefits, time and expense reporting, submitting purchase orders, and getting help from IT services.</span></span>

<span data-ttu-id="ef515-131">Per la creazione e la gestione delle risposte, vedere [pianificare il contenuto](plan-your-content.md).</span><span class="sxs-lookup"><span data-stu-id="ef515-131">For creating and managing answers, see [Plan your content](plan-your-content.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ef515-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ef515-132">Next steps</span></span>

<span data-ttu-id="ef515-133">Per ulteriori informazioni sul modo in cui gli utenti utilizzeranno Microsoft Search, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef515-133">If you'd like to learn more about how your users will use Microsoft Search, see the following articles:</span></span>

- [<span data-ttu-id="ef515-134">Trovare le informazioni necessarie con Microsoft Search in Office</span><span class="sxs-lookup"><span data-stu-id="ef515-134">Find what you need with Microsoft Search in Office</span></span>](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446)
- [<span data-ttu-id="ef515-135">Area risorse di Office 365</span><span class="sxs-lookup"><span data-stu-id="ef515-135">Office 365 Training Center</span></span>](https://support.office.com/office-training-center)
- [<span data-ttu-id="ef515-136">Microsoft Search Center</span><span class="sxs-lookup"><span data-stu-id="ef515-136">Microsoft Search Center</span></span>](https://support.office.com/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc)
