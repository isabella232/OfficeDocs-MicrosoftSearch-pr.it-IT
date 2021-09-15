---
title: Gestire Microsoft Graph Connectors per Microsoft Search
ms.author: mecampos
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Gestire Microsoft Graph Connectors per Microsoft Search.
ms.openlocfilehash: dd82114ff6aa651b57ce1941685840906ecf7318
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "59334534"
---
# <a name="monitor-your-connections"></a>Monitorare le connessioni

Per accedere e gestire i connettori, è necessario essere designati come amministratore della ricerca per il tenant. Contattare l'amministratore tenant per eseguire il provisioning del ruolo di amministratore della ricerca.

## <a name="connection-operations"></a>Operazioni di connessione

Passare alla [scheda Connettori nella](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) interfaccia di amministrazione di Microsoft 365 . [](https://admin.microsoft.com)

Per ogni tipo di connettore, [il interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) supporta le operazioni illustrate nella tabella seguente:

Operazione | Connettori di Graph Microsoft | Partner o Graph connettori
--- | --- | ---
Aggiungere una connessione | :heavy_check_mark: (Vedere Panoramica [dell'installazione](configure-connector.md)) | :x: (Fare riferimento all'esperienza utente dell'amministratore del partner o del connettore personalizzato)
Eliminazione di una connessione | :heavy_check_mark: | :heavy_check_mark:
Modificare una connessione pubblicata | :heavy_check_mark: Nome e descrizione<br></br> :heavy_check_mark: Impostazioni di connessione<br></br> :heavy_check_mark: etichette di proprietà<br></br> :heavy_check_mark: Schema<br></br> :heavy_check_mark: Pianificazione aggiornamento<br></br> | :heavy_check_mark: Name<br></br> :heavy_check_mark: Descrizione
Modificare una bozza di connessione | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a>Monitorare lo stato della connessione

Dopo aver creato una connessione, il numero di elementi elaborati viene visualizzato nella scheda **Connettori** **nella** pagina Microsoft Search. Al termine della ricerca per indicizzazione completa iniziale, viene visualizzato l'avanzamento delle ricerche per indicizzazione incrementali periodiche. In questa pagina vengono fornite informazioni sulle operazioni quotidiane del connettore e una panoramica dei registri e della cronologia degli errori.

Nella colonna Stato vengono visualizzati cinque **stati** per ogni connessione:

* **Sincronizzazione di**. Il connettore esegue la ricerca per indicizzazione dei dati dall'origine per indicizzare gli elementi esistenti e apportare eventuali aggiornamenti.

* **Pronto**: la connessione è pronta e non è in esecuzione alcuna ricerca per indicizzazione attiva. **L'ora dell'ultima** sincronizzazione indica quando si è verificata l'ultima ricerca per indicizzazione completata. La connessione è appena stata stabilita come l'ora dell'ultima sincronizzazione.

* **Paused**. Le ricerche per indicizzazione vengono sospese dagli amministratori tramite l'opzione di sospensione. La ricerca per indicizzazione successiva viene eseguita solo quando viene ripresa manualmente. Tuttavia, i dati di questa connessione continuano a essere ricercabili.

* **Con errori**. Si è verificato un errore critico nella connessione. Questo errore richiede un intervento manuale. L'amministratore deve eseguire l'azione appropriata in base al messaggio di errore visualizzato. I dati indicizzati fino a quando non si è verificato l'errore sono ricercabili.

* **Eliminazione non riuscita.** L'eliminazione della connessione non è riuscita. A seconda del motivo dell'errore, è possibile che i dati siano ancora indicizzati, che la quota degli elementi venga ancora utilizzata e che le ricerche per indicizzazione siano ancora in esecuzione per la connessione. Si consiglia di provare a eliminare di nuovo la connessione in questo stato.

## <a name="monitor-your-index-quota-utilization"></a>Monitorare l'utilizzo della quota di indice

La quota di indice e l'utilizzo disponibili vengono visualizzati nella pagina di destinazione dei connettori.

:::image type="content" alt-text="Barra di utilizzo della quota dell'indice." source="media/quota_utilization.png" lightbox="media/quota_utilization.png":::

La barra di utilizzo delle quote indicherà diversi stati in base all'utilizzo della quota da parte dell'organizzazione:

Stato | Livelli di utilizzo delle quote
--- | --- 
Normale | 0-79%
Alto | 80-89%
Critico | 90%-99%
Full | 100%

Con ogni connessione verrà visualizzato anche il numero di elementi indicizzati. Il numero di elementi indicizzati da ogni connessione contribuisce alla quota totale disponibile per l'organizzazione.

Quando viene superata la quota di indice per l'organizzazione, tutte le connessioni attive verranno influenzate e tali connessioni funzioneranno nello **stato limite superato.** In questo stato, le connessioni attive  

* Non sarà possibile aggiungere nuovi elementi.

* Sarà possibile aggiornare o eliminare elementi esistenti.

Per risolvere il problema, è possibile eseguire una delle operazioni seguenti:

* Per informazioni su come acquistare la quota di indice per l'organizzazione, vedere [Requisiti di licenza e prezzi.](licensing.md)

* Identificare le connessioni con troppo contenuto ingerito e aggiornarle in modo da indicizzare un numero minore di elementi per creare spazio per la quota. Per aggiornare la connessione, è necessario eliminare e creare una nuova connessione con un nuovo filtro di inserimento che comporta un numero minore di elementi.

* Eliminare definitivamente una o più connessioni.
