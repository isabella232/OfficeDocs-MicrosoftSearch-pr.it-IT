---
title: Domande frequenti
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Risposte ad alcune domande frequenti sulla ricerca di contenuti nell'organizzazione e su Microsoft Search
ms.openlocfilehash: 1acf4b5c4b3e771072ea67f4d807454723352c3f
ms.sourcegitcommit: c22e8c3dcc53857da677db98a1a2b7d5ca2c6170
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41721760"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="d3b7c-103">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="d3b7c-103">Frequently asked questions</span></span>

<span data-ttu-id="d3b7c-104">Ecco un elenco delle domande più comuni.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="d3b7c-105">Se questa sezione non contiene la risposta a una domanda specifica,</span><span class="sxs-lookup"><span data-stu-id="d3b7c-105">Don't see your question answered here?</span></span> <span data-ttu-id="d3b7c-106">porre la domanda nel feedback di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="d3b7c-107">La comprensione avanzata delle query è supportata?</span><span class="sxs-lookup"><span data-stu-id="d3b7c-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="d3b7c-p102">Sì, Microsoft Search analizza gli intenti delle query da frasi di dimensioni maggiori. Questa funzionalità utilizza Ia per imparare le frasi superflue comuni che gli utenti aggiungono alle query che non influiscono sull'intenzione di ricerca. Ad esempio, quando un utente cerca informazioni *su come modificare la password*, estrarre le parole meno importanti dalla query e dal trigger in base a quelle rilevanti come *Change password*.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for *tell me more about how to change my password please*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="d3b7c-111">Questa funzionalità non sostituirà le parole chiave impostate nell'interfaccia di [Amministrazione](https://admin.microsoft.com)di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-111">This feature won't override keywords set in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="d3b7c-112">È possibile cercare file in locale?</span><span class="sxs-lookup"><span data-stu-id="d3b7c-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="d3b7c-113">Sì.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-113">Yes.</span></span> <span data-ttu-id="d3b7c-114">Se si dispone di una distribuzione ibrida di SharePoint, è possibile eseguire la ricerca nei file di [SharePoint](http://sharepoint.com/) locali.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="d3b7c-115">Come si fa a impostare Bing come motore di ricerca predefinito per gli utenti dell'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="d3b7c-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="d3b7c-116">Di seguito sono riportate le istruzioni per l'impostazione del motore di ricerca predefinito, della Home page predefinita e del browser predefinito per offrire agli utenti la migliore esperienza con Microsoft Search in [Bing](https://Bing.com):</span><span class="sxs-lookup"><span data-stu-id="d3b7c-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="d3b7c-117">Impostare Microsoft Edge come browser predefinito</span><span class="sxs-lookup"><span data-stu-id="d3b7c-117">Set Microsoft Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="d3b7c-118">Impostare Bing come motore di ricerca predefinito</span><span class="sxs-lookup"><span data-stu-id="d3b7c-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="d3b7c-119">Impostare Bing.com come home page aziendale</span><span class="sxs-lookup"><span data-stu-id="d3b7c-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="d3b7c-120">In che modo vengono protetti i risultati della ricerca?</span><span class="sxs-lookup"><span data-stu-id="d3b7c-120">How are my search results protected?</span></span>

<span data-ttu-id="d3b7c-121">È necessaria l'autenticazione di [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) per accedere ai risultati dal cloud attendibile.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-121">We require [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="d3b7c-122">Gli utenti autenticati visualizzano solo i risultati della ricerca per i contenuti a cui hanno accesso.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="d3b7c-123">Le query di ricerca sono deidentificate e i registri sono separati dal traffico di ricerca [Bing](https://Bing.com) pubblico.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic.</span></span> <span data-ttu-id="d3b7c-124">Questo livello di protezione non è offerto da nessun altro nel settore.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="d3b7c-125">È possibile eseguire ricerche nelle organizzazioni federate?</span><span class="sxs-lookup"><span data-stu-id="d3b7c-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="d3b7c-126">No.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="d3b7c-127">Dove è possibile ottenere informazioni sulla sicurezza, la conformità e la privacy di Office 365?</span><span class="sxs-lookup"><span data-stu-id="d3b7c-127">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="d3b7c-128">È possibile trovare i dettagli nelle [pagine del Centro protezione per Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="d3b7c-128">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="d3b7c-129">Gli utenti possono guadagnare punti di Microsoft Rewards con l'account aziendale o dell'istituto di istruzione?</span><span class="sxs-lookup"><span data-stu-id="d3b7c-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="d3b7c-130">Gli utenti aziendali di Microsoft Search devono accedere con un account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="d3b7c-131">Non possono però partecipare al programma Microsoft Rewards o accedervi con tali account.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="d3b7c-132">Esiste però un caso in cui gli utenti aziendali possono accumulare punti di Microsoft Rewards,</span><span class="sxs-lookup"><span data-stu-id="d3b7c-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="d3b7c-133">ovvero quando un utente di Microsoft Search ha un account Rewards creato con un [account Microsoft](https://www.microsoft.com/welcome?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="d3b7c-133">This can happen when a Microsoft Search user has a Rewards account that was created with a [Microsoft account](https://www.microsoft.com/welcome?rtc=1).</span></span> <span data-ttu-id="d3b7c-134">L'indirizzo di posta elettronica associato a un account Microsoft può provenire da Outlook.com, Hotmail.com, Gmail, Yahoo o altri provider. Se gli utenti accedono sia con l'account aziendale che con l'account Microsoft nella stessa sessione del browser, possono accumulare punti nell'account Rewards.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="d3b7c-135">L'accumulo dei punti durante la ricerca con Microsoft Search viene interrotto quando si cancellano i cookie.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span>
