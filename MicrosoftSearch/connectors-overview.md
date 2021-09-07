---
title: Panoramica di Microsoft Graph Connectors
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Panoramica dei connettori microsoft Graph per Microsoft Search
ms.openlocfilehash: 0d0a1a89edfbcba0fed167c8b3f7bb2166da9439
ms.sourcegitcommit: 134749c0f3a10f63d667f86dca55656b020b920f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "58923144"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a>Panoramica dei connettori microsoft Graph

[Microsoft Search](./overview-microsoft-search.md) indicizza tutti i [dati Microsoft 365](https://www.microsoft.com/microsoft-365) per renderli ricercabili per gli utenti. Con i connettori Graph Microsoft, l'organizzazione può indicizzare i dati di terze parti in modo che appaino Microsoft Search risultati. Questa funzionalità espande i tipi di origini di contenuto disponibili per la ricerca nelle app di produttività Microsoft 365 e nell'ecosistema Microsoft più ampio. I dati di terze parti possono essere ospitati in locale o nel cloud pubblico o privato.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Questo articolo consente agli Microsoft 365 di individuare le risorse disponibili per rispondere alle domande seguenti:

* [Quali origini dati possono essere connesse Microsoft Search?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Come si gestiscono le connessioni?](#how-do-i-manage-my-connections)
* [Quali sono i requisiti di licenza e le condizioni di utilizzo per i connettori microsoft Graph?](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [Quali sono le funzionalità di anteprima?](#what-are-the-preview-features)
* [Come si personalizzano e si configurano i risultati della ricerca?](#how-do-i-customize-and-configure-search-results)
* [Come è possibile cercare i dati del connettore da un'applicazione personalizzata?](#how-do-i-search-my-connector-data-from-a-custom-application)
* [Come si personalizzano i risultati della ricerca?](#how-do-i-customize-search-results)
* [Quali sono le limitazioni del connettore](#what-are-the-connector-limitations)

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](./overview-microsoft-search.md) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Quali origini dati possono essere connesse Microsoft Search?

Microsoft fornisce 9 connettori e i partner dell'ecosistema hanno creato più di 100 connettori. È inoltre possibile creare un connettore personalizzato.

### <a name="microsoft-graph-connectors-by-microsoft"></a>Connettori Graph Microsoft

È possibile connettersi alle origini dati seguenti utilizzando i connettori creati da Microsoft:

<!---Add links below when new docs are created--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [SQL di Azure e Microsoft SQL Server](MSSQL-connector.md)
* [Siti Web aziendali](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Condivisione file](fileshare-connector.md)
* [SQL Oracle](OracleSQL-connector.md)
* [Salesforce ](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

La [raccolta di Graph](https://www.microsoft.com/microsoft-search/connectors) microsoft contiene una breve descrizione di ognuno di questi connettori. Se si è pronti per connettere una di queste origini dati [](configure-connector.md) al tenant, leggere la panoramica dell'installazione e qualsiasi altro articolo nella sezione Installazione dei connettori da parte di Microsoft che si applicano all'origine dati.

### <a name="microsoft-graph-connectors-by-our-partners"></a>Microsoft Graph connettori dai nostri partner

La [raccolta di Graph](https://www.microsoft.com/microsoft-search/connectors) microsoft include una breve descrizione di ognuno dei connettori creati dai partner e un collegamento al sito Web di ogni partner. Per ulteriori informazioni, contattare direttamente ogni partner.

### <a name="build-your-own-microsoft-graph-connector"></a>Creare un connettore microsoft Graph personalizzato

Se si preferisce, è possibile creare un connettore personalizzato. Per ulteriori informazioni sulla creazione di connettori, vedere [Build your first custom Microsoft Graph connector](/graph/connecting-external-content-build-quickstart).

## <a name="how-do-i-manage-my-connections"></a>Come si gestiscono le connessioni?

È possibile gestire le connessioni dalla [scheda Connettori](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) nella [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/). Per ulteriori informazioni sulla gestione delle connessioni, vedere: [Gestire le connessioni](manage-connector.md).

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a>Quali sono i requisiti di licenza e le condizioni di utilizzo per i connettori?

È necessaria una licenza Microsoft 365 o Office 365 e una quota di connettori sufficiente per consentire agli utenti dell'organizzazione di visualizzare i dati dei connettori nei risultati della ricerca.

Per altre informazioni, vedi [Requisiti di licenza e prezzi](licensing.md) e Condizioni per [l'uso.](terms-of-use.md)

## <a name="what-are-the-preview-features"></a>Quali sono le funzionalità di anteprima?

Anche se i connettori Graph Microsoft e le API Microsoft Search sono ora disponibili in genere, sono disponibili diverse funzionalità in anteprima.

L'insieme di connettori e funzionalità in anteprima include:

* [Azure DevOps connettore](azure-devops-connector.md)
* [Gestire filtri personalizzati](custom-filters.md)
* [Più connessioni in verticale](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a>Come si personalizzano e si configurano i risultati della ricerca?

Esistono molti modi per personalizzare e configurare i risultati della ricerca. Per ulteriori informazioni, vedere gli articoli seguenti:

* [Gestire le tipologie di verticali e i tipi di risultati](customize-search-page.md)
* [Gestire i layout dei risultati della ricerca](customize-results-layout.md)
* [Gestisci cluster dei risultati](result-cluster.md)
* [Gestire filtri personalizzati](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Come è possibile cercare i dati del connettore da un'applicazione personalizzata?

Dopo l'indicizzazione dei dati personalizzati, gli sviluppatori possono [eseguire query su tali dati.](/graph/search-concept-custom-types) È possibile visualizzare i dati in qualsiasi applicazione. Per altre informazioni, vedi [Panoramica dell'API Microsoft Search in Microsoft Graph](/graph/search-concept-overview).

## <a name="how-do-i-customize-search-results"></a>Come si personalizzano i risultati della ricerca?

Il passaggio successivo consiste nel personalizzare i risultati della ricerca come consigliato in questo articolo [Come personalizzare e configurare i risultati della ricerca?](#how-do-i-customize-and-configure-search-results). Per ulteriori informazioni sulla personalizzazione dei risultati della ricerca, vedere [Customize the search results page](customize-search-page.md).

## <a name="what-are-the-connector-limitations"></a>Quali sono le limitazioni del connettore?

* Quando si **pubblica** un connettore creato da Microsoft, la creazione della connessione può richiedere alcuni minuti. Durante questo periodo, lo stato della connessione verrà visualizzato come in sospeso.

* La velocità effettiva di inserimento è limitato a circa quattro elementi al secondo.

* Non è disponibile alcun supporto per gli aggiornamenti dello schema. Dopo aver creato una configurazione di connessione, non è possibile aggiornare lo schema. È possibile solo eliminare e creare di nuovo la connessione.

* Esiste un limite di connessione. Ogni tenant può creare fino a 10 connessioni.

* Non è possibile modificare o modificare una connessione dopo che è stata creata. Se è necessario modificare i dettagli, è necessario eliminare e ricreare la connessione.
