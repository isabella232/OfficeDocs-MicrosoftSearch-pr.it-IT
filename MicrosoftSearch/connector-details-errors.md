---
title: Dettagli ed errori dei connettori
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Dettagli ed errori dei connettori
ms.openlocfilehash: 915723a2a22771e89fdb433b4ddadba76fa91090
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701382"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="view-connection-details-and-errors"></a>Visualizzare i dettagli della connessione ed errori

Per accedere e gestire i connettori, è necessario essere designati come amministratore della ricerca per il tenant. Contattare l'amministratore tenant per eseguire il provisioning del ruolo di amministratore della ricerca.

Passare alla [scheda Connettori nella](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) interfaccia di amministrazione di Microsoft 365 . [](https://admin.microsoft.com)

È possibile visualizzare i dettagli della connessione e gli errori quando si fa clic sulla connessione nella [scheda Connettori](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).  

## <a name="view-your-last-crawl-info"></a>Visualizzare le informazioni sull'ultima ricerca per indicizzazione

Al termine della prima ricerca per indicizzazione incrementale o completa iniziale, gli ultimi valori dei dati di ricerca per indicizzazione vengono visualizzati nell'ultima intestazione della ricerca per indicizzazione nel riquadro dei dettagli. Se non è stata eseguita l'ultima ricerca per indicizzazione, non verranno visualizzate informazioni nell'ultima intestazione della ricerca per indicizzazione. Queste informazioni sull'ultima ricerca per indicizzazione consentono di ottenere informazioni dettagliate sull'esecuzione della ricerca per indicizzazione e di eseguire i passaggi necessari laddove necessario.

I valori dell'ultima ricerca per indicizzazione seguenti saranno disponibili per ogni connessione:

Valore | Descrizione
--- | ---
**Completato alle** | Data e ora dell'ultima ricerca per indicizzazione completata
**Type** | Ricerca per indicizzazione incrementale o completa
**Durata** | Quanto tempo è stato necessario per il completamento dell'ultima ricerca per indicizzazione
**Operazioni riuscite** | Numero di elementi inseriti correttamente nell'ultima ricerca per indicizzazione
**Errori** | Numero di elementi che hanno generato un errore nell'ultima ricerca per indicizzazione

## <a name="monitor-errors"></a>Monitorare gli errori

Per ogni **Active Connector** nella scheda **Connettori,** gli eventuali errori di ricerca per indicizzazione esistenti vengono visualizzati nella **scheda** Errore. Nella scheda sono elencati i codici di errore, il conteggio di ognuna e le opzioni di download del log degli errori. Vedi l'esempio nell'immagine seguente. Selezionare un **codice di errore** per visualizzare i dettagli dell'errore.

![Elenco connettori con un connettore selezionato e riquadro dei dettagli che mostra 3 errori per questo connettore.](media/errormonitoring1.png)

Per visualizzare i dettagli specifici di un errore, selezionarne il codice di errore. Viene visualizzata una schermata con i dettagli dell'errore e un collegamento. Gli errori più recenti vengono visualizzati nella parte superiore. Vedere l'esempio nella tabella seguente.

![Elenco connettori con un connettore selezionato e riquadro dei dettagli che mostra l'elenco degli errori per il connettore.](media/errormonitoring2.png)

Di seguito è riportato l'elenco dei diversi errori che possono essere visualizzati in qualsiasi connessione.

Codice di errore | Messaggio di errore | Soluzione
--- | --- | ---
1000 | L'origine dati non è disponibile. Controllare la connessione Internet o verificare che l'origine dati sia ancora accessibile dal connettore. | Questo errore si verifica quando l'origine dati non è raggiungibile a causa di un problema di rete o quando l'origine dati stessa viene eliminata, spostata o rinominata. Verificare se i dettagli dell'origine dati forniti sono ancora validi.
1001 | Impossibile aggiornare i dati, perché l'origine dati sta limitando il connettore. | Per annullare la limitazione dell'origine dati, verificare se i relativi limiti di scala possono essere aumentati o attendere fino a quando non si verifica un'ora meno pesante del giorno.
1002 | Impossibile eseguire l'autenticazione con l'origine dati. Verificare che le credenziali associate all'origine dati siano corrette. | Fare **clic su** Modifica per aggiornare le credenziali di autenticazione.
1003 | L'account associato al connettore non dispone dell'autorizzazione per accedere all'elemento. |  Verificare che l'account appropriato abbia accesso all'elemento che si desidera indicizzare.
1004 | Impossibile raggiungere il gateway dati locale. Verificare che il servizio gateway sia in esecuzione e che i dettagli del gateway siano aggiornati nella configurazione della connessione. | Controllare il computer con il gateway, aprire l'applicazione Power BI Gateway e verificare che il gateway sia in esecuzione. Verificare che il gateway utilizzi lo stesso account amministratore Microsoft Search, quindi verificare che tutti i dettagli del gateway siano tutti aggiornati nella configurazione della connessione.
1005 | Le credenziali associate a questa origine dati sono scadute. Rinnovare le credenziali e aggiornare la connessione. | Fare **clic su** Modifica per aggiornare le credenziali di autenticazione.
1006 | La versione del gateway non è aggiornata e non supporta più questo connettore. Sarà necessario aggiornare il gateway. | Visitare [Installare un gateway](/data-integration/gateway/service-gateway-install) dati locale per scaricare e installare la versione più recente del gateway di Power BI nel computer contenente il gateway.
1007 | Nessuna licenza Power BI stata rilevata. È necessaria una licenza di Power BI valida per eseguire questa ricerca per indicizzazione. | È necessaria una licenza di Power BI valida per eseguire questa ricerca per indicizzazione. Verificare che l'organizzazione abbia una licenza valida. In caso contrario, riprovare. In caso contrario, ottenere una licenza e riprovare.
1008 | L'utilizzo totale della quota del tenant ha raggiunto il limite. | Prova a eliminare una connessione per liberare parte della quota o a modificare i filtri di inserimento per ottenere meno dati. Se il problema persiste, contattare il supporto tecnico Microsoft.
1009 | L'utilizzo totale della quota per la connessione ha raggiunto il limite. | Prova a modificare i filtri di inserimento per ottenere meno dati. Se il problema persiste, contattare il supporto tecnico Microsoft.
1010 | L'utilizzo totale della quota per l'indicizzazione di gruppi non Azure AD ha raggiunto il limite di 100.000. | Prova a eliminare una connessione per liberare parte della quota o a modificare i filtri di inserimento per ottenere meno dati. Se il problema persiste, contattare il supporto tecnico Microsoft.
1011 | L'Graph [connettore non](graph-connector-agent.md) è raggiungibile o offline. | 
1012 | Autenticazione della connessione non riuscita a causa di una modalità di autenticazione non supportata. | Modificare la connessione per aggiornare le impostazioni di autenticazione per la connessione.
2001 | L'indicizzazione viene limitato a causa di un numero elevato di aggiornamenti nella coda. A seconda della coda, il completamento degli aggiornamenti può richiedere del tempo. | Attendere che la coda venga cancellata.
2002 | Indicizzazione non riuscita a causa della formattazione degli elementi non supportata. | Per ulteriori informazioni, vedere la documentazione specifica del connettore.
2003 | Indicizzazione non riuscita a causa di contenuto di elementi non supportato. | Per ulteriori informazioni, vedere la documentazione specifica del connettore.
2004 | Indicizzazione non riuscita a causa di un elemento o di una dimensione di file non supportata. | Per ulteriori informazioni, vedere la documentazione specifica del connettore.
2005 | Indicizzazione non riuscita perché l'URI è troppo lungo. | Per ulteriori informazioni, vedere la documentazione specifica del connettore.
2006 | Mapping utente non riuscito a causa di una formula di mapping non valida o nessun utente di Azure AD con questa proprietà. | Provare a eliminare e ricreare la connessione con una formula di mapping diversa. 
2007 | Questo elemento non verrà visualizzato in Microsoft Search perché non è stato possibile indicizzare alcuni utenti o gruppi senza l'autorizzazione per visualizzare questo elemento. | 
2008 | Le connessioni non possono avere gruppi non Azure AD con più di 50.000 membri. | Provare a rimuovere gli utenti da un gruppo o a rimuovere gli elementi ACL con tale gruppo dall'inserimento e ricreare la connessione.
2009 | L'indicizzazione dei gruppi non di Azure AD viene temporaneamente sospesa a causa di un numero elevato di richieste. L'indicizzazione verrà ripresa al termine dell'elaborazione delle richieste da parte del sistema. Riprovare più tardi. | 
2010 | Questa connessione non è più valida a causa di un aggiornamento effettuato da Microsoft. Eliminare la connessione e crearne una nuova. | Eliminare la connessione e crearne una nuova.
5000 | Si è verificato un problema. Se il problema persiste, contattare il supporto tecnico. |