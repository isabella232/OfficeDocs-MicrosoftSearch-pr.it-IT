---
title: Configurare il connettore di Graph Microsoft per Microsoft Search
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
description: Panoramica della configurazione per i connettori Graph di Microsoft
ms.openlocfilehash: 3b8ae9068b445e09f2df95fb5b29feb5ec3af74b
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701877"
---
<!-- Previous ms.author: monaray -->

<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Panoramica della configurazione per i connettori Graph di Microsoft 

In questo articolo viene illustrato il processo di base necessario per configurare i connettori Graph **da Microsoft** nel interfaccia di amministrazione di Microsoft 365 [.](https://admin.microsoft.com) Il processo si compone delle seguenti fasi:  
<!---Add links to each section in the doc--->

1. [Aggiungere un connettore di Graph nell'interfaccia di amministrazione di Microsoft 365.](#step-1-add-a-graph-connector-in-the-microsoft-365-admin-center)
2. [Assegnare un nome alla connessione](#step-2-name-the-connection)
3. [Configurare le impostazioni di connessione](#step-3-configure-the-connection-settings)
4. [Selezionare le proprietà](#step-4-select-properties)
5. [Gestire le autorizzazioni di ricerca](#step-5-manage-search-permissions)
6. [Assegnare etichette di proprietà](#step-6-assign-property-labels)
7. [Gestire lo schema](#step-7-manage-schema)
8. [Aggiornare le impostazioni.](#step-8-refresh-settings)
9. [Verificare la connessione](#step-9-review-connection)

In questo articolo sono inoltre incluse informazioni sulla risoluzione dei problemi, sulle limitazioni e sui passaggi successivi:

* [Risoluzione dei problemi](#troubleshooting)
* [Limiti](#limitations)
* [Passaggi successivi](#next-steps)

> [!NOTE]
> Il processo di configurazione è simile per tutti i connettori Graph microsoft, ma non è esattamente lo stesso. **Oltre a leggere questo articolo, leggere le informazioni specifiche del connettore per l'origine dati.**  

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nella interfaccia di amministrazione di Microsoft 365

Completare la procedura seguente per configurare uno qualsiasi dei connettori di Graph Microsoft:

1. Accedi al tuo account amministratore nella [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com).

2. Nel riquadro di spostamento selezionare **Impostazioni** e quindi selezionare **Ricerca & intelligence.** Selezionare la [scheda Origini dati](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).

3. Selezionare **+Aggiungi** e quindi selezionare l'origine dati desiderata dal menu delle opzioni disponibili.

   > [!div class="mx-imgBorder"]
   > ![Le origini dati disponibili includono: ADLS Gen2, siti Web di Enterprise, server Microsoft SQL, Azure SQL, database di Oracle SQL, ServiceNow, Condivisione file, Azure DevOps e MediaWiki.](media/add-connector.png)

> [!NOTE]
> È possibile aggiungere un massimo di dieci Graph connessioni a ogni tenant.

## <a name="step-2-name-the-connection"></a>Passaggio 2: assegnare un nome alla connessione

Specificare questi attributi:

* Nome (obbligatorio)
* ID connessione (obbligatorio)
* Descrizione (facoltativo)
* Selezionare la casella di controllo (obbligatorio)

L'ID di connessione crea proprietà implicite per il connettore. Deve contenere solo caratteri alfanumerici e un massimo di 32 caratteri.

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: Configurare le impostazioni di connessione

Il processo di configurazione delle impostazioni di connessione varia in base al tipo di origine dati. Vedere le [informazioni specifiche del](/microsoftsearch/servicenow-connector#step-31-basic-authentication) connettore per il tipo di origine dati che si desidera aggiungere al tenant per completare questo passaggio del processo di installazione.  

Per ulteriori informazioni sulla connessione a un'origine dati locale, vedere [Install an on-premises data gateway](/data-integration/gateway/service-gateway-install).

## <a name="step-4-select-properties"></a>Passaggio 4: Selezionare le proprietà

È possibile scegliere le proprietà che verranno indicizzate da Microsoft Search. 

La query ServiceNow può essere utilizzata per filtrare i dati prima di essere indicizzati in base Microsoft Search; in questo modo si ha un maggiore controllo sui dati che è possibile cercare. Per ulteriori informazioni sulle query ServiceNow, vedere [Learn about ServiceNow queries](https://go.microsoft.com/fwlink/?linkid=2151447). 

## <a name="step-5-manage-search-permissions"></a>Passaggio 5: Gestire le autorizzazioni di ricerca

Gli elenchi di controllo di accesso determinano quali utenti dell'organizzazione possono accedere a ogni elemento.  

Alcuni connettori come [Microsoft SQL](MSSQL-connector.md) e Azure Data Lake [Archiviazione Gen2](azure-data-lake-connector.md) supportano in modo nativo gli ACL [di Azure Active Directory (Azure AD).](/azure/active-directory/)

Altri connettori come [ServiceNow,](servicenow-connector.md) [Azure DevOps](azure-devops-connector.md)e [Salesforce](salesforce-connector.md) supportano la sincronizzazione di utenti e gruppi non di Azure AD.  

La selezione di tutti gli utenti consente a tutti gli utenti dell'organizzazione di visualizzare i risultati della ricerca da questa origine dati.

## <a name="step-6-assign-property-labels"></a>Passaggio 6: Assegnare etichette di proprietà

Puoi assegnare etichette semantiche alle proprietà di origine nella pagina "Assegna etichette di proprietà". Le etichette sono tag noti forniti da Microsoft che forniscono un significato semantico. Consentono a Microsoft di integrare i dati del connettore in Microsoft 365 esperienze quali la ricerca avanzata, le schede utente, l'individuazione intelligente e altro ancora.  

Nella tabella seguente sono elencate le etichette attualmente supportate e le relative descrizioni.  

Etichetta | Descrizione
--- | ---  
**title** | Titolo dell'elemento che si desidera visualizzare nella ricerca e in altre esperienze
**url** | URL di destinazione dell'elemento nel sistema di origine
**Creato da** | Nome della persona che ha creato l'elemento
**Autore ultima modifica** | Nome della persona che ha modificato l'elemento più di recente
**Autori** | Nome delle persone che hanno partecipato/collaborato all'elemento
**Data creazione** | Quando è stato creato l'elemento
**Data ultima modifica** | Quando è stato modificato l'elemento più di recente
**Nome file** | Nome dell'elemento file
**Estensione del file** | Tipo di elemento di file, ad esempio .pdf o .word

Le proprietà di questa pagina sono pre-selezionate in base all'origine dati, ma è possibile modificare questa selezione se esiste una proprietà diversa più adatta per una determinata etichetta.  

Il titolo **dell'etichetta** è l'etichetta più importante. È consigliabile **assegnare** una proprietà a questa etichetta per consentire alla connessione di partecipare all'esperienza [del cluster di risultati.](result-cluster.md)

Il mapping errato delle etichette causerà un peggioramento dell'esperienza di ricerca. Per alcune etichette non è possibile assegnare una proprietà.  

## <a name="step-7-manage-schema"></a>Passaggio 7: Gestire lo schema

### <a name="content-property"></a>Content, proprietà

È consigliabile selezionare una proprietà **del** contenuto dal menu a discesa delle opzioni oppure mantenere l'impostazione predefinita, se presente. Questa proprietà viene utilizzata per l'indicizzazione full-text del contenuto, la generazione di frammenti di pagina dei risultati di ricerca, la partecipazione al [cluster](result-cluster.md) di risultati, il rilevamento della lingua, il supporto HTML/testo, la classificazione e la pertinenza e la formulazione delle query.

Se si seleziona una proprietà di contenuto, sarà possibile utilizzare la proprietà generata dal sistema **ResultSnippet** quando si [crea il tipo di risultato](customize-results-layout.md). Questa proprietà funge da segnaposto per i frammenti di codice dinamici generati dalla proprietà di contenuto in fase di query. Se usi questa proprietà nel tipo di risultati, i frammenti di codice verranno generati nei risultati della ricerca.

### <a name="creating-aliases-for-source-properties"></a>Creazione di alias per le proprietà di origine

È possibile aggiungere alias alle proprietà nella colonna "Alias" della pagina "Gestisci schema". Gli alias sono nomi descrittivi per le proprietà e vengono utilizzati anche nelle query e nella creazione di filtri. Vengono inoltre utilizzati per normalizzare le proprietà di origine da più connessioni in modo che abbia lo stesso nome. In questo modo è possibile creare un singolo filtro per un verticale con più connessioni. Per ulteriori informazioni, vedere [Customize the search results page.](customize-search-page.md)  

### <a name="search-schema-attributes"></a>Attributi dello schema di ricerca

È possibile impostare gli attributi dello schema di ricerca per controllare la funzionalità di ricerca di ogni proprietà di origine. Uno schema di ricerca consente di determinare quali risultati vengono visualizzati nella pagina dei risultati di ricerca e quali informazioni possono essere visualizzate e a cui gli utenti finali possono accedere.

Gli attributi dello schema di ricerca includono **opzioni query,** **ricerca,** **recupero** e **affinamento.** Nella tabella seguente sono elencati tutti gli attributi supportati da Microsoft Graph connettori e vengono illustrate le relative funzioni.

Attributo dello schema di ricerca | Funzione | Esempio
--- | --- | ---
RICERCA | Rende possibile la ricerca del contenuto di testo di una proprietà. Il contenuto delle proprietà è incluso nell'indice full-text. | Se la proprietà è **title**, una query per **Enterprise** restituisce le risposte che contengono la parola **Enterprise** in qualsiasi testo o titolo.
QUERY | Cerca una corrispondenza per una determinata proprietà in base a una query. Il nome della proprietà può quindi essere specificato nella query a livello di programmazione o verbatim. |  Se è possibile eseguire query sulla proprietà **Title,** la query **Title: Enterprise** è supportata.
RETRIEVE | Solo le proprietà recuperabili possono essere utilizzate nel tipo di risultato e visualizzate nel risultato della ricerca. |
AFFINAMENTO RICERCA | L'opzione di affinamento può essere utilizzata come nella Microsoft Search dei risultati. | Gli utenti dell'organizzazione possono [filtrare](custom-filters.md) in **base all'URL** nella pagina dei risultati di ricerca se la proprietà refine viene contrassegnata durante l'installazione della connessione

Per tutti i connettori ad eccezione del connettore condivisione file, i tipi personalizzati devono essere impostati manualmente. Per attivare le funzionalità di ricerca per ogni campo, è necessario uno schema di ricerca mappato a un elenco di proprietà. La connessione guidata seleziona automaticamente uno schema di ricerca in base al set di proprietà di origine scelto. È possibile modificare questo schema selezionando le caselle di controllo per ogni proprietà e attributo nella pagina dello schema di ricerca.

> [!div class="mx-imgBorder"]
> ![Lo schema per un connettore può essere personalizzato aggiungendo o rimuovendo le funzioni Query, Search e Retrieve.](media/manageschema.png)

### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Restrizioni e suggerimenti per le impostazioni dello schema di ricerca

* La **proprietà content** è disponibile solo per la ricerca. Una volta selezionata nell'elenco a discesa, questa proprietà non può essere utilizzata con le opzioni **retrieve** o **query**.

* Si verificano problemi di prestazioni significativi quando viene eseguito il rendering dei risultati della ricerca con **la proprietà del** contenuto. Un esempio è il **campo Contenuto** di testo per un articolo della Knowledge Base [ServiceNow.](https://www.servicenow.com)

* Solo le proprietà contrassegnate come rendering recuperabile nei risultati della ricerca e possono essere utilizzate per creare tipi di risultati moderni (MRT).

* Solo le proprietà stringa possono essere contrassegnate come ricercabili.

> [!NOTE]
> Dopo aver creato una connessione, **non è possibile** modificare lo schema. A tale scopo, è necessario eliminare la connessione e crearne una nuova.

## <a name="step-8-refresh-settings"></a>Passaggio 8: aggiornare le impostazioni

L'intervallo di aggiornamento determina la frequenza di sincronizzazione dei dati tra l'origine dati e Microsoft Search. Ogni tipo di origine dati dispone di un set diverso di pianificazioni di aggiornamento ottimali in base alla frequenza di modifica dei dati e al tipo di modifiche.

Esistono due tipi di intervalli  di aggiornamento, ovvero Aggiornamento completo e **Aggiornamento incrementale,** ma gli aggiornamenti incrementali non sono disponibili per alcune origini dati.

Con un aggiornamento completo, il motore di ricerca elabora e indicizza gli elementi modificati nell'origine di contenuto, indipendentemente dalle ricerche per indicizzazione precedenti. Un aggiornamento completo è ideale per queste situazioni:

* Rilevamento delle eliminazioni di dati.
* L'aggiornamento incrementale ha rilevato errori e non è riuscito.
* Gli ACL sono stati modificati.
* Le regole di ricerca per indicizzazione sono state modificate.
* Lo schema per la connessione è stato aggiornato (gli aggiornamenti dello schema non sono ancora supportati).

Con un **aggiornamento incrementale,** il motore di ricerca può elaborare e indicizzare solo gli elementi creati o modificati dopo l'ultima ricerca per indicizzazione completata. Di conseguenza, non tutti i dati nell'origine di contenuto vengono reindicizzati. Gli aggiornamenti incrementali funzionano meglio per rilevare contenuto, metadati, autorizzazioni e altri aggiornamenti.

Gli aggiornamenti incrementali sono molto più veloci rispetto agli aggiornamenti completi perché gli elementi non modificati non vengono elaborati. Tuttavia, se si sceglie di eseguire aggiornamenti incrementali, è comunque necessario eseguire periodicamente aggiornamenti completi per mantenere la sincronizzazione dei dati corretta tra l'origine di contenuto e l'indice di ricerca.

> [!div class="mx-imgBorder"]
> ![Impostazioni incrementali per la ricerca per indicizzazione e l'intervallo di ricerca per indicizzazione completa che mostrano Incrementale a 15 minuti e Ricerca per indicizzazione completa a 1 settimana.](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-9-review-connection"></a>Passaggio 9: esaminare la connessione

È possibile esaminare l'intera configurazione e modificare le impostazioni in base alle esigenze prima di completare la connessione. **Assicurarsi di leggere le informazioni specifiche del connettore per l'origine dati, se non è già stata eseguita.** Selezionare **Fine aggiornamento** quando si è pronti per completare la connessione.

### <a name="confirm-if-the-connection-setup-worked"></a>Verificare se la configurazione della connessione ha funzionato

Passare all'elenco delle connessioni pubblicate nella **scheda Connettori** nell'interfaccia [di amministrazione.](https://admin.microsoft.com) Per informazioni su come apportare aggiornamenti ed eliminazioni, vedere [Manage your connector](manage-connector.md).

## <a name="troubleshooting"></a>Risoluzione dei problemi
<!---Insert troubleshooting recommendations for this data source-->
Leggere le informazioni specifiche del connettore per l'origine dati. 

> [!NOTE]
> Non tutti gli articoli specifici del connettore includono suggerimenti per la risoluzione dei problemi a questo punto.

## <a name="limitations"></a>Limitazioni
<!---Insert limitations for this data source-->
Per informazioni sulle limitazioni applicabili a tutte le origini dati, vedere [l'articolo Overview of Microsoft Graph connectors.](connectors-overview.md)

Vedere le informazioni specifiche del connettore per l'origine dati per scoprire se si applicano altre limitazioni a quel particolare Graph connettore.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver pubblicato la connessione, è necessario personalizzare la pagina dei risultati della ricerca. Per informazioni sulla personalizzazione dei risultati della ricerca, vedere [Personalizzare la pagina dei risultati della ricerca.](customize-search-page.md)
