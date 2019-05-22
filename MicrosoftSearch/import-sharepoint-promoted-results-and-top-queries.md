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
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importare i risultati alzati di livello e le query principali di SharePoint

> [!IMPORTANT]
> Le impostazioni di Microsoft Search in Bing sono ora disponibili nell'interfaccia di amministrazione di Microsoft 365. Per iniziare, [assegnare amministratori della ricerca](https://docs.microsoft.com/it-IT/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) nell'interfaccia di amministrazione.
    
Per sfruttare le query degli utenti e gli elementi di maggiore rilevanza creati in SharePoint, Microsoft Search include due strumenti che consentono di importare queste informazioni come segnalibri suggeriti: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importare le regole di query per i risultati alzati di livello di SharePoint

Importare queste regole, in precedenza denominate elementi di maggiore rilevanza, come segnalibri suggeriti. Per renderle disponibili agli utenti, pubblicarle. L'ora di pubblicazione varia in base al numero di segnalibri selezionati.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importare le query principali di SharePoint tramite PowerShell

- Scaricare le query principali da SharePoint. Lo script di PowerShell richiederà le credenziali di amministratore di SharePoint.
    
- Eseguire una ricerca di SharePoint per ognuna delle query principali per ottenere il miglior risultato di ricerca.
    
- Aggiungere segnalibri suggeriti al portale di amministrazione.
    
- Le query principali di SharePoint sono ottimi candidati per i segnalibri. Usare lo script di PowerShell per importarle come segnalibri suggeriti. Questo script:
    
Per informazioni sui requisiti, esempi e parametri disponibili, scaricare lo script e consultare il file README. Dopo aver eseguito lo script di PowerShell, un amministratore o un editor deve controllare i segnalibri suggeriti e apportare le eventuali modifiche necessarie prima della pubblicazione.

  

