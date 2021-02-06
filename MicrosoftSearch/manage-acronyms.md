---
title: Gestire le risposte degli acronimi in Microsoft Search
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Creare e aggiornare le risposte degli acronimi in Microsoft Search
ms.openlocfilehash: 45d3cc7b33f27d2f4e77d8099fbfa91e01aabcbb
ms.sourcegitcommit: ef94ffd6111acb929c8343f0f4f82ea109b68fb6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122157"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gestire le risposte degli acronimi in Microsoft Search

Gli utenti spesso si trovano in acronimi e abbreviazioni sconosciuti utilizzati dall'organizzazione o dal team. I termini specifici per le organizzazioni o i team potrebbero essere nuovi per gli utenti che passano da un team all'altro, lavorano con i team partner interni o sono nuovi nell'organizzazione.

Le organizzazioni non hanno sempre un singolo riferimento per la terminologia standard. La mancanza di un singolo riferimento rende difficile trovare definizioni o espansioni per questi acronimi. Microsoft Search risolve il problema con gli acronimi.

## <a name="what-users-experience"></a>Esperienza degli utenti

Gli utenti di Microsoft Search possono ottenere definizioni con acronimi in [Bing,](https://Bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)e [Office 365.](https://Office.com) Nella casella **di ricerca** gli utenti immettono query come questi esempi:

- *Che cos'è* DNN
- *Definire* DNN
- Definizione *DNN*
- *Espandi* DNN
- Espansione *DNN*
- *Significato di* DNN
- DNN *significa*

Il risultato include tutti i significati della DNN presenti all'interno dell'organizzazione dell'utente.

> [!NOTE]
> Gli utenti devono immettere una query che includa le parole chiave specificate dall'acronimo *per* attivare le risposte corrispondenti. Le query con acronimo non supportano la distinzione tra maiuscole e minuscole.

## <a name="set-up-acronyms-answers"></a>Configurare le risposte con acronimi

Nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com)passare [**ad Acronimi**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)e quindi selezionare **Aggiungi acronimo.**

Microsoft Search esegue una query su due origini dati per fornire agli acronimi le risposte alle ricerche degli utenti:

1. **Curato dall'amministratore.** Fornito dagli amministratori IT [nell'interfaccia di amministrazione.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)
2. **System-curated**. Individuato da Microsoft Search dalla posta elettronica e dai documenti degli utenti e dai dati disponibili pubblicamente all'interno dell'organizzazione.

### <a name="set-up-admin-curated-acronyms"></a>Configurare acronimi curati dall'amministratore

Gli amministratori della ricerca possono aggiungere acronimi nella [scheda Acronimi](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) nell'interfaccia [di amministrazione di Microsoft Search.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) È possibile aggiungere acronimi da qualsiasi sito o archivio interno all'interfaccia di amministrazione. Questi acronimi possono essere aggiunti allo **stato Published** o **Draft:**

**Stato pubblicato.** Gli acronimi sono disponibili per gli utenti dell'organizzazione tramite Microsoft Search.

> [!NOTE]
> Potrebbero essere disponibili fino a tre giorni prima che gli acronimi aggiunti allo stato Published diventino disponibili in Microsoft Search.

**Stato bozza.** Se si desidera esaminare un acronimo prima di renderlo disponibile in Microsoft Search, è possibile aggiungere l'acronimo in uno stato Bozza. Gli acronimi nello stato Bozza non verranno visualizzati nei risultati della ricerca. Sarà necessario spostare l'acronimo nello stato Published per renderlo visualizzato nei risultati della ricerca.

È possibile aggiungere gli acronimi singolarmente o importarli in blocco in un file CSV. Caricare un file CSV con i campi mostrati nella tabella seguente:

| Acronimo (obbligatorio) | Espansione (obbligatorio) | URL | Descrizione  | Stato (obbligatorio) | Ultima modifica | Data ultima modifica | Id |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *Abbreviazione con ortografia* | *Source* |  | *Published o Draft* |  |  |  |

### <a name="csv-fields"></a>Campi CSV

