---
title: Creare una pagina dei risultati di ricerca personalizzata in SharePoint Online
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Creare la propria pagina dei risultati di ricerca per un sito di SharePoint Online
ms.openlocfilehash: 9b168dccaa6126148c877b5841b91c63f7bdc2ac
ms.sourcegitcommit: 5fb46a04e86fb49477f8ce7ab3caa1b503215b8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503240"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Creare una pagina dei risultati di ricerca personalizzata in SharePoint Online

Uno dei modi per personalizzare l'esperienza di ricerca in SharePoint consiste nel creare una pagina dei risultati di ricerca personalizzata per un sito. In questo modo è possibile utilizzare una pagina creata, anziché quella predefinita nella pagina dei risultati di ricerca di Microsoft. In questo modo si ottiene una maggiore flessibilità per l'aspetto dei risultati di ricerca per gli utenti.

>[!NOTE]
> Per apportare modifiche alla pagina dei risultati di Microsoft Search predefinita disponibile per impostazione predefinita, vedere [personalizzare la pagina dei risultati di ricerca](customize-search-page.md).

Con una pagina dei risultati personalizzata è possibile creare una nuova pagina che può essere utilizzata per controllare il layout e la struttura dei risultati della ricerca per supportare le esigenze dell'organizzazione. È possibile utilizzare tutte le web part predefinite, le web part di ricerca di origine aperta provenienti da modelli e procedure di SharePoint, nonché tutte le web part personalizzate che possono essere state sviluppate con SharePoint Framework.

## <a name="configure-a-results-page"></a>Configurare una pagina dei risultati

Per configurare una pagina dei risultati personalizzata in SharePoint Online, eseguire la procedura seguente:

1. Passare al sito in cui si desidera configurare una pagina dei risultati personalizzata e passare a impostazioni **sito > impostazioni raccolta siti > impostazioni di ricerca**.

2. Nelle impostazioni di ricerca, cancellare la selezione dall' **utilizzo delle stesse impostazioni della pagina dei risultati dell'elemento padre**, scegliere **Invia query a una pagina dei risultati personalizzata**e specificare un valore per l' **URL della pagina dei risultati:**.Quindi, salvare le modifiche. L'URL utilizzato in questo articolo dovrebbe essere relativo alla pagina che è stata creata per essere utilizzata come pagina dei risultati personalizzata.

>[!NOTE]
> La pagina dei risultati personalizzata deve trovarsi nello stesso dominio del sito, ma non deve trovarsi nella stessa raccolta siti.  

In alternativa, è possibile utilizzare il [comando set-PnPSearchSettings di PowerShell di SharePoint PNP](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) per impostare il valore anziché utilizzare la pagina Impostazioni sito.

Una volta impostato, la pagina dei risultati di ricerca personalizzata viene visualizzata quando si esegue una ricerca utilizzando la casella di ricerca di Microsoft visualizzata nella barra di spostamento nella parte superiore della pagina e viene utilizzata quando si immette la ricerca dalle pagine del sito o dalla Home page del sito. Non viene utilizzato quando si esegue la ricerca all'interno di un elenco, una raccolta o la pagina contenuto del sito. È possibile utilizzare il collegamento per espandere la ricerca dai risultati della ricerca in elenchi e raccolte per accedere alla pagina dei risultati personalizzata.

## <a name="change-the-layout-of-your-custom-results-page"></a>Modificare il layout della pagina dei risultati personalizzata

È possibile utilizzare un layout di pagina denominato **HeaderlessSearchResults** per rendere la pagina dei risultati di ricerca più vicina alla nostra esperienza nei risultati della ricerca in box.Questo nuovo layout può essere attivo solo per le pagine che sono impostate come pagina dei risultati di ricerca personalizzata.

Per impostare il layout di pagina, è possibile utilizzare il [comando set-PnPClientSidePageSharePoint PNP PowerShell](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) con-LayoutType HeaderlessSearchResults.

## <a name="use-sharepoint-framework-query-extensions"></a>Utilizzare le estensioni di query di SharePoint Framework

Le pagine dei risultati di ricerca personalizzati possono anche avvalersi dell' [estensione di query di SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/building-search-extensions) per modificare la query prima che venga inviata al motore di ricerca.

## <a name="additional-resources"></a>Risorse aggiuntive

Per ulteriori informazioni sulla pagina dei risultati personalizzati, vedere la [sessione di personalizzazione e sviluppo di ignite 2019 Search](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions).

Per i progetti open source, per iniziare a usare le API di Microsoft Search e altri esempi di personalizzazione ed estensibilità, visitare [Microsoft Search su GitHub](https://github.com/microsoft-search).
