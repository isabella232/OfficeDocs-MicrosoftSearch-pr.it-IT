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
description: Utilizzare le query di ricerca di SharePoint per creare risultati di lavoro per Microsoft Search
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508754"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="c383b-103">Importare i risultati alzati di livello e le query principali di SharePoint</span><span class="sxs-lookup"><span data-stu-id="c383b-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="c383b-104">Per sfruttare le query e le migliori scommesse degli utenti creati in SharePoint, Microsoft Search include due strumenti per importare queste informazioni come segnalibri suggeriti:</span><span class="sxs-lookup"><span data-stu-id="c383b-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="c383b-105">Importare le regole di query dei risultati Promote da SharePoint</span><span class="sxs-lookup"><span data-stu-id="c383b-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="c383b-106">Importare queste regole, in precedenza dette Best Bet, come segnalibri suggeriti.</span><span class="sxs-lookup"><span data-stu-id="c383b-106">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="c383b-107">Per renderli disponibili agli utenti, pubblicarli.</span><span class="sxs-lookup"><span data-stu-id="c383b-107">To make them available to your users, publish them.</span></span> <span data-ttu-id="c383b-108">Il tempo di pubblicazione varia in base al numero di segnalibri selezionati.</span><span class="sxs-lookup"><span data-stu-id="c383b-108">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="c383b-109">Importare query di SharePoint principali tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="c383b-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="c383b-110">Scaricare le query principali da SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c383b-110">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="c383b-111">Lo script di PowerShell richiederà le credenziali di amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c383b-111">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="c383b-112">Eseguire una ricerca di SharePoint per ognuna delle query principali per ottenere il risultato della ricerca di primo livello.</span><span class="sxs-lookup"><span data-stu-id="c383b-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="c383b-113">Aggiungere segnalibri suggeriti al portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="c383b-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="c383b-114">Le query di SharePoint principali sono candidati eccellenti per i segnalibri.</span><span class="sxs-lookup"><span data-stu-id="c383b-114">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="c383b-115">Utilizzare lo script di PowerShell per importarli come segnalibri suggeriti.</span><span class="sxs-lookup"><span data-stu-id="c383b-115">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="c383b-116">Questo script eseguirà le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c383b-116">This script will:</span></span>
    
<span data-ttu-id="c383b-117">Per informazioni sui requisiti, sugli esempi e sui parametri disponibili, scaricare lo script ed esaminare il file README.</span><span class="sxs-lookup"><span data-stu-id="c383b-117">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="c383b-118">Dopo l'esecuzione dello script PowerShell, un amministratore o un editor deve rivedere i segnalibri suggeriti e apportare le modifiche necessarie prima che vengano pubblicate.</span><span class="sxs-lookup"><span data-stu-id="c383b-118">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

