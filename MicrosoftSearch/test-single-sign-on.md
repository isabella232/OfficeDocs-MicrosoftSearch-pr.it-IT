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
ROBOTS: NOINDEX
description: Ridurre il numero di volte che agli utenti di Windows 10 viene richiesto di accedere a Microsoft Search e Office 365
ms.openlocfilehash: c05a8ffcc973926add551bdbb20273b41ea23bc0
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591045"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="e7553-103">Testare l'accesso Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="e7553-103">Test single sign-on</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7553-104">Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="e7553-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="e7553-105">Stiamo trasferendo il portale nell’interfaccia di amministrazione di Microsoft 365, e lo stesso sarà poi rimosso.</span><span class="sxs-lookup"><span data-stu-id="e7553-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="e7553-106">Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7553-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="e7553-107">[Panoramica di Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="e7553-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="e7553-p102">Il Single Sign-On consente di ridurre il numero volte in cui agli utenti viene richiesto di effettuare l'accesso. Testare il Single Sign-On con un piccolo gruppo di utenti aiuta a identificare eventuali problemi di configurazione che impediscono l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e7553-p102">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="e7553-110">Per gli utenti di Chrome in Windows 10, il Single Sign-On funziona solo se è installata l'estensione di accesso di Windows 10 e AAD per Chrome.</span><span class="sxs-lookup"><span data-stu-id="e7553-110">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="e7553-111">Scaricare l'estensione di accesso di Windows 10 e AAD per Chrome</span><span class="sxs-lookup"><span data-stu-id="e7553-111">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="e7553-112">È consigliabile creare un criterio di gruppo per installare automaticamente l'estensione.</span><span class="sxs-lookup"><span data-stu-id="e7553-112">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="e7553-113">Passare al portale di amministrazione di Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="e7553-113">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="e7553-114">Nel riquadro di spostamento fare clic su **Strumenti**</span><span class="sxs-lookup"><span data-stu-id="e7553-114">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="e7553-115">Nell'elenco Strumenti scaricare **Estensione di accesso di Windows 10 e AAD per Chrome**</span><span class="sxs-lookup"><span data-stu-id="e7553-115">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="e7553-116">Condividere l'estensione con altri utenti di Chrome in Windows 10</span><span class="sxs-lookup"><span data-stu-id="e7553-116">Share the extension with Chrome users on Windows 10</span></span>

  

