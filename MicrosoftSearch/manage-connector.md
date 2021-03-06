---
title: Gestire i connettori di Microsoft Graph per Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gestire i connettori di Microsoft Graph per Microsoft Search.
ms.openlocfilehash: aa2e3db8c8dc9155c06f81fc0169dd4bda8f8343
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508833"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>Monitorare le connessioni

Per accedere e gestire i connettori, è necessario essere designati come amministratore della ricerca per il tenant. Contattare l'amministratore tenant per eseguire il provisioning del ruolo di amministratore della ricerca.

## <a name="connection-operations"></a>Operazioni di connessione

Passare alla scheda [Connettori nell'interfaccia](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) di amministrazione di [Microsoft 365.](https://admin.microsoft.com)

Per ogni tipo di connettore, l'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) supporta le operazioni illustrate nella tabella seguente:

Operazione | Connettori di Graph Microsoft | Connettori partner o grafico
--- | --- | ---
Aggiungere una connessione | :heavy_check_mark: (Vedere panoramica [dell'installazione)](configure-connector.md) | :x: (fare riferimento all'esperienza utente dell'amministratore del partner o del connettore personalizzato)
Eliminazione di una connessione | :heavy_check_mark: | :heavy_check_mark:
Modificare una connessione pubblicata | :heavy_check_mark: Nome e descrizione<br></br> :heavy_check_mark: Impostazioni di connessione<br></br> :heavy_check_mark: etichette di proprietà<br></br> :heavy_check_mark: Schema<br></br> :heavy_check_mark: Pianificazione dell'aggiornamento<br></br> | :heavy_check_mark: Nome<br></br> :heavy_check_mark: Descrizione
Modificare una bozza di connessione | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a>Monitorare lo stato della connessione

Dopo aver creato una connessione, il numero di elementi elaborati viene visualizzato nella scheda **Connettori** nella **pagina Microsoft Search.** Al termine della ricerca per indicizzazione completa iniziale, viene visualizzato l'avanzamento delle ricerche per indicizzazione incrementali periodiche. In questa pagina vengono fornite informazioni sulle operazioni quotidiane del connettore e una panoramica dei registri e della cronologia degli errori.

Nella colonna Stato vengono visualizzati quattro **stati** per ogni connessione:

* **Sincronizzazione in esecuzione.** Il connettore esegue la ricerca per indicizzazione dei dati dall'origine per indicizzare gli elementi esistenti e apportare eventuali aggiornamenti.

* **Abilitato:** la connessione è abilitata e non è in esecuzione alcuna ricerca per indicizzazione attiva. **L'ora dell'ultima** sincronizzazione indica quando si è verificata l'ultima ricerca per indicizzazione completata. La connessione è appena stata stabilita come l'ora dell'ultima sincronizzazione.

* **Paused**. Le ricerche per indicizzazione vengono sospese dagli amministratori tramite l'opzione di sospensione. La ricerca per indicizzazione successiva viene eseguita solo quando viene ripresa manualmente. Tuttavia, i dati di questa connessione continuano a essere ricercabili.

* **Failed**. Si è verificato un errore critico nella connessione. Questo errore richiede un intervento manuale. L'amministratore deve eseguire l'azione appropriata in base al messaggio di errore visualizzato. È possibile eseguire ricerche nei dati indicizzati fino a quando non si è verificato l'errore.

## <a name="monitor-your-index-quota-utilization"></a>Monitorare l'utilizzo della quota di indice

La quota di indice e il consumo disponibili vengono visualizzati nella pagina di destinazione dei connettori.

![Barra di utilizzo quota indice](media/quota_utilization.png)

>[!NOTE]
>Durante il periodo di anteprima, a ogni organizzazione che provava i connettori Graph è stata fornita una quota fissa gratuita di un massimo di 2 milioni di elementi in tutte le connessioni. Con la disponibilità generale dei connettori Graph, la quota gratuita scadrà il 1° aprile 2021 per le organizzazioni che hanno utilizzato i connettori Graph in anteprima.
>I connettori Microsoft Graph etichettati come ["Anteprima"](connectors-preview.md) non verranno inclusi nella quota di indice totale addebitata per l'organizzazione. Tuttavia, verrà conteggiato per il numero massimo di 10 connessioni che è possibile configurare per l'organizzazione e il numero massimo di 7 milioni di elementi che l'organizzazione può indicizzare tra le connessioni; ogni connessione è limitata a 700.000 elementi. 

La barra di utilizzo delle quote indicherà diversi stati in base all'utilizzo della quota da parte dell'organizzazione:

Stato | Utilizzo delle quote
--- | ---
Normale | 1-69%
Alta | 70-89%
Critico | 90%-99%
Full | 100%

Con ogni connessione verrà visualizzato anche il numero di elementi indicizzati. Il numero di elementi indicizzati da ogni connessione contribuisce alla quota totale disponibile per l'organizzazione.

Quando viene superata la quota di indice per l'organizzazione, tutte le connessioni attive verranno influenzate e tali connessioni funzioneranno nello **stato limite superato.** In questo stato, le connessioni attive  

* Non sarà possibile aggiungere nuovi elementi.

* Sarà possibile aggiornare o eliminare gli elementi esistenti.

Per risolvere il problema, è possibile eseguire una delle operazioni seguenti:

* Per informazioni su come acquistare la quota di indice per l'organizzazione, vedere [Requisiti di licenza e prezzi.](licensing.md)

* Identificare le connessioni con troppi contenuti inseriti e aggiornarle per indicizzare meno elementi per fare spazio alla quota. Per aggiornare la connessione, è necessario eliminare e creare una nuova connessione con un nuovo filtro di inserimento che comporta un numero minore di elementi.

* Eliminare definitivamente una o più connessioni
