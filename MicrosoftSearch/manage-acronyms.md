---
title: Gestire le risposte agli acronimi in Microsoft Search
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
description: Creare e aggiornare gli acronimi risposte in Microsoft Search
ms.openlocfilehash: ff79e3d741e10d401873c29d86739e61c9f53329
ms.sourcegitcommit: e6ceb07cae208648dadd5452a077414ab5a4513f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2020
ms.locfileid: "49728007"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gestire le risposte degli acronimi in Microsoft Search

Gli utenti spesso incorrono in acronimi e abbreviazioni non familiari utilizzati dall'organizzazione o dal team. Le condizioni specifiche per le organizzazioni o i team possono essere nuove per le persone che si spostano da un team all'altro, che lavorano con team partner interni o che sono nuove all'interno dell'organizzazione.

Le organizzazioni non dispongono sempre di un singolo riferimento per la terminologia standard. La mancanza di un singolo riferimento rende difficile trovare definizioni o espansioni per questi acronimi. Microsoft Search risolve il problema con gli acronimi.

## <a name="what-users-experience"></a>Esperienza degli utenti

Gli utenti di Microsoft Search possono ottenere definizioni con acronimi in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)e [Office 365](https://Office.com). Nella casella di **ricerca** gli utenti immettono query come questi esempi:

- *Che cos'è* DNN
- *Definire* DNN
- *Definizione* di DNN
- *Espandi* DNN
- *Espansione* di DNN
- *Significato di* DNN
- DNN *significa*

Il risultato include tutti i significati di DNN che sono presenti all'interno dell'organizzazione dell'utente.

> [!NOTE]
> Gli utenti devono immettere una query che includa le *parole chiave* specificate dall'acronimo per attivare le risposte corrispondenti. Le query di acronimo non sono case sensitive.

## <a name="set-up-acronyms-answers"></a>Configurare le risposte alle sigle

Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com), passare a [**acronimi**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), quindi selezionare **Aggiungi acronimo**.

Microsoft Search esegue una query su due origini dati per fornire agli acronimi risposte alle ricerche degli utenti:

1. **A cura di amministratore**. Fornite dagli amministratori IT nell'interfaccia di [Amministrazione](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).
2. **System-curato**. Scoperta da Microsoft Search dalla posta elettronica e dai documenti degli utenti e dati disponibili pubblicamente all'interno dell'organizzazione.

### <a name="set-up-admin-curated-acronyms"></a>Configurare gli acronimi a cura di amministratore

Gli amministratori della ricerca possono aggiungere gli acronimi nella [scheda acronimi](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) nell'interfaccia di  [amministrazione di Microsoft Search](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch). È possibile aggiungere acronimi da qualsiasi sito o repository interno all'interfaccia di amministrazione. È possibile aggiungere tali acronimi allo stato **Published** o **Draft** :

**Stato pubblicato**. Gli acronimi sono disponibili per gli utenti dell'organizzazione tramite Microsoft Search.

> [!NOTE]
> Potrebbe essere necessario fino a tre giorni prima che gli acronimi siano stati aggiunti allo stato pubblicato per diventare disponibili in Microsoft Search.

**Stato bozza**. Se si desidera esaminare un acronimo prima di renderlo disponibile in Microsoft Search, è possibile aggiungere l'acronimo in uno stato bozza. Gli acronimi nello stato bozza non verranno visualizzati nei risultati della ricerca. Sarà necessario spostare l'acronimo allo stato pubblicato in modo che venga visualizzato nei risultati della ricerca.

È possibile aggiungere gli acronimi singolarmente o importarli in blocco in un file CSV. Caricare un file CSV con i campi illustrati nella tabella seguente:

| Acronimo (obbligatorio) | Espansione (obbligatoria) | Descrizione  | Origine | Stato (obbligatorio) |
| --------- | --------- | ---------- | --------- |--------- |
| *XXX* | *Abbreviazione disscritta* |  | *URL* | *Pubblicazione o bozza* |

### <a name="csv-fields"></a>Campi CSV

**Acronimo**. Contiene la forma breve o l'acronimo effettivo. Un esempio è *DNN*.

