---
title: Report di utilizzo della ricerca
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.topic: article
ms.service: mssearch
audience: Admin
ms.audience: Admin
ms.date: 07/02/2021
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Esaminare i Microsoft Search di utilizzo
ms.openlocfilehash: 83a2d895ac251affdd5e1c9ea3b0d0fffcecc5a4
ms.sourcegitcommit: 36a699554bfe9debdb9a33e942597cceb575666b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53285559"
---
# <a name="microsoft-search-usage-reports"></a>Microsoft Search Report di utilizzo

I report sull'utilizzo della ricerca consentono di acquisire una maggiore comprensione del funzionamento della ricerca nell'organizzazione. Le informazioni dettagliate generate [](./make-content-easy-to-find.md) da questi report consentono di semplificare l'individuazione e l'azione del contenuto che renderanno la ricerca un'esperienza più utile e piacevole per gli utenti.

> [!IMPORTANT]
> Microsoft Search report di utilizzo sono attualmente in anteprima

I [Microsoft Search](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) di utilizzo includono grafici e tabelle generati dalle ricerche eseguite da SharePoint Home, Office.com e Microsoft Search nelle Bing di ricerca. È possibile visualizzare i dati degli ultimi 31 giorni, al giorno o mensili per l'anno precedente. Questi report vengono semplicemente in fase di implementazione in modo da richiedere tempo per accumulare i dati cronologici.

Una versione precedente di questa pagina includeva i dati delle ricerche eseguite solo per Microsoft Search in Bing in Bing.com. Questi dati sono ora integrati in questi report; è comunque possibile visualizzare la pagina precedente facendo clic sul collegamento nella parte inferiore della pagina per visualizzare le query principali Bing e **la distribuzione delle impression**. Questo collegamento e la pagina precedente verranno rimossi a breve.

> [!div class="mx-imgBorder"]
> ![Dashboard dei report di utilizzo della ricerca](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a>Panoramica dei report di ricerca

| Report | Descrizione |
|:-----|:-----|
|Query Volume|Questo report mostra il numero di query di ricerca eseguite. Utilizzare questo report per identificare le tendenze del volume delle query di ricerca e per determinare i periodi di attività di ricerca elevata e bassa.|
|Principali query|Questo report mostra le query di ricerca maggiormente eseguite. Una query viene aggiunta al report quando la ricerca viene eseguita almeno tre volte con un clic su un risultato. Utilizzare questo report per comprendere i tipi di informazioni che gli utenti stanno cercando.|
|Query abbandonate|Questo report mostra le query di ricerca più popolari che ricevono un click-through basso. Utilizzarlo per identificare le query di ricerca che potrebbero risultare insoddisfacenti per gli utenti e per migliorare le possibilità di individuazione del contenuto. È quindi possibile determinare se la creazione di una risposta, ad esempio un segnalibro, o l'inserimento di nuovo contenuto tramite un connettore di Graph è l'azione giusta.|
|Query senza risultati|Questo report mostra le query di ricerca frequenti che non hanno restituito alcun risultato. Utilizzarlo per identificare le query di ricerca che potrebbero risultare insoddisfacenti per gli utenti e per migliorare le possibilità di individuazione del contenuto. È quindi possibile determinare se la creazione di una risposta, ad esempio un segnalibro, o l'inserimento di nuovo contenuto tramite un connettore di Graph è l'azione giusta.|

>[!NOTE]
>Esiste attualmente un problema noto in cui le query soddisfatte da una risposta come bookmark vengono conteggiate come query abbandonate.

## <a name="viewing-reports"></a>Visualizzazione dei report

Quando si passa alla pagina dei report di utilizzo, tutti i report sono disponibili per la visualizzazione. È possibile utilizzare il filtro data per selezionare un giorno o un mese specifico da visualizzare.

Il download di un report consentirà di visualizzare i report da un intervallo di tempo più ampio. Fai clic sulla freccia di download e seleziona **ultimi 31 giorni** o **ultimi 12 mesi.** Il report viene scaricato come foglio Excel foglio di calcolo. Se è stato selezionato negli ultimi 31 giorni, il foglio di calcolo avrà una singola scheda per ogni giorno. Il download degli ultimi 12 mesi avrà una scheda per ogni mese.

Per visualizzare Bing principali query e report di distribuzione delle impression, fare clic sul collegamento nella pagina.

## <a name="frequently-asked-questions"></a>Domande frequenti

**Quando si selezionano gli ultimi 31 giorni o gli ultimi 12 mesi, perché è necessario scegliere un giorno o un mese specifico.**

La visualizzazione calendario, oggi, nei report di utilizzo di Microsoft Search è un processo in due passaggi. Seleziona innanzitutto l'intervallo di date dall'elenco a discesa (ultimi 31 giorni o ultimi 12 mesi) e quindi seleziona il giorno o il mese di inizio.

Le tabelle query principali, abbandonate e non riuscite mostrano i risultati del giorno o del mese scelto.

**Quando verranno visualizzati i dati aggregati per gli ultimi 7 giorni, gli ultimi 30 giorni e così via... ad esempio Bing report di query principali?**

Stiamo valutando questo tipo di aggregazione e semplificando il filtro degli intervalli di dati per le versioni future di questi report.

**Perché non è possibile visualizzare una suddivisione dei report di utilizzo da diverse app (origini)?**

Attualmente, il filtro in base all'origine non è disponibile. I report combinano le ricerche SharePoint Home e Office.com. La prossima versione includerà il filtro origine in modo da poter visualizzare le metriche specifiche per ogni applicazione.

**Quali altri filtri per i report di utilizzo sono disponibili?**

Stiamo lavorando a filtri aggiuntivi che consentono di dare un senso all'utilizzo della ricerca a un livello più granulare dell'organizzazione. Ad esempio, sarà possibile visualizzare il volume di query per una specifica area geografica o reparto.
