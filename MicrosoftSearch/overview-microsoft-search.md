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
ms.openlocfilehash: cbf372e9fa7ced4a5e23e7d80d566192ab703a49
ms.sourcegitcommit: aeb44797427bd39c133fa899ab77277dd90fe47b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "33970139"
---
# <a name="overview-of-microsoft-search"></a>Panoramica di Microsoft Search

Microsoft Search è la funzionalità di ricerca unificata inclusa nelle app di produttività di Microsoft 365 e nel più ampio ecosistema Microsoft. Col tempo Microsoft Search sarà disponibile in un numero sempre maggiore di app in Microsoft 365.

Microsoft Search consente agli utenti di trovare le risposte, le persone e i contenuti corretti per completare le attività direttamente nell'app. Con Microsoft Search:
- Gli utenti visualizzano i risultati pertinenti nel **contesto** dell'app da cui eseguono la ricerca. Ad esempio, quando eseguono una ricerca in Outlook, trovano messaggi di posta elettronica ma non siti di SharePoint. Quando eseguono una ricerca in SharePoint, trovano file, pagine e siti, non messaggi.
- Indipendentemente dall'app aperta, Microsoft Search è **personale**.  Microsoft Search usa le informazioni dettagliate di Microsoft Graph per visualizzare i risultati pertinenti per ogni utente. Ogni utente può visualizzare risultati diversi, anche se due utenti cercano le stesse parole. Gli utenti visualizzano solo quello i contenuti a cui hanno già accesso dal momento che Microsoft Search non modifica le autorizzazioni.   
- Gli utenti non devono ricordare dove si trovano le informazioni. Ad esempio, se un utente sta lavorando in Word e vuole usare le informazioni di una presentazione condivisa da un collega da OneDrive, non deve più passare a OneDrive e cercare quella presentazione, ma può cercarla direttamente da Word.  
- In Bing gli utenti possono visualizzare i risultati sia dal Web pubblico che dall'interno dell'organizzazione. 

La casella di Microsoft Search, sempre disponibile nella barra di intestazione, è simile a questa:

![Screenshot di finestre dell'app con la barra di Microsoft Search nell'intestazione](media/Headings_400.png)


Quando gli utenti fanno clic nella casella di ricerca, vengono suggeriti i risultati in base alle attività precedenti eseguite in Office 365 e in base ai contenuti di tendenza nell'organizzazione. I file su cui hanno lavorato di recente, gli ultimi comandi usati e le persone con cui hanno collaborato sono esempi di attività prese in considerazione dalla ricerca. Quando gli utenti iniziano a digitare nella casella di ricerca, i risultati suggeriti vengono aggiornati automaticamente. Gli utenti possono aprire i risultati della ricerca direttamente dalla casella di ricerca.

![Screenshot della casella Microsoft Search con una query e i risultati suggeriti](media/search_box.png)




Se i suggerimenti nella casella di ricerca non corrispondono all'elemento cercato, premere INVIO per aprire l'elenco completo dei risultati. È possibile usare i metadati, ad esempio l'autore e la data di modifica dell'elemento, la posizione degli elementi e l'anteprima per verificare se l'elemento trovato corrisponde a quello cercato.

![Screenshot della pagina dei risultati di Microsoft Search](media/SERP_text_520.png)



## <a name="benefits"></a>Vantaggi 
**Esecuzione di ricerche in Microsoft 365 da qualsiasi casella Microsoft Search**: gli utenti possono eseguire ricerche da qualsiasi casella Microsoft Search e tornare rapidamente alle proprie attività. Microsoft Search riunisce i risultati di varie origini dati in Office 365, tra cui SharePoint, OneDrive for Business, Exchange e il Web pubblico.

**Ricerca semplificata**: Microsoft Search suggerisce i risultati direttamente nella casella di ricerca in base alle attività precedenti degli utenti in Office 365.

**Ricerca di file condivisi**: Microsoft Search usa il riconoscimento avanzato delle query per semplificare la ricerca di file condivisi. Gli utenti possono quindi trovare facilmente i file a cui stanno collaborando.

**Visualizzazione di contenuto pertinente**: promuovere le informazioni e le risposte di cui gli utenti hanno bisogno per completare le attività, ad esempio criteri, vantaggi, risorse, strumenti e altro ancora. È inoltre possibile scegliere destinatari specifici come i nuovi assunti o i lavoratori in remoto.

**Evoluzione di Microsoft Search**: il set di tipi di contenuti che gli utenti possono cercare e l'intelligenza della casella di ricerca aumenteranno nel tempo.

**Amministrazione da tutte le app**: Microsoft Search è attivo per impostazione predefinita e qualsiasi operazione di amministrazione viene applicata a Microsoft Search in tutte le app.

## <a name="which-apps-currently-have-microsoft-search"></a>In quali app è attualmente disponibile Microsoft Search? 
Col tempo Microsoft Search sarà disponibile in un numero sempre maggiore di app in Microsoft 365.
Microsoft Search è attualmente disponibile nelle app di Office 365 seguenti:
- SharePoint Online 
- OneDrive for Business
- Outlook sul web
- App di Office in Windows

