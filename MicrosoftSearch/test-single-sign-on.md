---
title: Testare l'accesso Single Sign-On
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: a220c1bf-7cee-448a-90a3-310284d03e81
description: Ridurre il numero di volte che agli utenti di Windows 10 viene richiesto di accedere a Microsoft Search e Office 365
ms.openlocfilehash: 55d359edac36020ec8cf2aad6b64ca9737ee1066
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612356"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="71ffc-103">Testare l'accesso Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="71ffc-103">Test single sign-on</span></span>

<span data-ttu-id="71ffc-p101">Il Single Sign-On consente di ridurre il numero volte in cui agli utenti viene richiesto di effettuare l'accesso. Testare il Single Sign-On con un piccolo gruppo di utenti aiuta a identificare eventuali problemi di configurazione che impediscono l'accesso.</span><span class="sxs-lookup"><span data-stu-id="71ffc-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="71ffc-106">Per gli utenti di Chrome in Windows 10, il Single Sign-On funziona solo se è installata l'estensione di accesso di Windows 10 e AAD per Chrome.</span><span class="sxs-lookup"><span data-stu-id="71ffc-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="71ffc-107">Scaricare l'estensione di accesso di Windows 10 e AAD per Chrome</span><span class="sxs-lookup"><span data-stu-id="71ffc-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="71ffc-108">È consigliabile creare un criterio di gruppo per installare automaticamente l'estensione.</span><span class="sxs-lookup"><span data-stu-id="71ffc-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="71ffc-109">Passare al portale di amministrazione di Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="71ffc-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="71ffc-110">Nel riquadro di spostamento fare clic su **Strumenti**</span><span class="sxs-lookup"><span data-stu-id="71ffc-110">In the left navigation pane, click **Groups**.</span></span>
    
3. <span data-ttu-id="71ffc-111">Nell'elenco Strumenti scaricare **Estensione di accesso di Windows 10 e AAD per Chrome**</span><span class="sxs-lookup"><span data-stu-id="71ffc-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="71ffc-112">Condividere l'estensione con altri utenti di Chrome in Windows 10</span><span class="sxs-lookup"><span data-stu-id="71ffc-112">Share the extension with Chrome users on Windows 10</span></span>

  

