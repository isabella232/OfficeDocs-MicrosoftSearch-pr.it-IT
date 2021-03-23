---
title: Domande frequenti
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Risposte ad alcune domande frequenti sulla ricerca di contenuti nell'organizzazione e su Microsoft Search
ms.openlocfilehash: 98128297047d50e2d418a8ed062066ab9e86749e
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031621"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Domande frequenti

Ecco un elenco delle domande più comuni.

> [!TIP]
> Se questa sezione non contiene la risposta a una domanda specifica, porre la domanda nel feedback di questo articolo.

## <a name="is-advanced-query-understanding-supported"></a>La comprensione avanzata delle query è supportata?

Sì, Microsoft Search analizza lo scopo delle query da frasi più grandi. Questa funzionalità usa l'intelligenza artificiale per imparare le frasi superflue comuni che gli utenti aggiungono alle query che non influiscono sulle loro finalità di ricerca. Ad esempio, quando un utente cerca altre informazioni su come modificare la *password,* estraiamo le parole meno importanti dalla query e il trigger in base a quelle rilevanti, ad esempio *cambia password.*
  
Questa funzionalità non sostituisce le parole chiave impostate nell'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com)
  
## <a name="can-you-search-for-files-on-premises"></a>È possibile cercare file in locale?

Sì. È possibile eseguire ricerche nei file [di SharePoint](http://sharepoint.com/) locali se si dispone di una distribuzione ibrida di SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Come si fa a impostare Bing come motore di ricerca predefinito per gli utenti dell'organizzazione?

Ecco le istruzioni per impostare il motore di ricerca predefinito, la home page predefinita e il browser predefinito per offrire agli utenti la migliore esperienza con Microsoft Search in [Bing:](https://Bing.com)

- [Impostare Microsoft Edge come browser predefinito](/deployedge/edge-default-browser)
- [Impostare Bing come motore di ricerca predefinito](set-default-search-engine.md)
- [Impostare Bing.com come home page aziendale](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>In che modo vengono protetti i risultati della ricerca?

È necessaria [l'autenticazione di Azure Active Directory](/azure/active-directory/) per accedere ai risultati dal cloud attendibile. Gli utenti autenticati visualizzano solo i risultati della ricerca per i contenuti a cui hanno accesso. Le query di ricerca vengono de-identificate e i log sono separati dal traffico di ricerca [bing](https://Bing.com) pubblico quando si utilizza Microsoft Search in Bing.

## <a name="can-i-search-across-federated-organizations"></a>È possibile eseguire ricerche nelle organizzazioni federate?

No.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Dove è possibile ottenere informazioni su sicurezza, conformità e privacy di Office 365?

I dettagli sono disponibili nelle pagine [del Centro protezione per Office 365.](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>Gli utenti possono guadagnare punti di Microsoft Rewards con l'account aziendale o dell'istituto di istruzione?

Gli utenti aziendali di Microsoft Search devono accedere con un account aziendale o dell'istituto di istruzione. Non possono però partecipare al programma Microsoft Rewards o accedervi con tali account. Esiste però un caso in cui gli utenti aziendali possono accumulare punti di Microsoft Rewards, ovvero quando un utente di Microsoft Search ha un account Rewards creato con un [account Microsoft](https://www.microsoft.com/welcome?rtc=1). L'indirizzo di posta elettronica associato a un account Microsoft può provenire da Outlook.com, Hotmail.com, Gmail, Yahoo o altri provider. Se gli utenti accedono sia con l'account aziendale che con l'account Microsoft nella stessa sessione del browser, possono accumulare punti nell'account Rewards. L'accumulo dei punti durante la ricerca con Microsoft Search viene interrotto quando si cancellano i cookie.

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>Gli utenti guest possono sfruttare Microsoft Search nell'organizzazione?

Microsoft 365 consente una collaborazione ricca con persone esterne all'organizzazione tramite [l'accesso guest.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Questi utenti saranno in grado di eseguire operazioni di ricerca su documenti, siti, gruppi, elenchi e raccolte. Tuttavia, gli utenti guest non otterrà l'esperienza completa, personalizzata di Microsoft Search e potrebbe essere necessario sfruttare la casella di ricerca nella pagina anziché la casella unificata di Microsoft Search nell'intestazione.