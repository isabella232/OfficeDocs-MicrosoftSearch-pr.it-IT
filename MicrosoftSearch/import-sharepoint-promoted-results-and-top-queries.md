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
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importare i risultati alzati di livello e le query principali di SharePoint

Per sfruttare le query e le migliori scommesse degli utenti creati in SharePoint, Microsoft Search include due strumenti per importare queste informazioni come segnalibri suggeriti: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importare le regole di query dei risultati Promote da SharePoint

Importare queste regole, in precedenza dette Best Bet, come segnalibri suggeriti. Per renderli disponibili agli utenti, pubblicarli. Il tempo di pubblicazione varia in base al numero di segnalibri selezionati.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importare query di SharePoint principali tramite PowerShell

- Scaricare le query principali da SharePoint. Lo script di PowerShell richiederà le credenziali di amministratore di SharePoint.
    
- Eseguire una ricerca di SharePoint per ognuna delle query principali per ottenere il risultato della ricerca di primo livello.
    
- Aggiungere segnalibri suggeriti al portale di amministrazione.
    
- Le query di SharePoint principali sono candidati eccellenti per i segnalibri. Utilizzare lo script di PowerShell per importarli come segnalibri suggeriti. Questo script eseguirà le operazioni seguenti:
    
Per informazioni sui requisiti, sugli esempi e sui parametri disponibili, scaricare lo script ed esaminare il file README. Dopo l'esecuzione dello script PowerShell, un amministratore o un editor deve rivedere i segnalibri suggeriti e apportare le modifiche necessarie prima che vengano pubblicate.

  

