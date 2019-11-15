---
title: Gestire le risposte agli acronimi in Microsoft Search
ms.author: v-pamcna
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Creare e aggiornare gli acronimi risposte in Microsoft Search
ms.openlocfilehash: 4f47d5b743709657459ccbc6b03897c29a51e109
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626820"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gestire le risposte degli acronimi in Microsoft Search

I dipendenti spesso incorrono in acronimi e abbreviazioni non familiari utilizzati dall'organizzazione o dal team. Le condizioni specifiche per le organizzazioni o i team possono essere nuove per le persone che si spostano da un team all'altro, per coloro che lavorano con team partner interni o per i nuovi dipendenti.

Le organizzazioni non dispongono sempre di un singolo riferimento per la terminologia standard. La mancanza di un singolo riferimento rende difficile trovare definizioni o espansioni per questi acronimi. Microsoft Search risolve il problema con gli acronimi.

## <a name="what-users-experience"></a>Esperienza degli utenti
Gli utenti di Microsoft Search possono ottenere definizioni con acronimi in [Bing](https://Bing.com), [Microsoft Office 365](https://Office.com)e [Microsoft SharePoint Online](https://products.office.com/sharepoint/collaboration). Nelle caselle di **ricerca** nelle barre di intestazione gli utenti immettono query come questi esempi:

- *Che cos'è* DNN
- *Definire* DNN
- *Definizione* di DNN
- *Espandi* DNN
- *Espansione* di DNN
- *Significato di* DNN
- DNN *significa*

I risultati suggeriti includono tutti i significati di DNN che sono presenti all'interno dell'organizzazione dell'utente.

> [!NOTE]
> Gli utenti devono immettere una query che includa le *parole chiave* specificate dall'acronimo per attivare le risposte corrispondenti.  

## <a name="set-up-acronyms-answers"></a>Configurare le risposte alle sigle
Nell'interfaccia di [Amministrazione](https://admin.microsoft.com)di Microsoft 365, passare a **Impostazioni** > **acronimi**di**Microsoft Search** >, quindi selezionare **Aggiungi acronimi**. 

Microsoft Search esegue una query su due origini dati per fornire agli acronimi risposte alle ricerche degli utenti:

1.  **Acronimi editoriali**. Fornite dagli amministratori IT nell'interfaccia di [Amministrazione](https://admin.microsoft.com).
2.  **Acronimi estratti**. Estratto da Microsoft Search dalla posta elettronica personale e dai documenti personali dell'utente e dai dati disponibili pubblicamente all'interno dell'organizzazione.

### <a name="set-up-editorial-acronyms"></a>Configurare gli acronimi editoriali
Gli amministratori IT possono configurare gli acronimi editoriali nella [scheda acronimi](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) nell'interfaccia di [amministrazione di Microsoft 365]( https://admin.microsoft.com). È possibile aggiungere acronimi da qualsiasi sito o repository interno all'interfaccia di amministrazione. Gli acronimi editoriali possono essere aggiunti allo stato **Published** o **Draft** :

**Stato pubblicato**. Gli acronimi sono disponibili per i dipendenti dell'organizzazione tramite Microsoft Search.

> [!NOTE]
> Potrebbe essere necessario fino a tre giorni prima che gli acronimi siano stati aggiunti allo stato pubblicato per diventare disponibili in Microsoft Search.

**Stato bozza**. Se gli amministratori desiderano esaminare le risposte degli acronimi prima di renderli disponibili in Microsoft Search, possono aggiungere gli acronimi allo stato bozza. Gli acronimi aggiunti allo stato bozza non sono disponibili in Microsoft Search. Gli amministratori devono aggiungere gli acronimi allo stato pubblicato per renderli disponibili.

Gli amministratori possono aggiungere gli acronimi singolarmente o in blocco per importarli in un file CSV. Caricare un file CSV con i campi illustrati nella tabella seguente:

| Acronimo (obbligatorio) | Espansione (obbligatoria) | Descrizione  | Origine | Stato (obbligatorio) |
| --------- | --------- | ---------- | --------- |--------- |
| *XXX* | *Abbreviazione disscritta* |  | *URL* | *Pubblicazione o bozza* |

### <a name="csv-fields"></a>Campi CSV
**Acronimo**. Contiene la forma breve o l'acronimo effettivo. Un esempio è *DNN*.

**Espansione**. Contiene l'espansione dell'acronimo. Un esempio è la *rete neurale profonda*.

**Descrizione**. Breve descrizione dell'acronimo che fornisce agli utenti informazioni dettagliate su cosa significa l'acronimo e la relativa espansione. Ad esempio, *una rete neurale profonda è una rete neurale con un certo livello di complessità, una rete neurale con più di due layer*.

**Origine**. URL della pagina o del sito Web in cui si desidera consentire agli utenti di accedere per ulteriori informazioni sull'acronimo.

**Stato**. Questo campo può assumere due valori:

- **Bozza**. Aggiunge l'acronimo allo stato bozza.
- **Pubblicati**. Aggiunge l'acronimo allo stato pubblicato e lo rende disponibile in Microsoft Search.

### <a name="mined-acronyms"></a>Acronimi estratti
Potrebbe essere una sfida per gli amministratori aggiungere tutti gli acronimi utilizzati all'interno di un'organizzazione per rispondere alle risposte. Questa funzionalità consente di trovare gli acronimi di cui gli amministratori della ricerca non sono ancora a conoscenza. Per eseguire tale operazione, Microsoft Search estrae anche gli acronimi di queste origini:

- Messaggi di posta elettronica degli utenti.
- Documenti in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/) e [Microsoft OneNote](http://www.onenote.com/).
- Documenti pubblici all'interno dell'organizzazione a cui gli utenti hanno accesso in SharePoint, OneDrive o OneNote.

Microsoft Search garantisce che solo gli utenti con accesso e le autorizzazioni per un documento possano visualizzare gli acronimi estratti da esso. Gli acronimi vengono estratti dalla cartella posta in arrivo di un utente e archiviati nel frammento dell'utente. Solo l'utente può accedere agli acronimi estratti dalla cartella posta in arrivo dell'utente.

> [!NOTE]
> Non è necessaria alcuna configurazione dell'amministratore IT per gli acronimi estratti.

## <a name="frequently-asked-questions"></a>Domande frequenti
**D: in che modo vengono classificati i dati editoriali e estratti?**

**A:** La caratteristica attualmente classifica gli acronimi editoriali sopra gli acronimi estratti.

**D: quanto tempo occorre per rendere visibili gli acronimi editoriali in Microsoft Search dopo che sono stati pubblicati?**

**A:**  Sono necessari fino a tre giorni per gli acronimi aggiunti allo stato pubblicato per renderli disponibili in Microsoft Search. 

**D: in che modo gli utenti attivano le risposte alle sigle?**

**A: per**ottenere risposte agli acronimi, gli utenti devono immettere modelli di query specifici in una casella di **ricerca** [Bing](https://bing.com), [Office 365](https://Office.com)o [SharePoint](https://products.office.com/sharepoint/collaboration) . Di seguito sono riportati alcuni esempi di query che individuano le risposte per il termine *DNN* :

- *Che cos'è* DNN
- *Definire* DNN
- *Definizione* di DNN
- *Espandi* DNN
- *Espansione* di DNN
- *Significato di* DNN
- DNN *significa*

**D: quanto tempo è necessario per visualizzare gli acronimi estratti dopo aver ricevuto o inviato un nuovo messaggio di posta elettronica o documento?**

**A:** Gli acronimi estratti da un nuovo messaggio di posta elettronica o documento richiedono fino a sette giorni per essere visualizzati nei risultati della ricerca di Microsoft.

**D: i documenti devono essere in un formato specifico per l'estrazione delle informazioni?**

**A:** No. Sono supportati tutti i tipi di file, ad eccezione dell'immagine, delle cartelle e dei file zip.

**D: gli acronimi di Microsoft mine verranno da documenti in tutte le lingue?**

**A**: Microsoft supporta solo le attività minerarie dai documenti in inglese. Il supporto per altre lingue verrà aggiunto nelle fasi.

**D: che cosa accade se la mia organizzazione non vuole visualizzare gli acronimi estratti? È possibile interrompere la visualizzazione degli acronimi estratti nei risultati della ricerca?**

**A: per**disattivare la visualizzazione degli acronimi estratti nei risultati della ricerca, creare un ticket di supporto clienti attenendosi alle istruzioni riportate in [Contact Support for Business Products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).
Dopo aver creato un ticket di supporto, sono necessarie fino a 48 ore per evitare che gli acronimi estratti vengano visualizzati nei risultati della ricerca. 

**D: quando vengono visualizzate le risposte agli acronimi in [Office 365](https://Office.com) e [SharePoint Online](https://products.office.com/sharepoint/collaboration)?**

**A**: le risposte alle sigle sono attualmente disponibili solo in Microsoft Search in [Bing](https://bing.com). Verranno distribuiti a Office 365 e SharePoint Online nel 2020.
