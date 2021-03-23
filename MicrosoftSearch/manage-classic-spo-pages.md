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
description: Utilizzo di Microsoft Search nelle pagine classiche di SharePoint
ms.openlocfilehash: 33215c730d34c14f8ce1d55e93730615688f1e2a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031432"
---
# <a name="classic-pages-and-microsoft-search"></a>Pagine classiche e Microsoft Search

I siti di SharePoint creati prima dei siti moderni utilizzano una casella di ricerca classica e un'esperienza di risultati di ricerca classica. Verrà implementazione di una funzionalità che consente alle pagine classiche predefinite di iniziare a usare l'esperienza di ricerca moderna che utilizza Microsoft Search, che fornisce risultati personalizzati con maggiore pertinenza.

L'utilizzo di Microsoft Search è consigliato per tutti i siti, incluso il classico, ma se i siti classici utilizzano pagine master personalizzate e/o è stata personalizzata l'esperienza dei risultati di ricerca classica, queste personalizzazioni verranno rilevate automaticamente e non si passa a Microsoft Search.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Siti classici che passano automaticamente a Microsoft Search

I siti classici inizieranno a utilizzare Microsoft Search se si verificano tutte le condizioni seguenti:

* Il sito si basa sul modello di sito del team (ad esempio STS#0 e STS#1).
* Nel sito non è attivata la caratteristica di pubblicazione.
* Il sito non utilizza una pagina master personalizzata, ovvero una pagina master diversa da oslo.master o seattle.master.
* Non esistono regole di query attive diverse da quelle che aggiungono risultati alzati di livello per il sito, la raccolta siti o il tenant nell'origine dei risultati predefinita.
* Non sono disponibili tipi di risultati personalizzati per il sito o la raccolta siti nell'origine dei risultati predefinita.
* Il sito o la raccolta siti non è rifiutata esplicitamente tramite l'impostazione *SearchBoxInNavBar* descritta di seguito.

Dopo il passaggio a Microsoft Search, le pagine classiche del sito inizieranno a visualizzare la casella di ricerca nella barra di spostamento della famiglia di prodotti e rimuoveranno la casella di ricerca classica dalla pagina. Quindi, quando un utente cerca un termine, i risultati verranno visualizzati utilizzando l'esperienza di ricerca moderna di Microsoft Search.

## <a name="staying-with-the-classic-search-experience"></a>Rimanere con l'esperienza di ricerca classica

Se il sito soddisfa i criteri elencati in precedenza, ma non si desidera passare all'esperienza di Microsoft Search, è possibile rifiutare esplicitamente l'utilizzo dei comandi seguenti, come proprietario del sito o della raccolta siti.

Puoi usare questo comando in qualsiasi momento, prima o dopo che l'opzione si verifichi, quindi è facile tornare all'esperienza di ricerca che hai avuto in precedenza.

Per eseguire i comandi seguenti, si utilizzerà PowerShell con le estensioni di PowerShell PnP di SharePoint. Puoi installare e altre informazioni su come iniziare [qui](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Per accedere al sito o alla raccolta siti, utilizzare questo comando:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

Per mantenere l'esperienza di ricerca classica per un sito, eseguire il comando seguente:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

In alternativa, se si desidera impostarlo per tutti i siti di una raccolta siti, è possibile utilizzare questo comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Consenso esplicito in Microsoft Search

Per i siti che non soddisfano i criteri elencati in precedenza o per siti specifici di una raccolta siti che hanno scelto di rimanere nella versione classica, è possibile abilitare manualmente l'esperienza di Microsoft Search.

Per modificare questa impostazione per un sito specifico, è possibile utilizzare questo comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

Se si desidera impostarlo per tutti i siti di una raccolta siti, è possibile utilizzare questo comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> È possibile abilitare manualmente Microsoft Search solo per un sito del team o di pubblicazione (ID modello che contengono "STS", "CMSPUBLISHING", "BLANKINTERNET" e "GROUP").