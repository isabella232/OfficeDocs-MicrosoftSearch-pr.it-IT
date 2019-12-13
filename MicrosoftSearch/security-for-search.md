---
title: Protezione e privacy per Microsoft Search in Bing
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
description: Proteggere i dati dell'azienda e gli utenti finali fornendo informazioni agli utenti autorizzati con Microsoft Search in Bing
ms.openlocfilehash: d3d8822b68fc730885e973c0c24c52070d50eba8
ms.sourcegitcommit: f4cb37fdf85b895337caee827fb72b5b7fcaa8ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2019
ms.locfileid: "39995388"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Protezione e privacy per Microsoft Search in Bing

Grazie alle misure di sicurezza e privacy migliorate, Microsoft Search in Bing aiuta a proteggere gli utenti e i dati sul posto di lavoro.

## <a name="secure-by-default"></a>Sicuro per impostazione predefinita

La ricerca di Microsoft nelle richieste Bing viene effettuata su HTTPS. La connessione è crittografata end-to-end per garantire una maggiore sicurezza.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticazione e autorizzazione con Azure Active Directory

L'autenticazione per la ricerca Microsoft in Bing è associata ad Azure Active Directory. Quando gli utenti di Microsoft Search passano a Bing, l'intestazione Bing mostrerà le opzioni di accesso per un account Microsoft, nonché un account aziendale o dell'Istituto di istruzione. Se Bing non è in grado di determinare se un utente è un partecipante idoneo, gli utenti possono accedere alla pagina [Esplora Microsoft Search](https://www.bing.com/business/explore) , in cui verranno automaticamente reindirizzati alla pagina di accesso dell'organizzazione.
 
Gli utenti possono accedere a Microsoft Search solo con un account aziendale o dell'istituto di istruzione e con le stesse credenziali usate per accedere ai servizi di Office 365, ad esempio SharePoint o Outlook. Non è possibile accedere a Microsoft Search con un account Microsoft personale.
    
## <a name="single-sign-on"></a>Single Sign-On

Se un utente è già autenticato con l'account aziendale o dell'Istituto di istruzione in un altro servizio, ad esempio Outlook o SharePoint, verrà automaticamente firmato nello stesso account di lavoro o dell'Istituto di istruzione quando si accede a Bing nello stesso browser. Inoltre, quando l'utente si disconnette dall'account di lavoro o dell'Istituto di istruzione, verrà automaticamente disconnesso da altri servizi di Microsoft Office nello stesso browser.
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>Comunica con il cloud Microsoft dal browser

Quando un utente accede con il proprio account aziendale o dell'Istituto di istruzione, Bing scaricherà le raccolte client necessarie al browser per abilitare i risultati di ricerca di Microsoft. Successivamente, quando eseguono la ricerca, il codice in-browser chiama il cloud di Office 365 per ottenere i risultati del lavoro. A tale scopo, Microsoft Search utilizza un'API dedicata che è conforme a Tier C (SOC2 Type 1) in conformità a Office 365 [Compliance Framework for Industry Standards and Regulations] (https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (Download PDF). Questo significa che i risultati del lavoro e i dati di lavoro non scorrono mai attraverso sistemi Bing non conformi.
  
## <a name="permissions"></a>Autorizzazioni

I risultati di lavoro recuperati dai carichi di lavoro di Office 365, come SharePoint e OneDrive for Business, sono limitati per la sicurezza all'origine. Gli utenti non riescono a visualizzare le risorse come i documenti Word o le presentazioni PowerPoint a cui non possono accedere né visualizzare tramite Office 365, ma vedranno solo i propri file e quelli che sono stati condivisi con loro dall'autore in modo esplicito o implicito (ad esempio, attraverso un'appartenenza al gruppo) in SharePoint.

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Microsoft Search in Bing protegge le ricerche sul posto di lavoro

Quando un utente immette una query di ricerca in Microsoft Search in Bing, si verificano due richieste di ricerca simultanee:

- Una ricerca delle risorse interne dell'organizzazione.
- Ricerca separata dei risultati pubblici da Bing.com.

Poiché le ricerche sul posto di lavoro possono essere sensibili, Microsoft Search ha implementato una serie di misure di attendibilità che descrivono in che modo viene gestita la ricerca separata dei risultati pubblici di Bing.com.

### <a name="logging"></a>Registrazione

<Need an intro paragraph here>

- Tutti i registri di ricerca di Bing.com che si riferiscono a Microsoft Search nel traffico Bing sono dissociati dall'identità di lavoro.
- Se viene soddisfatta una serie di restrizioni o soglie di frequenza che forniscono la sicurezza che la query non è specifica di una determinata organizzazione, la query viene trattata come descritto nella sezione ricerca e intelligenza artificiale dell' [informativa sulla privacy](https://privacy.microsoft.com/privacystatement). Ad esempio, tali query verranno utilizzate per modellare e formare le caratteristiche pubbliche, come l'autosuggestione o le ricerche correlate.
- Le query che non soddisfano la serie di restrizioni o soglie di frequenza verranno archiviate separatamente dal traffico pubblico non di Microsoft Search.

### <a name="advertising"></a>Pubblicità

La pubblicità mostrata su Bing.com in connessione con le ricerche sul posto di lavoro è solo correlata al contenuto delle query di ricerca. Le inserzioni non vengono mai personalizzate in base all'identità professionale degli utenti.
     
## <a name="gdpr"></a>GDPR

Il [21 maggio 2018 post di Blog](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) di Microsoft riflette il nostro impegno per la conformità di GDPR e in che modo Microsoft aiuta le aziende e le organizzazioni con i propri obblighi di conformità a GDPR. È possibile trovare ulteriori dettagli nelle [domande frequenti sul Centro protezione](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)Microsoft. 

Le query di ricerca di Microsoft eseguite sulle risorse interne del cliente e i risultati restituiti sono considerati dati dei clienti e, come tali, soddisfano anche gli impegni del processore descritti nell'articolo 28 come riflesso nelle [domande frequenti sul Centro protezione](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs). Per quanto riguarda le query da Microsoft Search che passano a Bing pubblico, Microsoft è conforme ai propri obblighi GDPR come titolare del trattamento dei dati.

