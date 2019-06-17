---
title: Configurare **Microsoft Search**
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare Microsoft Search per la prima volta.
ms.openlocfilehash: c95cc0d11d60e3d4d9a509dc691c01858ede7262
ms.sourcegitcommit: 9df9b1a5f83c9fbe62900df183bee239a8ea6d91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2019
ms.locfileid: "34947744"
---
# <a name="set-up-microsoft-search"></a>Configurare Microsoft Search

**Microsoft Search** offre un'interfaccia semplice da usare per consentire agli utenti di trovare informazioni, ad esempio file e documenti, siti interni e strumenti aziendali, persone e gruppi, località e indicazioni stradali, conversazioni e risposte, con un accesso sicuro a tutte le origini dati, inclusi i messaggi di posta elettronica, i file, i file di SharePoint, i contenuti di OneDrive e altre risorse condivise, ad esempio Internet nell'organizzazione dell'utente.

Per altre informazioni sulle funzionalità di **Microsoft Search**, vedere [Panoramica di Microsoft Search](overview-microsoft-search.md).

## <a name="get-started"></a>Introduzione

**Microsoft Search** viene attivato per impostazione predefinita in Microsoft 365 per tutte le app Microsoft che lo supportano. Basta eseguire l'accesso con un account aziendale o dell'istituto di istruzione e usare un browser con Bing impostato come provider di ricerca predefinito.

È possibile amministrare **Microsoft Search** dall'**interfaccia di amministrazione di Microsoft 365**. Per accedere, usare l’account di accesso con le credenziali di amministratore e selezionare il riquadro **Amministratore** nell'elenco delle app di Office 365 (per l’elenco delle app, fare clic sull'icona di **avvio delle app** nell'angolo in alto a sinistra). Nell'**interfaccia di amministrazione di Microsoft 365** selezionare **Microsoft Search** sotto **Impostazioni** nel riquadro di spostamento sinistro. 

**Nota:** se NON viene visualizzato **Microsoft Search** in **Impostazioni** nell'**interfaccia di amministrazione di Microsoft 365**, attivare l'opzione **Prova l'anteprima** nell'angolo in alto a destra dell'interfaccia di amministrazione. 

Gli amministratori devono considerare alcuni aspetti che possono rendere l'esperienza di **Microsoft Search** più efficiente e intuitiva nell'organizzazione.

## <a name="step-1-check-access-level-of-your-users"></a>Passaggio 1: Verificare il livello di accesso degli utenti

**Microsoft Search** rispetta le impostazioni di sicurezza dell'origine contenuto. Gli elementi visualizzati nei risultati della ricerca dipendono dalle autorizzazioni e dai livelli di accesso degli utenti. Esaminare il livello di accesso degli utenti dell'organizzazione per assicurarsi che gli utenti trovino solo i contenuti cui sono autorizzati ad accedere.

