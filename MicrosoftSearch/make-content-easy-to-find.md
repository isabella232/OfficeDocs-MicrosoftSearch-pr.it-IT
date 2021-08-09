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
ms.openlocfilehash: 0cf3152e7fb47f0cb1b1fa3fe0df43645a2536e171fd8211050a1773ec86a490
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532940"
---
# <a name="make-content-easy-to-find"></a>Facilitare la ricerca del contenuto

Microsoft Search aiuta gli utenti a trovare contenuto pertinente. Costituisce un modo sicuro per cercare contenuto intranet e Web. Questo tipo di integrazione nel Web e nelle organizzazioni è offerto solo da Microsoft. Con Microsoft Search, gli amministratori della ricerca possono sfruttare la propria conoscenza di un'organizzazione per consentire agli utenti di trovare facilmente contenuto pertinente. 

## <a name="components-that-find-content"></a>Componenti che trovano contenuto
In Microsoft Search, gli amministratori creano [segnalibri,](manage-bookmarks.md) [PowerApps,](integrate-powerapps.md)domande&[](manage-locations.md) [A](manage-qas.md)e Posizioni che semplificano la ricerca del contenuto. Ognuno dei componenti della ricerca include un titolo, un URL e un set di parole chiave di attivazione.

## <a name="bookmarks"></a>Segnalibri
È possibile creare [segnalibri](manage-bookmarks.md) in pochi passaggi. Ogni segnalibro include un titolo, URL e un set di parole chiave di attivazione. Un segnalibro può avere diverse parole chiave e diversi segnalibri possono condividere la stessa parola chiave. Tuttavia, le parole chiave riservate non possono essere condivise. Quando si crea o si modifica un segnalibro, l'indice di ricerca viene aggiornato e il segnalibro è immediatamente disponibile per gli utenti.

Se l'organizzazione **ha alzato di** livello i risultati impostati in [SharePoint](http://sharepoint.com/), è possibile importare tali risultati in Microsoft Search. Con i risultati alzati di livello, è possibile popolare rapidamente i risultati della ricerca, rendere il contenuto disponibile per gli utenti e rendere Microsoft Search più efficace non appena lo si configura. È consigliabile usare i risultati alzati di livello di SharePoint come riferimento per determinare come assegnare un nome e creare i risultati della ricerca rilevanti. 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>Aggiungere o modificare segnalibri tramite le estensioni del browser
Gli amministratori della ricerca possono creare facilmente contenuti di ricerca usando le estensioni del browser. Per aggiungere il sito come segnalibro, installare l'estensione del browser. Passare quindi al sito e aggiungerlo come segnalibro. Per ulteriori informazioni, vedere [Manage bookmarks.](manage-bookmarks.md)

