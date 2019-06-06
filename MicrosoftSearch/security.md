---
title: Sicurezza per Microsoft Search
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
ROBOTS: NOINDEX
description: Microsoft Search consente di proteggere i dati e gli utenti aziendali, fornendo informazioni agli utenti autorizzati
ms.openlocfilehash: 4e5e23e5e1389c95d28ede66e06707f9856a3770
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727942"
---
# <a name="security-for-microsoft-search"></a>Sicurezza per Microsoft Search

Grazie alla sicurezza a livello enterprise, Microsoft Search protegge costantemente gli utenti e i dati.


## <a name="secure-by-default"></a>Sicuro per impostazione predefinita

Microsoft Search garantisce l'invio delle richieste su HTTPS. Questa misura di protezione garantisce l'applicazione della crittografia end-to-end alla connessione per una maggiore sicurezza.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticazione e autorizzazione con Azure Active Directory

L'autenticazione per Microsoft Search è collegata ad Azure Active Directory. Quando gli utenti di Microsoft Search visitano Bing, la relativa intestazione mostra opzioni di accesso per un account Microsoft oltre che per un account aziendale o dell'istituto di istruzione. Se Bing non riesce a determinare se è un partecipante idoneo, l'utente potrà passare alla pagina [Esplora Microsoft Search](https://www.bing.com/business/explore), dove sarà automaticamente reindirizzato alla pagina di accesso dell'organizzazione. 
  
Gli utenti possono accedere a Microsoft Search solo con un account aziendale o dell'istituto di istruzione e con le stesse credenziali usate per accedere ai servizi di Office 365, ad esempio SharePoint o Outlook. Non è possibile accedere a Microsoft Search con un account Microsoft personale.
  
Gli utenti non possono accedere contemporaneamente a Bing con un account Microsoft e un account aziendale o dell'istituto di istruzione.
  
## <a name="single-sign-on"></a>Single Sign-On

Se un utente si è già autenticato con il proprio account aziendale o dell'istituto di istruzione in un altro servizio, ad esempio Outlook o SharePoint, accederà automaticamente a Microsoft Search quando visita Bing nello stesso browser. In più, quando l'utente si disconnette da Microsoft Search, sarà automaticamente disconnesso dagli altri servizi nello stesso browser.
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>Comunica con il Cloud attendibile dal browser

Quando un utente accede con il proprio account aziendale o dell'istituto di istruzione, Bing scarica le librerie necessarie nel browser per abilitare i risultati di Microsoft Search. Quindi, quando l'utente esegue una ricerca, il codice nel browser chiama il cloud di Office 365 per ottenere risultati di lavoro. A tale scopo, Microsoft Search usa un'API dedicata conforme al livello C (SOC2 tipo 1) ai sensi degli standard e delle normative di settore di Office 365, consultabili nel documento [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (scaricabile in formato PDF). Questo significa che i risultati e i dati di lavoro non passano attraverso i sistemi Bing non conformi. 
  
## <a name="permissions"></a>Autorizzazioni

I risultati di lavoro recuperati dai carichi di lavoro di Office 365, come SharePoint e OneDrive for Business, sono limitati per la sicurezza all'origine. Gli utenti non riescono a visualizzare le risorse come i documenti Word o le presentazioni PowerPoint a cui non possono accedere né visualizzare tramite Office 365, ma vedranno solo i propri file e quelli che sono stati condivisi con loro dall'autore in modo esplicito o implicito (ad esempio, attraverso un'appartenenza al gruppo) in SharePoint.
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Protegge le query degli utenti della parte pubblica di Bing

Dal momento che le ricerche aziendali possono essere riservate, Microsoft Search ha implementato una serie di misure di protezione per la gestione delle stesse da parte dei risultati Web pubblici di Bing.
  
Indipendentemente dal fatto che una query utente contenga uno o più risultati di lavoro nella risposta risultante, vengono adottate le misure seguenti:
  
- Registrazione
    
  - Tutti i log di ricerca relativi al traffico di Microsoft Search vengono privati degli elementi identificativi e archiviati separatamente dal traffico pubblico non relativo a Microsoft Search, quindi conservati per 18 mesi, con accesso limitato solo ai fini del debug.
    
  - Le query in questi log non vengono usate per modellare o eseguire il traning delle funzionalità pubbliche, ad esempio i suggerimenti automatici o le ricerche correlate per il Web pubblico.
    
  - L'accesso limitato viene gestito usando vari meccanismi di sicurezza, inclusi i gruppi di sicurezza e altri livelli del sistema di progettazione.
    
- Cronologia di ricerca
    
  - Quando l'utente accede con un account aziendale o dell'istituto di istruzione, la cronologia di ricerca non sarà disponibile in altri computer o dispositivi.
    
- Pubblicità
    
  - Le query di ricerca di contenuti nell'organizzazione non vengono mai condivise o suggerite agli inserzionisti.
    
  - I log di Cerca inserzioni relativi a Microsoft Search vengono archiviati separatamente dal traffico pubblico.
    
  - Le inserzioni non vengono mai personalizzate in base all'identità professionale o all'azienda di un utente.
    
## <a name="gdpr"></a>GDPR

Il [post di blog del 21 maggio 2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) riflette l'impegno di Microsoft nei confronti della conformità al GDPR e il modo in cui aiuta le aziende e le organizzazioni ad adempiere ai propri obblighi in materia di conformità al GDPR. Altre informazioni dettagliate sono disponibili nelle [domande frequenti del Centro protezione](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs) di Microsoft. Le query di Microsoft Search eseguite in base ai dati del cliente aziendale nell'ambito dei servizi online soddisferanno anche gli impegni del responsabile del trattamento delineati nell'Articolo 28, come si evince dalle [domande frequenti del Centro protezione](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Per quanto riguarda le query di Microsoft Search indirizzate a Bing pubblico, Microsoft funge da titolare del trattamento dei dati e ha implementato misure per deidentificare le query come indicato nel GDPR.