Altre informazioni sulla [pianificazione delle autorizzazioni](https://docs.microsoft.com/it-IT/sharepoint/plan-your-permissions-strategy) e sulla [creazione dei livelli di autorizzazione](https://docs.microsoft.com/it-IT/sharepoint/how-to-create-and-edit-permission-levels).

## <a name="step-2-assign-search-admin-and-search-editor"></a>Passaggio 2: Assegnare l'amministratore della ricerca e l'editor della ricerca

Nell'**interfaccia di amministrazione di Microsoft** sono disponibili due nuovi ruoli: l'amministratore della ricerca e l'editor della ricerca.  L'amministratore globale, che dispone di privilegi completi, assegna i ruoli di amministratore agli utenti, incluso il ruolo di amministratore della ricerca. Gli amministratori della ricerca possono delegare i ruoli di amministratore della ricerca o di editor della ricerca ad altri utenti. Per altre informazioni sui diversi ruoli di amministratore, vedere [Informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide).

**Nota:** questi due nuovi ruoli, ovvero l'amministratore della ricerca e l'editor della ricerca, sono disponibili solo nell'**interfaccia di amministrazione di Microsoft 365**, non nel portale di amministrazione legacy. 

Gli amministratori della ricerca influiscono direttamente sull'esperienza di ricerca per gli utenti finali, ad esempio scegliendo i tipi di risultati che gli utenti possono visualizzare. Può risultare difficile scegliere e creare contenuti rilevanti nei numerosi argomenti diversi che gli utenti cercano in un'organizzazione. È consigliabile sfruttare le competenze e le conoscenze degli SME e di altri utenti aggiungendoli come editor. 

In **Microsoft Search** è possibile gestire i contenuti e le impostazioni di ricerca e dell'organizzazione usando due nuovi ruoli:
1. **Amministratore della ricerca:** questo ruolo può creare e gestire i contenuti dei risultati della ricerca e definire le impostazioni query per migliorare i risultati all'interno dell'organizzazione. L'amministratore della ricerca gestisce la configurazione di **Microsoft Search** e designa gli editor della ricerca, che creano i contenuti.
2. **Editor della ricerca:** crea, gestisce ed elimina i contenuti per **Microsoft Search** nell'interfaccia di amministrazione di Microsoft 365. Questo ruolo può creare e gestire contenuti editoriali, ad esempio domande frequenti, luoghi e località importanti, siti e app cercati e usati di frequente e così via. Non dispone però delle autorizzazioni di accesso per gestire le impostazioni di ricerca.

Per assegnare i ruoli di amministratore, vedere [Assegnare diritti di amministratore in Office 365 per le aziende](https://docs.microsoft.com/it-IT/office365/admin/add-users/assign-admin-roles?view=o365-worldwide).

## <a name="step-3-make-content-easy-to-find"></a>Passaggio 3: Facilitare la ricerca del contenuto 

**Microsoft Search** offre agli amministratori strumenti utili per creare un'esperienza di ricerca solida per gli utenti. In **Microsoft Search** gli amministratori possono creare tre diversi contenuti di ricerca per garantire una migliore esperienza di ricerca e ottimizzare la reperibilità dei contenuti:
- **Segnalibro:** i segnalibri sono simili ai risultati promossi in SharePoint e consentono di promuovere i migliori risultati possibili per le query degli utenti nella parte superiore dei risultati della ricerca. Consentono inoltre agli utenti di cercare facilmente siti interni importanti. 
- **Domande e risposte:** sono simili alle domande frequenti e in genere vengono visualizzate sotto forma di domande e risposte. Sono lo strumento ideale per rispondere nel miglior modo possibile alle domande correlate al lavoro degli utenti.
- **Località:** corrispondono agli indirizzi che consentono agli utenti di individuare edifici, uffici e campus dell'organizzazione. 

Più segnalibri, domande e risposte e località sono disponibili, maggiori saranno il valore e i vantaggi per gli utenti. Un numero eccessivo di questi elementi può causare un notevole sovraccarico di gestione in quanto questi contenuti devono essere revisionati e aggiornati periodicamente per garantire che i risultati siano pertinenti e aggiornati.

Ecco alcuni esempi di contenuti che è consigliabile aggiungere ai segnalibri per gli utenti:
- Informazioni relative all'organizzazione, a prodotti o a servizi.
- Contenuti informativi disponibili per tutti gli utenti, ad esempio informazioni sulla società, guida per le app di Windows e Office e così via. 
- Contenuti che gli utenti dell'organizzazione generalmente cercano durante le attività quotidiane. Le ricerche correlate al lavoro includono benefit dei dipendenti, report su orari e spese, invio di ordini di acquisto e assistenza dei servizi IT. 

Per la creazione e la gestione dei contenuti della ricerca, vedere [Facilitare la ricerca dei contenuti](make-content-easy-to-find.md).

## <a name="step-4-test-single-sign-on"></a>Passaggio 4: Testare l'accesso Single Sign-On
**Microsoft Search** usa Azure Active Directory (AAD) per autenticare e autorizzare l'accesso ai dati dell'organizzazione.  Gli utenti possono accedere automaticamente con l'account aziendale o dell'istituto di istruzione quando si è effettuato l'accesso a un'app di Office 365 o a Windows 10.

È consigliabile che gli utenti di **Microsoft Search** usino l'accesso Single Sign-On per ridurre il numero di volte in cui viene loro richiesto di accedere. Gli amministratori devono testare l'accesso Single Sign-On con un piccolo gruppo di utenti per consentire di identificare eventuali problemi di configurazione. 

Per gli utenti di Chrome in Windows 10, l'accesso Single Sign-On funziona solo quando è installata l'estensione di accesso di Windows 10 e AAD per Chrome. Dopo l'installazione è possibile usare l'estensione di Chrome per eseguire facilmente l'autenticazione con AAD quando si accede ai siti supportati, tra cui Office 365 e Bing. Questa funzionalità è disponibile solo per gli utenti autorizzati. 

Per scaricare e installare l'estensione di accesso di Windows 10 e AAD per Chrome, passare a [Chrome Web Store](https://go.microsoft.com/fwlink/?linkid=2090961).

## <a name="step-5-training-and-communication"></a>Passaggio 5: Formazione e comunicazione
Definire le risorse in modalità self-service a cui i dipendenti possono accedere in modo facile e autonomo. Questo consentirà di ridurre il carico complessivo sull'amministratore e sul team incaricato delle comunicazioni e supporterà la formazione autonoma dei dipendenti. Fornire agli utenti comunicazioni, domande frequenti, video e corsi di formazione o webinar registrati. Ecco alcuni collegamenti utili per iniziare:
- [Trovare le informazioni necessarie con Microsoft Search in Office](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Area risorse di Office 365](https://support.office.com/office-training-center)
- 
  [Microsoft Search Center](https://support.office.com/it-IT/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)

## <a name="trying-out-microsoft-search-in-bing"></a>Provare **Microsoft Search** in Bing 
L'amministratore di **Microsoft Search** può disattivare **Microsoft Search** in Bing. Se questa funzione viene disattivata, gli utenti non possono visualizzare i contenuti dell'organizzazione nella ricerca Bing. Per impostazione predefinita, **Microsoft Search** è attivato in Bing. È consigliabile tenere **Microsoft Search** attivato in Bing per un'esperienza utente migliore. 

Se si intende provare **Microsoft Search** su un tenant di test o si vuole testare l'esperienza di ricerca prima di renderla disponibile a tutti gli utenti, è possibile disattivare **Microsoft Search**.
Per attivare/disattivare **Microsoft Search** in Bing, passare a **Servizi e componenti aggiuntivi** in **Interfaccia di amministrazione di Microsoft 365** e attivare/disattivare **Microsoft Search in Bing**.
