---
title: Sicurezza e privacy per Microsoft Search in Bing
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Proteggere i dati dell'azienda e gli utenti finali fornendo informazioni agli utenti autorizzati con Microsoft Search in Bing
ms.openlocfilehash: bf3629b2508c705d19e3b7b772c6f3672063a6f1
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "59376057"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Sicurezza e privacy per Microsoft Search in Bing

Con misure di privacy e sicurezza avanzate, Microsoft Search in Bing protegge gli utenti e i dati dell'area di lavoro.

## <a name="secure-by-default"></a>Sicuro per impostazione predefinita

Microsoft Search in Bing richieste vengono effettuate tramite HTTPS. La connessione è crittografata end-to-end per una sicurezza avanzata.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticazione e autorizzazione con Azure Active Directory

L'autenticazione Microsoft Search in Bing è associata a Azure Active Directory. Quando Microsoft Search utenti passano a Bing, nell'intestazione Bing verranno mostrate le opzioni di accesso per un account Microsoft, nonché un account aziendale o dell'istituto di istruzione. Se Bing non è in grado di determinare se un utente è un partecipante idoneo, gli utenti possono passare alla pagina Esplora [Microsoft Search, dove](https://www.bing.com/business/explore) verranno reindirizzati automaticamente alla pagina di accesso dell'organizzazione.

Gli utenti possono accedere a Microsoft Search solo con un account aziendale o dell'istituto di istruzione e con le stesse credenziali usate per accedere ai servizi di Office 365, ad esempio SharePoint o Outlook. Non è possibile accedere a Microsoft Search con un account Microsoft personale.

## <a name="single-sign-on"></a>Single Sign-On

Se un utente è già autenticato con l'account aziendale o dell'istituto di istruzione in un altro servizio, ad esempio Outlook o SharePoint, verrà automaticamente eseguito l'accesso allo stesso account aziendale o dell'istituto di istruzione quando passa a Bing nello stesso browser. Inoltre, quando l'utente esce dal proprio account aziendale o dell'istituto di istruzione, verrà automaticamente disconnesso da altri servizi Microsoft Office nello stesso browser.
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>Comunica con il cloud Microsoft dal browser

Quando un utente accede con l'account aziendale o dell'istituto di istruzione, Bing le raccolte client necessarie verranno scaricate nel browser per abilitare i risultati Microsoft Search lavoro. Quindi, quando esegue una ricerca, il codice nel browser chiama il cloud Office 365 per ottenere risultati di lavoro. A tale scopo, Microsoft Search un'API dedicata che viene gestita in conformità agli obiettivi di controllo di SSAE 18 SOC2 Tipo 1. Ciò significa che i risultati del lavoro e i dati di lavoro non fluiranno attraverso sistemi Bing soggetti a obiettivi di controllo del trattamento dei dati meno stringenti rispetto ai risultati del lavoro stessi quando vengono elaborati in Office 365 Core Online Services.
  
## <a name="permissions"></a>Autorizzazioni

I risultati di lavoro recuperati dai carichi di lavoro di Office 365, come SharePoint e OneDrive for Business, sono limitati per la sicurezza all'origine. Gli utenti non riescono a visualizzare le risorse come i documenti Word o le presentazioni PowerPoint a cui non possono accedere né visualizzare tramite Office 365, ma vedranno solo i propri file e quelli che sono stati condivisi con loro dall'autore in modo esplicito o implicito (ad esempio, attraverso un'appartenenza al gruppo) in SharePoint.

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Microsoft Search in Bing protegge le ricerche sul luogo di lavoro

Quando un utente immette una query di ricerca in Microsoft Search in Bing, si verificano due richieste di ricerca simultanee:

- Ricerca delle risorse interne dell'organizzazione.
- Una ricerca separata dei risultati pubblici da Bing.com.

Poiché le ricerche sul luogo di lavoro potrebbero essere riservate, Microsoft Search ha implementato una serie di misure di attendibilità che descrivono come viene gestita la ricerca separata dei risultati pubblici da Bing.com.

### <a name="logging"></a>Registrazione

- Tutti i log di ricerca di Bing.com relativi a Microsoft Search nel traffico Bing vengono dissociati dall'identità aziendale.
- Se viene soddisfatto un set di restrizioni o soglie di frequenza che ci danno la certezza che la query non sia specifica di una determinata organizzazione, la query verrà trattata come descritto nella sezione Ricerca e intelligenza artificiale dell'Informativa sulla [privacy.](https://privacy.microsoft.com/privacystatement) Ad esempio, tali query verranno utilizzate per modellare e formare le funzionalità pubbliche, ad esempio il controllo automatico o le ricerche correlate.
- Le query che non soddisfano la serie di restrizioni o soglie di frequenza verranno archiviate separatamente dal traffico pubblico non di Microsoft Search.

### <a name="advertising"></a>Pubblicità

La pubblicità mostrata su Bing.com in relazione alle ricerche sul luogo di lavoro è esclusivamente correlata al contenuto delle query di ricerca. Le inserzioni non vengono mai personalizzate in base all'identità professionale degli utenti.

## <a name="gdpr"></a>GDPR

Il post di blog del [21 maggio 2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) di Microsoft riflette il nostro impegno per la conformità al GDPR e il modo in cui Microsoft aiuta le aziende e le organizzazioni a rispettare i propri obblighi di conformità al GDPR. Ulteriori dettagli sono disponibili nelle domande frequenti sul Centro [protezione Microsoft.](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)

Microsoft Search query eseguite sulle risorse interne di un cliente e sui risultati restituiti sono considerati dati del cliente e, di conseguenza, soddisfano anche gli impegni del processore descritti nell'articolo 28, come illustrato nelle domande frequenti sul [Centro](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)protezione. Per quanto riguarda le query provenienti da Microsoft Search che vengono Bing pubbliche, Microsoft è conforme agli obblighi del GDPR come controllore dei dati.
