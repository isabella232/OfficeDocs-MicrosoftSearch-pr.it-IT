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
ms.openlocfilehash: 14b46e8f689a4df1e41d1852f49157faf67f7fdece2fa09fb740b5652d719a34
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532921"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gestire le risposte degli acronimi in Microsoft Search

Gli utenti spesso si trovano in acronimi e abbreviazioni sconosciuti utilizzati dall'organizzazione o dal team. I termini specifici per le organizzazioni o i team potrebbero essere nuovi per le persone che si spostano da un team all'altro, lavorano con team partner interni o sono nuovi all'organizzazione.

Le organizzazioni non hanno sempre un singolo riferimento per la terminologia standard. La mancanza di un singolo riferimento rende difficile trovare le definizioni per questi acronimi. Microsoft Search risolve il problema con gli acronimi.

## <a name="what-users-experience"></a>Esperienza degli utenti

Microsoft Search utenti possono ottenere le definizioni con gli acronimi in [Bing,](https://Bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)e [Office 365](https://Office.com). Nella casella **Di ricerca** gli utenti immettono query come negli esempi seguenti:

- *Cos'è* DNN
- *Definire* DNN
- Definizione *DNN*
- *Espandi* DNN
- Espansione *DNN*
- *Significato di* DNN
- DNN *significa*
- DNN *è l'acronimo di*

Il risultato include tutti i significati di DNN presenti all'interno dell'organizzazione dell'utente.

> [!NOTE]
> Gli utenti devono immettere una query che includa le parole chiave specificate dell'acronimo per *attivare* le risposte corrispondenti. Per le query con acronimi non viene fatto distinzione tra maiuscole e minuscole.

## <a name="set-up-acronyms-answers"></a>Configurare le risposte acronimi

Nella [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com), passare [**ad Acronimi**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)e quindi selezionare **Aggiungi acronimo**.

Microsoft Search query su due origini dati per fornire agli acronimi le risposte alle ricerche degli utenti:

1. **Admin-curated**. Fornito dagli amministratori IT [nell'interfaccia di amministrazione.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)
2. **System-curated**. Individuato da Microsoft Search dalla posta elettronica e dai documenti degli utenti, nonché dai dati disponibili pubblicamente all'interno dell'organizzazione.

### <a name="set-up-admin-curated-acronyms"></a>Configurare acronimi curati dall'amministratore

Gli amministratori della ricerca possono aggiungere acronimi nella scheda [Acronimi](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) [nell'Microsoft Search di amministrazione.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) È possibile aggiungere acronimi da qualsiasi sito o archivio interno all'interfaccia di amministrazione. Questi acronimi possono essere aggiunti allo **stato Published** o **Draft:**

**Stato pubblicato**. Gli acronimi sono disponibili per gli utenti dell'organizzazione tramite Microsoft Search.

> [!NOTE]
> Potrebbero essere necessario fino a tre giorni prima che gli acronimi aggiunti allo stato Published diventino disponibili in Microsoft Search.

**Stato bozza**. Se vuoi rivedere un acronimo prima di renderlo disponibile in Microsoft Search, puoi aggiungere l'acronimo in stato Bozza. Gli acronimi nello stato Bozza non verranno visualizzati nei risultati della ricerca. Sarà necessario spostare l'acronimo allo stato Published per renderlo visualizzato nei risultati della ricerca.

**Stato escluso**. Se vuoi impedire la visualizzazione di un acronimo Microsoft Search, usa **Exclude an acronym** per aggiungerlo. Per impedire l'esclusione di un acronimo, è necessario eliminare l'acronimo escluso e aggiungerlo o verificare che sia presente nell'elenco pubblicato.

È possibile aggiungere gli acronimi singolarmente o importarli in blocco in un file CSV. Upload un file CSV con i campi mostrati nella tabella seguente:

| Acronimo (Obbligatorio) | Sta per (Obbligatorio) | URL | Descrizione  | Stato (obbligatorio) | Last Modified | Last Modified By | Id |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *Abbreviazione con ortografia* | *Source* |  | *Published, Draft o Excluded* |  |  |  |

### <a name="csv-fields"></a>Campi CSV

**Acronimo**. Contiene la forma breve o l'acronimo effettivo. Un esempio è *DNN*.

**L'acronimo di**. Contiene la definizione dell'acronimo. Un esempio è *Deep Neural Network.*

**Description**. Breve descrizione dell'acronimo che fornisce agli utenti altre informazioni sull'acronimo e sulla relativa definizione. Ad esempio, una rete neurale profonda è una rete neurale con un determinato livello di complessità, una rete *neurale con più di due livelli.*

**Origine**. URL della pagina o del sito Web in cui si desidera che gli utenti vadano per ulteriori informazioni sull'acronimo.

**State**. Questo campo può assumere due valori:

- **Draft**. Aggiunge l'acronimo allo stato Draft.
- **Published**. Aggiunge l'acronimo allo stato Published e lo rende disponibile in Microsoft Search.
- **Escluso**. Aggiunge l'acronimo allo stato Excluded e ne impedisce la visualizzazione Microsoft Search.

### <a name="system-curated-acronyms"></a>Acronimi curati dal sistema

Potrebbe essere una sfida per gli amministratori aggiungere a Answers tutti gli acronimi utilizzati all'interno di un'organizzazione. Questa funzionalità può trovare acronimi di cui gli amministratori della ricerca non sono nemmeno a conoscenza. A tale scopo, Microsoft Search individua e cura gli acronimi da queste origini:

- Messaggi di posta elettronica degli utenti
- Documenti in [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/)
- Documenti pubblici all'interno dell'organizzazione a cui gli utenti hanno accesso in SharePoint, OneDrive o OneNote

Microsoft Search che solo gli utenti con accesso e autorizzazioni a un documento possano visualizzare gli acronimi individuati da esso. Quando viene trovato un acronimo nella cassetta postale di un utente, solo tale utente può vedere tale acronimo.

> [!NOTE]
> Non è necessaria alcuna configurazione per gli acronimi curati dal sistema.

## <a name="frequently-asked-questions"></a>Domande frequenti

**D: In che modo vengono classificati i dati curati dall'amministratore e curati dal sistema?**

**A:** La classificazione dei risultati può variare da persona a persona in quanto i risultati sono personalizzati per ogni utente. Nessuna di queste categorie avrà sempre la precedenza sull'altra.

**D: Quanto tempo è necessario per la visibilità degli acronimi curati dall'amministratore Microsoft Search dopo la pubblicazione?**

**A:**  È necessario un giorno prima che gli acronimi aggiunti allo stato Published diventino disponibili in Microsoft Search.

**D: In che modo gli utenti attivano le risposte agli acronimi?**

**A**: Per ottenere risposte con acronimi, gli utenti devono immettere modelli di query specifici in una casella [Bing,](https://bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration)o [Office 365](https://Office.com) **ricerca.**

**D: Quanto tempo è necessario per visualizzare gli acronimi curati dal sistema dopo aver ricevuto o inviato un nuovo messaggio di posta elettronica o un nuovo documento?**

**A:** Gli acronimi trovati in un nuovo messaggio di posta elettronica o in un nuovo documento possono essere visualizzati fino a sette giorni Microsoft Search risultati.

**D: Cosa succede quando un acronimo viene escluso e pubblicato?**

**A:** L'acronimo escluso ha la priorità e impedisce la visualizzazione dell'acronimo pubblicato nei risultati della ricerca. Non elimina o rimuove l'acronimo pubblicato.

**D: Quanto tempo è necessario per escludere un acronimo dai Microsoft Search risultati?**

**A**: Un acronimo escluso non viene più visualizzato nei risultati della ricerca fino a un giorno.

**D: Per gli acronimi curati dal sistema, i documenti devono essere in un formato specifico?**

**A:** No. Sono supportati tutti i tipi di file, ad eccezione dei file immagine, cartella e zip.

**D: Microsoft scoprirà gli acronimi dei documenti in tutte le lingue?**

**A**: Microsoft supporta solo gli acronimi curati dal sistema da documenti in inglese, spagnolo, francese, italiano, tedesco e portoghese. Il supporto per altre lingue verrà aggiunto in più fasi.

**D: Cosa succede se l'organizzazione non vuole mostrare acronimi curati dal sistema? È possibile interrompere la visualizzazione di questo tipo di acronimo nei risultati della ricerca?**

**A**: Per disattivare la visualizzazione degli acronimi curati dal sistema nei risultati della ricerca, creare un ticket di supporto clienti seguendo le istruzioni disponibili in Contattare il supporto per [i prodotti aziendali.](/microsoft-365/admin/contact-support-for-business-products)
Dopo aver creato un ticket di supporto, sono necessari fino a 48 ore perché gli acronimi curati dal sistema non appaiano più nei risultati della ricerca.
