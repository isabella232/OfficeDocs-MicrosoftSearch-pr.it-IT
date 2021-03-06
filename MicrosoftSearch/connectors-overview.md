---
title: Panoramica dei connettori di Microsoft Graph
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Panoramica dei connettori di Microsoft Graph per Microsoft Search
ms.openlocfilehash: 1b3ea74cf571b1b5a048695633f6b9f698a21bf5
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508914"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a>Panoramica dei connettori di Microsoft Graph

[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indicizza tutti i dati [di Microsoft 365](https://www.microsoft.com/microsoft-365) per renderli ricercabili per gli utenti. Con i connettori di Microsoft Graph, l'organizzazione può indicizzare i dati di terze parti in modo che appaino nei risultati di Microsoft Search. Questa funzionalità espande i tipi di origini di contenuto disponibili per la ricerca nelle app di produttività di Microsoft 365 e nell'ecosistema Microsoft più ampio. I dati di terze parti possono essere ospitati in locale o nel cloud pubblico o privato.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Questo articolo ha lo scopo di aiutare gli amministratori di Microsoft 365 a individuare le risorse disponibili per rispondere alle domande seguenti:

* [Quali origini dati possono essere connesse a Microsoft Search?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Come si gestiscono le connessioni?](#how-do-i-manage-my-connections)
* [Quali sono i requisiti di licenza e le condizioni per l'utilizzo per i connettori graph?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [Quali sono le funzionalità di anteprima?](#what-are-the-preview-features)
* [Come si personalizzano e si configurano i risultati della ricerca?](#how-do-i-customize-and-configure-search-results)
* [Come è possibile cercare i dati del connettore da un'applicazione personalizzata?](#how-do-i-search-my-connector-data-from-a-custom-application)
* [Come si personalizzano i risultati della ricerca?](#how-do-i-customize-search-results)
* [Quali sono le limitazioni del connettore](#what-are-the-connector-limitations)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> I connettori di Microsoft Graph e le API di Microsoft Search sono ora disponibili a livello generale. Le prime implementazioni saranno destinate ai clienti configurati per il rilascio mirato. Se si desidera utilizzare un connettore Graph nel tenant, gli utenti e gli amministratori devono acconsentire esplicitamente [a Targeted Release.](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Quali origini dati possono essere connesse a Microsoft Search?

Microsoft fornisce 9 connettori Graph e i partner dell'ecosistema hanno creato più di 100 connettori Graph. È inoltre possibile creare un connettore Graph personalizzato.

### <a name="graph-connectors-by-microsoft"></a>Connettori di Graph Microsoft

È possibile connettersi alle origini dati seguenti utilizzando i connettori Graph creati da Microsoft:

<!---Add links below when new docs are created--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [SQL di Azure e Microsoft SQL Server](MSSQL-connector.md)
* [Siti Web aziendali](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Condivisione file](fileshare-connector.md)
* [SQL Oracle (anteprima)](OracleSQL-connector.md)
* [Salesforce (anteprima)](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

La [raccolta di connettori del grafico](connectors-gallery.md) contiene una breve descrizione di ognuno di questi connettori di Graph. Se si è pronti per connettere una di queste origini dati [](configure-connector.md) al tenant, leggere la panoramica dell'installazione e gli altri articoli nella sezione Configurazione dei connettori da parte di Microsoft che si applicano all'origine dati.

### <a name="graph-connectors-by-our-partners"></a>Connettori grafici dei partner

La [raccolta di connettori](connectors-gallery.md) di Microsoft Graph include una breve descrizione di ognuno dei connettori Graph creati dai partner e un collegamento al sito Web di ogni partner. Per altre informazioni, contattare direttamente ogni partner.

### <a name="build-your-own-graph-connector"></a>Creare un connettore Graph personalizzato

Se si preferisce, è possibile creare un connettore Graph personalizzato. Per ulteriori informazioni sulla creazione di connettori graph, vedere la panoramica [dell'API Microsoft Search in Microsoft Graph.](https://docs.microsoft.com/graph/search-concept-overview)

## <a name="how-do-i-manage-my-connections"></a>Come si gestiscono le connessioni?

È possibile gestire le connessioni dalla scheda [Connettori nell'interfaccia](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) di amministrazione [di Microsoft 365.](https://admin.microsoft.com/) Per ulteriori informazioni sulla gestione delle connessioni, vedere: [Gestire le connessioni.](manage-connector.md)

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>Quali sono i requisiti di licenza e le condizioni per l'utilizzo per i connettori graph?

È necessaria una licenza di Microsoft 365 o Office 365 valida e una quota sufficiente per i connettori Graph per consentire agli utenti dell'organizzazione di visualizzare i dati dai connettori nei risultati della ricerca.

Per ulteriori informazioni, vedere [Requisiti di licenza e prezzi](licensing.md) e Condizioni per [l'utilizzo.](terms-of-use.md)

## <a name="what-are-the-preview-features"></a>Quali sono le funzionalità di anteprima?

Anche se i connettori di Microsoft Graph e le API di Microsoft Search sono ora disponibili in generale, sono disponibili diverse funzionalità in anteprima.

L'insieme di connettori e funzionalità in anteprima include:

* [Connettore Azure DevOps](azure-devops-connector.md)
* [Connettore Salesforce](salesforce-connector.md)
* [Connettore ServiceNow](servicenow-connector.md) con autorizzazioni di ricerca che utilizzano ACL di origine
* [Gestisci cluster dei risultati](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a>Come si personalizzano e si configurano i risultati della ricerca?

Esistono molti modi per personalizzare e configurare i risultati della ricerca. Per ulteriori informazioni, vedere gli articoli seguenti:

* [Gestire le tipologie di verticali e i tipi di risultati](customize-search-page.md)
* [Gestire i layout dei risultati della ricerca](customize-results-layout.md)
* [Gestisci cluster dei risultati](result-cluster.md)
* [Gestire filtri personalizzati](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Come è possibile cercare i dati del connettore da un'applicazione personalizzata?

Dopo l'indicizzazione dei dati personalizzati, gli sviluppatori possono [eseguire query su tali dati.](https://docs.microsoft.com/graph/search-concept-custom-types) È possibile visualizzare i dati in qualsiasi applicazione. Per ulteriori informazioni, vedere la [panoramica dell'API di Microsoft Search in Microsoft Graph.](https://docs.microsoft.com/graph/search-concept-overview)

## <a name="how-do-i-customize-search-results"></a>Come si personalizzano i risultati della ricerca?

Il passaggio successivo consiste nel personalizzare i risultati della ricerca come consigliato in questo articolo Come [personalizzare e configurare i risultati della ricerca?](#how-do-i-customize-and-configure-search-results). Per ulteriori informazioni sulla personalizzazione dei risultati di ricerca, vedere [Personalizzare la pagina dei risultati di ricerca.](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)

## <a name="what-are-the-connector-limitations"></a>Quali sono le limitazioni del connettore?

* Quando si **pubblica** un connettore creato da Microsoft, la creazione della connessione potrebbe richiedere alcuni minuti. Durante questo periodo, lo stato della connessione sarà in sospeso.

* L'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) non supporta la modifica dello schema di **ricerca** dopo la pubblicazione di una connessione. Per modificare lo schema di ricerca, eliminare la connessione e crearne una nuova.

* La velocità effettiva di inserimento viene limitato a circa quattro elementi al secondo.

* Non è disponibile alcun supporto per gli aggiornamenti dello schema. Dopo aver creato una configurazione di connessione, non è possibile aggiornare lo schema. È possibile eliminare e creare di nuovo la connessione.

* Esiste un limite di connessione. Ogni tenant può creare fino a 10 connessioni.

* Il supporto della modifica per la connessione non è disponibile. Dopo aver creato la connessione, non è possibile modificarla. Se è necessario modificare i dettagli, è necessario eliminare e ricreare la connessione.
