---
title: Creare una pagina dei risultati di ricerca personalizzata in SharePoint Online
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
description: Creare la propria pagina dei risultati di ricerca per un sito SharePoint Online
ms.openlocfilehash: df99287dbdd9a82c1a8bc66b39e67a37fcb22da8
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375956"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Creare una pagina dei risultati di ricerca personalizzata in SharePoint Online

Un modo per personalizzare l'esperienza di ricerca in SharePoint è creare una pagina dei risultati di ricerca personalizzata per un sito. In questo modo è possibile utilizzare una pagina creata dall'utente anziché l'impostazione predefinita Microsoft Search pagina dei risultati. In questo modo è possibile ottenere maggiore flessibilità sull'aspetto dell'esperienza dei risultati di ricerca per gli utenti.

>[!NOTE]
> Per apportare modifiche alla pagina dei Microsoft Search predefinita, vedere [Personalizzare la pagina dei risultati della ricerca.](customize-search-page.md)

Con una pagina dei risultati personalizzata è possibile creare una nuova pagina che può essere utilizzata per controllare il layout e la progettazione dei risultati di ricerca per supportare le esigenze dell'organizzazione. È possibile utilizzare qualsiasi web part incorporata, web part di ricerca open source della community di modelli e procedure di SharePoint, nonché qualsiasi web part personalizzata sviluppata tramite SharePoint Framework.

## <a name="configure-a-results-page"></a>Configurare una pagina dei risultati

Per configurare una pagina dei risultati personalizzata in SharePoint Online, eseguire la procedura seguente:

1. Passare al sito in cui si desidera configurare una pagina dei risultati personalizzata e passare a Raccolta siti Impostazioni > **Impostazioni > ricerca Impostazioni**.

2. In Ricerca Impostazioni deselezionare Usa le stesse impostazioni della pagina dei risultati dell'elemento **padre,** scegliere Invia **query a** una pagina dei risultati personalizzata e specificare un valore per URL pagina **risultati:**. Salvare quindi le modifiche. L'URL utilizzato qui deve essere per la pagina creata per l'utilizzo come pagina dei risultati personalizzata.

>[!NOTE]
> La pagina dei risultati personalizzata deve essere nello stesso dominio del sito, ma non deve essere nella stessa raccolta siti.  

In alternativa, è possibile utilizzare il comando [Set-PnPSearchSettings SharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) per impostare il valore anziché utilizzare la pagina Impostazioni sito.

Una volta impostata, la pagina dei risultati di ricerca personalizzata viene visualizzata quando si esegue una ricerca utilizzando la casella Microsoft Search visualizzata nella barra di spostamento nella parte superiore della pagina e utilizzata quando si immette la ricerca dalle pagine del sito o dalla home page del sito. Non viene utilizzato quando si esegue una ricerca all'interno di un elenco, una raccolta o la pagina del contenuto del sito. È possibile utilizzare il collegamento per espandere la ricerca dai risultati della ricerca in elenchi e raccolte per accedere alla pagina dei risultati personalizzata.

## <a name="change-the-layout-of-your-custom-results-page"></a>Modificare il layout della pagina dei risultati personalizzata

È possibile utilizzare un layout di pagina denominato **HeaderlessSearchResults** per rendere la pagina dei risultati di ricerca più vicina all'esperienza dei risultati di ricerca predefinita. Questo nuovo layout può essere attivo solo per le pagine impostate come pagina dei risultati di ricerca personalizzata.

Per impostare il layout di pagina, è possibile utilizzare il comando [Set-PnPClientSidePageSharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) con -LayoutType HeaderlessSearchResults.

## <a name="use-sharepoint-framework-query-extensions"></a>Usare le SharePoint Framework query

Le pagine dei risultati di ricerca personalizzate possono inoltre utilizzare l'estensione SharePoint Framework [query](/sharepoint/dev/spfx/building-search-extensions) per modificare la query prima che venga inviata al motore di ricerca.

## <a name="additional-resources"></a>Risorse aggiuntive

Per ulteriori informazioni sulla pagina dei risultati personalizzati, vedere la sessione di personalizzazione e sviluppo della ricerca di [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)

Per i progetti open source, introduzione alle API Microsoft Search e altri esempi di personalizzazione ed estendibilità, visitare Microsoft Search [su GitHub](https://github.com/microsoft-search).