---
title: Panoramica di Microsoft Search
ms.author: tlarsen
author: tlarsen
manager: mnirkhe
ms.date: 12/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Panoramica di Microsoft Search, che include informazioni sui vantaggi e le app in cui Microsoft Search è attualmente disponibile.
ms.openlocfilehash: 339b3d6350fa059ddc4dc24685e18739777bf932
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639587"
---
# <a name="overview-of-microsoft-search"></a>Panoramica di Microsoft Search

Microsoft Search è la funzionalità di ricerca unificata inclusa nelle app di produttività di Microsoft 365 e nel più ampio ecosistema Microsoft. Col tempo Microsoft Search sarà disponibile in un numero sempre maggiore di app in Microsoft 365.

Microsoft Search consente agli utenti di trovare le risposte, le persone e i contenuti corretti per completare le attività direttamente nell'app.

- Gli utenti visualizzano i risultati pertinenti nel **contesto** dell'app da cui eseguono la ricerca. Ad esempio, quando eseguono una ricerca in Outlook, trovano messaggi di posta elettronica ma non siti di SharePoint. Quando eseguono una ricerca in SharePoint, trovano file, pagine e siti.
- Indipendentemente dall'app aperta, Microsoft Search è **personale**.  Microsoft Search usa le informazioni dettagliate di Microsoft Graph per visualizzare i risultati pertinenti per ogni utente. Ogni utente può visualizzare risultati diversi, anche se due utenti cercano le stesse parole. Gli utenti visualizzano solo quello i contenuti a cui hanno già accesso dal momento che Microsoft Search non modifica le autorizzazioni.
- Gli utenti non devono ricordare dove si trovano le informazioni. Ad esempio, se un utente sta lavorando in Word e vuole usare le informazioni di una presentazione condivisa da un collega da OneDrive, non deve più passare a OneDrive e cercare quella presentazione, ma può cercarla direttamente da Word.  
- In Bing gli utenti ottengono risultati sia dal Web pubblico sia dall'interno dell'organizzazione.

## <a name="what-users-see"></a>Cosa vedono gli utenti

In Bing, gli utenti usano la stessa casella di ricerca destinata alle ricerche Web. Nelle app di Microsoft 365, la casella di Microsoft Search è sempre disponibile nella barra di intestazione. L'aspetto è simile al seguente:

