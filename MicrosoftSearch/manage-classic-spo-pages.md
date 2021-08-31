---
title: Pagine classiche in SharePoint Online e Microsoft Search
ms.author: keremy
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
description: Utilizzo Microsoft Search pagine SharePoint classiche
ms.openlocfilehash: 5b9c40da63ccf3b28cf2d61282763d3d4f62f867
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702040"
---
# <a name="classic-pages-and-microsoft-search"></a>Pagine classiche e Microsoft Search

SharePoint siti creati prima dei siti moderni utilizzano una casella di ricerca classica e un'esperienza di risultati di ricerca classica. Verrà implementazione di una funzionalità che consente alle pagine classiche predefinite di iniziare a usare l'esperienza di ricerca moderna che usa Microsoft Search, che fornisce risultati personalizzati con maggiore pertinenza.

L'uso di Microsoft Search è consigliato per tutti i siti, incluso il classico, ma se i siti classici utilizzano pagine master personalizzate e/o se è stata personalizzata l'esperienza dei risultati di ricerca classica, queste personalizzazioni verranno rilevate automaticamente e non si passa a Microsoft Search.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Siti classici che passano automaticamente a Microsoft Search

I siti classici inizieranno a Microsoft Search se sono vere tutte le condizioni seguenti:

* Il sito si basa sul modello di sito del team (ad esempio STS#0 e STS#1).
* Nel sito non è attivata la caratteristica di pubblicazione.
* Il sito non utilizza una pagina master personalizzata, ovvero una pagina master diversa da oslo.master o seattle.master.
* Non esistono regole di query attive diverse da quelle che aggiungono risultati alzati di livello per il sito, la raccolta siti o il tenant nell'origine dei risultati predefinita.
* Non sono disponibili tipi di risultati personalizzati per il sito o la raccolta siti nell'origine dei risultati predefinita.
* Il sito o la raccolta siti non è rifiutata esplicitamente tramite l'impostazione *SearchBoxInNavBar* descritta di seguito.

Dopo il passaggio a Microsoft Search, le pagine classiche del sito inizieranno a visualizzare la casella di ricerca nella barra di spostamento della famiglia di prodotti e rimuoveranno la casella di ricerca classica dalla pagina. Quindi, quando un utente cerca un termine, i risultati verranno visualizzati utilizzando l'esperienza di ricerca moderna di Microsoft Search.

## <a name="staying-with-the-classic-search-experience"></a>Rimanere con l'esperienza di ricerca classica

Se il sito soddisfa i criteri elencati in precedenza, ma non si desidera passare all'esperienza di Microsoft Search, è possibile rifiutare esplicitamente l'utilizzo dei comandi seguenti, come proprietario del sito o della raccolta siti.

È possibile utilizzare questo comando in qualsiasi momento, prima o dopo che l'opzione si verifichi, quindi è facile tornare all'esperienza di ricerca precedente.

Per eseguire i comandi seguenti, si utilizzerà PowerShell con SharePoint powershell PnP. Puoi installare e altre informazioni su come iniziare [qui](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Per accedere al sito o alla raccolta siti, utilizzare questo comando:

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

## <a name="opting-into-microsoft-search"></a>Opting into Microsoft Search

Per i siti che non soddisfano i criteri elencati in precedenza o per siti specifici di una raccolta siti che hanno scelto di rimanere nella versione classica, è possibile abilitare manualmente l'esperienza Microsoft Search siti.

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