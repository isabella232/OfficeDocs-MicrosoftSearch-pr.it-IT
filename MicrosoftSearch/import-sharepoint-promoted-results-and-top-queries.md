---
title: Importare i risultati alzati di livello e le query principali di SharePoint
ms.author: dawholl
author: dawholl
manager: kellis
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
description: Utilizzare query di ricerca da SharePoint per creare risultati di lavoro per Microsoft Search
ms.openlocfilehash: cfd5fafd0529f537a55e436ef078800a4b9714177e04c63e65e968f16fcf322e
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533825"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importare i risultati alzati di livello e le query principali di SharePoint

> [!IMPORTANT]
> Questo articolo si applica alla Microsoft Search nel portale Bing di amministrazione. Il portale di amministrazione di Microsoft Search in Bing sta per essere trasferito nell'interfaccia di amministrazione di Microsoft 365 e successivamente verrà rimosso. Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365. [Panoramica di Microsoft Search](overview-microsoft-search.md).
    
Per sfruttare le query degli utenti e gli elementi di maggiore rilevanza creati in SharePoint, Microsoft Search include due strumenti per importare queste informazioni come segnalibri suggeriti: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importare SharePoint regole di query dei risultati alzate di livello

Importare queste regole, precedentemente denominate elementi di maggiore rilevanza, come segnalibri suggeriti. Per renderli disponibili per gli utenti, pubblicarli. Il tempo di pubblicazione varia in base al numero di segnalibri selezionati.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importare le query SharePoint principali tramite PowerShell

- Scaricare le query principali dalla SharePoint. Lo script di PowerShell richiederà le credenziali SharePoint amministratore.
    
- Eseguire una SharePoint di ricerca per ognuna delle query principali per ottenere il risultato della ricerca principale.
    
- Aggiungi segnalibri suggeriti al portale di amministrazione.
    
- Le query SharePoint sono ottimi candidati per i segnalibri. Usa lo script di PowerShell per importarli come segnalibri suggeriti. Questo script esegue le operazioni seguenti:
    - Aggiunge segnalibri suggeriti in base SharePoint query principali per migliorare la copertura Microsoft Search segnalibri. Questo script scarica le query principali accessibili dal portale di amministrazione di SharePoint e quindi le carica come segnalibri suggeriti per un amministratore da esaminare nel portale di amministrazione di Microsoft Search.
    - Per impostazione predefinita, lo script aggiunge segnalibri suggeriti al tenant specificato per tutti i mesi disponibili. Ottiene le query principali da un determinato SharePoint di amministrazione e le aggiunge a Microsoft Search come segnalibri suggeriti. I segnalibri suggeriti necessitano di un amministratore/editor per approvarli nel portale di amministrazione prima di essere pubblicati. Quando si esegue questo script, vengono richieste le credenziali per accedere al portale Microsoft Search di amministrazione.
    - Lo script consente di impostare parametri aggiuntivi. È possibile, ad esempio, aggiungere segnalibri suggeriti al tenant specificato per le prime N query in ognuno dei mesi disponibili.
    - Facoltativamente, è possibile aggiungere segnalibri suggeriti a un determinato tenant per mesi nell'anno specificato. Questo comando ottiene le query principali per il periodo di tempo specificato SharePoint sito Web di amministrazione e le aggiunge Microsoft Search come segnalibri suggeriti.
    - Sono inoltre disponibili numerose altre opzioni e modalità di comando: scaricare le query principali da SharePoint in una cartella specificata, eseguire lo script in modalità Cassaforte, eseguire lo script in modalità Verbose e una modalità Debug.
    - Scaricare lo script [qui](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip). 

Per informazioni su requisiti, esempi e parametri disponibili, scaricare lo script ed esaminare il file README. Dopo l'esecuzione dello script di PowerShell, un amministratore o un editor deve esaminare i segnalibri suggeriti e apportare le modifiche necessarie prima della pubblicazione.