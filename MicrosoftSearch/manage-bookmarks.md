---
title: Gestire i segnalibri
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Creazione e aggiornamento di segnalibri e modalità di modifica in blocco dei risultati dei segnalibri per Microsoft Search
ms.openlocfilehash: fee855e3d3fe780021530488dbaa5a864dcba2d8
ms.sourcegitcommit: 9daa3c8f6eeab502b28975a308d4d1014a00eb25
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49718649"
---
# <a name="manage-bookmarks"></a>Gestire i segnalibri

I segnalibri consentono agli utenti di trovare rapidamente siti e strumenti importanti con una semplice ricerca. Ogni segnalibro include un titolo, un URL, un set di parole chiave di facile utilizzo per attivare il segnalibro e una categoria.

## <a name="what-makes-a-great-bookmark"></a>Cosa rende un segnalibro grande

Un segnalibro grande ha quattro elementi chiave:

1. Un **titolo** forte e informativo. Puntare a non più di 8 parole o a un massimo di 60 caratteri. Si desidera consentire agli utenti di fare clic sul titolo e visualizzare il contenuto, ma evitare clickbait evidenti:
    - Good: provare i piatti preferiti di questa settimana dal menu caffetteria. Il titolo è chiaro, conciso e interessante, ma potrebbe essere troppo promettente.
    - Better: menu caffetteria di questa settimana. Non è troppo promettente o suona come un annuncio.
    - Evitare: non è possibile credere a ciò che viene al menu caffetteria questa settimana. Utilizza luoghi comuni di clickbait che suonano come un annuncio.
2. Una **Descrizione** succinta, circa 300 caratteri, che riepiloga lo scopo o la funzionalità della risorsa collegata.
3. Un insieme di **parole chiave** che consentono agli utenti di trovare il segnalibro quando eseguono la ricerca. È consigliabile un minimo di almeno cinque parole chiave. Sono inoltre disponibili varianti che possono essere utilizzate dagli utenti dell'organizzazione, ad esempio menu per la ristorazione, menu per il pranzo e menu Café, che possono essere varianti del menu caffetteria.
4. Un set di **categorie** utile per semplificare l'ordinamento e il filtro dei segnalibri nell'interfaccia di amministrazione. Gli utenti non vedranno mai le categorie assegnate.

## <a name="create-bookmark-answers"></a>Creare risposte ai segnalibri

Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/), andare a [segnalibri](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) e scegliere la modalità di creazione di nuovi segnalibri:

- Aggiungere segnalibri
- Importare i risultati di SharePoint
- Aggiungere segnalibri predefiniti e segnalibri consigliati
- Importare i segnalibri
- Pubblicare o rivedere i segnalibri consigliati

### <a name="add-bookmarks"></a>Aggiungere segnalibri

Gli amministratori e gli editor di ricerca possono aggiungere segnalibri nell'interfaccia di amministrazione di Microsoft 365. I segnalibri possono essere pubblicati o salvati in bozza. La pubblicazione di un segnalibro aggiorna immediatamente l'indice di ricerca in modo che gli utenti possano iniziare a scoprirlo e utilizzarlo subito. È inoltre possibile pianificare un segnalibro specificando la data e l'ora in cui verrà pubblicata.

- **Published**: i segnalibri sono disponibili per gli utenti dell'organizzazione tramite Microsoft Search.
- **Bozza**: i segnalibri salvati come bozze non sono disponibili per gli utenti. Utilizzare questo stato se l'utente o altre parti interessate desiderano rivedere o aggiornare i segnalibri prima di pubblicarli.
- **Pianificato**: segnalibri che verranno pubblicati nella data e l'ora specificate.

È possibile utilizzare l'estensione del browser creatore di contenuti di Microsoft Search per aggiungere facilmente segnalibri. Per installare l'estensione del browser, passare al sito che si desidera aggiungere come segnalibro e fare clic su Aggiungi nell'estensione.
Installare l'estensione per Edge e Chrome:

- Per Chromium Edge o Chrome: passare a [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) e aggiungere l'estensione.
- Per il server perimetrale legacy: andare a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) e aggiungere l'estensione.

### <a name="import-sharepoint-results"></a>Importare i risultati di SharePoint

Se l'organizzazione ha configurato i risultati promossi in SharePoint, è possibile importare i titoli, gli URL e le descrizioni dai risultati promossi per il tenant in Microsoft Search e rendere il contenuto importato disponibile per gli utenti. Nella maggior parte dei casi, l'importazione dei risultati di SharePoint richiede solo alcuni minuti. Se si sta importando un numero elevato di risultati, potrebbero essere necessari fino a 48 ore. Si tratta di un modo semplice per popolare rapidamente i risultati di ricerca e renderlo più efficace per gli utenti. È consigliabile utilizzare i risultati promossi da SharePoint come riferimento per comprendere come denominare e creare i risultati di ricerca rilevanti.

