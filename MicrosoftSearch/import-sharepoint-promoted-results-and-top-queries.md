---
title: Principali query e risultati alzati di livello importazione SharePoint
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
description: Utilizzare le query di ricerca di SharePoint per creare i risultati di lavoro di Microsoft Search
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378898"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="c4ca6-103">Principali query e risultati alzati di livello importazione SharePoint</span><span class="sxs-lookup"><span data-stu-id="c4ca6-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="c4ca6-104">Per sfruttare le query degli utenti ed elementi di maggiore rilevanza creati in SharePoint, Microsoft Search include due strumenti per importare tali informazioni sotto forma di segnalibri consigliati:</span><span class="sxs-lookup"><span data-stu-id="c4ca6-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="c4ca6-105">Importazione SharePoint promossi le regole di query risultati</span><span class="sxs-lookup"><span data-stu-id="c4ca6-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="c4ca6-p101">Importare queste regole, elementi di maggiore rilevanza, come suggeriti segnalibri stato chiamato in precedenza. Per renderli disponibili agli utenti, pubblicarli. Tempo di pubblicazione varia in base al numero di segnalibri selezionato.</span><span class="sxs-lookup"><span data-stu-id="c4ca6-p101">Import these rules, previously called Best Bets, as suggested bookmarks. To make them available to your users, publish them. Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="c4ca6-109">Importare principali query di SharePoint tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="c4ca6-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="c4ca6-p102">Scaricare le informazioni sulle query dall'area di SharePoint. Lo script di PowerShell richiederà le credenziali di amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c4ca6-p102">Download the top queries from your SharePoint. The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="c4ca6-112">Eseguire una ricerca di SharePoint per ognuna delle principali query per ottenere i risultati di ricerca principali.</span><span class="sxs-lookup"><span data-stu-id="c4ca6-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="c4ca6-113">Aggiungere i segnalibri suggeriti per il portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="c4ca6-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="c4ca6-p103">Le principali query di SharePoint sono candidati eccellenti per i segnalibri. Utilizzare lo script di PowerShell per importarli come suggeriti segnalibri. Questo script consente di:</span><span class="sxs-lookup"><span data-stu-id="c4ca6-p103">Your top SharePoint queries are excellent candidates for bookmarks. Use the PowerShell script to import them as suggested bookmarks. This script will:</span></span>
    
<span data-ttu-id="c4ca6-p104">Per informazioni sui requisiti, esempi e parametri disponibili, scaricare lo script ed esaminare il file Leggimi. Dopo lo script di PowerShell viene eseguito, un amministratore o editor deve esaminare i segnalibri suggeriti e apportate le modifiche necessarie prima che sta pubblicati.</span><span class="sxs-lookup"><span data-stu-id="c4ca6-p104">For information about requirements, examples, and available parameters, download the script and review the README file. After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