**Espansione**. Contiene l'espansione dell'acronimo. Un esempio è la *rete neurale profonda*.

**Descrizione**. Breve descrizione dell'acronimo che fornisce agli utenti altre informazioni sull'acronimo e sulla relativa espansione. Ad esempio, *una rete neurale profonda è una rete neurale con un certo livello di complessità, una rete neurale con più di due layer*.

**Origine**. URL della pagina o del sito Web in cui si desidera consentire agli utenti di accedere per ulteriori informazioni sull'acronimo.

**Stato**. Questo campo può assumere due valori:

- **Bozza**. Aggiunge l'acronimo allo stato bozza.
- **Pubblicati**. Aggiunge l'acronimo allo stato pubblicato e lo rende disponibile in Microsoft Search.

### <a name="system-curated-acronyms"></a>Acronimi a cura di sistema

Potrebbe essere una sfida per gli amministratori aggiungere tutti gli acronimi utilizzati all'interno di un'organizzazione per rispondere alle risposte. Questa funzionalità consente di trovare gli acronimi di cui gli amministratori della ricerca non sono ancora a conoscenza. Per eseguire tale operazione, Microsoft Search consente inoltre di individuare e curare gli acronimi da queste origini:

- Messaggi di posta elettronica degli utenti
- Documenti in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/)
- Documenti pubblici all'interno dell'organizzazione a cui gli utenti hanno accesso in SharePoint, OneDrive o OneNote

Microsoft Search garantisce che solo gli utenti con accesso e le autorizzazioni per un documento possano visualizzare gli acronimi da esso individuati. Quando si trova un acronimo nella cassetta postale di un utente, solo quell'utente può vedere quell'acronimo.

> [!NOTE]
> Non è necessaria alcuna configurazione per gli acronimi a cura di amministratore.

## <a name="frequently-asked-questions"></a>Domande frequenti

**D: in che modo vengono classificati i dati curati dall'amministratore e dal sistema?**

**A:** La classificazione dei risultati può variare da persona a persona poiché i risultati sono personalizzati per ogni utente. Nessuna di queste categorie avrà sempre la precedenza sull'altra.

**D: quanto tempo è necessario per rendere visibili gli acronimi curati dall'amministratore in Microsoft Search dopo che sono stati pubblicati?**

**A:**  Sono necessari fino a tre giorni per gli acronimi aggiunti allo stato pubblicato per renderli disponibili in Microsoft Search.

**D: in che modo gli utenti attivano le risposte alle sigle?**

**A: per** ottenere risposte agli acronimi, gli utenti devono immettere modelli di query specifici in una casella di **ricerca** [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)o [Office 365](https://Office.com) .

**D: quanto tempo occorre per visualizzare gli acronimi curati dal sistema dopo aver ricevuto o inviato un nuovo messaggio di posta elettronica o documento?**

**A:** Gli acronimi trovati in un nuovo messaggio di posta elettronica o documento richiedono fino a sette giorni per essere visualizzati nei risultati della ricerca di Microsoft.

**D: i documenti devono essere in un formato specifico per l'estrazione delle informazioni?**

**A:** No. Sono supportati tutti i tipi di file, ad eccezione dell'immagine, delle cartelle e dei file zip.

**D: Microsoft scoprirà gli acronimi dei documenti in tutte le lingue?**

**A**: Microsoft supporta solo le attività minerarie dai documenti in inglese. Il supporto per altre lingue verrà aggiunto nelle fasi.

**D: che cosa accade se l'organizzazione non desidera visualizzare gli acronimi a cura di sistema? È possibile interrompere la visualizzazione di questo tipo di acronimo nei risultati della ricerca?**

**A: per** disattivare la visualizzazione degli acronimi curati dal sistema nei risultati della ricerca, creare un ticket di supporto tecnico seguendo le istruzioni riportate in [Contact Support for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).
Dopo aver creato un ticket di supporto, sono necessarie fino a 48 ore affinché gli acronimi a cura di sistema smettano di essere visualizzati nei risultati della ricerca.
