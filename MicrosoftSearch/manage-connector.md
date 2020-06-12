---
title: Gestione dei connettori Microsoft Graph per Microsoft Search
ms.author: mounika.narayanan
author: monaray
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
ms.openlocfilehash: 3e652b9afad78f784ff4c726ecab34bef883d4c3
ms.sourcegitcommit: a8a6c949f249d106f37103e127d2ea7df730f7a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702768"
---
# <a name="manage-your-connector-for-microsoft-search"></a>Gestire il connettore per Microsoft Search

Per accedere e gestire i connettori, è necessario essere designati come amministratori della ricerca per il tenant. Contattare l'amministratore tenant per eseguire il provisioning dell'utente per il ruolo di amministratore della ricerca.

## <a name="get-started"></a>Introduzione

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

### <a name="monitor-errors"></a>Errori di monitoraggio

Per ogni **connettore attivo** nella scheda **connettori** , tutti gli errori di ricerca per indicizzazione esistenti vengono visualizzati sotto la scheda **errore** . La scheda elenca i codici di errore, il numero di ogni e le opzioni di download dei log degli errori. Vedere l'esempio nell'immagine seguente. Selezionare un **codice di errore** per visualizzare i dettagli dell'errore.

![Elenco connettori con un connettore selezionato e il riquadro dei dettagli che mostra 3 errori per questo connettore.](media/errormonitoring1.png)

Per visualizzare i dettagli specifici di un errore, selezionarne il codice di errore. Viene visualizzata una schermata con informazioni dettagliate sull'errore e un collegamento. Gli errori più recenti vengono visualizzati nella parte superiore. Vedere l'esempio nella tabella seguente.

![Elenco di connettori con un connettore selezionato e il riquadro dei dettagli che mostra l'elenco di errori per il connettore. ](media/errormonitoring2.png)

Di seguito è riportato l'elenco dei diversi errori che possono essere visualizzati su qualsiasi connessione. Se queste soluzioni non funzionano, contattare il supporto tecnico o inviarci [commenti e suggerimenti](connectors-feedback.md).

Codice errore | Messaggio di errore | Soluzione
--- | --- | ---
1000 | L'origine dati non è disponibile. Controllare la connessione a Internet o verificare che l'origine dati sia ancora accessibile dal connettore. | Questo errore si verifica quando l'origine dati non è raggiungibile a causa di un problema di rete o quando l'origine dati viene eliminata, spostata o rinominata. Controllare se i dettagli dell'origine dati forniti sono ancora validi.
1001 | Non è possibile aggiornare i dati, in quanto l'origine dati sta strozzando il connettore. | Per delimitare l'origine dati, controllare se i limiti di scalabilità possono essere aumentati o attendere fino a un periodo di tempo meno elevato per il traffico del giorno.
1002 | Non è possibile eseguire l'autenticazione con l'origine dati. Verificare che le credenziali associate a questa origine dati siano corrette. | Fare clic su **modifica** per aggiornare le credenziali di autenticazione.
1003 | L'account associato al connettore non dispone dell'autorizzazione necessaria per accedere all'elemento. |  Verificare che l'account appropriato abbia accesso all'elemento che si desidera indicizzare.
1004 | Impossibile raggiungere il gateway di dati locale. Verificare che il servizio gateway sia in esecuzione e che i dettagli del gateway vengano aggiornati nella configurazione della connessione. | Controllare il computer con il gateway, aprire l'applicazione Power BI gateway e verificare che il gateway sia in esecuzione. Verificare che il gateway utilizzi lo stesso account di amministratore di Microsoft Search, quindi accertarsi che tutti i dettagli del gateway siano tutti aggiornati nella configurazione della connessione.
1005 | Le credenziali associate a questa origine dati sono scadute. Rinnovare le credenziali e aggiornare la connessione. | Fare clic su **modifica** per aggiornare le credenziali di autenticazione.
1006 | La versione del gateway è obsoleta e non supporta più questo connettore. Sarà necessario aggiornare il gateway. | Visitare [installare un gateway di dati locale](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) per scaricare e installare la versione più recente del gateway di Power bi sul computer contenente il gateway.
1007 | Non è stata rilevata alcuna licenza valida Power BI. Per eseguire questa ricerca per indicizzazione, è necessaria una licenza di Power BI valida. | Per eseguire questa ricerca per indicizzazione, è necessaria una licenza di Power BI valida. Verificare che l'organizzazione disponga di una licenza valida. In caso affermativo, riprova. In caso contrario, ottenere una licenza e quindi riprovare.
1008 | L'utilizzo totale della quota del tenant ha raggiunto il limite. Provare a eliminare una connessione per liberare parte della quota o regolare i filtri di ingestione per ottenere meno dati. | Provare a eliminare una connessione per liberare parte della quota o regolare i filtri di ingestione per ottenere meno dati. Se non si risolve il problema, contattare il supporto tecnico Microsoft.
2001 | L'indicizzazione viene limitata a causa di un numero elevato di aggiornamenti nella coda. A seconda della coda, il completamento degli aggiornamenti può richiedere del tempo. | Attendere che la coda venga deselezionata.
2002 | Indicizzazione non riuscita a causa della formattazione degli elementi non supportata. | Per ulteriori informazioni, vedere documentazione specifica del connettore.
2003 | Indicizzazione non riuscita a causa del contenuto di elementi non supportati. | Per ulteriori informazioni, vedere documentazione specifica del connettore.
2004 | La [dimensione del file](https://docs.microsoft.com/microsoftsearch/file-share-connector#content-requirements) è troppo grande per essere indicizzata. Il valore deve essere 100 MB o meno prima dell'elaborazione e non superiore a 4 MB dopo l'elaborazione. Il file viene indicizzato parzialmente in questo caso. Alcune frasi presenti nel file potrebbero non restituire un risultato di ricerca. | Per ulteriori informazioni, vedere [documentazione specifica](https://docs.microsoft.com/MicrosoftSearch/file-share-connector#content-requirements) per la condivisione di file.
5000 | Qualcosa è andato storto. Se questo continua, contattare il supporto. |

## <a name="preview-limitations"></a>Limitazioni relative all'anteprima

* Quando si **pubblica** un connettore basato su Microsoft, potrebbero essere necessari alcuni minuti per la creazione della connessione. Durante tale periodo, la connessione Visualizza lo stato in sospeso. Inoltre, non è possibile eseguire l'aggiornamento automatico, quindi è necessario aggiornarlo manualmente.

* L'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) non supporta la visualizzazione e la modifica dello **schema di ricerca** dopo la pubblicazione di una connessione. Per modificare lo schema di ricerca, eliminare la connessione e crearne uno nuovo.

* Quando si gestisce la pianificazione di **aggiornamento**della connessione, viene visualizzato il numero di elementi sincronizzati durante ogni sessione. Tuttavia, la cronologia di sincronizzazione non è disponibile.
