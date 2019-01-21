---
title: Sicurezza per la ricerca di Microsoft
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
description: Proteggere i dati dell'organizzazione e gli utenti fornendo informazioni per gli utenti autorizzati a Microsoft Search
ms.openlocfilehash: 65cf1d49e32edbb8061a06f8da7ba644c2145e24
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378912"
---
# <a name="security-for-microsoft-search"></a>Sicurezza per la ricerca di Microsoft

Con protezione di livello aziendale Microsoft Search sempre consente di mantenere gli utenti e dati protetti.
  
## <a name="secure-by-default"></a>Proteggere per impostazione predefinita

Microsoft Search assicura sempre le richieste vengono effettuate tramite HTTPS. In tal garantisce che la connessione è crittografate end-to-end per la protezione avanzata.
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Autenticazione e autorizzazione con Azure Active Directory

Autenticazione per Microsoft Search è collegato al Azure Active Directory. Quando gli utenti di Microsoft Search Bing, nonché un lavoro Bing intestazione visualizzerà le opzioni di accesso per un account Microsoft o scuola account. Se Bing non è possibile determinare se un utente è un partecipante idoneo, gli utenti possono accedere alla pagina [Esplora Microsoft Search](https://www.bing.com/business/explore) , in cui verrà automaticamente reindirizzati alla pagina di accesso dell'organizzazione. 
  
Gli utenti possono accedere a Microsoft Search solo tramite un account di lavoro o della scuola. È necessario accedere con le stesse credenziali utilizzata per accedere a servizi di Office 365, ad esempio SharePoint o Outlook. Un account Microsoft personale non può essere utilizzato per accedere a Microsoft Search.
  
Gli utenti non possono eseguire l'accesso a Bing con un account Microsoft e un account di lavoro o della scuola contemporaneamente.
  
## <a name="single-sign-on"></a>Single Sign-On

Se un utente è già stato autenticato con loro account ufficio o della scuola in un altro servizio, ad esempio Outlook o SharePoint, si verrà eseguire automaticamente l'accesso a Microsoft Search quando accedono al Bing nel browser stesso. Inoltre, quando l'utente accede da Microsoft Search, si verrà automaticamente la disconnessione provenienti da altri servizi nel browser stesso.
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>Comunica con il Cloud attendibili dal browser

Quando un utente accede con il proprio lavoro o un account scuola, Bing scaricheranno le librerie client necessarie al browser per attivare i risultati di Microsoft Search. Quando si esegue la ricerca, il codice nel browser chiama nel cloud di Office 365 per ottenere risultati di lavoro. A tale scopo, Microsoft Search utilizza un'API dedicata è livello C SOC2 tipo 1 compatibile in conformità a Office 365 [Conformità normativa per gli standard del settore e normative](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (download del file PDF). Di conseguenza, i risultati di lavoro e dati sul lavoro mai trasmessi in sistemi Bing non conformi. 
  
## <a name="permissions"></a>Autorizzazioni

Risultati lavoro recuperati da carichi di lavoro di Office 365, ad esempio SharePoint e OneDrive for Business sono sicurezza tagliato in corrispondenza dell'origine. Gli utenti non possono visualizzare le risorse, ad esempio documenti di Word o presentazioni di PowerPoint non possono vedere e accedere tramite Office 365. È possibile visualizzare solo i propri file e i file che sono state condivise con loro dall'autore in modo esplicito o implicito (mediante l'appartenenza al gruppo, ad esempio) in SharePoint.
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Impedisce la parte pubblica di Bing che le query degli utenti

Poiché le ricerche lavorative possono essere riservate, Microsoft Search ha implementato un gruppo di misure di protezione di come vengono gestiti dalla parte risultati web pubblici di Bing.
  
Indipendentemente dal fatto che una query utente contiene uno o più risultati di lavoro in risposta restituito, vengono eseguite le seguenti misure:
  
- Logging
    
  - Tutti i log di ricerca relative al traffico Microsoft Search vengono identificati deprovisioning e archiviati separatamente dal traffico pubblico, non Microsoft Search. Si sta conservati per 18 mesi e l'accesso è limitato solo scopo di debug.
    
  - Le query in tali registri non consentono di modello o treno funzionalità pubblica come suggerimenti automatici o correlati consente di cercare il web pubblici.
    
  - Accesso limitato viene gestita mediante diversi sistemi protette, inclusi i gruppi di protezione e altri livelli all'interno del sistema engineering.
    
- Cronologia di ricerca
    
  - Dopo l'accesso con un account di lavoro o della scuola, la cronologia di ricerca dell'utente non sarà disponibile in altri computer o dispositivi.
    
- Pubblicità
    
  - Query di ricerca organizzazione mai condivisi o consigliata agli annunci.
    
  - Vengono archiviati i registri di annunci di ricerca relativo a Microsoft Search separatamente dal traffico pubblico.
    
  - ADS mai destinate a un utente in base alle loro identità aziendale dell'utente o dell'organizzazione.
    
## <a name="gdpr"></a>GDPR

Il [21 maggio 2018, post di blog di](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) Microsoft riflette la conferma dell'impegno per conformità PILR e come Microsoft aiuta le aziende e organizzazioni con i propri obblighi di conformità PILR. È possibile trovare ulteriori dettagli nella Microsoft [Domande frequenti su Centro protezione](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Query Microsoft Search che operano sulla base di dati dei clienti i clienti dell'organizzazione all'interno dei servizi Online soddisferà anche gli impegni di processore descritti nell'articolo 28, come descritto nell' [Domande frequenti su Centro protezione](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Per quanto riguarda le query Microsoft Search che fa riferimento alla Bing pubblica, Microsoft è un controller di dati e ha implementato le misure per identificare le query deprovisioning come descritto in PILR.


