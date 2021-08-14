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
ms.openlocfilehash: 84f53755625e65328f8ffe8aabf78f93a9a36a22
ms.sourcegitcommit: 5151bcd8fd929ef37239b7c229e2fa33b1e0e0b7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235870"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Domande frequenti

Ecco un elenco delle domande più comuni.

> [!TIP]
> Se questa sezione non contiene la risposta a una domanda specifica, porre la domanda nel feedback di questo articolo.

## <a name="is-advanced-query-understanding-supported"></a>La comprensione avanzata delle query è supportata?

Sì, Microsoft Search analizza lo scopo della query da frasi più grandi. Questa funzionalità usa l'IA per apprendere frasi superflue comuni che gli utenti aggiungono alle query che non influiscono sulle finalità di ricerca. Ad esempio, quando un utente cerca altre informazioni su come modificare la *password,* estraiamo le parole meno importanti dalla query e il trigger in base a quelle rilevanti, ad esempio cambia *password.*
  
Questa funzionalità non sostituisce le parole chiave impostate nella [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com).
  
## <a name="can-you-search-for-files-on-premises"></a>È possibile cercare file in locale?

Sì. È possibile eseguire ricerche [](http://sharepoint.com/) nei SharePoint locali se si dispone di una distribuzione ibrida di SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Come si fa a impostare Bing come motore di ricerca predefinito per gli utenti dell'organizzazione?

Ecco le istruzioni per impostare il motore di ricerca predefinito, la home page predefinita e il browser predefinito per offrire agli utenti la migliore esperienza con Microsoft Search in [Bing](https://Bing.com):

- [Impostare Microsoft Edge browser predefinito](/deployedge/edge-default-browser)
- [Impostare Bing come motore di ricerca predefinito](set-default-search-engine.md)
- [Impostare Bing.com come home page aziendale](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>In che modo vengono protetti i risultati della ricerca?

È necessaria [Azure Active Directory](/azure/active-directory/) autenticazione per accedere ai risultati dal cloud attendibile. Gli utenti autenticati visualizzano solo i risultati della ricerca per i contenuti a cui hanno accesso. Quando si Microsoft Search in Bing, le query di ricerca vengono de-identificate e i log sono separati dal traffico di [ricerca](https://Bing.com) Bing pubblico.

## <a name="can-i-search-across-federated-organizations"></a>È possibile eseguire ricerche nelle organizzazioni federate?

No.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Dove è possibile ottenere informazioni su Office 365 sicurezza, conformità e privacy?

I dettagli sono disponibili nelle pagine [del Centro protezione per Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-guest-users-access-microsoft-search-in-my-organization"></a>Gli utenti guest possono accedere Microsoft Search all'interno dell'organizzazione?

Microsoft 365 collaborazione con persone esterne all'organizzazione tramite [l'accesso guest.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Questi utenti possono cercare documenti, siti, gruppi, elenchi e raccolte. Tuttavia, gli utenti guest non otterrà l'esperienza Microsoft Search completa e personalizzata e potrebbe essere necessario utilizzare la casella di ricerca nella pagina anziché la casella Microsoft Search unificata nell'intestazione.

## <a name="how-do-i-turn-microsoft-search-in-bing-on-or-off"></a>Come si attiva o Microsoft Search Bing di attivazione o disattivazione?

Per la maggior parte delle organizzazioni, incluse le organizzazioni e l'istruzione, Microsoft Search in Bing è disponibile per impostazione predefinita. Per attivare Microsoft Search in Bing, passare [alla](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/configurations) pagina Configurazioni nell'interfaccia di amministrazione di Microsoft 365. In Microsoft Search in Bing impostazioni scegliere  Modifica impostazioni e attivare Consenti all'organizzazione di **Microsoft Search in Bing**. L'applicazione di questa modifica richiede fino a 24 ore.

Se questa impostazione è disattivata, gli utenti non otterrà risultati interni durante la ricerca Bing, Windows ricerca o in Microsoft Edge. La disattivazione Microsoft Search in Bing non interrompe né impedisce l'aggiunta di contenuto interno all'indice di ricerca. Disabilita solo i Bing di ingresso da Microsoft Search. Per trovare risposte e risultati interni, gli utenti dovranno usare altri punti di ingresso, ad esempio SharePoint Online o un Office 365 app.
