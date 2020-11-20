---
title: Panoramica sui connettori
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Panoramica dei connettori di Microsoft Graph per Microsoft Search
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367524"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Panoramica dei connettori di Microsoft Graph

[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indicizza tutti i dati di [Microsoft 365](https://www.microsoft.com/microsoft-365) per renderlo ricercabile per gli utenti. Con i connettori di Microsoft Graph, l'organizzazione può indicizzare i dati di terze parti in modo che vengano visualizzati nei risultati di ricerca di Microsoft. Questo espande i tipi di origini di contenuto che possono essere ricercate nelle app per la produttività di Microsoft 365 e nel più vasto ecosistema di Microsoft. I dati di terze parti possono essere ospitati in locale o in un cloud pubblico o privato.

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

Il resto di questo articolo è stato progettato per aiutare gli amministratori di Microsoft 365 a individuare le risorse disponibili per rispondere alle domande seguenti:

* [Quali origini dati possono essere connesse a Microsoft Search?](#what-data-sources-can-be-connected-to-microsoft-search)
* [Come si gestiscono le connessioni?](#how-do-i-manage-my-connections)
* [Quali sono i requisiti di licenza e i termini di utilizzo per i connettori grafico?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [Come si personalizzano e configurano i risultati della ricerca?](#how-do-i-customize-and-configure-search-results)
* [Come eseguire la ricerca dei dati del connettore da un'applicazione personalizzata](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> I connettori Microsoft Graph e le API di Microsoft Search sono ora generalmente disponibili. La prima graduali sarà rivolta ai clienti configurati per la versione di destinazione. Se si desidera utilizzare un connettore grafico nel tenant, è necessario che gli utenti e gli amministratori optino per la [versione di destinazione](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Quali origini dati possono essere connesse a Microsoft Search?

Microsoft fornisce dieci connettori grafico e i nostri partner ecosistemici hanno creato oltre 100 connettori grafico aggiuntivi. È inoltre possibile creare un connettore grafico personalizzato. 

### <a name="graph-connectors-by-microsoft"></a>Connettori del grafico da Microsoft

È possibile connettersi alle origini dati seguenti utilizzando i connettori grafico creati da Microsoft:

<!---Need to add a few links below when docs exist--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* SQL di Azure
* [Siti Web aziendali](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [Condivisione file](fileshare-connector.md)
* Oracle (anteprima)
* [Salesforce (anteprima)](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

La [raccolta dei connettori grafico](connectors-gallery.md) contiene una breve descrizione di ognuno di questi connettori grafico. Se si è pronti per connettere una di queste origini dati al tenant, leggere la [Panoramica dell'installazione](configure-connector.md) e tutti gli altri articoli nella sezione Setup Connectors by Microsoft che si applicano all'origine dati.

### <a name="graph-connectors-by-our-partners"></a>Connettori del grafico da parte dei partner

La [raccolta Microsoft Graph Connectors](connectors-gallery.md) include una breve descrizione di ognuno dei connettori grafico creati dai partner e un collegamento al sito Web di ogni partner. Per ulteriori informazioni, contattare ogni partner direttamente.

### <a name="build-your-own-graph-connector"></a>Creare il proprio connettore grafico

Se si prevede di creare un connettore grafico personalizzato, vedere la [Panoramica dell'API di Microsoft Search in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) per ulteriori informazioni.

## <a name="how-do-i-manage-my-connections"></a>Come si gestiscono le connessioni?

È possibile gestire le connessioni dalla [scheda Connettori](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/). Per ulteriori informazioni, vedere [gestire le connessioni](manage-connector.md) .

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>Quali sono i requisiti di licenza e i termini di utilizzo per i connettori grafico?

Per gli utenti dell'organizzazione è necessaria una licenza valida di Microsoft 365 o Office 365 e una quota sufficiente dei connettori del grafico per visualizzare i dati dei connettori nei risultati della ricerca.

Per ulteriori informazioni, vedere [requisiti di licenza e prezzi](licensing.md) e [condizioni di utilizzo](terms-of-use.md).

## <a name="how-do-i-customize-and-configure-search-results"></a>Come si personalizzano e configurano i risultati della ricerca?

Sono disponibili diversi modi per personalizzare e configurare i risultati della ricerca. Per ulteriori informazioni, vedere gli articoli seguenti:

* [Gestire le tipologie di verticali e i tipi di risultati](customize-search-page.md)
* [Gestire i layout dei risultati della ricerca](customize-results-layout.md)
* [Gestire il cluster di risultati](result-cluster.md)
* [Gestione di filtri personalizzati](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>Come eseguire la ricerca dei dati del connettore da un'applicazione personalizzata

Dopo l'indicizzazione dei dati personalizzati, gli sviluppatori possono [eseguire query su tali dati](https://docs.microsoft.com/graph/search-concept-custom-types). È possibile visualizzare i dati in qualsiasi applicazione. Per ulteriori informazioni, vedere la [Panoramica dell'API di Microsoft Search in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).
