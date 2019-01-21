---
title: Configurazione di DNS avanzata
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
description: Garantire un'esperienza di accesso semplice per gli utenti mediante la configurazione di server DNS utilizzando un record CNAME
ms.openlocfilehash: f08fc4c29c4c4356a1616faab67fdebdd6c85839
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378902"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="e33e1-103">Configurazione di DNS avanzata</span><span class="sxs-lookup"><span data-stu-id="e33e1-103">Advanced DNS configuration</span></span>

<span data-ttu-id="e33e1-p101">Per garantire Bing possono sempre identificare gli utenti all'interno dell'organizzazione e correttamente accedere li al proprio account di lavoro o della scuola, configurare i server DNS interno o server proxy per risolvere da `www.bing.com` a `ms.bing.com`. A tale scopo, creare una voce DNS per `www.bing.com` da un record CNAME per `ms.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-p101">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="e33e1-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e33e1-106">**Name**</span></span>|<span data-ttu-id="e33e1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e33e1-107">**Type**</span></span>|<span data-ttu-id="e33e1-108">**Valore**</span><span class="sxs-lookup"><span data-stu-id="e33e1-108">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="e33e1-109">CNAME</span><span class="sxs-lookup"><span data-stu-id="e33e1-109">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="e33e1-p102">Utilizzo di un record CNAME anziché l'indirizzo IP è preferibile dopo un record CNAME continuerà a funzionare se viene modificato l'indirizzo IP. Dopo aver apportato la modifica DNS, i risultati continuerà a essere visualizzato agli utenti come se provenire da `www.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="e33e1-p102">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="e33e1-p103">Questo non richiede configurazioni aggiuntive nei computer client e offre un'esperienza trasparente per gli utenti. Quando si passa a `bing.com`, si verrà automaticamente eseguito l'accesso in più coerente e se non possono essere firmati automatico, verrà richiesto di farlo.</span><span class="sxs-lookup"><span data-stu-id="e33e1-p103">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
