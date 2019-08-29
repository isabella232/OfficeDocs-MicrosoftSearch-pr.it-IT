---
title: Configurare Microsoft Search
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 08/06/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare Microsoft Search per la prima volta.
ms.openlocfilehash: 7c80701e83fea7b9b93e4e01f98fd1eeedbfa749
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639502"
---
# <a name="set-up-microsoft-search"></a>Configurare Microsoft Search

Microsoft Search offre un'interfaccia semplice da usare per consentire agli utenti di trovare informazioni, ad esempio file e documenti, siti interni e strumenti aziendali, persone e gruppi, località e indicazioni stradali, conversazioni e risposte, con un accesso sicuro a tutte le origini dati, inclusi i messaggi di posta elettronica, i file, i file di SharePoint, i contenuti di OneDrive e altre risorse condivise, ad esempio Internet nell'organizzazione dell'utente.

Per altre informazioni sulle funzionalità di Microsoft Search, vedere [Panoramica di Microsoft Search](overview-microsoft-search.md).

## <a name="get-started"></a>Introduzione

Microsoft Search viene attivato per impostazione predefinita in Microsoft 365 per tutte le app Microsoft che lo supportano. Basta eseguire l'accesso con un account aziendale o dell'istituto di istruzione e usare un browser con Bing impostato come provider di ricerca predefinito.

È possibile gestire Microsoft Search dall'interfaccia di amministrazione di Microsoft 365.

1. Nell'interfaccia di amministrazione di Microsoft 365, andare a **Impostazioni** > **Microsoft**.

**Nota:** se NON viene visualizzato Microsoft Search in **Impostazioni**, attivare l'opzione **Prova l'anteprima** nell'angolo in alto a destra dell'interfaccia di amministrazione.

Gli amministratori devono considerare alcuni aspetti che possono rendere l'esperienza di Microsoft Search più efficiente e intuitiva nell'organizzazione.

## <a name="step-1-check-access-level-of-your-users"></a>Passaggio 1: Verificare il livello di accesso degli utenti

Microsoft Search rispetta le impostazioni di sicurezza dell'origine contenuto. Gli elementi visualizzati nei risultati della ricerca dipendono dalle autorizzazioni e dai livelli di accesso degli utenti. Esaminare il livello di accesso degli utenti dell'organizzazione per assicurarsi che gli utenti trovino solo i contenuti cui sono autorizzati ad accedere.

