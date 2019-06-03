---
title: Configurazione DNS avanzata
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
ROBOTS: NoIndex
description: Per garantire un'esperienza di accesso semplificata per gli utenti, è possibile configurare il server DNS con un record CNAME
ms.openlocfilehash: 6a291165df33f8acc99d247104e8e88cd35c3a0e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591360"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="0f50b-103">Configurazione DNS avanzata</span><span class="sxs-lookup"><span data-stu-id="0f50b-103">Advanced DNS configuration</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f50b-104">Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="0f50b-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="0f50b-105">Stiamo trasferendo il portale nell’interfaccia di amministrazione di Microsoft 365, e lo stesso sarà poi rimosso.</span><span class="sxs-lookup"><span data-stu-id="0f50b-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="0f50b-106">Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f50b-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="0f50b-107">[Panoramica di Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="0f50b-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="0f50b-p102">Per essere certi che Bing possa sempre identificare gli utenti dell'organizzazione e consentire loro di accedere all'account aziendale o dell'istituto di istruzione, configurare il server DNS interno o il server proxy per la risoluzione di `www.bing.com` in `ms.bing.com`. A questo scopo, creare una voce DNS per `www.bing.com` da usare come record CNAME per `ms.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="0f50b-p102">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="0f50b-110">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0f50b-110">**Name**</span></span>|<span data-ttu-id="0f50b-111">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0f50b-111">**Type**</span></span>|<span data-ttu-id="0f50b-112">**Valore**</span><span class="sxs-lookup"><span data-stu-id="0f50b-112">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="0f50b-113">Record CNAME</span><span class="sxs-lookup"><span data-stu-id="0f50b-113">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="0f50b-p103">L'uso di un record CNAME in alternativa all'indirizzo IP è da preferirsi perché un record CNAME continuerà a funzionare anche in caso di modifica dell'indirizzo IP. Dopo aver apportato questa modifica al server DNS, i risultati continueranno a essere visualizzati come se provenissero da `www.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="0f50b-p103">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="0f50b-p104">Questo approccio non richiede alcuna configurazione aggiuntiva nei computer client e offre un'esperienza semplificata per gli utenti. Quando gli utenti visitano `bing.com`, l'accesso verrà eseguito quasi sempre automaticamente. Nel caso in cui non fosse possibile accedere automaticamente, verrà visualizzata la richiesta di accesso.</span><span class="sxs-lookup"><span data-stu-id="0f50b-p104">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
