---
title: Panoramica di Microsoft Search
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Ottenere una panoramica delle funzionalità di ricerca di Microsoft, dei vantaggi e delle app che supportano Microsoft Search.
ms.openlocfilehash: 4acc3b9fcb7453f84db256cc20e839066dc94af5
ms.sourcegitcommit: f4cb37fdf85b895337caee827fb72b5b7fcaa8ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2019
ms.locfileid: "39995033"
---
# <a name="overview-of-microsoft-search"></a>Panoramica di Microsoft Search

Microsoft Search aiuta a trovare le informazioni necessarie per completare il lavoro. Se si sta cercando persone, file, organigrammi, siti o risposte a domande comuni, è possibile utilizzare Microsoft Search per tutta la giornata lavorativa per ottenere risposte.

Microsoft Search consente agli utenti di trovare le risposte, le persone e i contenuti corretti per completare le attività direttamente nell'app.

- Gli utenti visualizzano i risultati pertinenti nel **contesto** dell'app da cui eseguono la ricerca. Ad esempio, quando si esegue una ricerca in [Microsoft Outlook](https://www.microsoft.com/outlook), vengono trovati messaggi di posta elettronica e non siti di [SharePoint](http://sharepoint.com/) . Quando eseguono una ricerca in SharePoint, trovano file, pagine e siti.
- Indipendentemente dall'app aperta, Microsoft Search è **personale**. Microsoft Search utilizza informazioni approfondite da [Microsoft Graph](https://developer.microsoft.com/graph/) per visualizzare i risultati rilevanti per ogni utente. Ogni utente può visualizzare risultati diversi, anche se due utenti cercano le stesse parole. Gli utenti visualizzano solo quello i contenuti a cui hanno già accesso dal momento che Microsoft Search non modifica le autorizzazioni.
- Gli utenti non devono ricordare dove si trovano le informazioni. Ad esempio, un utente lavora in [Microsoft Word](https://products.office.com/word) e desidera riutilizzare le informazioni di una presentazione che un collega ha condiviso dal proprio [OneDrive](https://onedrive.live.com/about/). non deve più passare a OneDrive e cercare quella presentazione, ma può cercarla direttamente da Word.
- In [Bing](https://bing.com) gli utenti ottengono risultati sia dal Web pubblico sia dall'interno dell'organizzazione.

## <a name="what-users-see"></a>Cosa vedono gli utenti

In [Bing](https://bing.com)gli utenti utilizzano la stessa casella di ricerca per le ricerche Web. Nelle app di Office, gli utenti trovano la casella di ricerca di Microsoft nella barra di intestazione. L'aspetto è simile al seguente:

![Screenshot di finestre dell'app con la casella di Microsoft Search nella barra di intestazione](media/Headings_520.png)

Quando gli utenti fanno clic nella casella di **ricerca** , vengono suggeriti i risultati in base alle attività precedenti di Office 365 e basati sul contenuto che è in trend nell'organizzazione. I file su cui hanno lavorato di recente, gli ultimi comandi usati e le persone con cui hanno collaborato sono esempi di attività prese in considerazione dalla ricerca. Quando gli utenti iniziano a digitare nella casella di **ricerca** , l'aggiornamento dei risultati suggeriti. Gli utenti possono aprire i risultati della ricerca direttamente dalla casella di **ricerca** . Di seguito è riportato un esempio di ricerca in [SharePoint](http://sharepoint.com/).

![Screenshot della casella Microsoft Search con una query e i risultati suggeriti](media/SERP_text_520.png)

Se i suggerimenti nella casella di ricerca non sono ciò che gli utenti stanno cercando, **Enter** apre l'elenco completo dei risultati. È possibile usare i metadati, ad esempio l'autore e la data di modifica dell'elemento, la posizione degli elementi e l'anteprima per verificare se l'elemento trovato corrisponde a quello cercato.

![Screenshot della pagina dei risultati di Microsoft Search](media/search_box.png)

## <a name="benefits-of-microsoft-search"></a>Vantaggi di Microsoft Search

**Esecuzione di ricerche in Microsoft 365 da qualsiasi casella Microsoft Search**: gli utenti possono eseguire ricerche da qualsiasi casella Microsoft Search e tornare rapidamente alle proprie attività. Microsoft Search riunisce i risultati delle origini dati in Office 365, tra cui [SharePoint](http://sharepoint.com/), [Microsoft OneDrive for business](https://onedrive.live.com/about/business/)e [Microsoft Exchange Server](https://products.office.com/exchange/microsoft-exchange-server).

**Facile da cercare** : la ricerca di Microsoft suggerisce i risultati in base alle attività precedenti degli utenti in Office 365, direttamente nella casella di **ricerca** .

**Ricerca di file condivisi**: Microsoft Search usa il riconoscimento avanzato delle query per semplificare la ricerca di file condivisi. Gli utenti possono quindi trovare facilmente i file a cui stanno collaborando.

**Visualizzazione di contenuto pertinente**: promuovere le informazioni e le risposte di cui gli utenti hanno bisogno per completare le attività, ad esempio criteri, vantaggi, risorse, strumenti e altro ancora. È inoltre possibile assegnare a gruppi specifici, come nuovi assunti, operatori remoti o diverse aree geografiche.

**Amministrazione da tutte le app**: Microsoft Search è **attivo** per impostazione predefinita e qualsiasi operazione di amministrazione viene applicata a Microsoft Search in tutte le app.

## <a name="tailoring-microsoft-search-to-your-organization"></a>Personalizzazione di Microsoft Search in base alle esigenze dell'organizzazione

Come amministratore, è possibile creare un'incredibile esperienza di ricerca di Microsoft per gli utenti. 

**Mostra contenuto utile** : le risposte forniscono risultati veloci e autorevoli alle query di ricerca in base alle parole chiave. [Rendere il contenuto facile da trovare](make-content-easy-to-find.md).

**Aggiungi contenuto esterno** : i connettori Microsoft Graph consentono di portare contenuto esterno nell'indice. Utilizzare i connettori per arricchire l'esperienza di ricerca con dati e file provenienti dall'esterno di Microsoft 365. [Panoramica dei connettori di Microsoft Graph](connectors-overview.md)

**Personalizzare l'esperienza utente** : è possibile personalizzare l'esperienza utente tramite l'utilizzo di verticali e altre configurazioni. [Personalizzare la pagina di ricerca di Microsoft](customize-search-page.md)

## <a name="what-content-is-searched"></a>Contenuto cercato

Microsoft Search Visualizza il contenuto archiviato dall'organizzazione in Microsoft 365 o indicizzato tramite i connettori. Microsoft Search non esegue la ricerca tra i tenant o Mostra i risultati del contenuto condiviso da altre organizzazioni. Se l'organizzazione ha configurato un ambiente di SharePoint ibrido con la ricerca ibrida nel cloud, Microsoft Search restituisce risultati di ricerca dai contenuti di SharePoint in locale e online, inclusi tutti i contenuti esterni connessi all'ambiente di SharePoint Server. [Altre informazioni sugli ambienti di ricerca ibridi](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint).

Gli utenti riceveranno gli stessi risultati della ricerca ottenuti da altre posizioni e riceveranno anche i risultati da Internet.

## <a name="how-does-microsoft-search-work"></a>Come funziona Microsoft Search?

Quando un utente esegue una ricerca, Microsoft Search elabora la query e analizza l'intento della ricerca da frasi più lunghe, usando l'intelligenza artificiale (AI) per apprendere le frasi superflue comuni che gli utenti aggiungono alle query e che non influiscono sull'intento della ricerca. Ad esempio, quando un utente cerca "come cambiare la password", le parole meno importanti vengono estratte dalla query e viene attivata la ricerca in base a quelle più pertinenti, ad esempio "cambiare la password".  
I risultati della ricerca che gli utenti sono **autorizzati** a vedere vengono visualizzati nella pagina dei risultati della ricerca. Microsoft Search usa algoritmi di classificazione intelligenti per ordinare i risultati in base alla pertinenza.

## <a name="how-does-microsoft-search-in-bing-help-protect-my-company-data"></a>In che modo Microsoft Search in Bing aiuta a proteggere i dati aziendali?

[Protezione e privacy per Microsoft Search in Bing](security-for-search.md)

## <a name="see-also"></a>Vedere anche

[Configurare Microsoft Search](setup-microsoft-search.md)

[Facilitare la ricerca del contenuto](make-content-easy-to-find.md)
