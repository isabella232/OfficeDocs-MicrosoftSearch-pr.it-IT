---
title: Pagine classiche in SharePoint Online e Microsoft Search
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Utilizzo di Microsoft Search nelle pagine di SharePoint classiche
ms.openlocfilehash: 9a5aeb2e683297faccfb55d3407653c1791b3961
ms.sourcegitcommit: 7133d46ca9c3a5216ee9159db781febd17e5a831
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "49863175"
---
# <a name="classic-pages-and-microsoft-search"></a>Pagine classiche e Microsoft Search

I siti di SharePoint creati prima dei siti moderni utilizzano una casella di ricerca classica e un'esperienza di risultati della ricerca classica. Verrà implementata una funzionalità che utilizzerà le pagine classiche predefinite per iniziare a utilizzare l'esperienza di ricerca moderna che utilizza Microsoft Search, che fornisce risultati personalizzati con maggiore rilevanza.

L'utilizzo di Microsoft Search è consigliato per tutti i siti, tra cui quello classico, ma se i siti classici utilizzano pagine master personalizzate e/o se sono state personalizzate le classiche esperienze dei risultati di ricerca, verranno rilevate automaticamente queste personalizzazioni e non si passerà a Microsoft Search.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Siti classici che passano automaticamente a Microsoft Search

I siti classici inizieranno a utilizzare Microsoft Search se sono soddisfatte tutte le seguenti condizioni:

* Il sito è basato sul modello di sito del team (come STS # 0 e STS # 1).
* Al sito non è attivata la caratteristica di pubblicazione.
* Il sito non utilizza una pagina master personalizzata (una pagina master diversa da Oslo. master o Seattle. master).
* Non vi sono regole di query attive diverse da quelle che aggiungono risultati alzati di valore per il sito, la raccolta siti o il tenant nell'origine dei risultati predefinita.
* Non sono disponibili tipi di risultati personalizzati per il sito o la raccolta siti nell'origine dei risultati predefinita.
* Il sito o la raccolta siti non viene disattivata tramite l'impostazione *SearchBoxInNavBar* descritta di seguito.

Dopo il passaggio a Microsoft Search, le pagine classiche del sito inizieranno a visualizzare la casella di ricerca nella barra di spostamento della famiglia e rimuovere la casella di ricerca classica dalla pagina. Successivamente, quando un utente cerca un termine, i risultati verranno visualizzati utilizzando l'esperienza di ricerca moderna di Microsoft Search.

## <a name="staying-with-the-classic-search-experience"></a>Rimanere con l'esperienza di ricerca classica

Se il sito soddisfa i criteri elencati in questo argomento, ma non si desidera che passi all'esperienza di ricerca di Microsoft, è possibile escludere l'utilizzo dei comandi seguenti, come proprietario del sito o della raccolta siti.

È possibile utilizzare questo comando in qualsiasi momento, prima o dopo l'operazione, per cui è facile tornare all'esperienza di ricerca precedentemente eseguita.

Per eseguire i comandi riportati di seguito, si utilizzerà PowerShell con le estensioni di PowerShell di SharePoint PnP. È possibile installare e scoprire altre informazioni su come [iniziare.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps) Si eseguirà l'accesso al sito o alla raccolta siti utilizzando il comando seguente:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

Per rimanere con l'esperienza di ricerca classica per un sito, eseguire il seguente comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

In alternativa, se si desidera impostarlo per tutti i siti di una raccolta siti, è possibile utilizzare questo comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Scelta di Microsoft Search

Per i siti che non soddisfano i criteri sopra elencati o per siti specifici di una raccolta siti che hanno scelto di rimanere in modalità classica, è possibile abilitare manualmente l'esperienza di ricerca di Microsoft.

Per modificare questa impostazione per un sito specifico, è possibile utilizzare questo comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

Se si desidera impostarla per tutti i siti di una raccolta siti, è possibile utilizzare questo comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> È possibile abilitare manualmente la ricerca di Microsoft solo per un sito del team o un sito di pubblicazione (ID modello che contengono "STS", "CMSPUBLISHING", "BLANKINTERNET" e "GROUP").
