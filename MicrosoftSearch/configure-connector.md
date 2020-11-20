---
title: Configurare il connettore Microsoft-built per Microsoft Search
ms.author: monaray
author: monaray97
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
ms.openlocfilehash: 86ddf0387e3d00a005f25207a322c8470799b76b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367609"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Panoramica dell'installazione dei connettori del grafico da parte di Microsoft 

In questo articolo viene riepilogato il processo di base necessario per utilizzare l'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com) per configurare i connettori del grafico da Microsoft. Il processo di base include i passaggi seguenti:  
<!---Add links to each section in the doc--->

1. Aggiungere un connettore grafico nell'interfaccia di amministrazione di Microsoft 365.
2. Denominare la connessione.
3. Configurare le impostazioni di connessione.
4. Gestire le autorizzazioni di ricerca.
5. Assegnare le etichette delle proprietà.
6. Gestione schema.
7. Scegliere Aggiorna impostazioni.
8. Esaminare la connessione.

È importante tenere presente che il processo di installazione è molto simile per tutti i connettori del grafico da parte di Microsoft, ma non è esattamente lo stesso. **Oltre a leggere questo articolo, leggere il connettore specifico per l'origine dati.**  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: aggiungere un connettore grafico nell'interfaccia di amministrazione di Microsoft 365

Completare la procedura seguente per configurare uno qualsiasi dei connettori Microsoft-built.

1. Accedere all'account di amministratore nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com)
2. Nel riquadro di spostamento, selezionare **Impostazioni**, quindi selezionare **Cerca & Intelligence**. Selezionare la [scheda Connettori](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).
3.  Selezionare **+ Aggiungi**, quindi selezionare l'origine dati desiderata nel menu delle opzioni disponibili.

![Le origini dati disponibili includono: ADL Gen2, siti Web aziendali, Microsoft SQL Server, Azure SQL, database SQL Oracle, ServiceNow, condivisione file, DevOps di Azure e MediaWiki.](media/add-connector.png)

>[! Nota:] è possibile aggiungere un massimo di dieci connessioni grafico a ogni tenant.

## <a name="step-2-name-the-connection"></a>Passaggio 2: denominare la connessione
Sarà necessario specificare gli attributi seguenti: 

* Nome  
* ID connessione 
* Descrizione (facoltativa) 

L'ID di connessione crea proprietà implicite per il connettore. Deve contenere solo caratteri alfanumerici e avere un massimo di 32 caratteri. 

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: configurare le impostazioni di connessione

Il processo di configurazione delle impostazioni di connessione varia in base al tipo di origine dati. Vedere le informazioni specifiche del connettore per il tipo di origine dati che si desidera aggiungere al tenant per completare questo passaggio nel processo di installazione.  

Per ulteriori informazioni sulla connessione a un'origine dati locale, vedere [Install an on-premises Data Gateway](https://aka.ms/configuregateway).

## <a name="step-4-manage-search-permissions"></a>Passaggio 4: gestire le autorizzazioni di ricerca

Gli elenchi di controllo di accesso (ACL, Access Control List) determinano gli utenti dell'organizzazione che possono accedere a ogni elemento di dati.  

Alcuni connettori come [Microsoft SQL](MSSQL-connector.md) e [Azure Data Lake storage Gen2](azure-data-lake-connector.md) supportano nativamente gli ACL di [Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/) .

Altri connettori come [ServiceNow](servicenow-connector.md), [Azure DevOps](azure-devops-connector.md)e [Salesforce](salesforce-connector.md) supportano la sincronizzazione di utenti e gruppi non di Azure ad.  

## <a name="step-5-assign-property-labels"></a>Passaggio 5: assegnare etichette delle proprietà
È possibile assegnare etichette semantiche alle proprietà di origine nella pagina "assegnare etichette delle proprietà". Le etichette sono tag ben noti forniti da Microsoft che forniscono significato semantico. Consentono a Microsoft di integrare i dati del connettore in esperienze di Microsoft 365, ad esempio ricerca avanzata, schede persone, individuazione intelligente e altro ancora.  

Nella tabella seguente sono elencate le etichette attualmente supportate e le relative descrizioni.  