### <a name="add-default-and-suggested-bookmarks"></a>Aggiungere segnalibri predefiniti e consigliati

Sono stati inclusi alcuni segnalibri di default consigliati che gli utenti possono trovare utili, inclusi i segnalibri per HR, i vantaggi, il supporto IT, la gestione delle password e altro ancora. Rivedere, aggiornare e pubblicare questi segnalibri consigliati per fornire subito risultati di alta qualità agli utenti.

Gli utenti possono anche suggerire i segnalibri che si desidera vengano aggiunti utilizzando i collegamenti di feedback in Microsoft Search. I suggerimenti verranno visualizzati come segnalibri suggeriti.

### <a name="import-bookmarks"></a>Importare i segnalibri

Utilizzare la caratteristica di importazione per rendere più semplice e veloce l'aggiunta o la modifica di un numero elevato di segnalibri. Utilizzarla per:

- Aggiungere i segnalibri in blocco: aggiungere dettagli nel file del modello di segnalibro e quindi importarlo.
- Modifica in blocco dei segnalibri: esportare i segnalibri in un file. csv, modificare i dettagli del segnalibro nel file esportato e quindi importare il file modificato.

Alcuni punti importanti sul file modello:

- Non modificare mai i dati in questi campi: *ID*, *Ultima modifica* e *Ultima modifica da*
- Se si include l' *ID* di un segnalibro esistente, verrà sostituito con le informazioni contenute nel file di importazione.
- Per i segnalibri esistenti con lo stesso titolo o URL, il segnalibro verrà aggiornato con le informazioni contenute nel file di importazione.
- Non tutti i campi sono obbligatori nel file modello e i campi obbligatori variano in base allo stato del segnalibro.
- In base al campo *dello stato* , i segnalibri verranno salvati come bozza, suggeriti, pianificati, esclusi o verranno pubblicati automaticamente.
- Per i partner che gestiscono più organizzazioni, è possibile esportare i segnalibri da un'organizzazione e importarli in un altro. È tuttavia necessario rimuovere i dati nella colonna *ID* prima di essere importati.

### <a name="prevent-import-errors"></a>Evitare gli errori di importazione

Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore e viene generato un file di log con altre informazioni sulle righe e sulle colonne da correggere. Apportare le modifiche necessarie e riprovare l'importazione del file. Non è possibile importare o salvare alcun segnalibro finché non saranno stati risolti tutti gli errori.

Per evitare errori, verificare che il file di importazione sia formattato correttamente e che:

- Includa la riga di intestazione e tutte le colonne presenti nel modello di importazione
- L'ordine delle colonne equivalga a quello del modello di importazione
- Tutte le colonne dispongono di valori, ad eccezione delle tre che possono essere vuote: *ID*, *Last modified* e *Last modified by*
- La colonna *dello stato* non è vuota, sono necessarie informazioni
- Quando si importano segnalibri pubblicati, suggeriti, pianificati o Draft, sono necessarie le colonne *title*, *URL* e *Keywords*
- Quando si importano i segnalibri esclusi, è necessaria la colonna *URL*

Per evitare errori di duplicazione da segnalibro a segnalibro:

- Non utilizzare URL duplicati per segnalibri diversi. Se un URL viene assegnato a un altro segnalibro e si tenta di aggiungerlo nuovamente da un file di importazione, verrà visualizzato un messaggio di errore. Questo vale anche per gli URL duplicati di altri tipi di risposte.
- Quando si aggiornano i segnalibri esistenti, utilizzare la colonna *ID segnalibro* . È possibile aggiornare qualsiasi altra proprietà di un segnalibro esistente, ad esempio una parola chiave o una descrizione, ma è necessario verificare che l' *ID del segnalibro* si trovi nella colonna appropriata del file di importazione. Se l' *ID del segnalibro* è presente, non verrà trattato come nuova aggiunta e non verrà elaborato come errore.

### <a name="publish-or-review-recommended-bookmarks"></a>Pubblicare o rivedere i segnalibri consigliati

Per ridurre lo sforzo manuale necessario per aggiungere segnalibri, Microsoft Search è in grado di valutare i collegamenti di SharePoint nell'organizzazione e di consigliare i segnalibri ed è possibile esaminarli prima di pubblicarli o impostarli in modo che vengano pubblicati automaticamente. Non è necessaria alcuna configurazione per i segnalibri consigliati, che sono abilitati e impostati per la pubblicazione automatica per impostazione predefinita. Per modificare queste impostazioni in qualsiasi momento, selezionare **Gestisci segnalibri** per aprire il riquadro Impostazioni segnalibro.

![Schermata delle impostazioni consigliate del segnalibro nel portale di amministrazione di Microsoft 365](media/bookmarks-recommendedsettings.png)

