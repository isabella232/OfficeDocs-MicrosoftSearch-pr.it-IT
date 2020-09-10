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
ms.openlocfilehash: c4b0d888e7765cf965832c252a79bdcf8aa5f6cf
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422965"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Domande frequenti

Ecco un elenco delle domande più comuni.

> [!TIP]
> Se questa sezione non contiene la risposta a una domanda specifica, porre la domanda nel feedback di questo articolo.

## <a name="is-advanced-query-understanding-supported"></a>La comprensione avanzata delle query è supportata?

Sì, Microsoft Search analizza gli intenti delle query da frasi di dimensioni maggiori. Questa funzionalità utilizza Ia per imparare le frasi superflue comuni che gli utenti aggiungono alle query che non influiscono sull'intenzione di ricerca. Ad esempio, quando un utente cerca informazioni *su come modificare la password*, estrarre le parole meno importanti dalla query e dal trigger in base a quelle rilevanti come *Change password*.
  
Questa funzionalità non sostituirà le parole chiave impostate nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).
  
## <a name="can-you-search-for-files-on-premises"></a>È possibile cercare file in locale?

Sì. Se si dispone di una distribuzione ibrida di SharePoint, è possibile eseguire la ricerca nei file di [SharePoint](http://sharepoint.com/) locali.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Come si fa a impostare Bing come motore di ricerca predefinito per gli utenti dell'organizzazione?

Di seguito sono riportate le istruzioni per l'impostazione del motore di ricerca predefinito, della Home page predefinita e del browser predefinito per offrire agli utenti la migliore esperienza con Microsoft Search in [Bing](https://Bing.com):

- [Impostare Microsoft Edge come browser predefinito](set-default-browser.md)
- [Impostare Bing come motore di ricerca predefinito](set-default-search-engine.md)
- [Impostare Bing.com come home page aziendale](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>In che modo vengono protetti i risultati della ricerca?

È necessaria l'autenticazione di [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) per accedere ai risultati dal cloud attendibile. Gli utenti autenticati visualizzano solo i risultati della ricerca per i contenuti a cui hanno accesso. Le query di ricerca sono deidentificate e i registri sono separati dal traffico di ricerca [Bing](https://Bing.com) pubblico. Questo livello di protezione non è offerto da nessun altro nel settore.

## <a name="can-i-search-across-federated-organizations"></a>È possibile eseguire ricerche nelle organizzazioni federate?

No.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Dove è possibile ottenere informazioni sulla sicurezza, la conformità e la privacy di Office 365?

È possibile trovare i dettagli nelle [pagine del Centro protezione per Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>Gli utenti possono guadagnare punti di Microsoft Rewards con l'account aziendale o dell'istituto di istruzione?

Gli utenti aziendali di Microsoft Search devono accedere con un account aziendale o dell'istituto di istruzione. Non possono però partecipare al programma Microsoft Rewards o accedervi con tali account. Esiste però un caso in cui gli utenti aziendali possono accumulare punti di Microsoft Rewards, ovvero quando un utente di Microsoft Search ha un account Rewards creato con un [account Microsoft](https://www.microsoft.com/welcome?rtc=1). L'indirizzo di posta elettronica associato a un account Microsoft può provenire da Outlook.com, Hotmail.com, Gmail, Yahoo o altri provider. Se gli utenti accedono sia con l'account aziendale che con l'account Microsoft nella stessa sessione del browser, possono accumulare punti nell'account Rewards. L'accumulo dei punti durante la ricerca con Microsoft Search viene interrotto quando si cancellano i cookie.
