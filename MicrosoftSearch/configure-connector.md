---
title: Configurare il connettore Microsoft-built per Microsoft Search
ms.author: mounika.narayanan
author: monaray
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore Microsoft-built per Microsoft Search
ms.openlocfilehash: 3c54f04c1ac6cc42eef2e27a2b40b6ce92357630
ms.sourcegitcommit: 46303c60e905c89c133278fa41e87055f81a8637
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "44535310"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="set-up-your-microsoft-built-connector-for-microsoft-search"></a>Configurare il connettore Microsoft-built per Microsoft Search

In questo articolo vengono illustrati i passaggi per la configurazione di un connettore basato su Microsoft. Descrive il flusso di configurazione di una connessione nell'interfaccia di [Amministrazione](https://admin.microsoft.com)di Microsoft 365. Per ulteriori informazioni su come configurare connettori basati su Microsoft specifici, vedere gli articoli seguenti:

* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Siti Web aziendali](enterprise-web-connector.md)
* [Condivisione file](file-share-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [ServiceNow](servicenow-connector.md)

## <a name="set-up"></a>Configurazione

Per configurare i connettori Microsoft-built, accedere all'interfaccia di [Amministrazione](https://admin.microsoft.com):

1. Accedere al proprio account con le credenziali per il tenant di testing di [Microsoft 365](https://www.microsoft.com/microsoft-365) .
2. Passare a **Impostazioni**  >  connettori di**ricerca di Microsoft**  >  **Connectors**.
3. Selezionare **Aggiungi un connettore**.
4. Nell'elenco dei connettori disponibili, selezionare il connettore desiderato.

![Le origini dati disponibili includono: ADL Gen2 Connector, Enterprise websites, ServiceNow, file share, Microsoft SQL Server e MediaWiki.](media/addconnector_final.png)

### <a name="name-the-connector"></a>Assegnare un nome al connettore

Per creare una connessione, specificare innanzitutto gli attributi seguenti:

1. Nome della connessione
2. ID connessione
3. Descrizione (facoltativa)

L'ID di connessione crea proprietà implicite per il connettore. Deve contenere solo caratteri alfanumerici e avere un massimo di 32 caratteri.

### <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati

Il processo di connessione dati varia in base al tipo di connettore. Per ulteriori informazioni sulla connessione all'origine dati locale, vedere [Install an on-premises Data Gateway](https://aka.ms/configuregateway).

### <a name="select-source-properties"></a>Selezionare le proprietà di origine

I campi dati impostati dall'origine dati di terze parti come proprietà di origine vengono indicizzati in Microsoft Search. Per modificare queste proprietà, selezionare **modifica proprietà** nella barra laterale a destra della pagina **connettori** . È possibile selezionare **fino a 64 proprietà di origine**.

### <a name="manage-the-search-schema"></a>Gestire lo schema di ricerca

Gli amministratori possono impostare gli attributi dello schema di ricerca per controllare la funzionalità di ricerca di ogni proprietà di origine. Uno schema di ricerca consente di determinare quali risultati vengono visualizzati nella pagina dei risultati di ricerca e quali informazioni possono essere visualizzate e accessibili dagli utenti finali.

Gli attributi dello schema di ricerca includono **ricercabili**, **Queryable**e **recuperabili**. Nella tabella seguente sono elencati tutti gli attributi supportati da Microsoft Graph e vengono illustrate le loro funzioni.

**Attributo dello schema di ricerca** | **Funzione** | **Esempio**
--- | --- | ---
RICERCHE | Consente di eseguire ricerche nel contenuto del testo di una proprietà. Il contenuto della proprietà è incluso nell'indice full-text. | Se la proprietà è **title**, una query per **Enterprise** restituirà le risposte che contengono la parola **Enterprise** in qualsiasi testo o titolo.
QUERY | Esegue una ricerca in base alla query per una corrispondenza per una proprietà specifica. Il nome della proprietà può quindi essere specificato nella query a livello di programmazione o Verbatim. |  Se la proprietà **title** è Queryable, il titolo della query **: Enterprise** è supportato.
RECUPERATE | È possibile utilizzare solo le proprietà recuperabili nel tipo di risultati e visualizzarle nei risultati della ricerca. |

Per tutti i connettori, ad eccezione del connettore di condivisione file, è necessario impostare manualmente i tipi personalizzati. Per attivare le funzionalità di ricerca per ogni campo, è necessario uno schema di ricerca mappato a un elenco di proprietà. La procedura guidata consente di selezionare automaticamente uno schema di ricerca basato sul set di proprietà di origine che si desidera scegliere. È possibile modificare questo schema selezionando le caselle di controllo per ogni proprietà e attributo nella pagina schema di ricerca.

![Lo schema per un connettore può essere personalizzato aggiungendo o rimuovendo le funzioni query, Search e retrieve.](media/manageschema.png)

Queste restrizioni e suggerimenti si applicano alle impostazioni dello schema di ricerca:

* Per i connettori che indicino tipi personalizzati, è consigliabile **non** contrassegnare il campo che contiene il contenuto principale **recuperabile**. Quando i risultati della ricerca eseguono il rendering con quell'attributo di ricerca, si verificano problemi significativi. Un esempio è il campo di contenuto di **testo** per un articolo della Knowledge base di [ServiceNow](https://www.servicenow.com) .
* Solo le proprietà contrassegnate come rendering recuperabili nei risultati della ricerca possono essere utilizzate per creare i tipi di risultati moderni (MRTs).
* Solo le proprietà della stringa possono essere contrassegnate come ricercabili.

> [!Note]
> Dopo aver creato una connessione, **non è possibile** modificare lo schema. A tale scopo, è necessario eliminare la connessione e crearne uno nuovo.

### <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca

Gli elenchi di controllo di accesso (ACL, Access Control List) determinano gli utenti dell'organizzazione che possono accedere a ogni elemento di dati. Il connettore di condivisione file supporta solo gli elenchi ACL che è possibile mappare a [Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/). Tutti gli altri connettori supportano le autorizzazioni di ricerca che sono visibili a tutti gli utenti.

### <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento

La pianificazione di aggiornamento determina la frequenza con cui i dati vengono sincronizzati con l'indice in Microsoft Graph e Microsoft Search. È possibile pianificare l'aggiornamento in due modi: ricerca per indicizzazione completa o ricerca per indicizzazione incrementale.

Con una ricerca per indicizzazione **completa**, il motore di ricerca elabora e indicizza tutti gli elementi nell'origine di contenuto, indipendentemente dalle ricerche per indicizzazione precedenti. La ricerca per indicizzazione completa funziona meglio in queste situazioni:

* È necessario rilevare le eliminazioni di dati.
* La ricerca per indicizzazione incrementale non è riuscita a eseguire la ricerca per errori.
* È necessario un aggiornamento software per Microsoft Search. Gli aggiornamenti modificano lo schema di ricerca.
* Gli elenchi ACL sono stati modificati.
* Sono state modificate regole di ricerca per indicizzazione.

Con una ricerca per **indicizzazione incrementale**, è possibile elaborare e indicizzare solo gli elementi che sono stati creati o modificati dopo l'ultima ricerca per indicizzazione riuscita. Pertanto, non tutti i dati nell'origine di contenuto vengono reindicizzati. Le ricerche per indicizzazione incrementali funzionano meglio per rilevare contenuti, metadati, autorizzazioni e altri aggiornamenti.

Le ricerche per indicizzazione incrementali sono molto più veloci delle ricerche per indicizzazione complete perché non vengono elaborati elementi non modificati. Per mantenere una sincronizzazione accurata dei dati tra l'origine di contenuto e l'indice di ricerca, è necessario eseguire periodicamente entrambe le ricerche per indicizzazione.

Ogni connettore avrà un insieme ottimale di pianificazioni di aggiornamento in base alla frequenza con cui i dati vengono modificati e al tipo di modifica.

![Impostazioni di ricerca per indicizzazione incrementali e intere per la ricerca per indicizzazione con incremento a 15 minuti e ricerca per indicizzazione completa](media/refreshschedule.png)

### <a name="review-connector-settings"></a>Esaminare le impostazioni del connettore

Dopo aver configurato il connettore, l'interfaccia di [Amministrazione](https://admin.microsoft.com) porta a una pagina in cui è possibile rivedere le impostazioni. È possibile tornare indietro nel processo di configurazione per modificare le impostazioni prima di confermare la connessione. Per ulteriori informazioni, vedere [gestire il connettore](manage-connector.md).

## <a name="next-steps-customize-the-search-results-page"></a>Passaggi successivi: personalizzare la pagina dei risultati di ricerca

Con l'interfaccia utente di Microsoft Search (UI), gli utenti finali possono ricercare contenuto dalle app di produttività [microsoft 365](https://www.microsoft.com/microsoft-365) e dall'ecosistema Microsoft più ampio. Un verticale di ricerca si riferisce alle schede visualizzate quando un utente Visualizza i risultati della ricerca in [SharePoint](https://sharepoint.com/), [Microsoft Office](https://Office.com)e Microsoft Search in [Bing](https://Bing.com). È possibile personalizzare i verticali di ricerca per limitare i risultati, in modo che venga visualizzato solo un determinato tipo di risultati della ricerca. Tali verticali vengono visualizzate come una tabulazione nella parte superiore della pagina dei risultati di ricerca. Un tipo di risultato moderno (MRT) è l'interfaccia utente che designa il modo in cui vengono presentati i risultati.

È necessario creare i propri tipi di verticali e di risultati, in modo che gli utenti finali possano visualizzare i risultati della ricerca dalle nuove connessioni. Senza questo passaggio, i dati della connessione non verranno visualizzati nella pagina dei risultati della ricerca.

Per ulteriori informazioni su come creare i verticali e MRTs, vedere Personalizzazione della [pagina dei risultati di ricerca](customize-search-page.md).

## <a name="how-do-i-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo?

Passare all'elenco delle connessioni pubblicate sotto la scheda **connettori** nell'interfaccia di [Amministrazione](https://admin.microsoft.com). Per informazioni su come effettuare aggiornamenti ed eliminazioni, vedere [gestire il connettore](manage-connector.md).