**Acronimo**. Contiene il formato breve o l'acronimo effettivo. Un esempio è *DNN.*

**Espansione**. Contiene l'espansione dell'acronimo. Un esempio è *Deep Neural Network.*

**Descrizione**. Breve descrizione dell'acronimo che fornisce agli utenti altre informazioni sull'acronimo e sulla relativa espansione. Ad esempio, *una rete deep-neurale* è una rete di tipo neurale con un determinato livello di complessità, una rete di reti di tipo neurale con più di due livelli.

**Origine**. URL della pagina o del sito Web in cui si desidera che gli utenti vadano per ulteriori informazioni sull'acronimo.

**Stato**. Questo campo può assumere due valori:

- **Bozza.** Aggiunge l'acronimo allo stato Bozza.
- **Published**. Aggiunge l'acronimo allo stato Published e lo rende disponibile in Microsoft Search.

### <a name="system-curated-acronyms"></a>Acronimi curati dal sistema

L'aggiunta di tutti gli acronimi utilizzati all'interno di un'organizzazione a Answers potrebbe essere una sfida per gli amministratori. Questa funzionalità può trovare acronimi di cui gli amministratori della ricerca non sono nemmeno a conoscenza. A tale scopo, Microsoft Search individua e cura anche gli acronimi da queste origini:

- Messaggi di posta elettronica degli utenti
- Documenti in [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/)
- Documenti pubblici all'interno dell'organizzazione a cui gli utenti hanno accesso in SharePoint, OneDrive o OneNote

Microsoft Search garantisce che solo gli utenti con accesso e autorizzazioni per un documento possano visualizzare gli acronimi individuati da tale documento. Quando viene trovato un acronimo nella cassetta postale di un utente, solo tale utente può vedere tale acronimo.

> [!NOTE]
> Non è necessaria alcuna configurazione per gli acronimi curati dall'amministratore.

## <a name="frequently-asked-questions"></a>Domande frequenti

**D: In che modo vengono classificati i dati curati dall'amministratore e curati dal sistema?**

**A:** La classificazione dei risultati può variare da persona a persona in quanto i risultati sono personalizzati per ogni utente. Nessuna di queste categorie avrà sempre la precedenza sull'altra.

**D: Quanto tempo è necessario perché gli acronimi curati dall'amministratore siano visibili in Microsoft Search dopo la pubblicazione?**

**A:**  Sono necessari fino a tre giorni prima che gli acronimi aggiunti allo stato Published diventino disponibili in Microsoft Search.

**D: In che modo gli utenti attivano le risposte agli acronimi?**

**A:** Per ottenere risposte con acronimi, gli utenti devono immettere modelli di query specifici in una casella di ricerca di [Bing,](https://bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)o [Office 365.](https://Office.com) 

**D: Quanto tempo è necessario per visualizzare gli acronimi curati dal sistema dopo aver ricevuto o inviato un nuovo messaggio di posta elettronica o documento?**

**A:** Gli acronimi trovati in un nuovo messaggio di posta elettronica o documento possono richiedere fino a sette giorni per essere visualizzati nei risultati di Microsoft Search.

**D: I documenti devono essere in un formato specifico per poter essere selezionati dal data mining?**

**A:** No. Sono supportati tutti i tipi di file, ad eccezione dei file immagine, cartelle e zip.

**D: Microsoft scoprirà gli acronimi dai documenti in tutte le lingue?**

**A:** Microsoft supporta solo il mining da documenti in inglese. Il supporto per altre lingue verrà aggiunto in più fasi.

**D: Cosa succede se l'organizzazione non vuole mostrare acronimi curati dal sistema? È possibile interrompere la visualizzazione di questo tipo di acronimo nei risultati della ricerca?**

**A:** Per disattivare la visualizzazione degli acronimi curati dal sistema nei risultati della ricerca, creare un ticket di supporto clienti seguendo le istruzioni in Contattare il supporto per [i prodotti aziendali.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
Dopo aver creato un ticket di supporto, sono necessari fino a 48 ore prima che gli acronimi curati dal sistema non appaiano più nei risultati della ricerca.