Label | Descrizione
--- | ---  
**titolo** | Il titolo dell'elemento che si desidera visualizzare in Search and other experiences 
**url** | L'URL di destinazione dell'elemento nel sistema di origine 
**createdBy** | Nome della persona che ha creato l'elemento 
**lastModifiedBy** | Nome della persona che ha modificato più di recente l'elemento 
**authors** | Nome delle persone che hanno partecipato/collaborato all'articolo 
**createdDateTime** | Quando è stato creato l'elemento 
**lastModifiedDateTime** | Quando l'elemento è stato modificato più di recente 
**fileName** | Nome dell'elemento del file 
**fileExtension** | Tipo di elemento del file, ad esempio. pdf o. Word 

Le proprietà di questa pagina sono preselezionate in base all'origine dati, ma è possibile modificare questa opzione se esiste una proprietà diversa che è più adatta per una determinata etichetta.  

Il **titolo** dell'etichetta è l'etichetta più importante. È **consigliabile** disporre di una proprietà assegnata a questa etichetta affinché la connessione partecipi all' [esperienza del cluster di risultati](result-cluster.md).

La mappatura erronea delle etichette provocherà un'esperienza di ricerca deteriorata. Per alcune etichette non è possibile assegnare una proprietà.  

## <a name="step-6-manage-schema"></a>Passaggio 6: gestire lo schema

### <a name="content-property"></a>Content, proprietà

È consigliabile selezionare una * * proprietà di contenuto dal menu a discesa delle opzioni oppure mantenere l'impostazione predefinita, se presente. Questa proprietà viene utilizzata per l'indicizzazione full-text del contenuto, la generazione di frammenti di pagina dei risultati della ricerca, la partecipazione del [cluster](result-cluster.md) di risultati, il rilevamento della lingua, il supporto HTML/testo, la classificazione e la pertinenza e la formulazione delle

Se si seleziona una proprietà di contenuto, si avrà la possibilità di utilizzare la proprietà generata dal sistema **ResultSnippet** quando si [Crea il tipo di risultato](customize-results-layout.md). Questa proprietà funge da segnaposto per i frammenti dinamici generati dalla proprietà Content in fase di query. Se si utilizza questa proprietà nel tipo di risultati, i frammenti verranno generati nei risultati della ricerca.

### <a name="creating-aliases-for-source-properties"></a>Creazione di alias per le proprietà di origine

È possibile aggiungere alias alle proprietà sotto la colonna "alias" nella pagina "Gestisci schema". Gli alias sono nomi descrittivi per le proprietà. Vengono utilizzati nelle query e nella creazione di filtri. Vengono inoltre utilizzati per normalizzare le proprietà di origine da più connessioni, in modo da avere lo stesso nome. In questo modo è possibile creare un singolo filtro per un verticale con più connessioni. Per ulteriori informazioni, vedere [personalizzare la pagina dei risultati di ricerca](customize-search-page.md) .  

### <a name="search-schema-attributes"></a>Attributi dello schema di ricerca

È possibile impostare gli attributi dello schema di ricerca per controllare la funzionalità di ricerca di ogni proprietà di origine. Uno schema di ricerca consente di determinare quali risultati vengono visualizzati nella pagina dei risultati di ricerca e quali informazioni possono essere visualizzate e accessibili dagli utenti finali.

Gli attributi dello schema di ricerca sono disponibili per la **ricerca**, per **query**, per il **recupero** e **per affinamento ricerca**. Nella tabella seguente sono elencati tutti gli attributi supportati da Microsoft Graph e vengono illustrate le loro funzioni.

Attributo dello schema di ricerca | Funzione | Esempio
--- | --- | ---
RICERCHE | Consente di eseguire ricerche nel contenuto del testo di una proprietà. Il contenuto della proprietà è incluso nell'indice full-text. | Se la proprietà è **title**, una query per **Enterprise** restituirà le risposte che contengono la parola **Enterprise** in qualsiasi testo o titolo.
QUERY | Esegue una ricerca in base alla query per una corrispondenza per una proprietà specifica. Il nome della proprietà può quindi essere specificato nella query a livello di programmazione o Verbatim. |  Se la proprietà **title** è Queryable, il titolo della query **: Enterprise** è supportato. 
RECUPERATE | È possibile utilizzare solo le proprietà recuperabili nel tipo di risultati e visualizzarle nei risultati della ricerca. |
PER affinamento ricerca | È possibile utilizzare le proprietà di per affinamento ricerca come nella pagina dei risultati di ricerca di Microsoft. | Gli utenti dell'organizzazione possono [filtrare](custom-filters.md) in base a **lastModifiedDateTime** nella pagina dei risultati di ricerca se la proprietà è contrassegnata come per affinamento ricerca durante l'installazione della connessione