| Servizio         | Descrizione                                                                                                                                                                                                                                         |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Gruppi          | [Aggiungere o rimuovere membri dai gruppi](https://docs.microsoft.com/office365/admin/create-groups/add-or-remove-members-from-groups)                                                                                                                     |
| Persone          | È possibile nascondere alcuni utenti dalle ricerche nell'elenco di indirizzi impostando il parametro `HiddenFromAddressListEnabled` su `true` con il cmdlet [Set-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-user). |
| Microsoft Teams | [Gestione degli accessi utente per Microsoft Teams](https://docs.microsoft.com/microsoftteams/user-access)                                                                                                                                                      |
| OneDrive        | [Gestire la condivisione](https://docs.microsoft.com/OneDrive/manage-sharing)                                                                                                                                                                                |
| SharePoint      | 
  [Pianificazione delle autorizzazioni](https://docs.microsoft.com/it-IT/sharepoint/plan-your-permissions-strategy)<br> 
  [Creare livelli di autorizzazione](https://docs.microsoft.com/it-IT/sharepoint/how-to-create-and-edit-permission-levels)                          |
| OneNote         | Non è possibile eseguire ricerche nei file incorporati in OneNote. [Modificare le autorizzazioni per un blocco appunti in OneDrive](https://support.office.com/article/B9600CCF-045A-40E6-9913-4A7EB02869A5)                                                                    |
| Yammer          | [Impostazioni di sicurezza di Yammer](https://docs.microsoft.com/Yammer/manage-security-and-compliance/yammer-security-settings)                                                                                                                               |

## <a name="step-2-assign-search-admin-and-search-editor"></a>Passaggio 2: Assegnare l'amministratore della ricerca e l'editor della ricerca

In Microsoft Search è possibile gestire i contenuti e le impostazioni di ricerca dell'organizzazione attribuendo questi ruoli agli utenti:

1. **Amministratore della ricerca:** questo ruolo può creare e gestire i contenuti dei risultati della ricerca e definire le impostazioni query per migliorare i risultati all'interno dell'organizzazione. L'amministratore della ricerca gestisce la configurazione di Microsoft Search ed è in grado di eseguire tutte le attività di gestione del contenuto che possono essere eseguite dall'editor della ricerca.
2. **Editor della ricerca:** crea, gestisce ed elimina i contenuti per Microsoft Search nell'interfaccia di amministrazione di Microsoft 365. Questo ruolo può creare e gestire contenuti editoriali, ad esempio domande frequenti, luoghi e località importanti, siti e app cercati e usati di frequente.

Attualmente, i ruoli di amministratore della ricerca e di editor della ricerca devono essere assegnati da un amministratore globale. Per altre informazioni, vedere [Assegnare ruoli di amministrazione](https://docs.microsoft.com/it-IT/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).

Gli amministratori della ricerca influiscono direttamente sull'esperienza di ricerca per gli utenti finali, ad esempio scegliendo i tipi di risultati che gli utenti possono visualizzare. Può risultare difficile scegliere e creare contenuti rilevanti nei numerosi argomenti diversi che gli utenti cercano in un'organizzazione. È consigliabile sfruttare le competenze e le conoscenze degli SME (Subject Matter Expert) e di altri utenti aggiungendoli come editor della ricerca.

## <a name="step-3-make-content-easy-to-find"></a>Passaggio 3: Facilitare la ricerca del contenuto

Microsoft Search offre agli amministratori strumenti utili per creare un'esperienza di ricerca solida per gli utenti. In Microsoft Search gli amministratori possono creare tre diversi contenuti di ricerca per garantire una migliore esperienza di ricerca e ottimizzare la reperibilità dei contenuti:

- **Segnalibri:** i segnalibri sono simili ai risultati promossi in SharePoint e consentono di promuovere i migliori risultati possibili per le query degli utenti nella parte superiore dei risultati della ricerca. Consentono inoltre agli utenti di cercare facilmente siti interni importanti.
- **Domande e risposte:** sono simili alle domande frequenti e in genere vengono visualizzate sotto forma di domande e risposte. Sono lo strumento ideale per rispondere nel miglior modo possibile alle domande correlate al lavoro degli utenti.
- **Località:** le località corrispondono agli indirizzi che consentono agli utenti di individuare edifici, uffici e campus dell'organizzazione.

Più segnalibri, domande e risposte e località sono disponibili, maggiori saranno il valore e i vantaggi per gli utenti. Un numero eccessivo di questi elementi può causare un notevole sovraccarico di gestione in quanto questi contenuti devono essere revisionati e aggiornati periodicamente per garantire che i risultati siano pertinenti e aggiornati.

Ecco alcuni esempi di contenuti che è consigliabile aggiungere ai segnalibri per gli utenti:

- Informazioni relative all'organizzazione, a prodotti o a servizi.
- Contenuti informativi disponibili per tutti gli utenti, ad esempio informazioni sulla società, guida per le app di Windows e Office e così via.
- Contenuti che gli utenti dell'organizzazione generalmente cercano durante le attività quotidiane. Le ricerche correlate al lavoro includono benefit dei dipendenti, report su orari e spese, invio di ordini di acquisto e assistenza dei servizi IT.

Per la creazione e la gestione dei contenuti della ricerca, vedere [Facilitare la ricerca del contenuto](make-content-easy-to-find.md).

## <a name="step-4-training-and-communication"></a>Passaggio 4: Formazione e comunicazione

Definire le risorse in modalità self-service a cui i dipendenti possono accedere in modo facile e autonomo. Questo consentirà di ridurre il carico complessivo sull'amministratore e sul team incaricato delle comunicazioni e supporterà la formazione autonoma dei dipendenti. Fornire agli utenti comunicazioni, domande frequenti, video e corsi di formazione o webinar registrati. Ecco alcuni collegamenti utili per iniziare:

- [Trovare le informazioni necessarie con Microsoft Search in Office](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Area risorse di Office 365](https://support.office.com/office-training-center)
- 
  [Microsoft Search Center](https://support.office.com/it-IT/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)