---
title: Anteprima connettori
ms.author: v-pamcn
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Informazioni sull'anteprima dei connettori Microsoft Graph per Microsoft Search.
ms.openlocfilehash: 025b4f0d7ad4ecae2909f02687c66938d931a2fc
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949874"
---
# <a name="microsoft-graph-connectors-preview"></a>Anteprima connettori Microsoft Graph

I connettori Microsoft Graph, le API di indicizzazione e le API di ricerca sono attualmente in anteprima. Per accedere alla funzionalità dei connettori, è necessario richiedere di partecipare al programma di anteprima inviando il <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">modulo di iscrizione all'anteprima dei connettori Microsoft Graph</a>. Si tratta di un'anteprima iniziale e non vi è alcuna garanzia a livello di servizio. Si consiglia ai clienti di provare la funzionalità dei connettori e fornire commenti e suggerimenti. Non è consigliabile utilizzare i connettori per scopi di produzione durante il periodo di anteprima.

## <a name="set-up-targeted-release"></a>Configurare la versione di destinazione
Per provare i connettori, è necessario che l'opzione di **rilascio di destinazione** sia impostata per tutti gli utenti dell'organizzazione. Il requisito di rilascio mirato si applica indipendentemente dalla scelta degli ambienti di anteprima seguenti.
Per ulteriori informazioni sull'opzione di rilascio mirato e su come impostarla, vedere <a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">configurare le opzioni di rilascio standard o di destinazione in Office 365</a>.

## <a name="choose-a-preview-environment"></a>Scegliere un ambiente di anteprima 
Per provare connettori, API di indicizzazione e API di ricerca, è consigliabile utilizzare i due metodi seguenti:
1. **Tenant di testing**.  Si consiglia di utilizzare un tenant di test per provare l'anteprima dei connettori di Microsoft Graph.
2. **Raccolta siti di test**. Se non si dispone di un tenant di prova, è possibile creare una raccolta siti di prova per provare la funzionalità di connettori. Per visualizzare i risultati dei connettori senza influire sulle pagine di ricerca in nessun'altra parte dell'organizzazione, personalizzare l'esperienza di ricerca solo per la raccolta siti.

## <a name="preview-limitations"></a>Limitazioni relative all'anteprima
La versione di anteprima presenta le limitazioni seguenti:
* La velocità effettiva di ingestione viene limitata a circa quattro elementi al secondo.
* Non è disponibile alcun supporto per gli aggiornamenti dello schema. Dopo aver creato una configurazione di connessione, non è possibile aggiornare lo schema. È possibile eliminare e ricreare la connessione solo.
* Il contenuto indicizzato viene visualizzato solo nella pagina dei risultati di ricerca in un verticale personalizzato. Questa restrizione si applica al contenuto con tipi personalizzati.
* Prima della disponibilità generale, potrebbe essere necessario eliminare e ricreare qualsiasi connessione configurata durante il periodo di anteprima. Tali connessioni non funzioneranno più se sono incompatibili con le modifiche apportate per migliorare il prodotto.
* Limite connessioni. Ogni tenant è in grado di creare fino a 10 connessioni.
