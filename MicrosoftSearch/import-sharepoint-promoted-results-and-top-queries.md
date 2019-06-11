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
description: Utilizzare le query di ricerca di SharePoint per creare risultati di lavoro per Microsoft Search
ms.openlocfilehash: 59d133aceb15c8f1fa75ecc3f35522def4201d0a
ms.sourcegitcommit: 9a9d24b4b7a6f3e80b89086d29fd369ebded0619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2019
ms.locfileid: "34810647"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>Importare i risultati alzati di livello e le query principali di SharePoint

> [!IMPORTANT]
> Questo articolo si applica a Microsoft Search nel portale di amministrazione di Bing. Si sta spostando il portale nell'interfaccia di amministrazione di Microsoft 365 e quindi verrà rimosso. Per iniziare, è consigliabile utilizzare l'interfaccia di amministrazione di Microsoft 365. [Panoramica di Microsoft Search](overview-microsoft-search.md).
    
Per sfruttare le query e le migliori scommesse degli utenti creati in SharePoint, Microsoft Search include due strumenti per importare queste informazioni come segnalibri suggeriti: 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>Importare le regole di query dei risultati Promote da SharePoint

Importare queste regole, in precedenza dette Best Bet, come segnalibri suggeriti. Per renderli disponibili agli utenti, pubblicarli. Il tempo di pubblicazione varia in base al numero di segnalibri selezionati.
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>Importare query di SharePoint principali tramite PowerShell

- Scaricare le query principali da SharePoint. Lo script di PowerShell richiederà le credenziali di amministratore di SharePoint.
    
- Eseguire una ricerca di SharePoint per ognuna delle query principali per ottenere il risultato della ricerca di primo livello.
    
- Aggiungere segnalibri suggeriti al portale di amministrazione.
    
- Le query di SharePoint principali sono candidati eccellenti per i segnalibri. Utilizzare lo script di PowerShell per importarli come segnalibri suggeriti. Questo script esegue le operazioni seguenti:
    - Aggiunge segnalibri suggeriti in base alle query di SharePoint Top per migliorare la copertura del segnalibro di Microsoft Search. Questo script consente di scaricare le query principali accessibili dal portale di amministrazione di SharePoint e quindi di caricarle come segnalibri consigliati per un amministratore da esaminare nel portale di amministrazione di Microsoft Search.
    - Per impostazione predefinita, lo script aggiunge i segnalibri suggeriti al tenant per tutti i mesi disponibili. Ottiene le query principali da un determinato sito Web di amministrazione di SharePoint e le aggiunge a Microsoft Search come segnalibri consigliati. I segnalibri consigliati devono essere approvati da un amministratore o da un editor nel portale di amministrazione prima di essere pubblicati. Quando si esegue questo script, vengono richieste le credenziali per accedere al portale di amministrazione di Microsoft Search.
    - Lo script consente di specificare ulteriori parametri. È possibile, ad esempio, aggiungere segnalibri suggeriti al tenant specificato per le query Top N in ognuno dei mesi disponibili.
    - Facoltativamente, è possibile aggiungere segnalibri suggeriti a un determinato tenant per mesi nell'anno specificato. Questo comando consente di ottenere le query principali per il periodo di tempo specificato dal sito Web di amministrazione di SharePoint e di aggiungerle a Microsoft Search come segnalibri consigliati.
    - Esistono anche numerose altre opzioni e modalità di comando: scaricare query principali da SharePoint in una cartella specificata, eseguire lo script in modalità provvisoria, eseguire lo script in modalità verbose e una modalità di debug.
    - Scaricare lo script [qui](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip). 

Per informazioni sui requisiti, sugli esempi e sui parametri disponibili, scaricare lo script ed esaminare il file README. Dopo l'esecuzione dello script PowerShell, un amministratore o un editor deve rivedere i segnalibri suggeriti e apportare le modifiche necessarie prima che vengano pubblicate.