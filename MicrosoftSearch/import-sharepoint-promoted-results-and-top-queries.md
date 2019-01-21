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
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Principali query e risultati alzati di livello importazione SharePoint

Per sfruttare le query degli utenti ed elementi di maggiore rilevanza creati in SharePoint, Microsoft Search include due strumenti per importare tali informazioni sotto forma di segnalibri consigliati: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importazione SharePoint promossi le regole di query risultati

Importare queste regole, elementi di maggiore rilevanza, come suggeriti segnalibri stato chiamato in precedenza. Per renderli disponibili agli utenti, pubblicarli. Tempo di pubblicazione varia in base al numero di segnalibri selezionato.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importare principali query di SharePoint tramite PowerShell

- Scaricare le informazioni sulle query dall'area di SharePoint. Lo script di PowerShell richiederà le credenziali di amministratore di SharePoint.
    
- Eseguire una ricerca di SharePoint per ognuna delle principali query per ottenere i risultati di ricerca principali.
    
- Aggiungere i segnalibri suggeriti per il portale di amministrazione.
    
- Le principali query di SharePoint sono candidati eccellenti per i segnalibri. Utilizzare lo script di PowerShell per importarli come suggeriti segnalibri. Questo script consente di:
    
Per informazioni sui requisiti, esempi e parametri disponibili, scaricare lo script ed esaminare il file Leggimi. Dopo lo script di PowerShell viene eseguito, un amministratore o editor deve esaminare i segnalibri suggeriti e apportate le modifiche necessarie prima che sta pubblicati.

  