Microsoft Search è disponibile anche in:
- Bing 
- Office.com
- Pagine iniziali di Word, Excel e PowerPoint Online

È anche possibile avviare una ricerca in Bing dalla barra degli indirizzi di Edge.

## <a name="requirements"></a>Requisiti 
L'organizzazione deve disporre di un tenant di Office 365 con uno dei seguenti abbonamenti:
- Office 365 Business Essentials e Business Premium
- Office 365 A1/A3/A5
- Office 365 Education E1/E3
- Office 365 Enterprise E1/E3/E3 Developer/E5 
- Office 365 F1 
- Microsoft 365 Business 
- Microsoft 365 A3/A5 
- Microsoft 365 F1/E3/E5 

Possono usare Microsoft Search solo utenti con account attivi che hanno **effettuato l'accesso**.

## <a name="what-can-users-find-with-microsoft-search"></a>Cosa trovano gli utenti con Microsoft Search? 
Microsoft Search consente di cercare in contenuti archiviati in Outlook, OneDrive e SharePoint Online, incluse le persone nell'elenco indirizzi globale e nei gruppi di Office 365. Se si usa la ricerca ibrida nel cloud per configurare un ambiente di SharePoint ibrido, gli utenti di Microsoft Search possono visualizzare risultati dai contenuti di SharePoint locale, inclusi tutti i contenuti esterni connessi all'ambiente di SharePoint Server. [Altre informazioni sugli ambienti di ricerca ibridi](https://docs.microsoft.com/it-IT/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint).

Quando gli utenti cercano nella pagina iniziale di SharePoint o Office.com, Microsoft Search cerca all'interno dell'organizzazione e mostra tutti i risultati trovati. Questa funzionalità è nota come ambito di ricerca globale.

Durante la ricerca da Bing, Microsoft Search cerca sia nell'organizzazione che nel Web pubblico. Viene visualizzata una vasta gamma dei risultati più pertinenti dell'organizzazione incorporata nell'elenco dei risultati. Se è necessario visualizzare tutti i risultati dell'organizzazione, l'ambito di ricerca globale è a portata di clic.

Durante la ricerca da un'app, gli utenti visualizzano i risultati pertinenti al contesto in cui stanno lavorando. Ad esempio, troveranno messaggi di posta elettronica quando eseguono ricerche da Outlook, siti, notizie e contenuti negli elenchi quando cercano da SharePoint e azioni o parole nella presentazione quando lavorano o cercano da PowerPoint.

Ecco una panoramica dei tipi di risultati che gli utenti possono visualizzare in ogni app:

**Outlook**: messaggi di posta elettronica, allegati e persone nell'organizzazione.

**App di Office in Windows**: azioni nell'app, persone dell'organizzazione e nel Web pubblico, file, definizioni di parole, risultati della query all'interno del file o nella Guida, contenuti nel Web pubblico. I risultati includono file di Word, Excel, PowerPoint, Visio e OneNote.

**OneDrive**: vengono trovati file dello stesso tipo di SharePoint.

**SharePoint**: file, cartelle, persone nell'organizzazione, organigrammi, siti, pagine del sito, notizie, elenchi e voci di elenco. Se definiti, risposte alle domande comuni, segnalibri relativi a informazioni rilevanti, posizioni in una mappa e strumenti. Informazioni sui tipi di file che è possibile trovare.

**Bing**: contenuti nel Web pubblico, file, gruppi di Office 365, persone, conversazioni di Yammer e Teams, organigrammi, siti di SharePoint. Se definiti, risposte alle domande comuni, segnalibri relativi a informazioni rilevanti, posizioni in una mappa e strumenti.  I risultati includono file di Word, Excel, PowerPoint, OneNote e PDF.

**Pagine iniziali di Office.com, Word, Excel e PowerPoint Online**: app, file, cartelle, persone, organigrammi, siti di SharePoint, pagine del sito, elenchi e voci di elenco. Se definiti, risposte alle domande comuni, segnalibri relativi a informazioni rilevanti, posizioni in una mappa e strumenti. Vengono trovati file dello stesso tipo di SharePoint.

## <a name="tailoring-microsoft-search-to-your-organization"></a>Personalizzazione di Microsoft Search in base alle esigenze dell'organizzazione

Gli amministratori possono semplificare la ricerca per consentire agli utenti di ottenere risultati specifici dell'organizzazione durante la ricerca dalla pagina iniziale di SharePoint, da Office.com o da Bing. È possibile gestire Microsoft Search dalla sezione di Microsoft Search nell'interfaccia di amministrazione di Microsoft 365.

**Mostrare contenuti utili**: consentire agli utenti di trovare strumenti e risorse utili all'interno dell'organizzazione aggiungendoli ai segnalibri. Così come è possibile creare un segnalibro in una pagina Web pubblica, è possibile creare un segnalibro per qualsiasi pagina Web interna che gli utenti possono cercare. È anche possibile integrare una Power App nel segnalibro per consentire agli utenti di completare le attività direttamente dal segnalibro.

**Rispondere a domande comuni**: fornire le risposte migliori alle domande più frequenti. Quando gli utenti immettono una domanda frequente nella casella di ricerca, Microsoft Search mostra la risposta come risultato invece di fornire semplicemente un collegamento alla pagina Web.

**Mostrare posizioni utili**: visualizzare i risultati nella mappa e le informazioni sugli indirizzi per gli edifici, gli uffici e per altre aree di lavoro dell'organizzazione. Gli utenti possono usare le mappe per ottenere indicazioni stradali, vedere cosa c'è nelle vicinanze e altro ancora.

## <a name="how-does-microsoft-search-work"></a>Come funziona Microsoft Search?
Microsoft Search trova automaticamente il contenuto in SharePoint Online, OneDrive for Business e Exchange. Se è stato configurato uno SharePoint Server ibrido e l'ambiente di ricerca di SharePoint Online con la ricerca ibrida nel cloud, Microsoft Search può trovare contenuto da SharePoint locale, inclusi i contenuti tramite connettori locali.

Quando un utente esegue una ricerca, Microsoft Search elabora la query e analizza l'intento della ricerca da frasi più lunghe, usando l'intelligenza artificiale (AI) per apprendere le frasi superflue comuni che gli utenti aggiungono alle query e che non influiscono sull'intento della ricerca. Ad esempio, quando un utente cerca "informazioni su come cambiare la password", le parole meno importanti vengono estratte dalla query e viene attivata la ricerca in base a quelle più pertinenti, ad esempio "cambiare la password".  

I risultati della pagina che gli utenti sono autorizzati a vedere vengono visualizzati nella pagina dei risultati della ricerca. Microsoft Search usa algoritmi di classificazione intelligenti per ordinare i risultati in base alla pertinenza.

## <a name="microsoft-search-in-sharepoint"></a>Microsoft Search in SharePoint 
Microsoft Search è l'esperienza di ricerca moderna disponibile in SharePoint Online. In SharePoint Online è disponibile anche un'esperienza di ricerca classica. L'amministratore della ricerca non può attivare o disattivare l'esperienza di ricerca classica né quella moderna. Sono entrambe attivate per impostazione predefinita. Il tipo di esperienza di ricerca visualizzata dagli utenti varia in base alla posizione in cui effettuano la ricerca:

- La casella di Microsoft Search viene visualizzata nella pagina iniziale, nei siti hub, nei siti di comunicazione e nei siti dei team moderni di SharePoint.
- La casella di ricerca classica viene invece visualizzata nei siti di pubblicazione, nei siti dei team classici e nel Centro ricerche.

Entrambe le esperienze di ricerca consentono di trovare risultati da contenuti in SharePoint e OneDrive for Business e utenti in Office 365.

Se si continua a usare la ricerca classica in SharePoint, consultare le [informazioni su come evitare di influire sull'esperienza di Microsoft Search in SharePoint](https://docs.microsoft.com/it-IT/sharepoint/differences-classic-modern-search).  

## <a name="microsoft-search-in-bing"></a>Microsoft Search in Bing 
Quando gli utenti che hanno eseguito l'accesso a Microsoft 365 eseguono ricerche in Bing, vengono visualizzati sia i risultati Web che quelli dell'organizzazione.
Dal momento che le ricerche aziendali possono essere riservate, Microsoft Search ha implementato una serie di misure di protezione per la gestione delle stesse da parte dei risultati Web pubblici di Bing.

Indipendentemente dal fatto che una query utente contenga uno o più risultati di lavoro nella risposta risultante, vengono adottate le misure seguenti: 

**Registrazione**: tutti i log di ricerca appartenenti al traffico di Microsoft Search vengono privati degli elementi identificativi e archiviati separatamente dal traffico pubblico, non di Microsoft Search. Vengono conservati per 18 mesi e l'accesso è limitato solo ai fini del debug. Le query in questi log non vengono usate per modellare o eseguire il traning delle funzionalità pubbliche, ad esempio i suggerimenti automatici o le ricerche correlate per il Web pubblico. L'accesso limitato viene gestito usando vari meccanismi di sicurezza, inclusi i gruppi di sicurezza e altri livelli del sistema di progettazione.

**Cronologia di ricerca**: quando l'utente accede con un account aziendale o dell'istituto di istruzione, la cronologia di ricerca non sarà disponibile in altri computer o dispositivi.

**Pubblicità**: le query di ricerca di contenuti nell'organizzazione non vengono mai condivise né suggerite agli inserzionisti.
I log di Cerca inserzioni relativi a Microsoft Search vengono archiviati separatamente dal traffico pubblico.
Le inserzioni non vengono mai personalizzate in base all'identità professionale o all'azienda di un utente.

## <a name="see-also"></a>Vedere anche
[Configurare Microsoft Search](setup-microsoft-search.md)

[Facilitare la ricerca del contenuto](make-content-easy-to-find.md)

