---
title: Cluster di risultati dei connettori
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Dettagli dell'esperienza del cluster di risultati dei connettori
ms.openlocfilehash: ae5528f2e12c9e331b66e821f2a9c03947d788df
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031774"
---
# <a name="graph-connectors-result-cluster"></a>Cluster di risultati dei connettori grafici

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Panoramica del cluster di risultati dei connettori graph (anteprima)  

Con i cluster di risultati dei connettori Graph, le aziende possono cercare contenuto da origini dati di terze parti nella visualizzazione predefinita, la scheda **Tutti,** in SharePoint, Office.com e Microsoft Search in Bing.

I cluster di risultati consentono agli utenti di individuare tutto il contenuto di terze parti in un'unica posizione. I risultati visualizzati in un cluster di risultati sono raggruppati in base alla configurazione verticale di ricerca.

## <a name="how-connector-results-are-selected-and-displayed"></a>Modalità di selezione e visualizzazione dei risultati del connettore

I risultati dei connettori forniti nel cluster di risultati derivano da singoli verticali di ricerca con contenuto del connettore. Ogni verticale di ricerca fornisce un set di risultati pertinenti che diventa un cluster di risultati candidato. I risultati pertinenti vengono scelti in base alla proprietà "title" e alla proprietà "content" di ogni elemento. La proprietà content è contrassegnata *come isContent=true* nello schema.

Per garantire l'individuazione del contenuto dai verticali di ricerca, ti consigliamo di fornire titoli significativi per gli elementi. Ciò influisce positivamente sull'arbitraggio dei candidati del cluster di risultati e sulla probabilità che il contenuto sia visualizzato in un cluster di risultati. Ad esempio, evita l'uso di ID come valori per la proprietà "title" a meno che gli utenti non utilizzino gli ID per cercare il contenuto.

La frequenza di visualizzazione di un cluster di risultati varia in base a fattori quali il numero di verticali di ricerca da configurare e il tipo di contenuto. Interagendo o ignorando un cluster di risultati, gli utenti forniranno implicitamente suggerimenti che ne modificano l'attivazione nel tempo.

L'esperienza dei risultati della ricerca per gli elementi dei connettori mostrati nel cluster di risultati [utilizza](./customize-search-page.md#create-your-own-result-type) i tipi di risultati definiti dall'utente. Se non è configurato alcun tipo di risultato, viene [utilizzato un layout generato](./customize-search-page.md#default-search-result-layout) dal sistema. 

È consigliabile utilizzare la proprietà "title" come titolo del risultato della ricerca e la proprietà "content" come descrizione della ricerca. In questo modo gli utenti potranno ottenere la migliore esperienza attivando in modo accurato il cluster di risultati e i risultati più rilevanti nel cluster. 

## <a name="enable-result-clusters"></a>Abilitare i cluster di risultati
  
L'esperienza del cluster di risultati è disattivata per impostazione predefinita.  

Seguire questa procedura per attivare l'esperienza a livello di organizzazione:

1. Nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com)passare a [**Verticali.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Selezionare il **verticale Tutti,** quindi abilitare **Mostra risultati connettore**. 


Seguire questa procedura per attivare l'esperienza a livello di sito di SharePoint:

1. Nel sito di SharePoint in cui si desidera ottenere l'esperienza del cluster di risultati, passare a **Impostazioni**.
2. Vai a **Informazioni sito** Visualizza tutte le impostazioni > **del sito.**
3. Passare alla sezione Microsoft Search, quindi selezionare **Configura Microsoft Search per questa raccolta siti.**
4. Nel riquadro di spostamento passare a **Esperienza personalizzata,** quindi selezionare **Verticali.**
5. Selezionare il **verticale Tutti,** quindi abilitare **Mostra risultati connettore**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Visualizzare l'esperienza del cluster di risultati dopo che è stato abilitato

Una volta attivata l'esperienza del cluster di risultati, possono essere necessario fino a 12 ore prima di poterla visualizzare. Se si desidera che l'esperienza sia immediata, è possibile aggiungere *cacheClear=true* all'URL in SharePoint e Office.