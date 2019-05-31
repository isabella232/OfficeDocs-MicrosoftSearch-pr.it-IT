---
title: Importare i risultati alzati di livello e le query principali di SharePoint
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/8/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
ROBOTS: NOINDEX
description: Usare le query di ricerca da SharePoint per creare risultati di lavoro per Microsoft Search
ms.openlocfilehash: 1538c57a7b4138b36fe62e3076feb58d746b2b3e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591603"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="6b1f2-103">Importare i risultati alzati di livello e le query principali di SharePoint</span><span class="sxs-lookup"><span data-stu-id="6b1f2-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b1f2-104">Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="6b1f2-105">Stiamo trasferendo il portale nell’interfaccia di amministrazione di Microsoft 365, e lo stesso sarà poi rimosso.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="6b1f2-106">Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="6b1f2-107">[Panoramica di Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="6b1f2-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="6b1f2-108">Per sfruttare le query degli utenti e gli elementi di maggiore rilevanza creati in SharePoint, Microsoft Search include due strumenti che consentono di importare queste informazioni come segnalibri suggeriti:</span><span class="sxs-lookup"><span data-stu-id="6b1f2-108">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="6b1f2-109">Importare le regole di query per i risultati alzati di livello di SharePoint</span><span class="sxs-lookup"><span data-stu-id="6b1f2-109">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="6b1f2-110">Importare queste regole, in precedenza denominate elementi di maggiore rilevanza, come segnalibri suggeriti.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-110">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="6b1f2-111">Per renderle disponibili agli utenti, pubblicarle.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-111">To make them available to your users, publish them.</span></span> <span data-ttu-id="6b1f2-112">L'ora di pubblicazione varia in base al numero di segnalibri selezionati.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-112">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="6b1f2-113">Importare le query principali di SharePoint tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b1f2-113">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="6b1f2-114">Scaricare le query principali da SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-114">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="6b1f2-115">Lo script di PowerShell richiederà le credenziali di amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-115">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="6b1f2-116">Eseguire una ricerca di SharePoint per ognuna delle query principali per ottenere il miglior risultato di ricerca.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-116">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="6b1f2-117">Aggiungere segnalibri suggeriti al portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-117">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="6b1f2-118">Le query principali di SharePoint sono ottimi candidati per i segnalibri.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-118">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="6b1f2-119">Usare lo script di PowerShell per importarle come segnalibri suggeriti.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-119">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="6b1f2-120">Questo script:</span><span class="sxs-lookup"><span data-stu-id="6b1f2-120">This script will:</span></span>
    
<span data-ttu-id="6b1f2-121">Per informazioni sui requisiti, esempi e parametri disponibili, scaricare lo script e consultare il file README.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-121">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="6b1f2-122">Dopo aver eseguito lo script di PowerShell, un amministratore o un editor deve controllare i segnalibri suggeriti e apportare le eventuali modifiche necessarie prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="6b1f2-122">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

