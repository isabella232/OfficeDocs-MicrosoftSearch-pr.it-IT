---
title: Connettore siti Web Enterprise per Microsoft Search
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
description: Configurare il connettore dei siti Web dell'organizzazione per Microsoft Search
ms.openlocfilehash: 3caca53204bfb2cca4209e048a21173f550e3d39
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949878"
---
# <a name="enterprise-websites-connector"></a>Connettore siti Web Enterprise

Con il connettore siti Web Enterprise, l'organizzazione può indicizzare articoli e **contenuti dai propri siti Web interni**. Dopo aver configurato il connettore e aver sincronizzato il contenuto del sito Web, gli utenti finali possono cercare il contenuto proveniente da qualsiasi client di ricerca di Microsoft.

Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitorano un connettore di siti Web dell'organizzazione. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.  

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati 
Per connettersi all'origine dati, è necessario l'URL radice e una forma di autenticazione (autenticazione di base o OAuth 2,0 con Azure AD).

### <a name="root-url"></a>URL radice
L'URL radice è ciò che consente di avviare la ricerca per indicizzazione e viene utilizzato per l'autenticazione. È possibile ottenere l'URL dalla Home page del sito Web che si desidera sottoporre a ricerca per indicizzazione.

### <a name="authentication"></a>Autenticazione 
L'autenticazione di base richiede un nome utente e una password. Creare questo account bot utilizzando l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).

OAuth 2,0 con Azure AD richiede un ID tenant, un ID risorsa, un ID client e un segreto client.
Per ulteriori informazioni, vedere [autorizzare l'accesso alle applicazioni Web di Azure Active Directory tramite OAuth 2,0 Code Grant Flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Registrarsi con i valori seguenti:
* **Nome:** Microsoft Search
* **Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Per ottenere i valori per il tenant denominato, la risorsa, client_id e client_secret, passare a **utilizzare il codice di autorizzazione per richiedere un token di accesso** nella pagina Web URL di reindirizzamento.

Per ulteriori informazioni, vedere [Guida introduttiva: registrare un'applicazione con la piattaforma Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

### <a name="reverse-proxy-url"></a>URL del proxy inverso 
Il connettore dei siti Web dell'organizzazione è basato sul cloud, quindi non accede ai contenuti locali. Per fornire tale accesso, installare un proxy inverso. Un proxy inverso fornisce un accesso sicuro e affidabile ai siti Web locali. È consigliabile utilizzare Azure Application Proxy (AAP).

Il requisito del proxy inverso per l'URL radice e l'autenticazione è lo stesso per il contenuto basato sul cloud, tranne per il fatto che l'URL radice e l'autenticazione sono forniti dal server proxy inverso.

Vedere [considerazioni sulla sicurezza per l'accesso alle app in remoto con il proxy di applicazione Azure ad](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security).

## <a name="select-the-source-properties"></a>Selezionare le proprietà di origine 
Le proprietà di origine sono definite in base al formato dei dati del sito Web dell'organizzazione. Tuttavia, è possibile creare un **elenco di esclusione** che escluda che alcuni URL vengano sottoposti a ricerca per indicizzazione dal momento che il contenuto potrebbe essere sensibile o meno. Per creare un elenco di esclusione, passare all'URL radice. È possibile aggiungere gli URL esclusi all'elenco durante il processo di configurazione.

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca 
Non è disponibile alcun supporto per gli elenchi di controllo di accesso (ACL). Pertanto, si consiglia di connettere solo i siti Web che sono visibili a qualsiasi utente all'interno dell'organizzazione.

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento
Il connettore dei siti Web dell'organizzazione supporta solo una ricerca per indicizzazione completa. Questo significa che il connettore legge tutto il contenuto del sito Web durante ogni ricerca per indicizzazione. Per assicurarsi che il connettore abbia un tempo sufficiente per leggere il contenuto, è consigliabile impostare un intervallo di pianificazione di aggiornamento di grandi dimensioni. È consigliabile eseguire un aggiornamento pianificato tra tre giorni e due settimane.

## <a name="limitations"></a>Limitazioni 
Il connettore dei siti Web dell'organizzazione non supporta la ricerca di dati nelle Web page dinamiche. Esempi di tali pagine sono presenti in sistemi di gestione del contenuto, quali confluenza e Unily o database che archiviano il contenuto del sito Web.