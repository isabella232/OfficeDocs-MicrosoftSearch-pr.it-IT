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
ms.openlocfilehash: 94161d3ac53ca72a9f8298674a53fdaa0a80caaf5ca3802d47ea693043a30530
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533933"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Domande frequenti

Ecco un elenco delle domande più comuni.

> [!TIP]
> Se questa sezione non contiene la risposta a una domanda specifica, porre la domanda nel feedback di questo articolo.

## <a name="is-advanced-query-understanding-supported"></a>La comprensione avanzata delle query è supportata?

Sì, Microsoft Search analizza lo scopo della query da frasi più grandi. Questa funzionalità usa l'intelligenza artificiale per imparare le frasi superflue comuni che gli utenti aggiungono alle query che non influiscono sulle loro finalità di ricerca. Ad esempio, quando un utente cerca altre informazioni su come modificare la *password,* estraiamo le parole meno importanti dalla query e il trigger in base a quelle rilevanti, ad esempio *cambia password.*
  
Questa funzionalità non sostituisce le parole chiave impostate nella [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com).
  
## <a name="can-you-search-for-files-on-premises"></a>È possibile cercare file in locale?

Sì. È possibile eseguire ricerche nei SharePoint [locali](http://sharepoint.com/) se si dispone di una distribuzione ibrida di SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Come si fa a impostare Bing come motore di ricerca predefinito per gli utenti dell'organizzazione?

Ecco le istruzioni per impostare il motore di ricerca predefinito, la home page predefinita e il browser predefinito per offrire agli utenti la migliore esperienza con Microsoft Search in [Bing](https://Bing.com):

- [Impostare Microsoft Edge browser predefinito](/deployedge/edge-default-browser)
- [Impostare Bing come motore di ricerca predefinito](set-default-search-engine.md)
- [Impostare Bing.com come home page aziendale](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>In che modo vengono protetti i risultati della ricerca?

È necessaria [Azure Active Directory'autenticazione](/azure/active-directory/) per accedere ai risultati dal cloud attendibile. Gli utenti autenticati visualizzano solo i risultati della ricerca per i contenuti a cui hanno accesso. Le query di ricerca vengono de-identificate [](https://Bing.com) e i log sono separati dal traffico di Bing pubblico quando si utilizza Microsoft Search in Bing.

## <a name="can-i-search-across-federated-organizations"></a>È possibile eseguire ricerche nelle organizzazioni federate?

No.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Dove è possibile ottenere informazioni su Office 365 sicurezza, conformità e privacy?

I dettagli sono disponibili nelle pagine [del Centro protezione per Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>Gli utenti guest possono sfruttare Microsoft Search nell'organizzazione?

Microsoft 365 collaborazione con persone esterne all'organizzazione tramite [l'accesso guest.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Questi utenti saranno in grado di eseguire operazioni di ricerca su documenti, siti, gruppi, elenchi e raccolte. Tuttavia, gli utenti guest non riceveranno l'esperienza completa, personalizzata e Microsoft Search e potrebbe essere necessario utilizzare la casella di ricerca nella pagina anziché la casella di Microsoft Search unificata nell'intestazione.