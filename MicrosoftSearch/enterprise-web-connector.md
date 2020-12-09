---
title: Connettore siti Web Enterprise per Microsoft Search
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
description: Configurare il connettore dei siti Web dell'organizzazione per Microsoft Search
ms.openlocfilehash: 443e903e0fa371d2a056fd4bf06310eb2627b11c
ms.sourcegitcommit: 031e7c595496d9faed9038725b04f3c8b5f9ccbd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604774"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a>Connettore siti Web Enterprise

Con il connettore siti Web Enterprise, l'organizzazione può indicizzare articoli e **contenuti dai propri siti Web interni**. Dopo aver configurato il connettore e aver sincronizzato il contenuto del sito Web, gli utenti finali possono cercare il contenuto proveniente da qualsiasi client di ricerca di Microsoft.

Questo articolo è per gli amministratori di [Microsoft 365](https://www.microsoft.com/microsoft-365) o per tutti coloro che configurano, eseguono e monitorano un connettore di siti Web dell'organizzazione. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.  

## <a name="connection-settings"></a>Impostazioni di connessione

Per connettersi all'origine dati, è necessario immettere l'URL radice del sito Web, selezionare un'origine di ricerca per indicizzazione e il tipo di autenticazione che si desidera utilizzare: None, autenticazione di base o OAuth 2,0 con [Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/). Dopo aver completato queste informazioni, fare clic su Test Connection per verificare le impostazioni.

### <a name="url"></a>URL

Utilizzare il campo URL per specificare la radice del sito Web che si desidera sottoporre a ricerca per indicizzazione. Il connettore dei siti Web dell'organizzazione utilizzerà questo URL come punto iniziale e seguirà tutti i collegamenti da questo URL per la ricerca per indicizzazione.

### <a name="crawl-mode-cloud-or-on-premises-preview"></a>Modalità di ricerca per indicizzazione: cloud o locale (anteprima)

La modalità di ricerca per indicizzazione determina il tipo di siti Web che si desidera indicizzare, ovvero cloud o locale. Per i siti Web Cloud, selezionare **cloud** come modalità di ricerca per indicizzazione.

Inoltre, il connettore supporta la ricerca per indicizzazione dei siti Web locali. Questa modalità è in anteprima. Per accedere ai dati locali, è necessario innanzitutto installare e configurare l'agente del connettore grafico. Per ulteriori informazioni, vedere [Graph Connector Agent](https://docs.microsoft.com/microsoftsearch/on-prem-agent).

Per i siti Web locali, selezionare **agente** come modalità di ricerca per indicizzazione e nel campo **agente su-Prem** scegliere l'agente del connettore grafico installato e configurato in precedenza.  

![Schermata del riquadro delle impostazioni di connessione per Enterprise Web Connector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)

### <a name="authentication"></a>Autenticazione

L'autenticazione di base richiede un nome utente e una password. Creare questo account bot utilizzando l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).

OAuth 2,0 con [Azure ad](https://docs.microsoft.com/azure/active-directory/) richiede un ID risorsa, un ID client e un segreto client. OAuth 2,0 funziona solo con la modalità cloud.

Per ulteriori informazioni, vedere [autorizzare l'accesso alle applicazioni Web di Azure Active Directory tramite OAuth 2,0 Code Grant Flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code). Registrarsi con i valori seguenti:

**Nome:** Microsoft Search <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

Per ottenere i valori per la risorsa, client_id e client_secret, andare a **utilizzare il codice di autorizzazione per richiedere un token di accesso** nella pagina Web URL di reindirizzamento.

Per ulteriori informazioni, vedere [Guida introduttiva: registrare un'applicazione con la piattaforma Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="support-for-robotstxt"></a>Supporto per robots.txt

Il connettore verifica se esiste un file di robots.txt per il sito radice e, se presente, seguirà e rispetterà le indicazioni rilevate all'interno di tale file. Se non si desidera che il connettore venga sottoposto a ricerca per indicizzazione di determinate pagine o directory del sito, è possibile richiamare tali pagine o directory nelle dichiarazioni "non consentite" nel file di robots.txt.

## <a name="add-urls-to-exclude"></a>Aggiungere URL da escludere

Facoltativamente, è possibile creare un **elenco di esclusione** per escludere che alcuni URL vengano sottoposti a ricerca per indicizzazione se tale contenuto è sensibile o meno. Per creare un elenco di esclusione, passare all'URL radice. È possibile aggiungere gli URL esclusi all'elenco durante il processo di configurazione.

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca

Il connettore dei siti Web dell'organizzazione supporta solo le autorizzazioni di ricerca visibili a **tutti**. I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione.

## <a name="assign-property-labels"></a>Assegnare etichette delle proprietà

È possibile assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni. Anche se questo passaggio non è obbligatorio, l'utilizzo di alcune etichette di proprietà migliorerà la pertinenza della ricerca e assicurerà risultati di ricerca più accurati per gli utenti finali.

## <a name="manage-schema"></a>Gestione dello schema

Nella schermata **Gestisci schema** è possibile modificare gli attributi dello schema (**Queryable**, **Searchable**, **Retrievable** e **per affinamento ricerca**) associati alle proprietà, aggiungere alias facoltativi e scegliere la proprietà **Content** .

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento

Il connettore dei siti Web dell'organizzazione supporta solo un aggiornamento completo. Questo significa che il connettore rieseguirà la ricerca per indicizzazione di tutto il contenuto del sito Web durante ogni aggiornamento. Per assicurarsi che il connettore abbia un tempo sufficiente per eseguire la ricerca per indicizzazione del contenuto, è consigliabile impostare un intervallo di pianificazione di aggiornamento di grandi dimensioni. È consigliabile eseguire un aggiornamento pianificato tra una e due settimane.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Quando si legge il contenuto del sito Web, la ricerca per indicizzazione potrebbe incontrare alcuni errori di origine, che sono rappresentati dai codici di errore dettagliati riportati di seguito. Per ottenere ulteriori informazioni sui tipi di errori, passare alla pagina dei **Dettagli dell'errore** dopo aver selezionato la connessione. Fare clic sul **codice di errore** per visualizzare gli errori più dettagliati. Fare riferimento anche a [gestione del connettore](https://docs.microsoft.com/microsoftsearch/manage-connector) per ulteriori informazioni.

 Codice di errore dettagliato | Messaggio di errore
 --- | ---
 6001 | Il sito che si sta tentando di indicizzare non è raggiungibile
 6005 | La pagina di origine che si sta tentando di indicizzare è stata bloccata secondo robots.txt configurazione.
 6008 | Impossibile risolvere il DNS
 6009 | Per tutti gli errori sul fronte client (ad eccezione di HTTP 404, 408), vedere i codici di errore HTTP 4xx per informazioni dettagliate.
 6013 | Non è stato possibile trovare la pagina di origine che si sta tentando di indicizzare. (Errore HTTP 404)
 6018 | La pagina di origine non risponde e la richiesta è scaduta. (Errore HTTP 408)
 6021 | La pagina di origine che si sta tentando di indicizzare non ha contenuto testuale nella pagina.
 6023 | La pagina di origine che si sta tentando di indicizzare non è supportata (non una pagina HTML)
 6024 | La pagina di origine che si sta tentando di indicizzare contiene contenuto non supportato.

* Gli errori 6001-6013 si verificano quando l'origine dati non è raggiungibile a causa di un problema di rete o quando l'origine dati viene eliminata, spostata o rinominata. Controllare se i dettagli dell'origine dati forniti sono ancora validi.
* Gli errori 6021-6024 si verificano quando l'origine dati contiene contenuto non testuale nella pagina o quando la pagina non è un codice HTML. Controllare l'origine dati e aggiungere questa pagina in elenco di esclusione o ignorare l'errore.

## <a name="limitations"></a>Limitazioni

Il connettore dei siti Web dell'organizzazione non supporta la ricerca di dati nelle **Web page dinamiche**. Esempi di tali pagine sono presenti in sistemi di gestione del contenuto, quali [confluenza](https://www.atlassian.com/software/confluence) e [Unily](https://www.unily.com/) o database che archiviano il contenuto del sito Web.

## <a name="next-steps"></a>Passaggi successivi

Dopo la pubblicazione della connessione, è necessario personalizzare la pagina dei risultati di ricerca. Per ulteriori informazioni sulla personalizzazione dei risultati della ricerca, vedere [Customize the search results page](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).
