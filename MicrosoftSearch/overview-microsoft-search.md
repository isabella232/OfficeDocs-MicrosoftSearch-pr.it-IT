---
title: Panoramica di Microsoft Search
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Panoramica di Microsoft Search, dei relativi vantaggi e delle app che supportano Microsoft Search.
ms.openlocfilehash: a7250bccd3f77eb3ad2f3c91bdfd176a2141fd98
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508815"
---
# <a name="overview-of-microsoft-search"></a>Panoramica di Microsoft Search

Microsoft Search consente di trovare gli elementi necessari per completare ciò su cui si sta lavorando. Sia che si cerchino persone, file, organigrammi, siti o risposte a domande comuni, è possibile utilizzare Microsoft Search per tutta la giornata lavorativa per ottenere risposte.

Microsoft Search consente agli utenti di trovare le risposte, le persone e il contenuto giuste per completare le proprie attività nell'app in cui stanno già lavorando.

- Gli utenti visualizzano i risultati pertinenti nel **contesto** dell'app da cui eseguono la ricerca. Ad esempio, quando e ricercano in [Microsoft Outlook,](https://www.microsoft.com/outlook)trovano i messaggi di posta elettronica e non i [siti di SharePoint.](http://sharepoint.com/) Quando eseguono una ricerca in SharePoint, trovano file, pagine e siti.
- Indipendentemente dall'app aperta, Microsoft Search è **personale**. Microsoft Search usa le informazioni dettagliate di [Microsoft Graph](https://developer.microsoft.com/graph/) per visualizzare i risultati rilevanti per ogni utente. Ogni utente può visualizzare risultati diversi, anche se due utenti cercano le stesse parole. Visualizzano solo i risultati a cui hanno già accesso. Microsoft Search non modifica le autorizzazioni.
- Gli utenti non devono ricordare dove si trovano le informazioni. Ad esempio, un utente sta lavorando in [Microsoft Word](https://products.office.com/word) e vuole riutilizzare le informazioni di una presentazione che un collega ha condiviso da [OneDrive.](https://onedrive.live.com/about/) Non è necessario passare a OneDrive e cercare la presentazione, ma è sufficiente eseguire ricerche da Word.
- In [Bing](https://bing.com) gli utenti ottengono risultati sia dal Web pubblico sia dall'interno dell'organizzazione.

## <a name="what-users-see"></a>Cosa vedono gli utenti

In [Bing,](https://bing.com)gli utenti usano la stessa casella di ricerca delle ricerche Web. Nelle app di Office gli utenti trovano la casella Microsoft Search nella barra di intestazione. L'aspetto è simile al seguente:

![Screenshot di finestre dell'app con la casella di Microsoft Search nella barra di intestazione](media/Headings_520.png)

Quando gli utenti  fa clic nella casella di ricerca, la ricerca suggerisce i risultati in base all'attività precedente in Office 365 e in base ai contenuti di tendenza nell'organizzazione. I file su cui lavoravano di recente, i comandi usati di recente e le persone con cui collaborano sono esempi di attività che la ricerca considera. Quando gli utenti iniziano a digitare nella **casella di** ricerca, i risultati suggeriti vengono aggiornati. Gli utenti possono aprire i risultati della ricerca direttamente dalla **casella di** ricerca. Ecco un esempio di ricerca in [SharePoint.](http://sharepoint.com/)

![Screenshot della casella Microsoft Search con una query e i risultati suggeriti](media/SERP_text_520.png)

Se i suggerimenti nella casella di ricerca non sono quelli cercati dagli utenti, **invio** apre l'elenco completo dei risultati. Possono usare metadati come chi ha modificato per ultimo l'elemento e quando, dove si trova l'elemento, nonché visualizzarne l'anteprima per determinare se è quello che stanno cercando.

![Screenshot della pagina dei risultati di Microsoft Search](media/search_box.png)

## <a name="benefits-of-microsoft-search"></a>Vantaggi di Microsoft Search

**Esecuzione di ricerche in Microsoft 365 da qualsiasi casella Microsoft Search**: gli utenti possono eseguire ricerche da qualsiasi casella Microsoft Search e tornare rapidamente alle proprie attività. Microsoft Search riunisce i risultati delle origini dati in Office 365, tra [cui SharePoint,](http://sharepoint.com/) [Microsoft OneDrive for Business](https://onedrive.live.com/about/business/)e [Microsoft Exchange Server.](https://products.office.com/exchange/microsoft-exchange-server)

**Ricerca semplice:** Microsoft Search suggerisce i risultati in base all'attività precedente degli utenti in Office 365, direttamente nella **casella di** ricerca.

**Ricerca di file condivisi**: Microsoft Search usa il riconoscimento avanzato delle query per semplificare la ricerca di file condivisi. Gli utenti possono quindi trovare facilmente i file a cui stanno collaborando.

**Visualizzazione di contenuto pertinente**: promuovere le informazioni e le risposte di cui gli utenti hanno bisogno per completare le attività, ad esempio criteri, vantaggi, risorse, strumenti e altro ancora. È inoltre possibile scegliere gruppi specifici, ad esempio nuovi assunti, lavoratori remoti o aree geografiche diverse.

**Amministrazione da tutte le app**: Microsoft Search è **attivo** per impostazione predefinita e qualsiasi operazione di amministrazione viene applicata a Microsoft Search in tutte le app.

## <a name="tailoring-microsoft-search-to-your-organization"></a>Personalizzazione di Microsoft Search in base alle esigenze dell'organizzazione

Gli amministratori possono creare un'esperienza di Microsoft Search straordinaria per gli utenti.

**Mostra contenuto utile:** le risposte forniscono risultati rapidi e autorevoli alle query di ricerca basate su parole chiave. [Pianificare il contenuto.](plan-your-content.md)

**Aggiungere contenuto esterno:** i connettori di Microsoft Graph consentono di portare il contenuto esterno nell'indice. Usare i connettori per migliorare l'esperienza di ricerca con dati e file esterni a Microsoft 365. [Panoramica dei connettori di Microsoft Graph](connectors-overview.md)

**Personalizzare l'esperienza utente:** è possibile personalizzare l'esperienza utente tramite l'uso di verticali e altre configurazioni. [Personalizzare la pagina di Microsoft Search](customize-search-page.md)

## <a name="what-content-is-searched"></a>Contenuto in cui viene ricercata

Microsoft Search mostra il contenuto archiviato dall'organizzazione in Microsoft 365 o indicizzato tramite connettori. Microsoft Search non esegue ricerche nei tenant né mostra i risultati dei contenuti condivisi da altre organizzazioni. Se l'organizzazione ha configurato un ambiente ibrido di SharePoint utilizzando la ricerca ibrida cloud, Microsoft Search restituisce i risultati della ricerca dai contenuti di SharePoint online e locali, inclusi eventuali contenuti esterni connessi all'ambiente SharePoint Server. [Altre informazioni sugli ambienti di ricerca ibridi](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint).

Gli utenti otterrà gli stessi risultati della ricerca ottenuti da altre posizioni e anche da Internet.

## <a name="how-microsoft-search-works"></a>Funzionamento di Microsoft Search

Quando un utente esegue una ricerca, Microsoft Search elabora la query e analizza l'intento della ricerca da frasi più lunghe, usando l'intelligenza artificiale (AI) per apprendere le frasi superflue comuni che gli utenti aggiungono alle query e che non influiscono sull'intento della ricerca. Ad esempio, quando un utente cerca "come cambiare la password", le parole meno importanti vengono estratte dalla query e viene attivata la ricerca in base a quelle più pertinenti, ad esempio "cambiare la password".  
I risultati della ricerca che gli utenti sono **autorizzati** a vedere vengono visualizzati nella pagina dei risultati della ricerca. Microsoft Search usa algoritmi di classificazione intelligenti per ordinare i risultati in base alla pertinenza.

## <a name="how-microsoft-search-in-bing-protects-your-company-data"></a>Come Microsoft Search in Bing protegge i dati aziendali

[Sicurezza e privacy per Microsoft Search in Bing](security-for-search.md)

## <a name="see-also"></a>Vedere anche

[Configurare Microsoft Search](setup-microsoft-search.md)