Attualmente, le estensioni del browser sono disponibili [per Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) e [Google Chrome:](https://www.google.com) 
- Per scaricare l'estensione Edge, passare alla [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Per scaricare l'estensione Chrome, vai [all'archivio Web chrome.](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)

## <a name="powerapps"></a>PowerApps

Aggiungendo [PowerApps esistenti](integrate-powerapps.md) ai [segnalibri,](manage-bookmarks.md)gli utenti possono completare attività come l'immissione di periodi di ferie o la segnalazione delle spese. 

Con [PowerApps](integrate-powerapps.md)puoi creare app aziendali che vengono eseguite in un browser o in un telefono o un tablet. Non è necessaria alcuna esperienza di codifica. PowerApps funziona in qualsiasi browser e in qualsiasi dispositivo. L'aggiunta richiede meno di un minuto. Per altre informazioni su PowerApps, vedi questi articoli:
- [Apprendimento guidato](/learn/browse/?products=powerapps)
- [Documentazione di PowerApps](/powerapps/maker/canvas-apps/get-sessionid)
- [Home page di PowerApps](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Aggiungere una PowerApp a un segnalibro

1. Trova [l'ID dell'app](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) PowerApp che vuoi aggiungere.
1. Nell'Microsoft 365 [di amministrazione](https://admin.microsoft.com)passare a **Impostazioni**  >  **Microsoft Search**. 
1. Aggiungere un segnalibro o trovare un segnalibro esistente a cui si vuole aggiungere una PowerApp.
1. In **Impostazioni segnalibro** selezionare **Power App.** Selezionare quindi **Aggiungi un'app Power.**
1. Immetti **l'ID app**. L'altezza e la larghezza vengono regolate automaticamente. [I segnalibri](manage-bookmarks.md) possono supportare l'orientamento verticale e orizzontale, ma attualmente le dimensioni non possono essere modificate. Per semplificare il test, l'anteprima dei segnalibri mostra una PowerApp completamente funzionante.
1. Selezionare **Pubblica** o **Salva come bozza**.

## <a name="qa"></a>Domande e risposte

La creazione [di un&domande e](manage-qas.md) risposte è simile alla creazione di [segnalibri.](manage-bookmarks.md) Con domande&A, è possibile fornire risposte alle domande degli utenti invece di un semplice collegamento alla pagina Web. È possibile formattare le risposte in formato RTF utilizzando gli strumenti disponibili. Se un segnalibro e una domanda&A condividono la stessa parola chiave, il risultato del segnalibro viene visualizzato per primo. Come i segnalibri, l'&domande e risposte viene aggiornato immediatamente dopo l'aggiunta o la modifica di una domanda&A. 

### <a name="supported-html-tags"></a>Tag HTML supportati

È possibile utilizzare contenuto HTML o aggiungere tag HTML alla risposta o alla descrizione. I tag HTML supportati sono i seguenti:
 
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
> Non è possibile importare domande&elementi A se sono presenti errori nel file modello. Per evitare errori, verificare che il file di importazione sia formattato correttamente e che includa tutte le informazioni necessarie. Per ulteriori informazioni su come evitare errori [di importazione,](#prevent-import-errors)vedere .

## <a name="locations"></a>Posizioni

Con [Percorsi](manage-locations.md), gli utenti possono trovare gli indirizzi e individuare gli edifici dell'organizzazione. La **funzionalità Posizioni** offre una posizione accurata per uffici, campus ed edifici, nonché indicazioni stradali e spostamenti. Per ottenere risultati ottimali, gli amministratori devono aggiungere tutte le posizioni importanti delle organizzazioni a Microsoft Search. A [differenza di Bookmarks](manage-bookmarks.md) [e Q&A](manage-qas.md), l'indice Locations non viene aggiornato immediatamente. La visualizzazione dei percorsi nuovi o modificati nei risultati della ricerca può richiedere diverse ore.

## <a name="get-started"></a>Per iniziare
Per scoprire di cosa hanno bisogno gli utenti e semplificare l'individuazione di tali informazioni, provare alcuni di questi metodi:

- Usare i log di ricerca intranet per determinare i siti e le pagine con maggior traffico.
- Determinare quali sono le app, i siti e gli strumenti usati ogni giorno o ogni settimana.
- Trovare collegamenti diretti per i benefit dipendenti.
- Cercare le direttive e i processi di cui gli utenti devono essere a conoscenza.
- Decidere quali utenti contattano per il supporto e come farlo.
- Ottenere le informazioni necessarie su base ricorrente, in base a cicli di lavoro o a livello di stagione. Un esempio è la ricerca di strumenti per la prenotazione di aggiornamenti finanziari trimestrali o di tempo libero.
- Raccogliere i criteri per gli utenti regionali o mobili. Alcuni esempi sono i vantaggi che variano in base alla posizione.
- Determinare i siti interni e le informazioni per le ricerche Web comuni. Esempi sono il traffico, le informazioni sui mezzi pubblici, il meteo locale, gli sconti disponibili dai partner aziendali e i programmi di salute e fitness.
- Trovare le informazioni su eventi, conferenze o incontri organizzati dall'azienda.
- Ricercare problemi comuni nonché domande frequenti e risposte relativi a IT, risorse umane e supporto tecnico.

## <a name="involve-smes-and-users"></a>Coinvolgere LE PMI e gli utenti
In un'organizzazione, gli utenti ricercano una serie di argomenti semplici e complessi. Esempi semplici sono gli indirizzi dell'ufficio e i vantaggi dei dipendenti. Esempi complessi sono nuovi processi di lavoro, informazioni tecniche e contenuto procedurali. Per creare o trovare un'ampia gamma di contenuti, è necessario disporre di competenze in diversi campi, argomenti e tecnologie. 

La maggior parte degli amministratori della ricerca non dispone di conoscenze specifiche su ogni argomento. Per ridimensionare la quantità di contenuto disponibile senza l'aiuto di risorse esterne, cercare competenze e conoscenze da altri utenti dell'organizzazione.

### <a name="get-content-from-smes"></a>Ottenere contenuto dalle PMI
Sfruttare gli esperti in materia (PMI) nell'organizzazione, inclusi esperti di risorse umane, supporto, vendite, tecnologia e altre aree chiave. Le PMI possono contribuire direttamente al contenuto se vengono aggiunti Microsoft Search editor. 

### <a name="involve-your-users"></a>Coinvolgere i propri utenti
Chiedere agli utenti di suggerire risorse a cui aggiungere un segnalibro. Chiedere inoltre agli utenti di segnalare errori come collegamenti interrotti o non validi.

## <a name="set-up-components"></a>Configurare i componenti
Per aggiungere o modificare segnalibri singoli o in blocco [,](manage-bookmarks.md) [domande&A](manage-qas.md)e Posizioni , eseguire la procedura descritta nelle sezioni seguenti. [](manage-locations.md) 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>Aggiungere o modificare un singolo segnalibro, domande&A o un componente di posizione
1. Nell'Microsoft 365 [di amministrazione](https://admin.microsoft.com)passare a **Impostazioni**  >  **Microsoft Search**. Selezionare la scheda denominata del componente. La **scheda Segnalibri** è selezionata per impostazione predefinita.
1. Per aggiungere un componente, selezionare **Aggiungi nuovo**. 
1. Per modificare un componente, selezionare il segnalibro nell'elenco dei componenti pertinenti. 
1. Quando si aggiungono o modificano le informazioni, l'anteprima viene aggiornata automaticamente.

### <a name="bulk-add-or-edit-components"></a>Aggiunta o modifica in blocco di componenti
Con le **funzionalità di** importazione **ed** esportazione, gli amministratori della ricerca possono creare o modificare in blocco segnalibri, domande [&A](manage-qas.md)e [Posizioni.](manage-locations.md) [](manage-bookmarks.md) Questa funzionalità è utile quando un amministratore desidera aggiungere o modificare molti componenti. 

Le funzionalità di importazione ed esportazione offrono queste funzioni:
- **Aggiunta in blocco**. Aggiungi dettagli nel file modello del componente e quindi importalo.
- **Modifica in blocco**. Esportare i componenti in un file CSV, quindi modificare i dettagli dei segnalibri nel file CSV esportato e quindi importare il file CSV aggiornato.
- **Importare siti alzati [di livello da SharePoint](http://sharepoint.com/)**. Questa funzionalità si applica solo [ai segnalibri.](manage-bookmarks.md)
- **Backup**. Esportare i componenti in un file CSV.

Per importare o esportare componenti, eseguire la procedura seguente:
1. Nell'angolo superiore destro della scheda denominata del componente selezionare **Importa.** 
1. Per scaricare tutti i componenti esistenti in un file CSV, selezionare **Esporta**.
1. Nel riquadro destro scegliere l'opzione per l'importazione utilizzando un file CSV o [da SharePoint](http://sharepoint.com/).
1. Per ottenere un elenco dei campi e dei dettagli obbligatori, scarica il file modello del componente. 
1. Aggiungere o modificare i dettagli del componente nel file modello. Quindi salvarlo nel computer. 
1. Nel riquadro Importa **del** componente selezionare **Sfoglia**. Selezionare quindi il file CSV desiderato e selezionare **Importa**.

### <a name="template-guidelines"></a>Linee guida per i modelli
Tenere presenti queste linee guida e restrizioni quando si lavora con i file modello:
- Non modificare mai i dati in questi campi: *Id,* Ultima *modifica* e *Ultima modifica da.*
- Se si include *l'ID* di un segnalibro esistente, questo verrà sostituito con le informazioni nel file di importazione.
- Se nel file esistente è presente un segnalibro con lo stesso titolo o URL, il segnalibro viene aggiornato con le informazioni nel file di importazione.
- Non tutti i campi nel file modello sono obbligatori e i campi obbligatori variano a seconda dello stato del segnalibro.
- In base al *campo Stato,* i segnalibri vengono salvati come **bozza,** **suggerita** o **pianificata.** In caso contrario, vengono pubblicati automaticamente.
- Se si gestiscono più organizzazioni, è possibile esportare i segnalibri da un'organizzazione e importarli in un'altra. È tuttavia necessario rimuovere i dati dalla colonna *Id* prima di importarli.

> [!Note]
> Non è possibile importare gli elementi del componente in caso di errori nel file modello. Per evitare errori, verificare che il file di importazione sia formattato correttamente e che includa tutte le informazioni necessarie.

### <a name="prevent-import-errors"></a>Evitare gli errori di importazione

Viene visualizzato un messaggio di errore se i dati necessari sono mancanti o non validi. Un file di registro viene generato con ulteriori informazioni sulle righe e sulle colonne da correggere. Apportare le modifiche necessarie e provare di nuovo a importare il file. Non è possibile importare o salvare segnalibri finché non vengono risolti tutti gli errori.

Per evitare errori, verificare che il file di importazione sia formattato correttamente e soddisfi questi requisiti:
- Vengono incluse la riga di intestazione e tutte le colonne del modello di importazione.
- L'ordine delle colonne corrisponde al modello di importazione.
- Tutte le colonne hanno valori, ad eccezione delle tre che possono essere vuote: *Id,* Ultima modifica e *Ultima modifica da.* 
- La *colonna State* non è vuota.

### <a name="titles-and-descriptions"></a>Titoli e descrizioni
Le descrizioni e i titoli connessi consentono agli utenti di determinare se i risultati rispondono alla query di ricerca. Titoli e descrizioni buone riflettono lo scopo principale del risultato. Un esempio è il titolo **Prestazioni per l'assistenza** all'infanzia con la descrizione Informazioni sui *vantaggi per aiutare a pagare i costi per l'assistenza all'infanzia.* Con questi dati connessi,  gli utenti che ricercano l'assistenza all'infanzia possono trovare vantaggi di supporto monetario e ottenere un collegamento per saperne di più.

### <a name="keywords"></a>Parole chiave
Con le parole chiave, gli utenti dell'organizzazione possono cercare e trovare contenuto pertinente. È necessario associare termini di parole chiave ai relativi risultati di ricerca. Microsoft Search suggerisce parole chiave in base al titolo e all'URL del contenuto. Per identificare più parole chiave, ottenere risposte a queste domande:

1. **Quali termini di ricerca possono trovare le informazioni identificate?** Fare riferimento a qualsiasi terminologia esistente nell'organizzazione, nonché a varianti, acronimi, argomenti e argomenti correlati.
1. **Quali varianti o parole usano gli utenti per parlare di queste informazioni?** Chiedere al team di supporto di fornire tali parole chiave.

Ad esempio, se si crea un risultato che collega a uno  strumento per l'invio di richieste di ferie, le parole chiave **ferie** e inviare la richiesta di ferie sono buone opzioni da includere. Gli utenti dell'organizzazione possono anche cercare informazioni relative alle ferie con **festività** **o periodi di ferie.** Per semplificare la ricerca di contenuto pertinente per gli utenti, aggiungi queste parole chiave e altre parole chiave come **inviare** una richiesta di festività e **richiedere un periodo di tempo libero.**

### <a name="reserved-keywords"></a>Parole chiave riservate
 Una parola chiave riservata è un termine o frase unica che consente di ottenere un risultato. A differenza di altre parole chiave, le parole chiave riservate sono associate a un solo risultato. Usare le parole chiave riservate con moderazione per permettere a Microsoft Search di imparare in base all'utilizzo.

Un esempio è un segnalibro per un sito per l'invio delle ore. Se **l'ora** del registro è una parola  chiave riservata, gli utenti dell'organizzazione che ricercano il tempo di registrazione vedono tale sito come l'unico segnalibro nella casella Microsoft Search. 

### <a name="group-related-content-with-keywords"></a>Raggruppare contenuto correlato con parole chiave
Se si desidera che gli utenti trovino set di contenuti correlati durante la ricerca di un termine specifico, assegnare la stessa parola chiave a tutto il contenuto correlato. Un esempio è la ricerca di processi e strumenti per le modifiche dello stato di vita. Per raggruppare le risposte sull'aggiornamento di vantaggi, informazioni fiscali e modifiche al nome e all'alias, includere una parola chiave come **il matrimonio.**

### <a name="search-settings"></a>Impostazioni ricerca
Con le impostazioni di ricerca, puoi personalizzare il contenuto e scegliere come destinazione gruppi specifici di utenti. Queste Microsoft Search controllano quando viene visualizzato un risultato di ricerca e chi può vederlo:

- **Date**. Per controllare quando il contenuto è disponibile o non disponibile, impostare una data di inizio e una data di fine. Ad esempio, il materiale sensibile al tempo viene visualizzato nei risultati della ricerca quando è rilevante.
- **Paese o area geografica**. Puoi selezionare paesi o aree geografiche, in modo che solo gli utenti di tali posizioni vedano determinati contenuti. Ad esempio, le informazioni specifiche del paese vengono visualizzate solo nei risultati della ricerca in tali paesi.
- **Le impostazioni** di gruppo rendono i risultati disponibili solo per i membri dei gruppi selezionati. Ad esempio, se si creano siti correlati solo ai dipendenti del reparto Risorse umane, eseguire il mapping di questa impostazione al gruppo di sicurezza HR appropriato.
- **Dispositivo o sistema operativo**. Selezionare i tipi di dispositivi o i sistemi operativi, in modo che solo gli utenti che eseere una ricerca su tali dispositivi o che usano tali sistemi vedano il segnalibro.
- **Varianti mirate**. Questa impostazione varia il contenuto di un segnalibro in base al dispositivo e alla posizione di un utente.

## <a name="test-your-content"></a>Testare il contenuto
Dopo aver creato [segnalibri](manage-bookmarks.md) e [domande&A,](manage-qas.md)verificare i risultati seguenti:
- Viene visualizzato il segnalibro o la&A corretti.
- Tutto il contenuto raggruppato con parole chiave viene visualizzato come pianificato.
- Nelle risposte alla ricerca non viene visualizzato alcun elemento imprevisto.
- Il segnalibro o la&A contiene informazioni sufficienti.

Gli utenti e le PMI che contribuiscono alla creazione di contenuto possono aiutare a testare e convalidare i risultati della ricerca.

## <a name="review-and-update-periodically"></a>Rivedere e aggiornare periodicamente
Informazioni autorevoli come [Segnalibri](manage-bookmarks.md) e [Domande&A](manage-qas.md) devono rimanere aggiornate. Eseguire questi passaggi regolarmente:
- Correggere o rimuovere URL non validi e interrotti.
- Rimuovere segnalibri o domande&A che non sono più rilevanti.
- Controllare eventuali modifiche di segnalibri, domande e risposte o nome del team.
- Valutare se il segnalibro o la&A è sufficientemente autorevole o se necessita di una descrizione più chiara.

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>Ottenere informazioni dettagliate su segnalibri, domande&A e posizioni

Microsoft Search viene illustrato il numero [di](manage-bookmarks.md)segnalibri, domande&[A](manage-qas.md)e [Posizioni](manage-locations.md) pubblicati, pianificati o suggeriti. Il [dashboard Insights mostra](./usage-reports.md) i totali di segnalibro, domande&A e posizione per stato:

- **Pubblicato**: il numero di risultati pubblicati che sono disponibili per gli utenti.
- **Programmato**: il numero di risultati programmati nella pipeline di pubblicazione.
- **Suggeriti**: il numero di suggerimenti degli utenti.

Segnalibri [suggeriti,](manage-bookmarks.md) [Domande&A](manage-qas.md) [e](manage-locations.md) Posizioni sono un buon indicatore delle lacune nel contenuto. Consentono di comprendere ciò che gli utenti ricercano ma non trovano. Questi dati potrebbero indicare che è necessario creare più segnalibri, domande&A o Posizioni. In caso contrario, potrebbe essere necessario aggiornare il contenuto esistente utilizzando parole chiave migliori, parole chiave riservate e stringhe di ricerca per rendere il contenuto più individuabile.

### <a name="review-top-search-queries"></a>Esaminare le query di ricerca principali

Per scoprire quali ricerche hanno generato il maggior numero di impression negli ultimi 90 giorni, esaminare le query di ricerca principali. *Impression* indica quante volte una pagina è stata visualizzata nei risultati della ricerca. La **scheda Query principali** nel dashboard di [Insights](./usage-reports.md) mostra le prime 25 ricerche utente per ogni tipo di risultato, il numero totale di ricerche e la frequenza di clic (CTR). Con questo report è possibile identificare il volume delle query di ricerca e determinare le query con un'attività di ricerca elevata e bassa.

Un numero basso di ricerche potrebbe indicare insoddisfazione dell'utente. Gli utenti non cercano tale contenuto o usano parole chiave diverse per trovarlo. Il CTR mostra la frequenza con cui gli utenti selezionano i risultati alzati di livello e quanto sono utili le regole di query e i risultati per gli utenti. Un CTR basso indica che gli utenti trovano il contenuto, ma non soddisfano le loro esigenze. In questi casi, esaminare il contenuto. Per allineare il contenuto alle query di ricerca, verificare che corrisponda ai titoli, alle descrizioni e alle parole chiave di ricerca e aggiornamento degli utenti. 

### <a name="analyze-impressions-by-result-type"></a>Analizzare le impression in base al tipo di risultato

Grafici di facile lettura nella  scheda di distribuzione impression nel dashboard Insights [mostra](./usage-reports.md) le impression in vari fotogrammi di tempo. La sequenza temporale mostra il numero giornaliero di impression per un tipo di risultato. Con questi grafici, è possibile determinare quale tipo di risultato viene utilizzato più frequentemente o raramente. L'uso poco frequenti di un determinato tipo di risultato non significa necessariamente che il tipo di risultato non sia corretto. ma indica unicamente il modo in cui gli utenti usano il risultato della ricerca.

 Se un determinato tipo di risultati è preferito dagli utenti, è possibile creare più risultati di ricerca dello stesso tipo. Per verificare che le parole chiave siano appropriate, esaminare le parole chiave dei tipi di risultati con un utilizzo basso. Questo report consente di visualizzare anche le modifiche apportate al comportamento dell'utente nel tempo.