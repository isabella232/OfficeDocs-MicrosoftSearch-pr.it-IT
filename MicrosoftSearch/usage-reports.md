---
title: Report sull'utilizzo della ricerca
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Esaminare i report sull'utilizzo di Microsoft Search
ms.openlocfilehash: ad349e60794f219fa757861081b12a33c6806091
ms.sourcegitcommit: 25b82bce1eaec5803111161b04ee9fd9e82a0bd8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "50072240"
---
# <a name="microsoft-search-usage-reports"></a>Report sull'utilizzo di Microsoft Search

I report sull'utilizzo della ricerca consentono di comprendere meglio il funzionamento della ricerca nell'organizzazione. Le informazioni dettagliate generate [](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find) da questi report consentono di semplificare l'individuazione e l'azione del contenuto per rendere la ricerca un'esperienza più utile e piacevole per gli utenti.

I [report sull'utilizzo di Microsoft Search](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) includono grafici e tabelle generati dalle ricerche eseguite dalla home page di SharePoint e dalle Office.com di ricerca. È possibile visualizzare i dati degli ultimi 31 giorni, al giorno o mensili per l'anno precedente. Questi report vengono semplicemente in fase di distribuzione, quindi sarà necessario del tempo per l'attribuzione dei dati cronologici.

Una versione precedente di questa pagina includeva i dati delle ricerche eseguite per Microsoft Search in Bing in Bing.com. Questi dati verranno integrati in questi report a breve, ma per il momento è comunque possibile visualizzarli facendo clic sul collegamento nella parte inferiore della pagina per visualizzare le query principali di Bing e la distribuzione delle **impression.**

> [!div class="mx-imgBorder"]
> ![Dashboard dei report di utilizzo della ricerca](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>Panoramica dei report di ricerca

| Report | Descrizione |
|:-----|:-----|
|Query Volume|Questo report mostra il numero di query di ricerca eseguite. Utilizzare questo report per identificare le tendenze del volume delle query di ricerca e per determinare i periodi di attività di ricerca elevata e bassa.|
|Principali query|Questo report mostra le query di ricerca maggiormente eseguite. Utilizzare questo report per comprendere i tipi di informazioni che gli utenti stanno cercando.|
|Query abbandonate|Questo report mostra le query di ricerca più popolari che ricevono un click-through basso. Utilizzarlo per identificare le query di ricerca che potrebbero risultare insoddisfacenti per gli utenti e per migliorare le possibilità di individuazione del contenuto. È quindi possibile determinare se la creazione di una risposta, ad esempio un segnalibro o l'inserimento di nuovo contenuto tramite un connettore grafico, è l'azione corretta.|
|Query senza risultati|Questo report mostra le query di ricerca frequenti che non hanno restituito alcun risultato. Utilizzarlo per identificare le query di ricerca che potrebbero risultare insoddisfacenti per gli utenti e per migliorare le possibilità di individuazione del contenuto. È quindi possibile determinare se la creazione di una risposta, ad esempio un segnalibro o l'inserimento di nuovo contenuto tramite un connettore grafico, è l'azione corretta.|

## <a name="viewing-reports"></a>Visualizzazione di report

Quando si passa alla pagina dei report di utilizzo, tutti i report sono disponibili per la visualizzazione. È possibile utilizzare il filtro data per selezionare un giorno o un mese specifico da visualizzare.

Il download di un report consente di visualizzare i report da un intervallo di tempo più ampio. Fai clic sulla freccia per il download e seleziona **gli ultimi 31 giorni** o gli ultimi **12 mesi.** Il report viene scaricato come foglio di calcolo di Excel. Se hai selezionato gli ultimi 31 giorni, il foglio di calcolo avrà una singola scheda per ogni giorno. Il download degli ultimi 12 mesi avrà una scheda per ogni mese.

Per visualizzare le query principali di Bing e i report sulla distribuzione delle impression, fare clic sul collegamento nella pagina.

## <a name="frequently-asked-questions"></a>Domande frequenti

**Quando si selezionano gli ultimi 31 giorni o gli ultimi 12 mesi, perché è necessario scegliere un giorno o un mese specifico.**

La visualizzazione calendario, oggi, nei report di utilizzo di Microsoft Search è un processo in due passaggi. Selezionare innanzitutto l'intervallo di date dall'elenco a discesa (ultimi 31 giorni o 12 mesi), quindi selezionare il giorno o il mese di inizio.

Le tabelle query principali, abbandonate e non riuscite mostrano i risultati del giorno o del mese scelto.

**When will I see aggregate data for past 7 days, past 30 days, etc... Come i report sulle query principali di Bing?**

Stiamo valutando questo tipo di aggregazione e semplificando il filtro degli intervalli di dati per le versioni future di questi report.

**Perché non è possibile visualizzare un'analisi dei report di utilizzo da parte di app (origini) diverse?**

Attualmente, il filtro in base all'origine non è disponibile. I report combinano le ricerche da SharePoint Home e Office.com. La prossima versione includerà il filtro origine in modo da poter visualizzare le metriche specifiche per ogni applicazione.

**Quali altri filtri per i report di utilizzo sono in arrivo?**

We are working on additional filters that will help make sense of search usage at a more granular level of your organization. Ad esempio, sarà possibile visualizzare il volume di query per una specifica area geografica o reparto.

**Perché i report di Microsoft Search in Bing si trova in una pagina separata?**

La modernizzazione della ricerca nelle applicazioni di Office 365 a Microsoft Search ha richiesto l'aggiunta di sistemi diversi in precedenza, inclusa la generazione di report. Questa operazione richiede tempo e abbiamo ritenuto che fosse più importante ottenere questi report ora rispetto all'attesa fino a quando non è stato possibile completare l'integrazione dei dati di Bing. Una volta completata l'integrazione, i dati di tutti gli endpoint di ricerca verranno inclusi negli stessi report.
