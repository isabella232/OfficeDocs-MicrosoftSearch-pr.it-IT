---
title: Gestione dei connettori Microsoft Graph per Microsoft Search
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gestione dei connettori Microsoft Graph per Microsoft Search.
ms.openlocfilehash: 5aab310a05d073221918a8aaa80ea1e06c818e51
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949885"
---
# <a name="manage-your-connector-for-microsoft-search"></a>Gestire il connettore per Microsoft Search

Per accedere e gestire i connettori, è necessario essere designati come amministratori della ricerca per il tenant. Contattare l'amministratore tenant per eseguire il provisioning dell'utente per il ruolo di amministratore della ricerca.

## <a name="get-started"></a>Introduzione

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).
2. Passare a **Impostazioni** > **** > **connettori**di ricerca di Microsoft.

Per ogni tipo di connettore, l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) supporta le operazioni illustrate nella tabella seguente:

**Operazione** | **Connettore basato su Microsoft** | **Partner o connettore personalizzato**
--- | --- | ---
Aggiungere una connessione | : heavy_check_mark: (vedere [Configure your Microsoft-built Connector](configure-connector.md)) | : x: (fare riferimento al partner o all'amministratore del connettore basato su personalizzato)
Eliminazione di una connessione | :heavy_check_mark: | :heavy_check_mark:
Modificare una connessione pubblicata | : heavy_check_mark: nome<br></br> : heavy_check_mark: Descrizione<br></br> : heavy_check_mark: credenziali di autenticazione per l'origine dati esterna<br></br> : heavy_check_mark: credenziali del gateway per l'origine dati locale<br></br> : heavy_check_mark: pianificazione dell'aggiornamento<br></br> | : heavy_check_mark: nome<br></br> : heavy_check_mark: Descrizione
Modificare una connessione di sformo | :heavy_check_mark: | x

## <a name="monitor-your-connection-status"></a>Monitorare lo stato della connessione
Dopo aver creato una connessione, il numero di elementi elaborati viene visualizzato nella scheda **connettori** della pagina di **ricerca di Microsoft** . Una volta completata la ricerca per indicizzazione completa iniziale, viene visualizzato lo stato di avanzamento delle ricerche per indicizzazione incrementali periodiche. In questa pagina vengono fornite informazioni sulle operazioni quotidiane del connettore e una panoramica dei registri e della cronologia degli errori.

Quattro Stati vengono visualizzati nella colonna **stato** su ogni connessione:
* **Sincronizzazione**. Il connettore esegue la ricerca per indicizzazione dei dati dall'origine per indicizzare gli elementi esistenti e apportare eventuali aggiornamenti.
* **Enabled**: la connessione è abilitata e non è in esecuzione una ricerca per indicizzazione attiva. **Data ultima sincronizzazione** indica quando è stata eseguita l'ultima ricerca per indicizzazione riuscita. La connessione è fresca come l'ultima ora di sincronizzazione.
* **Sospesa**. Le ricerche per indicizzazione vengono sospese dagli amministratori tramite l'opzione pause. La ricerca per indicizzazione successiva viene eseguita solo quando riprende manualmente. Tuttavia, i dati provenienti da questa connessione continuano a essere disponibili per la ricerca.
* **Operazione non riuscita**. La connessione ha avuto un errore critico. Questo errore richiede un intervento manuale. L'amministratore deve intraprendere un'azione appropriata in base al messaggio di errore visualizzato. I dati indicizzati fino a quando non si è verificato l'errore sono disponibili per la ricerca.

### <a name="monitor-errors"></a>Errori di monitoraggio
Per ogni **connettore attivo** nella scheda **connettori** , tutti gli errori di ricerca per indicizzazione esistenti vengono visualizzati sotto la scheda **errore** . La scheda elenca i codici di errore, il numero di ogni e le opzioni di download dei log degli errori. Vedere l'esempio nell'immagine seguente. Selezionare un **codice di errore** per visualizzare i dettagli dell'errore.

![Elenco connettori con un connettore selezionato e il riquadro dei dettagli che mostra 3 errori per questo connettore.](media/errormonitoring1.png)

Per visualizzare i dettagli specifici di un errore, selezionarne il codice di errore. Viene visualizzata una schermata con informazioni dettagliate sull'errore e un collegamento. Gli errori più recenti vengono visualizzati nella parte superiore. Vedere l'esempio nella tabella seguente.

![Elenco di connettori con un connettore selezionato e il riquadro dei dettagli che mostra l'elenco di errori per il connettore. ](media/errormonitoring2.png)

## <a name="preview-limitations"></a>Limitazioni relative all'anteprima
* Quando si **pubblica** un connettore basato su Microsoft, potrebbero essere necessari alcuni minuti per la creazione della connessione. Durante tale periodo, la connessione Visualizza lo stato in sospeso. Inoltre, non è possibile eseguire l'aggiornamento automatico, quindi è necessario aggiornarlo manualmente.
* L'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) non supporta la visualizzazione e la modifica dello **schema di ricerca** dopo la pubblicazione di una connessione. Per modificare lo schema di ricerca, eliminare la connessione e crearne uno nuovo.
* Quando si gestisce la pianificazione di **aggiornamento**della connessione, viene visualizzato il numero di elementi sincronizzati durante ogni sessione. Tuttavia, la cronologia di sincronizzazione non è disponibile.
