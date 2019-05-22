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
description: Usare le query di ricerca da SharePoint per creare risultati di lavoro per Microsoft Search
ms.openlocfilehash: 6e55e2000792bdb576a18a0efeb353dc3ea13605
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968452"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="e990b-103">Importare i risultati alzati di livello e le query principali di SharePoint</span><span class="sxs-lookup"><span data-stu-id="e990b-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e990b-104">Le impostazioni di Microsoft Search in Bing sono ora disponibili nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e990b-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e990b-105">Per iniziare, [assegnare amministratori della ricerca](https://docs.microsoft.com/it-IT/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="e990b-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="e990b-106">Per sfruttare le query degli utenti e gli elementi di maggiore rilevanza creati in SharePoint, Microsoft Search include due strumenti che consentono di importare queste informazioni come segnalibri suggeriti:</span><span class="sxs-lookup"><span data-stu-id="e990b-106">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="e990b-107">Importare le regole di query per i risultati alzati di livello di SharePoint</span><span class="sxs-lookup"><span data-stu-id="e990b-107">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="e990b-108">Importare queste regole, in precedenza denominate elementi di maggiore rilevanza, come segnalibri suggeriti.</span><span class="sxs-lookup"><span data-stu-id="e990b-108">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="e990b-109">Per renderle disponibili agli utenti, pubblicarle.</span><span class="sxs-lookup"><span data-stu-id="e990b-109">To make them available to your users, publish them.</span></span> <span data-ttu-id="e990b-110">L'ora di pubblicazione varia in base al numero di segnalibri selezionati.</span><span class="sxs-lookup"><span data-stu-id="e990b-110">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="e990b-111">Importare le query principali di SharePoint tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="e990b-111">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="e990b-112">Scaricare le query principali da SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e990b-112">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="e990b-113">Lo script di PowerShell richiederà le credenziali di amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e990b-113">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="e990b-114">Eseguire una ricerca di SharePoint per ognuna delle query principali per ottenere il miglior risultato di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e990b-114">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="e990b-115">Aggiungere segnalibri suggeriti al portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="e990b-115">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="e990b-116">Le query principali di SharePoint sono ottimi candidati per i segnalibri.</span><span class="sxs-lookup"><span data-stu-id="e990b-116">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="e990b-117">Usare lo script di PowerShell per importarle come segnalibri suggeriti.</span><span class="sxs-lookup"><span data-stu-id="e990b-117">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="e990b-118">Questo script:</span><span class="sxs-lookup"><span data-stu-id="e990b-118">This script will:</span></span>
    
<span data-ttu-id="e990b-119">Per informazioni sui requisiti, esempi e parametri disponibili, scaricare lo script e consultare il file README.</span><span class="sxs-lookup"><span data-stu-id="e990b-119">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="e990b-120">Dopo aver eseguito lo script di PowerShell, un amministratore o un editor deve controllare i segnalibri suggeriti e apportare le eventuali modifiche necessarie prima della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="e990b-120">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

