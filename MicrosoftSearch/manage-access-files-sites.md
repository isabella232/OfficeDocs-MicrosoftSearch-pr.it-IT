---
title: Gestire l'accesso a file e siti
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Panoramica del modo in cui gli amministratori possono garantire che l'accesso a siti e file sia adeguatamente limitato all'interno dell'organizzazione.
ms.openlocfilehash: c85cce6208743b884cce86cc11c46aab3e01254d
ms.sourcegitcommit: 70c48e470262099feb79553e36593521cc5e7abc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2021
ms.locfileid: "58835021"
---
# <a name="manage-access-to-files-and-sites"></a>Gestire l'accesso a file e siti

Non tutti i file o i siti devono essere disponibili per tutti gli utenti dell'organizzazione. Gli amministratori e gli utenti possono gestire l'accesso a informazioni riservate o riservate usando soluzioni che consentono di risolvere al meglio i problemi specifici. Se i controlli di accesso adeguati non vengono applicati in modo coerente, può risultare in qualcosa che viene detto "oversharing". Semplificando la ricerca di informazioni condivise all'interno dell'organizzazione, è possibile accedere inavvertitamente a file e siti con restrizioni non Microsoft Search.

Gli amministratori della ricerca non possono risolvere questi problemi di sovrascrittura. I file e i siti senza accesso limitato verranno visualizzati nei risultati di ricerca interni e in altre modalità di individuazione. Tuttavia, quando sono presenti controlli per evitare il sovrastono, tutte le vie, inclusa la ricerca, verranno chiuse.

## <a name="solutions-to-prevent-oversharing"></a>Soluzioni per evitare il oversharing

Usa gli strumenti, i criteri e le tecniche seguenti per limitare o offuscare l'accesso alle informazioni per evitare la sovrasfazione. L'implementazione di queste soluzioni richiederà probabilmente l'accesso di amministratore globale, di conformità o di sicurezza. È inoltre consigliabile una campagna interna per informare gli utenti su come proteggere, etichettare e consentire correttamente i propri siti e file.

### <a name="public-sites-or-sites-with-public-owners"></a>Siti pubblici o siti con proprietari pubblici

Un modo per condividere i file con tutti gli utenti dell'organizzazione è tramite siti pubblici o siti con proprietari pubblici. Le etichette di riservatezza possono impedire agli utenti di creare gruppi o siti pubblici. Questa operazione viene eseguita configurando tutte le etichette per creare gruppi privati e richiedendo un'etichetta per i gruppi. Per informazioni dettagliate, vedere [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). Sarà necessario definire un processo separato per consentire agli utenti di richiedere o creare gruppi pubblici.

Un'altra opzione è definire chi può creare Microsoft 365 gruppi nell'organizzazione. Per ulteriori informazioni, vedere [Create a group for users who need to create Microsoft 365 groups](/microsoft-365/solutions/manage-creation-of-groups#step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups). Un amministratore globale dovrà configurare un processo per consentire agli utenti di inviare richieste di creazione di gruppi. Consigliamo inoltre di informare gli utenti di questa modifica.

Se non è possibile limitare la possibilità di creare gruppi per l'organizzazione, è possibile monitorare le attività, inclusa la creazione dei gruppi, tramite il controllo. Per informazioni dettagliate sul controllo di base e avanzato, vedere [Auditing solutions in Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview).

### <a name="shared-files"></a>File condivisi

Per limitare l'accesso a tutti i file classificati come sensibili alle aziende, è possibile definire e applicare classificazioni dei dati per l'organizzazione. I dati di esempio dovranno essere raccolti per formare nuovi classificatori. Per informazioni dettagliate sui prerequisiti e sulle autorizzazioni, vedere [Learn about data classification.](/microsoft-365/compliance/data-classification-overview)

Per limitare l'accesso ai file ai membri di un gruppo specifico, come i dirigenti, è possibile creare etichette personalizzate con ambito a un gruppo di sicurezza. Quindi, quando un membro del gruppo di sicurezza applica l'etichetta, limita automaticamente l'accesso al gruppo. Per ulteriori informazioni sulle etichette personalizzate, vedere [Create and configure sensitivity labels and their policies](/microsoft-365/compliance/create-sensitivity-labels) e Restrict access to content by using [sensitivity labels to apply encryption.](/microsoft-365/compliance/encryption-sensitivity-labels)

Per garantire che i documenti e i messaggi di posta elettronica siano etichettati correttamente, gli amministratori possono anche impostare un criterio di etichetta predefinito e richiedere agli utenti di etichettarli. Per altre informazioni, vedere [Richiedere agli utenti di applicare un'etichetta alla posta elettronica e ai documenti](/microsoft-365/compliance/sensitivity-labels-office-apps#require-users-to-apply-a-label-to-their-email-and-documents).

È inoltre possibile ridurre al minimo il sovrascrittura dei file impedendo la visualizzazione dei file recenti durante la ricerca. Questa operazione può essere eseguita a livello di gruppo o per tutti gli utenti dell'organizzazione. Per impedire la visualizzazione dei file recenti per un gruppo, vedere [Personalizzazione](/graph/insights-customize-item-insights-privacy)della privacy degli elementi in Microsoft Graph . Un membro del gruppo sarà in grado di visualizzare i propri file recenti, ma altri riceveranno un messaggio che indica che non vengono trovati risultati. Per disattivare i file recenti per tutti gli utenti dell'organizzazione, è necessario disattivare Delve. Per informazioni dettagliate, vedere [Control access to Delve](/sharepoint/delve-for-office-365-admins#control-access-to-delve).

> [!Note]
> Gli utenti potranno comunque trovare i file condivisi con loro nei Microsoft Search risultati. La personalizzazione delle informazioni dettagliate sull'elemento Delve solo la visualizzazione dei file nell'elenco dei file recenti di un utente.

### <a name="sites-and-files-between-groups"></a>Siti e file tra gruppi

Per limitare la condivisione di file e siti tra gruppi, ad esempio un team finanziario che gestisce progetti riservati con un team di marketing, è possibile definire e implementare criteri di barriera delle informazioni. Queste barriere impediscono anche altri aspetti della comunicazione e della collaborazione in Microsoft Teams, SharePoint e OneDrive. Per informazioni dettagliate, vedere [Learn about information barriers in Microsoft 365.](/microsoft-365/compliance/information-barriers)

## <a name="get-access-insights"></a>Ottenere informazioni dettagliate sull'accesso

La governance dell'accesso fornisce informazioni dettagliate sui siti con i documenti più riservati e i siti sovracondivisi nell'organizzazione. Per una panoramica, vedere Novità di Sicurezza e conformità [in SharePoint e OneDrive](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/what-s-new-in-security-and-compliance-in-sharepoint-and-onedrive/ba-p/1696705). Dovrai nominare [l'organizzazione per](https://forms.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) questa anteprima.
