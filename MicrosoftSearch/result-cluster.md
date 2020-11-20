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
ms.openlocfilehash: eac4180a247fe17b4e86b57a69f2b7bdb79e56bb
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367745"
---
# <a name="graph-connectors-result-cluster"></a>Cluster di risultati dei connettori del grafico

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Panoramica del cluster di risultati dei connettori del grafico (anteprima)  

 Con i cluster di risultati dei connettori grafico, le aziende possono cercare contenuto da origini dati di terze parti nella visualizzazione predefinita (la scheda tutti) in SharePoint e Office.com.

I cluster di risultati aiutano gli utenti a individuare tutti i contenuti di terze parti (previoulsy collegato a un singolo connettore e verticale) in un'unica posizione. I risultati mostrati in un cluster di risultati vengono raggruppati in base al modo in cui l'amministratore tenant le configura in un verticale di ricerca.  

## <a name="how-connector-results-are-selected-and-displayed"></a>Modalità di selezione e visualizzazione dei risultati del connettore

I risultati del connettore forniti nel cluster di risultati sono derivati da singoli verticali di ricerca con contenuto del connettore. Ogni verticale di ricerca fornisce una serie di risultati rilevanti che diventeranno un cluster di risultati candidato. I risultati rilevanti vengono scelti in base alla proprietà "title", al frammento di risultati e al componente contenuto di ogni elemento.

Per garantire l'individuazione del contenuto dai verticali di ricerca, è consigliabile fornire titoli significativi per gli elementi. Questo incide positivamente sull'arbitrato dei candidati del cluster di risultati e sulla probabilità che il contenuto venga visualizzato in un cluster di risultati. Ad esempio, evitare l'utilizzo di ID come valori per la proprietà "title" a meno che gli utenti non utilizzino gli ID per cercare il contenuto.

La frequenza con cui viene visualizzato un cluster di risultati varia in base a fattori quali il numero di verticali di ricerca configurati e il tipo di contenuto. Se si seleziona o si ignorano i risultati dei cluster di risultati, verranno forniti implicitamente suggerimenti che consentiranno di regolare l'attivazione di cluster di risultati nel tempo.

L'esperienza dei risultati di ricerca per gli elementi del connettore mostrati nel cluster di risultati è generata dal sistema e non utilizza layout dei risultati personalizzati. Se si desidera che i risultati vengano visualizzati nel cluster di risultati, è necessario dichiarare la proprietà "title" e il contenuto dell'elemento durante la registrazione della connessione.

## <a name="enable-result-clusters"></a>Abilitare i cluster di risultati
  
L'esperienza del cluster di risultati è disattivata per impostazione predefinita.  
Seguire questa procedura per abilitare l'esperienza a livello dell'organizzazione:

Interfaccia di amministrazione di Microsoft 365

1. Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/)passare a **Impostazioni** di  >  **ricerca &**  >  verticale di **personalizzazione** dell'Intelligence  >  **Verticals**.  
2. Seleziona la sezione **tutto** verticale e vai a **Mostra i risultati del connettore** . Attiva l'esperienza a livello di sito.

SharePoint

1. Nel sito di SharePoint in cui si desidera utilizzare il cluster di risultati, passare a **Impostazioni**.
2. Vai a **informazioni sito** > **Visualizza tutte le impostazioni del sito**.
3. Andare alla sezione ricerca di Microsoft, quindi selezionare **configura Microsoft Search per la raccolta siti**.
4. Nel riquadro di spostamento, passare a **esperienza personalizzata**, quindi selezionare **verticali**.
5. Selezionare la verticale **tutto** , quindi Abilita **Mostra risultati connettore**.

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>Visualizzare l'esperienza del cluster di risultati dopo che è stata abilitata

Dopo aver attivato l'esperienza del cluster di risultati, potrebbero essere necessari alcuni minuti prima che sia possibile visualizzarla. Se si desidera che l'esperienza venga immediatamente configurata, è possibile aggiungere *cacheClear = true* all'URL in SharePoint e Office.
