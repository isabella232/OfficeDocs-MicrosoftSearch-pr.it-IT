---
title: Connettore siti Web Enterprise per Microsoft Search
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
description: Configurare il connettore dei siti Web dell'organizzazione per Microsoft Search
ms.openlocfilehash: de466d4cc1156f520bb6a5fe3117389bd29f3e78
ms.sourcegitcommit: 8ccbf0ea4463d17f810c2f5b484882869a74a996
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "43793550"
---
# <a name="enterprise-websites-connector"></a>Connettore siti Web Enterprise

Con il connettore siti Web Enterprise, l'organizzazione può indicizzare articoli e **contenuti dai propri siti Web interni**. Dopo aver configurato il connettore e aver sincronizzato il contenuto del sito Web, gli utenti finali possono cercare il contenuto proveniente da qualsiasi client di ricerca di Microsoft.

Questo articolo è per gli amministratori di [Microsoft 365](https://www.microsoft.com/microsoft-365) o per tutti coloro che configurano, eseguono e monitorano un connettore di siti Web dell'organizzazione. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.  

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati 
Per connettersi all'origine dati, è necessario l'URL radice e una forma di autenticazione: autenticazione di base o OAuth 2,0 con [Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/).

### <a name="root-url"></a>URL radice
L'URL radice è ciò che consente di avviare la ricerca per indicizzazione e viene utilizzato per l'autenticazione. È possibile ottenere l'URL dalla Home page del sito Web che si desidera sottoporre a ricerca per indicizzazione.

### <a name="authentication"></a>Autenticazione 
L'autenticazione di base richiede un nome utente e una password. Creare questo account bot utilizzando l'interfaccia di [Amministrazione](https://admin.microsoft.com)di Microsoft 365.

OAuth 2,0 con [Azure ad](https://docs.microsoft.com/azure/active-directory/) richiede un ID tenant, un ID risorsa, un ID client e un segreto client.
Per ulteriori informazioni, vedere [autorizzare l'accesso alle applicazioni Web di Azure Active Directory tramite OAuth 2,0 Code Grant Flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Registrarsi con i valori seguenti:
* **Nome:** Microsoft Search
* **Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Per ottenere i valori per il tenant denominato, la risorsa, client_id e client_secret, andare a **utilizzare il codice di autorizzazione per richiedere un token di accesso** nella pagina Web URL di reindirizzamento.

Per ulteriori informazioni, vedere [Guida introduttiva: registrare un'applicazione con la piattaforma Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

### <a name="reverse-proxy-url"></a>URL del proxy inverso 
Il connettore dei siti Web dell'organizzazione è basato sul cloud, quindi non accede ai contenuti locali. Per fornire tale accesso, installare un proxy inverso. Un proxy inverso fornisce un accesso sicuro e affidabile ai siti Web locali. È consigliabile il [proxy di applicazione di Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

Il requisito del proxy inverso per l'URL radice e l'autenticazione è lo stesso per il contenuto basato sul cloud, tranne per il fatto che l'URL radice e l'autenticazione sono forniti dal server proxy inverso.

Vedere [considerazioni sulla sicurezza per l'accesso alle app in remoto con il proxy di applicazione Azure ad](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security).

## <a name="select-the-source-properties"></a>Selezionare le proprietà di origine 
Le proprietà di origine sono definite in base al formato dei dati del sito Web dell'organizzazione. Tuttavia, è possibile creare un **elenco di esclusione** che escluda che alcuni URL vengano sottoposti a ricerca per indicizzazione se tale contenuto è sensibile o meno. Per creare un elenco di esclusione, passare all'URL radice. È possibile aggiungere gli URL esclusi all'elenco durante il processo di configurazione.

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca 
Non è disponibile alcun supporto per gli elenchi di controllo di accesso (ACL). Pertanto, si consiglia di connettere solo i siti Web che sono visibili a qualsiasi utente all'interno dell'organizzazione.

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento
Il connettore dei siti Web dell'organizzazione supporta solo una ricerca per indicizzazione completa. Questo significa che il connettore legge tutto il contenuto del sito Web durante ogni ricerca per indicizzazione. Per assicurarsi che il connettore abbia un tempo sufficiente per leggere il contenuto, è consigliabile impostare un intervallo di pianificazione di aggiornamento di grandi dimensioni. È consigliabile eseguire un aggiornamento pianificato tra tre giorni e due settimane. 

## <a name="troubleshooting"></a>Risoluzione dei problemi
Se si verifica un errore critico in una connessione, il relativo stato viene visualizzato come non riuscito. Per ottenere ulteriori informazioni sui tipi di errori, passare alla pagina dei dettagli dell'errore dopo aver selezionato la connessione non riuscita.  Fare clic sul codice di errore per visualizzare gli errori più dettagliati. Fare riferimento anche a [gestione del connettore](https://docs.microsoft.com/microsoftsearch/manage-connector) per ulteriori informazioni.

 **Codice di errore dettagliato** | **Messaggio di errore**
 --- | --- 
 6001   | Il sito che si sta tentando di indicizzare non è raggiungibile 
 6005 | La pagina di origine che si sta tentando di indicizzare è stata bloccata dalla configurazione di robots. txt.
 6008 | Impossibile risolvere il DNS
 6009 | Per tutti gli errori sul client (ad eccezione di HTTP 404, 408), vedere i codici di errore HTTP 4xx per informazioni dettagliate.
 6013 | Non è stato possibile trovare la pagina di origine che si sta tentando di indicizzare. (Errore HTTP 404)
 6018 | La pagina di origine non risponde e la richiesta è scaduta. (Errore HTTP 408)
 6021 | La pagina di origine che si sta tentando di indicizzare non ha contenuto testuale nella pagina.
 6023 | La pagina di origine che si sta tentando di indicizzare non è supportata (non una pagina HTML)
 6024 | La pagina di origine che si sta tentando di indicizzare contiene contenuto non supportato.

* Gli errori 6001-6013 si verificano quando l'origine dati non è raggiungibile a causa di un problema di rete o quando l'origine dati viene eliminata, spostata o rinominata. Controllare se i dettagli dell'origine dati forniti sono ancora validi.
* Errori 6021-24 si verifica un errore quando l'origine dati contiene contenuto non testuale nella pagina o quando la pagina non è un codice HTML. Controllare l'origine dati e aggiungere questa pagina in elenco di esclusione o ignorare l'errore.

## <a name="limitations"></a>Limitazioni
Il connettore dei siti Web dell'organizzazione non supporta la ricerca di dati nelle Web page dinamiche. Esempi di tali pagine sono presenti in sistemi di gestione del contenuto, quali [confluenza](https://www.atlassian.com/software/confluence) e [Unily](https://www.unily.com/) o database che archiviano il contenuto del sito Web.
