---
title: Facilitare la ricerca del contenuto con Microsoft Search
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Creare segnalibri, posizioni, domande e risposte per facilitare la ricerca del contenuto dell'organizzazione.
ms.openlocfilehash: 605610264e2068deb6215c3157efc24cf0b0a2fd
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626829"
---
# <a name="make-content-easy-to-find"></a>Facilitare la ricerca del contenuto

Microsoft Search aiuta gli utenti a trovare contenuto pertinente. Si tratta di un modo sicuro per cercare sia il contenuto Web che la rete Intranet. Questo tipo di integrazione tra il Web e le organizzazioni è disponibile solo da Microsoft. Microsoft Search consente agli amministratori di utilizzare le proprie conoscenze di un'organizzazione per semplificare la ricerca di contenuti rilevanti per gli utenti. 

## <a name="components-that-find-content"></a>Componenti che trovano contenuto
In Microsoft Search gli amministratori creano [segnalibri](manage-bookmarks.md), [PowerApps](integrate-powerapps.md), [Q&a](manage-qas.md)e [percorsi](manage-locations.md) che facilitano la ricerca del contenuto. Ognuno dei componenti della ricerca include un titolo, un URL e un set di parole chiave di attivazione.

## <a name="bookmarks"></a>Segnalibri
È possibile creare [segnalibri](manage-bookmarks.md) in pochi passaggi. Ogni segnalibro include un titolo, URL e un set di parole chiave di attivazione. Un segnalibro può avere diverse parole chiave e diversi segnalibri possono condividere la stessa parola chiave. Tuttavia, non è possibile condividere parole chiave riservate. Quando si crea o si modifica un segnalibro, l'indice di ricerca viene aggiornato e il segnalibro è immediatamente disponibile per gli utenti.

Se l'organizzazione ha **promosso i risultati** configurati in [SharePoint](http://sharepoint.com/), è possibile importare tali risultati in Microsoft Search. Con i risultati alzati di grado, è possibile popolare rapidamente i risultati della ricerca, rendere il contenuto disponibile per gli utenti e rendere Microsoft Search più efficace non appena viene configurata. È consigliabile usare i risultati alzati di livello di SharePoint come riferimento per determinare come assegnare un nome e creare i risultati della ricerca rilevanti. 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>Aggiungere o modificare segnalibri tramite le estensioni del browser
Gli amministratori della ricerca possono creare facilmente contenuti di ricerca usando le estensioni del browser. Per aggiungere il sito come segnalibro, installare l'estensione del browser. Passare quindi al sito e aggiungerlo come segnalibro. Per ulteriori informazioni, vedere [Manage Bookmarks](manage-bookmarks.md).

