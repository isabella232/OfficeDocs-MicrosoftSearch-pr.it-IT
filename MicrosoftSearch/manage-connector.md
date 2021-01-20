---
title: Gestione dei connettori Microsoft Graph per Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gestione dei connettori Microsoft Graph per Microsoft Search.
ms.openlocfilehash: 5258f26a5c97be4ee9f90c7a8b2b9bb8fec447bc
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905931"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>Monitorare le connessioni

Per accedere e gestire i connettori, è necessario essere designati come amministratori della ricerca per il tenant. Contattare l'amministratore tenant per eseguire il provisioning dell'utente per il ruolo di amministratore della ricerca.

## <a name="connection-operations"></a>Operazioni di connessione

Passare alla [scheda Connettori](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).

Per ogni tipo di connettore, l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) supporta le operazioni illustrate nella tabella seguente:

Operazione | Connettore basato su Microsoft | Partner o connettore personalizzato
--- | --- | ---
Aggiungere una connessione | : heavy_check_mark: (vedere [Configure your Microsoft-built Connector](configure-connector.md)) | : x: (fare riferimento al partner o all'amministratore del connettore basato su personalizzato)
Eliminazione di una connessione | : heavy_check_mark: | : heavy_check_mark:
Modificare una connessione pubblicata | : heavy_check_mark: nome<br></br> : heavy_check_mark: Descrizione<br></br> : heavy_check_mark: credenziali di autenticazione per l'origine dati esterna<br></br> : heavy_check_mark: credenziali del gateway per l'origine dati locale<br></br> : heavy_check_mark: pianificazione dell'aggiornamento<br></br> | : heavy_check_mark: nome<br></br> : heavy_check_mark: Descrizione
Modificare una connessione di sformo | : heavy_check_mark: | x

## <a name="monitor-your-connection-status"></a>Monitorare lo stato della connessione

Dopo aver creato una connessione, il numero di elementi elaborati viene visualizzato nella scheda **connettori** della pagina di **ricerca di Microsoft** . Una volta completata la ricerca per indicizzazione completa iniziale, viene visualizzato lo stato di avanzamento delle ricerche per indicizzazione incrementali periodiche. In questa pagina vengono fornite informazioni sulle operazioni quotidiane del connettore e una panoramica dei registri e della cronologia degli errori.

Quattro Stati vengono visualizzati nella colonna **stato** su ogni connessione:

* **Sincronizzazione**. Il connettore esegue la ricerca per indicizzazione dei dati dall'origine per indicizzare gli elementi esistenti e apportare eventuali aggiornamenti.

* **Enabled**: la connessione è abilitata e non è in esecuzione una ricerca per indicizzazione attiva. **Data ultima sincronizzazione** indica quando è stata eseguita l'ultima ricerca per indicizzazione riuscita. La connessione è fresca come l'ultima ora di sincronizzazione.

* **Sospesa**. Le ricerche per indicizzazione vengono sospese dagli amministratori tramite l'opzione pause. La ricerca per indicizzazione successiva viene eseguita solo quando riprende manualmente. Tuttavia, i dati provenienti da questa connessione continuano a essere disponibili per la ricerca.

* **Operazione non riuscita**. La connessione ha avuto un errore critico. Questo errore richiede un intervento manuale. L'amministratore deve intraprendere un'azione appropriata in base al messaggio di errore visualizzato. I dati indicizzati fino a quando non si è verificato l'errore sono disponibili per la ricerca.

## <a name="monitor-your-index-quota-utilization"></a>Monitorare l'utilizzo della quota di indice

La quota e il consumo di indice disponibili sono visualizzati nella pagina di destinazione dei connettori.

![Barra di utilizzo della quota di indice](media/quota_utilization.png)

>[!NOTE]
>Durante il periodo di anteprima, ogni organizzazione che prova i connettori del grafico è stata fornita una quota fissa libera di fino a 2 milioni elementi in tutte le connessioni. Con i connettori grafico generalmente disponibili, la quota libera scadrà il 1 ° febbraio 2021 per le organizzazioni che utilizzano i connettori grafico in anteprima.
>I connettori del grafico Microsoft-built etichettati come ["Preview"](connectors-preview.md) non verranno inclusi nella quota totale di indice addebitata per l'organizzazione. Tuttavia, conterà verso il numero massimo di 10 connessioni che è possibile configurare per l'organizzazione e il numero massimo di 7 milioni elementi che l'organizzazione può indicizzare tra le connessioni; ogni connessione è limitata a 700.000 elementi. 

La barra di utilizzo delle quote indicherà vari stati basati sull'utilizzo della quota da parte dell'organizzazione:

Stato | Consumi delle quote
--- | ---
Normale | 1-69%
Alta | 70-89%
Critico | 90%-99%
Full | 100%

Il numero di elementi indicizzati verrà visualizzato anche con ogni connessione. Il numero di elementi indicizzati da ciascuna connessione contribuisce alla quota totale disponibile per l'organizzazione.

Quando si supera la quota di indice per l'organizzazione, tutte le connessioni attive verranno influenzate e tali connessioni funzioneranno nello stato **limite superato** . In questo stato, le connessioni attive  

* Non sarà in grado di aggiungere nuovi elementi.

* Sarà in grado di aggiornare o eliminare gli elementi esistenti.

Per risolvere il problemi, è possibile eseguire una delle operazioni seguenti:

* Informazioni su come acquistare la quota di indice per l'organizzazione in base ai [requisiti di licenza e ai prezzi](licensing.md).

* Identificare le connessioni che dispongono di un numero eccessivo di contenuti che vengono ingeriti e aggiornarli in modo che gli elementi vengano indicizzati in meno per ottenere quote. Per aggiornare la connessione, è necessario eliminare e creare una nuova connessione con un nuovo filtro di ingestione che comporta un numero minore di elementi.

* Eliminare definitivamente una o più connessioni