Se sono abilitati i segnalibri consigliati, il motore di raccomandazione valuterà i siti di SharePoint nell'organizzazione per identificare i collegamenti ad alto traffico. Dopo un periodo di valutazione iniziale, i segnalibri consigliati verranno pubblicati automaticamente o aggiunti all'elenco dei segnalibri suggeriti. Il ciclo successivo, ovvero un periodo di valutazione di 30 giorni seguito da pubblicazione automatica o aggiunta di segnalibri suggeriti, inizierà.

Si consiglia agli amministratori di ricerca o ai redattori di esaminare periodicamente questi segnalibri pubblicati automaticamente o suggeriti. Inoltre, i segnalibri consigliati non includeranno mai gli URL trovati nei segnalibri pubblicati, suggeriti, pianificati o esclusi esistenti.

Per garantire che solo gli utenti con accesso visualizzino un segnalibro consigliato nei risultati del lavoro, è inclusa una funzionalità di controllo di accesso per tutti i segnalibri consigliati. Gli utenti che non dispongono delle autorizzazioni per accedere a un sito di SharePoint non vedranno mai il segnalibro consigliato per il sito. Questo controllo di accesso è controllato dall'opzione **solo gli utenti con accesso a questo collegamento** nell'impostazione gruppi per ogni segnalibro consigliato.

Il controllo di accesso si interrompe se viene modificato l'URL nel segnalibro consigliato o nell'impostazione gruppi.

Per impedire al motore di raccomandazione di pubblicare o suggerire un segnalibro a un sito specifico, è possibile aggiungere l'URL a un elenco escluso. Il motore di raccomandazione non pubblicherà mai o suggerirà un segnalibro per un sito escluso o una pagina all'interno di un sito escluso.

## <a name="about-keywords-and-reserved-keywords"></a>Informazioni su parole chiave e parole chiave riservate

Un segnalibro può avere più parole chiave e i segnalibri possono condividere la stessa parola chiave, ma la parola chiave riservata non può essere condivisa. Una parola chiave riservata è un termine o una frase univoca che attiva un segnalibro specifico. Una parola chiave riservata può essere associata a una sola risposta. Utilizzare parole chiave riservate con parsimonia.

## <a name="frequently-asked-questions"></a>Domande frequenti

**D: quanto tempo è necessario per rendere visibile un segnalibro in Microsoft Search dopo la pubblicazione?**

**A:**  Un segnalibro è disponibile in Microsoft Search subito dopo la pubblicazione.

**D: quanto tempo è necessario per visualizzare un segnalibro consigliato?**

**A:**  I segnalibri consigliati verranno visualizzati solo in Microsoft Search se sono stati abilitati entrambi i segnalibri consigliati e la pubblicazione automatica. Durante il periodo di valutazione iniziale, il motore di raccomandazione valuterà il traffico di SharePoint per identificare i segnalibri appropriati e quindi pubblicarli automaticamente. Dopo la pubblicazione, diventano disponibili immediatamente in Microsoft Search.

**D: Microsoft Search consiglia i segnalibri dei siti in tutte le lingue?**

**A**: Sì, Microsoft Search è in grado di consigliare i segnalibri di qualsiasi sito di SharePoint interno, indipendentemente dalla lingua.

**D: è possibile interrompere la visualizzazione dei segnalibri consigliati nei risultati della ricerca?**

**A:** Per interrompere la visualizzazione dei segnalibri consigliati, disattivare l'impostazione di pubblicazione automatica nell'interfaccia di amministrazione. I segnalibri consigliati verranno aggiunti all'elenco dei segnalibri suggeriti.

**D: come è possibile identificare un segnalibro consigliato nei risultati della ricerca o nell'interfaccia di amministrazione?**

**A:** Nei risultati della ricerca, i segnalibri consigliati includono la frase "suggerito per te" prima dell'URL. Nell'interfaccia di amministrazione, i segnalibri consigliati avranno un valore proprietario "SYSTEM".

**D: in che modo viene gestito l'accesso a un segnalibro consigliato?**

**A**: un motore di accesso progettato da Microsoft determina se l'URL del segnalibro è accessibile a un utente specifico e visualizza il segnalibro consigliato solo per il gruppo di destinatari corretto. Tuttavia, se l'URL è stato modificato o l'impostazione gruppi è stata modificata, il motore di accesso progettato verrà disabilitato.

**D: che cosa accade se non è stata eseguita alcuna azione nei segnalibri consigliati aggiunti all'elenco consigliato?**

**A: per** evitare un volume elevato di segnalibri nell'elenco consigliato, un segnalibro consigliato (Owner = System) verrà eliminato dopo 180 giorni.

**D: dove è possibile trovare l'ID app per un'applicazione di alimentazione?**

**A**: passare al sito Power Apps e visualizzare il riquadro dei dettagli per l'app. Ulteriori informazioni su [come ottenere un ID app](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id).