Per tutti i connettori, ad eccezione del connettore di condivisione file, è necessario impostare manualmente i tipi personalizzati. Per attivare le funzionalità di ricerca per ogni campo, è necessario uno schema di ricerca mappato a un elenco di proprietà. La procedura guidata consente di selezionare automaticamente uno schema di ricerca basato sul set di proprietà di origine che si desidera scegliere. È possibile modificare questo schema selezionando le caselle di controllo per ogni proprietà e attributo nella pagina schema di ricerca.

![Lo schema per un connettore può essere personalizzato aggiungendo o rimuovendo le funzioni query, Search e retrieve.](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Restrizioni e suggerimenti per le impostazioni dello schema di ricerca

* La proprietà **Content** è solo per le ricerche. Una volta selezionata nell'elenco a discesa, questa proprietà non può essere contrassegnata come **recuperabile** o **Queryable**.

* I problemi di prestazioni significativi si verificano quando i risultati della ricerca eseguono il rendering con la proprietà **Content** . Un esempio è il campo di contenuto di **testo** per un articolo della Knowledge base di [ServiceNow](https://www.servicenow.com) .

* Solo le proprietà contrassegnate come rendering recuperabili nei risultati della ricerca possono essere utilizzate per creare i tipi di risultati moderni (MRTs).

* Solo le proprietà della stringa possono essere contrassegnate come ricercabili.

> [!NOTE]
> Dopo aver creato una connessione, **non è possibile** modificare lo schema. A tale scopo, è necessario eliminare la connessione e crearne uno nuovo.

## <a name="step-7-refresh-settings"></a>Passaggio 7: aggiornare le impostazioni

L'intervallo di aggiornamento determina la frequenza con cui i dati vengono sincronizzati tra l'origine dati e Microsoft Search. Ogni tipo di origine dati presenta una serie diversa di pianificazioni di aggiornamento ottimali, in base alla frequenza con cui i dati vengono modificati e al tipo di modifica.

Esistono due tipi di intervalli di aggiornamento, ovvero l'aggiornamento **completo** e l' **aggiornamento incrementale**, ma gli aggiornamenti incrementali non sono disponibili per alcune origini dati.

Con un aggiornamento completo, il motore di ricerca elabora e indicizza tutti gli elementi nell'origine di contenuto, indipendentemente dalle ricerche per indicizzazione precedenti. Un aggiornamento completo funziona in modo ottimale per queste situazioni:

* Rilevamento di eliminazioni di dati.
* L'aggiornamento incrementale non è stato in grado di aggiornare il contenuto a causa di errori.
* Gli elenchi ACL sono stati modificati.
* Sono state modificate regole di ricerca per indicizzazione.
* Quando lo schema per la connessione è stato aggiornato (gli aggiornamenti dello schema non sono ancora supportati)

Con un **aggiornamento incrementale**, il motore di ricerca è in grado di elaborare e indicizzare solo gli elementi creati o modificati dopo l'ultima ricerca per indicizzazione riuscita. Pertanto, non tutti i dati nell'origine di contenuto vengono reindicizzati. Gli aggiornamenti incrementali funzionano al meglio per rilevare contenuti, metadati, autorizzazioni e altre modifiche.

Gli aggiornamenti incrementali sono molto più veloci degli aggiornamenti completi, in quanto gli elementi non modificati non vengono elaborati. Tuttavia, se si sceglie di eseguire aggiornamenti incrementali, sarà comunque necessario eseguire periodicamente aggiornamenti completi per mantenere una sincronizzazione dei dati accurata tra l'origine di contenuto e l'indice di ricerca.

![Impostazioni di ricerca per indicizzazione incrementali e intere per la ricerca per indicizzazione con incremento a 15 minuti e ricerca per indicizzazione completa](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>Passaggio 8: verifica della connessione

Prima di completare la connessione, è possibile esaminare l'intera configurazione e modificare le impostazioni in base alle esigenze. **Se non è stato ancora fatto, leggere le informazioni specifiche del connettore per l'origine dati.** Selezionare **Finish Updating** quando si è pronti per completare la connessione.

## <a name="how-do-i-know-the-connection-setup-worked"></a>Come si può verificare che l'installazione della connessione abbia avuto esito positivo?

Passare all'elenco delle connessioni pubblicate sotto la scheda **connettori** nell'interfaccia di [Amministrazione](https://admin.microsoft.com). Per informazioni su come effettuare aggiornamenti ed eliminazioni, vedere [gestire il connettore](manage-connector.md).
