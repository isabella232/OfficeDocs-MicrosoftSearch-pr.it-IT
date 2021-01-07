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
description: Informazioni dettagliate sull'esperienza del cluster di risultati dei connettori
ms.openlocfilehash: f2355213a0b1821968c801153841c274e539d72e
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773028"
---
# <a name="graph-connectors-result-cluster"></a>Cluster di risultati dei connettori del grafico

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Panoramica del cluster di risultati dei connettori del grafico (anteprima)  

Con i cluster di risultati dei connettori grafico, le aziende possono cercare contenuto da origini dati di terze parti nella visualizzazione predefinita, la scheda **tutti** , in SharePoint, Office.com e Microsoft Search in Bing.

I cluster di risultati aiutano gli utenti a individuare tutti i contenuti di terze parti in un'unica posizione. I risultati mostrati in un cluster di risultati vengono raggruppati in base alla configurazione verticale della ricerca.

## <a name="how-connector-results-are-selected-and-displayed"></a>Modalità di selezione e visualizzazione dei risultati del connettore

I risultati del connettore forniti nel cluster di risultati sono derivati da singoli verticali di ricerca con contenuto del connettore. Ogni verticale di ricerca fornisce una serie di risultati rilevanti che diventeranno un cluster di risultati candidato. I risultati rilevanti vengono scelti in base alla proprietà "title" e alla proprietà "Content" di ogni elemento. La proprietà Content è contrassegnata come *incontent = true* nello schema.

Per garantire l'individuazione del contenuto dai verticali di ricerca, è consigliabile fornire titoli significativi per gli elementi. Questo incide positivamente sull'arbitrato dei candidati del cluster di risultati e sulla probabilità che il contenuto venga visualizzato in un cluster di risultati. Ad esempio, evitare l'utilizzo di ID come valori per la proprietà "title" a meno che gli utenti non utilizzino gli ID per cercare il contenuto.

La frequenza con cui viene visualizzato un cluster di risultati varia in base a fattori quali il numero di verticali di ricerca configurati e il tipo di contenuto. Interagendo o ignorando un cluster di risultati, gli utenti forniranno implicitamente suggerimenti che ne modificheranno l'attivazione nel tempo.

L'esperienza dei risultati di ricerca per gli elementi del connettore mostrati nel cluster di risultati utilizza i [tipi di risultati](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) definiti dall'utente. Se non è stato configurato alcun tipo di risultato, viene utilizzato un [layout generato dal sistema](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) . 

È consigliabile utilizzare la proprietà "title" come titolo del risultato della ricerca e la proprietà "Content" come descrizione della ricerca. In questo modo si otterrà la migliore esperienza per gli utenti tramite l'attivazione accurata del cluster di risultati e la maggior parte dei risultati rilevanti nel cluster. 

## <a name="enable-result-clusters"></a>Abilitare i cluster di risultati
  
L'esperienza del cluster di risultati è disattivata per impostazione predefinita.  

Seguire questa procedura per abilitare l'esperienza a livello dell'organizzazione:

1. Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com), andare a [**verticali**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Selezionare la verticale **tutto** , quindi Abilita **Mostra risultati connettore**. 


Seguire questa procedura per abilitare l'esperienza a livello di sito di SharePoint:

1. Nel sito di SharePoint in cui si desidera utilizzare il cluster di risultati, passare a **Impostazioni**.
2. Vai a **informazioni sito** > **Visualizza tutte le impostazioni del sito**.
3. Andare alla sezione ricerca di Microsoft, quindi selezionare **configura Microsoft Search per la raccolta siti**.
4. Nel riquadro di spostamento, passare a **esperienza personalizzata**, quindi selezionare **verticali**.
5. Selezionare la verticale **tutto** , quindi Abilita **Mostra risultati connettore**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Visualizzare l'esperienza del cluster di risultati dopo che è stata abilitata

Dopo aver attivato l'esperienza del cluster di risultati, potrebbero essere necessari alcuni minuti prima che sia possibile visualizzarla. Se si desidera che l'esperienza venga immediatamente configurata, è possibile aggiungere *cacheClear = true* all'URL in SharePoint e Office.