Attualmente, le estensioni del browser sono disponibili per [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) e [Google Chrome](https://www.google.com): 
- Per scaricare l'estensione perimetrale, passare a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Per scaricare l'estensione Chrome, passare a [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="powerapps"></a>PowerApps

Aggiungendo [PowerApps](integrate-powerapps.md) esistenti ai [segnalibri](manage-bookmarks.md), gli utenti possono completare attività quali l'immissione di un periodo di ferie o le spese di segnalazione. 

Con [PowerApps](integrate-powerapps.md), è possibile creare app aziendali che vengono eseguite in un browser o su un telefono o tablet. Non è necessaria alcuna esperienza di codifica. PowerApps funziona in qualsiasi browser e su qualsiasi dispositivo. Sono necessari meno di un minuto per aggiungere. Per ulteriori informazioni su PowerApps, vedere gli articoli seguenti:
- [Apprendimento guidato](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [Documentazione di PowerApps](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Home page di PowerApps](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Aggiungere una PowerApp a un segnalibro

1. Individuare l' [ID dell'app](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) per il PowerApp che si desidera aggiungere.
1. Nell'interfaccia di [Amministrazione](https://admin.microsoft.com)di Microsoft 365, andare a **Settings** > **Microsoft Search**. 
1. Aggiungere un segnalibro o trovare un segnalibro esistente a cui si vuole aggiungere una PowerApp.
1. In **Impostazioni segnalibro**selezionare **Power app**. Quindi seleziona **Aggiungi un'applicazione di alimentazione**.
1. Immettere l' **ID app**. L'altezza e la larghezza vengono regolate automaticamente. I [segnalibri](manage-bookmarks.md) sono in grado di supportare gli orientamenti verticale e orizzontale, ma al momento non è possibile modificare le dimensioni. Per rendere più semplice la verifica, l'anteprima del segnalibro Mostra un PowerApp completamente funzionante.
1. Selezionare **Pubblica** o **Salva come bozza**.

## <a name="qa"></a>Domande e risposte

La creazione di un [&Q](manage-qas.md) è simile alla creazione di [segnalibri](manage-bookmarks.md). Con Q&A, è possibile fornire risposte alle domande degli utenti anziché solo un collegamento a una pagina Web. È possibile formattare le risposte in testo RTF utilizzando gli strumenti disponibili. Se un segnalibro e un Q&condividono la stessa parola chiave, il risultato del segnalibro viene visualizzato per primo. Analogamente ai segnalibri, la Q&un indice viene aggiornato subito dopo l'aggiunta o la modifica di una Q&A. 

### <a name="supported-html-tags"></a>Tag HTML supportati

È possibile utilizzare il contenuto HTML o aggiungere tag HTML alla risposta o alla descrizione. I tag HTML supportati sono i seguenti:
 
- blockquote
- div
- em
- h1, h2, h3, and h4
- ol, ul, and li
- p
- pre
- span
- strong
- table, thead, tbody, tr, th, and td
- u
- a
- code
- br
- hr
- img

I tag non supportati vengono ignorati o visualizzati come testo. Assicurarsi di visualizzare in anteprima le schede.

> [!Note]
> Non è possibile importare gli elementi Q&se sono presenti errori nel file modello. Per evitare errori, verificare che il file di importazione sia formattato correttamente e che includa tutte le informazioni necessarie. Per ulteriori informazioni, vedere come [prevenire gli errori di importazione](#prevent-import-errors).

## <a name="locations"></a>Sedi

Con le [posizioni](manage-locations.md), gli utenti possono trovare gli indirizzi e individuare gli edifici dell'organizzazione. La caratteristica **locations** offre una posizione accurata per uffici, campus e edifici, nonché le direzioni e la struttura di spostamento. Per ottenere risultati ottimali, gli amministratori devono aggiungere tutti i percorsi importanti delle rispettive organizzazioni a Microsoft Search. A differenza dei [segnalibri](manage-bookmarks.md) e [Q&A](manage-qas.md), l'indice locations non viene aggiornato immediatamente. È possibile che le posizioni nuove o modificate vengano visualizzate nei risultati della ricerca.

## <a name="get-started"></a>Introduzione
Per scoprire cosa è necessario per gli utenti e rendere tali informazioni facili da individuare, provare alcuni di questi metodi:

- Usare i log di ricerca intranet per determinare i siti e le pagine con maggior traffico.
- Determinare quali sono le app, i siti e gli strumenti usati ogni giorno o ogni settimana.
- Trovare collegamenti diretti per i benefit dipendenti.
- Cercare le direttive e i processi di cui gli utenti devono essere a conoscenza.
- Decidere gli utenti che contattano il supporto e come lo fanno.
- Ottenere le informazioni necessarie su base ricorrente, sia stagionalmente che in base ai cicli aziendali. Un esempio è la ricerca di strumenti per la prenotazione di aggiornamenti finanziari trimestrali o di tempo libero.
- Raccogliere i criteri per gli utenti regionali o mobili. Gli esempi sono vantaggi che variano in base alla posizione.
- Determinare i siti interni e le informazioni per le ricerche Web comuni. Alcuni esempi sono il traffico, le informazioni sul trasporto pubblico, le condizioni meteorologiche locali, gli sconti disponibili per i partner aziendali e i programmi di integrità e fitness.
- Trovare le informazioni su eventi, conferenze o incontri organizzati dall'azienda.
- Ricercare problemi comuni nonché domande frequenti e risposte relativi a IT, risorse umane e supporto tecnico.

## <a name="involve-smes-and-users"></a>Coinvolgere PMI e utenti
In un'organizzazione, gli utenti cercano una serie di argomenti semplici e complessi. Esempi semplici sono gli indirizzi di Office e i vantaggi per i dipendenti. Gli esempi complessi sono nuovi processi di lavoro, informazioni tecniche e contenuti su come eseguire le attività. Per creare o trovare una vasta gamma di contenuti, è necessario avere esperienza in diversi campi, argomenti e tecnologie. 

La maggior parte degli amministratori di ricerca non ha conoscenze specifiche su tutti gli argomenti. Per ridimensionare la quantità di contenuto disponibile senza l'ausilio di risorse esterne, cercare informazioni e conoscenze da parte di altri utenti dell'organizzazione.

### <a name="get-content-from-smes"></a>Ottenere contenuto dalle PMI
Sfruttare gli esperti del settore (PMI) dell'organizzazione, compresi gli esperti provenienti da risorse umane, supporto, vendite, tecnologia e altre aree chiave. Le PMI possono contribuire direttamente al contenuto se vengono aggiunte come redattori di ricerca di Microsoft. 

### <a name="involve-your-users"></a>Coinvolgere i propri utenti
Chiedere agli utenti di suggerire risorse a cui aggiungere un segnalibro. Chiedere inoltre agli utenti di segnalare errori come collegamenti interrotti o non validi.

## <a name="set-up-components"></a>Configurare i componenti
Per aggiungere o modificare [segnalibri](manage-bookmarks.md)singoli o in blocco, [Q&a](manage-qas.md)e [locations](manage-locations.md), eseguire la procedura descritta nelle sezioni seguenti. 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>Aggiungere o modificare un singolo segnalibro, Q&A o un componente di posizione
1. Nell'interfaccia di [Amministrazione](https://admin.microsoft.com)di Microsoft 365, andare a **Settings** > **Microsoft Search**. Selezionare la scheda denominata del componente. La scheda **segnalibri** è selezionata per impostazione predefinita.
1. Per aggiungere un componente, selezionare **Aggiungi nuovo**. 
1. Per modificare un componente, selezionarlo nell'elenco componente pertinente. 
1. Quando si aggiungono o modificano le informazioni, l'anteprima viene aggiornata automaticamente.

### <a name="bulk-add-or-edit-components"></a>Aggiunta o modifica di componenti di massa
Con le funzionalità di **importazione** ed **esportazione** , gli amministratori della ricerca possono creare o modificare in blocco [segnalibri](manage-bookmarks.md), [Q&A](manage-qas.md)e [posizioni](manage-locations.md). Questa funzionalità è utile quando un amministratore desidera aggiungere o modificare molti componenti. 

Le funzionalità di importazione ed esportazione forniscono queste funzioni:
- **Aggiunta in blocco**. Aggiungere dettagli nel file modello del componente e quindi importarlo.
- **Modifica in blocco**. Esportare i componenti in un file CSV, quindi modificare i dettagli del segnalibro nel CSV esportato e quindi importare il formato CSV aggiornato.
- **Importare i siti promossi da [SharePoint](http://sharepoint.com/)**. Questa funzionalità si applica solo ai [segnalibri](manage-bookmarks.md).
- **Backup**. Esportare i componenti in un file CSV.

Per importare o esportare i componenti, procedere come segue:
1. Nell'angolo in alto a destra della scheda denominata del componente selezionare **Importa**. 
1. Per scaricare tutti i componenti esistenti in un file CSV, selezionare **Esporta**.
1. Nel riquadro destro scegliere l'opzione da importare utilizzando un file CSV o [SharePoint](http://sharepoint.com/).
1. Per ottenere un elenco dei campi e dettagli necessari, scaricare il file del modello del componente. 
1. Aggiungere o modificare i dettagli del componente nel file modello. Salvarla nel computer. 
1. Nel riquadro **importazione** del componente selezionare **Browse**. Selezionare quindi il file CSV desiderato e selezionare **Importa**.

### <a name="template-guidelines"></a>Linee guida per i modelli
Tenere presenti le linee guida e le restrizioni quando si lavora con i file modello:
- Non modificare mai i dati in questi campi: *ID*, *Ultima modifica*e *Ultima modifica di*.
- Se si include l' *ID* di un segnalibro esistente, quest'ultimo viene sostituito con le informazioni contenute nel file di importazione.
- Se è presente un segnalibro con lo stesso titolo o URL nel file esistente, il segnalibro viene aggiornato con le informazioni contenute nel file di importazione.
- Non tutti i campi nel file modello sono obbligatori e i campi obbligatori variano a seconda dello stato del segnalibro.
- In base al campo *dello stato* , i segnalibri vengono salvati come **bozza**, **suggerito**o **pianificato**. In caso contrario, verranno pubblicati automaticamente.
- Se si gestiscono più organizzazioni, è possibile esportare i segnalibri da un'organizzazione e importarli in un altro. È tuttavia necessario rimuovere i dati dalla colonna *Id* prima di importarli.

> [!Note]
> Non è possibile importare elementi del componente se sono presenti errori nel file modello. Per evitare errori, verificare che il file di importazione sia formattato correttamente e che includa tutte le informazioni necessarie.

### <a name="prevent-import-errors"></a>Evitare gli errori di importazione

Se i dati necessari sono mancanti o non validi, viene visualizzato un messaggio di errore. Un file di registro genera una serie di informazioni sulle righe e le colonne da correggere. Apportare le modifiche necessarie e provare a importare di nuovo il file. Non è possibile importare o salvare segnalibri fino a quando non vengono risolti tutti gli errori.

Per evitare errori, verificare che il file di importazione sia formattato correttamente e soddisfi i requisiti seguenti:
- Sono incluse la riga di intestazione e tutte le colonne del modello di importazione.
- L'ordine di colonna è identico a quello del modello di importazione.
- Tutte le colonne dispongono di valori, ad eccezione delle tre che possono essere vuote: *ID*, *Last modified*e *Last modified by*. 
- La colonna *dello stato* non è vuota.

### <a name="titles-and-descriptions"></a>Titoli e descrizioni
I titoli e le descrizioni connessi aiutano gli utenti a determinare se i risultati rispondono alla query di ricerca. I buoni titoli e le descrizioni rispecchiano lo scopo principale del risultato. Un esempio è il titolo **vantaggi** per l'infanzia con la descrizione *informazioni sui vantaggi che consentono di pagare i costi per l'infanzia*. Con questi dati connessi, gli utenti che effettuano ricerche per i **bambini** possono trovare vantaggi per il supporto monetario e ottenere un collegamento per ulteriori informazioni.

### <a name="keywords"></a>Parole chiave
Con parole chiave, gli utenti dell'organizzazione possono cercare e trovare contenuti rilevanti. È necessario associare termini di parole chiave con i risultati di ricerca correlati. Microsoft Search suggerisce parole chiave basate sul titolo e sull'URL del contenuto. Per identificare più parole chiave, ottenere risposte a queste domande:

1. **Quali termini di ricerca sono in grado di trovare le informazioni identificate?** Fare riferimento a qualsiasi terminologia esistente nell'organizzazione, oltre a varianti correlate, acronimi, argomenti e argomenti.
1. **Quali varianti o parole vengono utilizzate dalle persone per parlare di queste informazioni?** Rivolgersi al team di supporto per fornire tali parole chiave.

Ad esempio, se si crea un risultato che collega uno strumento per l'invio delle richieste di ferie, le parole chiave **Vacation** and **Submit Vacation request** sono opzioni ottimali da includere. Gli utenti dell'organizzazione possono anche cercare informazioni relative alle **festività** con una vacanza o un **tempo di disattivazione**. Per semplificare l'individuazione di contenuto pertinente da parte degli utenti, aggiungere tali parole chiave e altre come **inviare la richiesta di festività** e **richiedere un intervallo di tempo**.

### <a name="reserved-keywords"></a>Parole chiave riservate
 Una parola chiave riservata è un termine o frase unica che consente di ottenere un risultato. A differenza di altre parole chiave, le parole chiave riservate sono associate a un solo risultato. Usare le parole chiave riservate con moderazione per permettere a Microsoft Search di imparare in base all'utilizzo.

Un esempio è un segnalibro per un sito per l'invio delle ore. Se il **tempo di registrazione** è una parola chiave riservata, gli utenti dell'organizzazione che cercano il tempo di **registrazione** visualizzano il sito come l'unico segnalibro nella casella di ricerca di Microsoft. 

### <a name="group-related-content-with-keywords"></a>Contenuto correlato a un gruppo con parole chiave
Se si desidera che gli utenti possano trovare insiemi di contenuto correlato quando eseguono la ricerca di un termine specifico, assegnare la stessa parola chiave a tutto il contenuto correlato. Un esempio è la ricerca di processi e strumenti relativi alle modifiche allo stato di vita. Per raggruppare le risposte insieme sull'aggiornamento dei vantaggi, delle informazioni fiscali e delle modifiche relative a nome e alias, includere una parola chiave come **matrimonio**.

### <a name="search-settings"></a>Impostazioni ricerca
Con le impostazioni di ricerca, è possibile adattare il contenuto e i gruppi di utenti specifici di destinazione. Il controllo delle impostazioni di ricerca di Microsoft quando viene visualizzato un risultato di ricerca e chi può visualizzarlo:

- **Data**. Per controllare se il contenuto è disponibile o non disponibile, impostare una data di inizio e una data di fine. Ad esempio, il materiale sensibile al tempo viene visualizzato nei risultati della ricerca quando è pertinente.
- **Paese o area geografica**. È possibile selezionare paesi o aree geografiche, in modo che solo gli utenti di tali posizioni visualizzino contenuto specifico. Ad esempio, le informazioni specifiche del paese vengono visualizzate nei risultati della ricerca solo in quei paesi.
- Impostazioni **gruppo** rendere i risultati disponibili solo per i membri dei gruppi selezionati. Ad esempio, se si creano siti che si riferiscono solo ai dipendenti del reparto risorse umane, eseguire il mapping di questa impostazione al gruppo di sicurezza HR appropriato.
- **Dispositivo o sistema operativo**. Selezionare tipi di dispositivo o sistemi operativi, in modo che solo gli utenti che eseguono la ricerca su tali dispositivi o utilizzino tali sistemi, vedere quel segnalibro.
- **Varianti mirate**. Questa impostazione è diversa dal contenuto di un segnalibro basato sul dispositivo e sulla posizione di un utente.

## <a name="test-your-content"></a>Testare il contenuto
Dopo aver creato i [segnalibri](manage-bookmarks.md) e [Q&A](manage-qas.md), verificare i risultati seguenti:
- Viene visualizzato il segnalibro o la Q&corretta.
- Tutto il contenuto raggruppato insieme alle parole chiave viene visualizzato insieme come pianificato.
- Non viene visualizzato alcun evento imprevisto nelle risposte alla ricerca.
- Il segnalibro o Q&A contiene informazioni sufficienti.

Gli utenti e le PMI che contribuiscono alla creazione di contenuto possono aiutare a testare e convalidare i risultati della ricerca.

## <a name="review-and-update-periodically"></a>Rivedere e aggiornare periodicamente
Le informazioni autorevoli come i [segnalibri](manage-bookmarks.md) e [Q&](manage-qas.md) a devono rimanere aggiornate. Eseguire regolarmente queste operazioni:
- Consente di correggere o rimuovere URL non validi e interrotti.
- Rimuovere i segnalibri o Q&A che non sono più rilevanti.
- Controllare eventuali modifiche di segnalibri, domande e risposte o nome del team.
- Valutare se il segnalibro o la Q&A è sufficientemente autorevole o ha bisogno di una descrizione più chiara.

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>Ottenere informazioni dettagliate sui segnalibri, su Q&A e sui percorsi

Microsoft Search Visualizza il numero di [segnalibri](manage-bookmarks.md), [Q&A](manage-qas.md)e [percorsi](manage-locations.md) pubblicati, pianificati o suggeriti. Il [Dashboard Insights](get-insights.md) Visualizza Bookmark, Q&A e Totals location by Status:

- **Pubblicato**: il numero di risultati pubblicati che sono disponibili per gli utenti.
- **Programmato**: il numero di risultati programmati nella pipeline di pubblicazione.
- **Suggeriti**: il numero di suggerimenti degli utenti.

I [segnalibri](manage-bookmarks.md)suggeriti, [Q&a](manage-qas.md)e i [percorsi](manage-locations.md) sono un buon indicatore degli spazi vuoti nel contenuto. Aiutano a capire cosa cercano gli utenti, ma non lo trovano. Questi dati potrebbero indicare che è necessario creare più segnalibri, Q&A o percorsi. In alternativa, potrebbe essere necessario aggiornare il contenuto esistente utilizzando parole chiave migliori, parole chiave riservate e stringhe di ricerca per rendere il contenuto più individuabile.

### <a name="review-top-search-queries"></a>Esaminare le query di ricerca principali

Per scoprire quali ricerche hanno generato la maggior parte delle impressioni negli ultimi 90 giorni, esaminare le query di ricerca principali. L' *impressione* indica il numero di volte in cui una pagina è stata visualizzata nei risultati della ricerca. La scheda **query superiore** nel [Dashboard Insights](get-insights.md) Visualizza le prime 25 ricerche degli utenti per ogni tipo di risultato, il numero totale di ricerche e la frequenza di clic (CTR). Con questo report, è possibile identificare il volume delle query di ricerca e determinare le query con un'attività di ricerca elevata e bassa.

Il numero di ricerca basso può indicare l'insoddisfazione degli utenti. Gli utenti non sono in cerca di tale contenuto oppure utilizzano parole chiave diverse per individuarlo. Il CTR mostra la frequenza con cui gli utenti selezionano i risultati alzati di livello e quanto sono utili le regole di query e i risultati per gli utenti. Un CTR basso indica che gli utenti individuano il contenuto, ma non soddisfano le proprie esigenze. In tali casi, esaminare il contenuto. Per allineare il contenuto alle query di ricerca, verificare che corrisponda ai titoli di ricerca e agli aggiornamenti degli utenti, alle descrizioni e alle parole chiave. 

### <a name="analyze-impressions-by-result-type"></a>Analizzare le impression in base al tipo di risultato

I grafici di facile lettura nella scheda di **distribuzione dell'impressione** nel [Dashboard Insights](get-insights.md) mostrano le impressioni su vari periodi di tempo. La sequenza temporale mostra il numero giornaliero di impression per un tipo di risultato. Con questi grafici, è possibile determinare il tipo di risultato più frequentemente o raramente utilizzato. L'utilizzo infrequente di un determinato tipo di risultati non significa necessariamente che il tipo di risultato non sia positivo. ma indica unicamente il modo in cui gli utenti usano il risultato della ricerca.

 Se un determinato tipo di risultati è preferibile dagli utenti, è possibile creare più risultati della ricerca dello stesso tipo. Per assicurarsi che le parole chiave siano appropriate, esaminare le parole chiave dei tipi di risultati con un utilizzo limitato. Con questo report, è anche possibile visualizzare le modifiche apportate al comportamento degli utenti nel tempo.
