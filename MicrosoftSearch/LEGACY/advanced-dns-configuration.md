---
title: Configurazione DNS avanzata
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
ROBOTS: NoIndex
description: Per garantire un'esperienza di accesso semplificata per gli utenti, è possibile configurare il server DNS con un record CNAME
ms.openlocfilehash: 062c43cfbc8d25c263eb2402bd05191e385411b2
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311682"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="566a1-103">Configurazione DNS avanzata</span><span class="sxs-lookup"><span data-stu-id="566a1-103">Advanced DNS configuration</span></span>

<span data-ttu-id="566a1-p101">Per essere certi che Bing possa sempre identificare gli utenti dell'organizzazione e consentire loro di accedere all'account aziendale o dell'istituto di istruzione, configurare il server DNS interno o il server proxy per la risoluzione di `www.bing.com` in `ms.bing.com`. A questo scopo, creare una voce DNS per `www.bing.com` da usare come record CNAME per `ms.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="566a1-p101">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="566a1-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="566a1-106">**Name**</span></span>|<span data-ttu-id="566a1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="566a1-107">**Type**</span></span>|<span data-ttu-id="566a1-108">**Valore**</span><span class="sxs-lookup"><span data-stu-id="566a1-108">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="566a1-109">Record CNAME</span><span class="sxs-lookup"><span data-stu-id="566a1-109">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="566a1-p102">L'uso di un record CNAME in alternativa all'indirizzo IP è da preferirsi perché un record CNAME continuerà a funzionare anche in caso di modifica dell'indirizzo IP. Dopo aver apportato questa modifica al server DNS, i risultati continueranno a essere visualizzati come se provenissero da `www.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="566a1-p102">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="566a1-p103">Questo approccio non richiede alcuna configurazione aggiuntiva nei computer client e offre un'esperienza semplificata per gli utenti. Quando gli utenti visitano `bing.com`, l'accesso verrà eseguito quasi sempre automaticamente. Nel caso in cui non fosse possibile accedere automaticamente, verrà visualizzata la richiesta di accesso.</span><span class="sxs-lookup"><span data-stu-id="566a1-p103">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