![Screenshot di finestre dell'app con la casella di Microsoft Search nella barra di intestazione](media/Headings_520.png)


Quando gli utenti fanno clic nella casella di ricerca, vengono suggeriti i risultati in base alle attività precedenti eseguite in Office 365 e in base ai contenuti di tendenza nell'organizzazione. I file su cui hanno lavorato di recente, gli ultimi comandi usati e le persone con cui hanno collaborato sono esempi di attività prese in considerazione dalla ricerca. Quando gli utenti iniziano a digitare nella casella di ricerca, i risultati suggeriti vengono aggiornati automaticamente. Gli utenti possono aprire i risultati della ricerca direttamente dalla casella di ricerca. Ecco un esempio di ricerca in SharePoint.

![Screenshot della casella Microsoft Search con una query e i risultati suggeriti](media/search_box.png)

Se i suggerimenti nella casella di ricerca non corrispondono all'elemento cercato, premere **Invio** per aprire l'elenco completo dei risultati. È possibile usare i metadati, ad esempio l'autore e la data di modifica dell'elemento, la posizione degli elementi e l'anteprima per verificare se l'elemento trovato corrisponde a quello cercato.

![Screenshot della pagina dei risultati di Microsoft Search](media/SERP_text_520.png)

## <a name="benefits-of-microsoft-search"></a>Vantaggi di Microsoft Search

**Esecuzione di ricerche in Microsoft 365 da qualsiasi casella Microsoft Search**: gli utenti possono eseguire ricerche da qualsiasi casella Microsoft Search e tornare rapidamente alle proprie attività. Microsoft Search riunisce i risultati di varie origini dati in Office 365, tra cui SharePoint, OneDrive for Business ed Exchange.

**Ricerca semplificata**: Microsoft Search suggerisce i risultati direttamente nella casella di ricerca in base alle attività precedenti degli utenti in Office 365.

**Ricerca di file condivisi**: Microsoft Search usa il riconoscimento avanzato delle query per semplificare la ricerca di file condivisi. Gli utenti possono quindi trovare facilmente i file a cui stanno collaborando.

**Visualizzazione di contenuto pertinente**: promuovere le informazioni e le risposte di cui gli utenti hanno bisogno per completare le attività, ad esempio criteri, vantaggi, risorse, strumenti e altro ancora. È inoltre possibile scegliere destinatari specifici come i nuovi assunti o i lavoratori in remoto.

**Evoluzione di Microsoft Search**: il set di tipi di contenuti che gli utenti possono cercare e l'intelligenza della casella di ricerca aumenteranno nel tempo.

**Amministrazione da tutte le app**: Microsoft Search è **attivo** per impostazione predefinita e qualsiasi operazione di amministrazione viene applicata a Microsoft Search in tutte le app.

## <a name="apps-that-currently-have-microsoft-search"></a>App in cui è attualmente disponibile Microsoft Search

 Microsoft Search è attivato per impostazione predefinita per tutte le app Microsoft che lo supportano. Basta eseguire l'accesso con un account aziendale o dell'istituto di istruzione.

Microsoft Search è attualmente disponibile nelle app seguenti:
- SharePoint Online
- OneDrive for Business
- Outlook sul web
- App di Office in Windows

Microsoft Search è disponibile per gli utenti connessi anche in:

- Home page di Bing
- Office.com
- Pagine iniziali di Word, Excel e PowerPoint Online

È anche possibile avviare una ricerca in Bing dalla barra degli indirizzi di Edge, se si usa Bing come motore di ricerca predefinito.

## <a name="requirements"></a>Requisiti

È necessario avere uno degli abbonamenti seguenti a Office 365 o Microsoft 365:

- Office 365 Business Essentials e Business Premium
- Office 365 A1/A3/A5
- Office 365 Education E1/E3
- Office 365 Enterprise E1/E3/E3 Developer/E5
- Office 365 F1
- Microsoft 365 Business
- Microsoft 365 A3/A5
- Microsoft 365 F1/E3/E5

È necessario assegnare una di queste licenze sia agli utenti che agli amministratori della ricerca. Possono usare Microsoft Search solo utenti con account attivi che abbiano eseguito l'**accesso** perché Microsoft Search richiede Azure Active Directory

## <a name="tailoring-microsoft-search-to-your-organization"></a>Personalizzazione di Microsoft Search in base alle esigenze dell'organizzazione

Gli amministratori possono semplificare la ricerca per consentire agli utenti di ottenere risultati specifici dell'organizzazione durante la ricerca dalla pagina iniziale di SharePoint, da Office.com o da Bing. A questo scopo, si possono definire le risposte visualizzate da Microsoft Search in risposta a determinate parole chiave usate nelle query. È possibile definire diversi tipi di risposte: 

**Mostrare contenuti utili**: consentire agli utenti di trovare strumenti e risorse utili all'interno dell'organizzazione aggiungendoli ai segnalibri. Così come è possibile creare un segnalibro in una pagina Web pubblica, è possibile creare un segnalibro per qualsiasi pagina Web interna che gli utenti possono cercare. È anche possibile integrare una Power App nel segnalibro per consentire agli utenti di completare le attività direttamente dal segnalibro.

**Rispondere a domande comuni**: fornire le risposte migliori alle domande più frequenti nell’organizzazione. Quando gli utenti immettono una domanda frequente nella casella di ricerca, Microsoft Search mostra la risposta come risultato invece di fornire semplicemente un collegamento alla pagina Web.

**Mostrare posizioni utili**: visualizzare i risultati nella mappa e le informazioni sugli indirizzi per gli edifici, gli uffici e per altre aree di lavoro dell'organizzazione. Gli utenti possono usare le mappe per ottenere indicazioni stradali, vedere cosa c'è nelle vicinanze e altro ancora.

È possibile visualizzare le statistiche di utilizzo che mostrano in che modo gli utenti interagiscono con le risposte e se riescono a trovare quello che cercano. In base a questi dati, è quindi possibile ottimizzare le risposte esistenti o aggiungere nuove risposte.

Per altre informazioni sull'uso di parole chiave e parole chiave riservate, vedere [Facilitare la ricerca del contenuto](make-content-easy-to-find.md).

## <a name="what-content-is-searched"></a>Contenuto cercato

Microsoft Search consente di cercare in contenuti archiviati dall'organizzazione in SharePoint Online, OneDrive for Business ed Exchange, inclusi l'elenco di indirizzi globale e i gruppi di Office 365. Microsoft Search non esegue la ricerca nei tenant né visualizza risultati presenti in contenuti condivisi dalle organizzazioni. Se l'organizzazione ha configurato un ambiente di SharePoint ibrido con la ricerca ibrida nel cloud, Microsoft Search restituisce risultati di ricerca dai contenuti di SharePoint in locale e online, inclusi tutti i contenuti esterni connessi all'ambiente di SharePoint Server. [Altre informazioni sugli ambienti di ricerca ibridi](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint).

Quando gli utenti cercano nella pagina iniziale di SharePoint o in Office.com, Microsoft Search esegue la ricerca in tutto il contenuto all'interno dell'organizzazione e mostra i risultati che l'utente è autorizzato a visualizzare. Questa funzionalità è nota come **ambito di ricerca globale**.

Quando gli utenti cercano in Bing, ottengono i risultati più rilevanti da tutto il contenuto dell'organizzazione incorporato nell'elenco dei risultati dal **Web.** Se è necessario visualizzare **tutti** i risultati dell'organizzazione, l'ambito di ricerca globale è a portata di clic.

## <a name="what-types-of-results-can-users-find"></a>Quali tipi di risultati possono essere trovati dagli utenti?
Gli utenti trovano i seguenti tipi di risultati quando eseguono una ricerca in:

**SharePoint**: file, cartelle, persone nell'organizzazione, organigrammi, siti, pagine del sito, notizie, elenchi e voci di elenco. Se definiti, risposte alle domande comuni, segnalibri relativi a informazioni rilevanti, posizioni in una mappa e strumenti. [Informazioni sui tipi di file che è possibile trovare](https://docs.microsoft.com/it-IT/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).

**Pagine iniziali di Office.com, Word, Excel e PowerPoint Online**: app, file, cartelle, persone, organigrammi, siti di SharePoint, pagine del sito, elenchi e voci di elenco. Se definiti, risposte alle domande comuni, segnalibri relativi a informazioni rilevanti, posizioni in una mappa e strumenti. Vengono trovati file dello stesso tipo di SharePoint.

**Bing**: contenuti nel Web pubblico, file, gruppi di Office 365, persone, conversazioni di Yammer e Teams, organigrammi, siti di SharePoint. Se definiti, risposte alle domande comuni, segnalibri relativi a informazioni rilevanti, posizioni in una mappa e strumenti.  I risultati includono file di Word, Excel, PowerPoint, Visio, OneNote e PDF.

**Outlook**: messaggi di posta elettronica, allegati e persone nell'organizzazione.

**App di Office in Windows**: azioni nell'app, persone dell'organizzazione e nel Web, file, definizioni di parole, risultati della query all'interno del file o nella Guida, contenuti nel Web. I risultati includono file di Word, Excel, PowerPoint, Visio e OneNote.

**OneDrive**: vengono trovati file dello stesso tipo di SharePoint.

## <a name="how-does-microsoft-search-work"></a>Come funziona Microsoft Search?

Quando un utente esegue una ricerca, Microsoft Search elabora la query e analizza l'intento della ricerca da frasi più lunghe, usando l'intelligenza artificiale (AI) per apprendere le frasi superflue comuni che gli utenti aggiungono alle query e che non influiscono sull'intento della ricerca. Ad esempio, quando un utente cerca "come cambiare la password", le parole meno importanti vengono estratte dalla query e viene attivata la ricerca in base a quelle più pertinenti, ad esempio "cambiare la password".  

Microsoft Search non crea un nuovo indice, ma cerca negli indici esistenti dei contenuti di SharePoint Online, OneDrive for Business ed Exchange.

I risultati della ricerca che gli utenti sono **autorizzati** a vedere vengono visualizzati nella pagina dei risultati della ricerca. Microsoft Search usa algoritmi di classificazione intelligenti per ordinare i risultati in base alla pertinenza.

## <a name="microsoft-search-in-sharepoint"></a>Microsoft Search in SharePoint

Microsoft Search in SharePoint è l'esperienza di ricerca moderna disponibile in SharePoint Online. In SharePoint Online è disponibile anche un'esperienza di ricerca classica. Entrambe le esperienze sono attivate per impostazione predefinita e consentono di eseguire ricerche nello stesso contenuto. L'amministratore della ricerca non può attivare queste esperienze di ricerca in SharePoint. Il tipo di esperienza di ricerca visualizzata dagli utenti varia in base alla posizione in cui effettuano la ricerca:

- La casella di Microsoft Search viene visualizzata nella pagina iniziale, nei siti hub, nei siti di comunicazione e nei siti dei team moderni di SharePoint.
- La casella di ricerca classica viene invece visualizzata nei siti di pubblicazione, nei siti dei team classici e nel Centro ricerche.

È possibile personalizzare l'esperienza di ricerca, ad esempio aggiungendo affinamenti personalizzati per la pagina dei risultati o visualizzando un determinato tipo di risultati in modo diverso. Non è possibile personalizzare l'esperienza di Microsoft Search in questo modo. Alcune delle personalizzazioni apportate alla ricerca classica potrebbero influire su Microsoft Search in SharePoint. Se l'organizzazione userà entrambe le esperienze di ricerca in SharePoint, [ottenere informazioni sulle differenze e su come evitare di influire su Microsoft Search in SharePoint](https://docs.microsoft.com/it-IT/sharepoint/differences-classic-modern-search).

## <a name="microsoft-search-in-bing"></a>Microsoft Search in Bing

Dal momento che le ricerche aziendali possono essere riservate, Microsoft Search usa una serie di misure di protezione per la gestione di tali ricerche da parte dei risultati Web pubblici di Bing.

Le richieste di Microsoft Search vengono effettuate tramite HTTPS. Questa caratteristica garantisce una connessione crittografata end-to-end per una sicurezza avanzata. Inoltre, tutti i log di ricerca correlati al traffico di Microsoft Search vengono resi anonimi e archiviati separatamente dal traffico pubblico, non di Microsoft Search.

Indipendentemente dal fatto che una query utente contenga uno o più risultati correlati al lavoro nella risposta risultante, vengono adottate le misure seguenti:

**Registrazione**: tutti i log di ricerca appartenenti al traffico di Microsoft Search vengono privati degli elementi identificativi e mantenuti per 18 mesi. Le query archiviate in questi log di sistema verranno usate solo per modellare ed eseguire il training di funzionalità pubbliche, come i suggerimenti automatici o le ricerche correlate per i risultati di siti Web pubblici, quando vengono le soglie di frequenza e i set di restrizioni, in modo da essere certi che queste query siano comuni e non specifiche di una determinata organizzazione. La query deve apparire un numero significativo di volte nella correlazione dei dati di utenti non di Microsoft Search e non deve attivare esclusivamente risultati della ricerca aziendali. Le query che non soddisfano questi requisiti verranno archiviate separatamente dal traffico pubblico non di Microsoft Search. L'accesso limitato viene gestito usando vari meccanismi di sicurezza, inclusi i gruppi di sicurezza e altri livelli del sistema di progettazione.

**Cronologia di ricerca**: quando l'utente accede con un account aziendale o dell'istituto di istruzione, la cronologia di ricerca non sarà disponibile in altri computer o dispositivi.

**Pubblicità**: le query di ricerca di contenuti nell'organizzazione non vengono mai condivise né suggerite agli inserzionisti.
Le inserzioni non vengono mai personalizzate in base all'identità professionale o all'azienda di un utente.

## <a name="see-also"></a>Vedere anche

[Configurare Microsoft Search](setup-microsoft-search.md)

[Facilitare la ricerca del contenuto](make-content-easy-to-find.md)