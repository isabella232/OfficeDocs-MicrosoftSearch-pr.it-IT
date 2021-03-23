---
title: Gestire le risposte di Power BI
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Gestire la modalità di visualizzazione dei report e dei dati di Power BI nei risultati della ricerca
ms.openlocfilehash: 3d67f79cce2392f949541690879ffb9202d79060
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031441"
---
# <a name="manage-power-bi-answers"></a>Gestire le risposte di Power BI

Per facilitare agli utenti l'individuazione dei dati e dell'analisi necessari per prendere decisioni informate, Microsoft Search ha aggiunto il supporto per i dashboard e i report di Power BI. Ecco alcuni dei vantaggi della ricerca di Power BI:

* **Facile da usare:** Questa esperienza di ricerca avanzata consente agli utenti di trovare facilmente e rapidamente dashboard e report di Power BI all'interno dell'organizzazione.
* **Contenuto più ricco:** Per rendere più utili i risultati di ricerca di Power BI, includono informazioni chiave come il tipo di contenuto, ovvero dashboard o report, e il team o la persona a cui è proprietario.
* **Protezione dei dati incorporata:** I risultati di Power BI verranno visualizzati solo per gli utenti che hanno accesso al dashboard o al report.
* **Esperienza di ricerca unificata:** Per mantenere un'esperienza coerente, i risultati di Power BI sono coerenti in tutti i punti di ingresso di ricerca. Ovunque si eserciti la ricerca, si otterrà gli stessi risultati con lo stesso aspetto.

## <a name="what-users-experience"></a>Esperienza degli utenti

Gli utenti di Microsoft Search possono trovare i risultati di Power BI eseguendo una ricerca dalla casella di ricerca di Windows, SharePoint, Office 365 e Bing. Gli utenti possono cercare report e dashboard con query come queste:

* Informazioni su Power BI `<topic>`
* Power BI per `<topic>`
* `<topic>` Dashboard di Power BI o dashboard di Power BI `<topic>`
* `<topic>` Report di Power BI o report di Power BI `<topic>`
* `<topic>` Metriche di Power BI o metriche di Power BI `<topic>`
* `<topic>` Scorecard di Power BI o scorecard di Power BI `<topic>`

Sostituire negli esempi precedenti con le informazioni che si stanno cercando, ad esempio `<topic>` vendite, utilizzo, capacità, 2021, Q1 e altro ancora, per visualizzare i risultati pertinenti di Power BI.

:::image type="content" source="media/powerbi-answers/powerbi-serp.png" alt-text="Screenshot of a SERP with Power BI answers and vertical" border="true":::

## <a name="turn-power-bi-search-on-or-off"></a>Attivare o disattivare la ricerca di Power BI

I risultati di Power BI sono abilitati per l'organizzazione per impostazione predefinita. L'amministratore di Power BI può disabilitarli in qualsiasi momento. Nel portale di amministrazione di Power BI passare a Impostazioni tenant e disabilitare **l'impostazione Usa ricerca globale per Power BI.** Per ulteriori informazioni, vedere [Administering Power BI in the admin portal.](/power-bi/admin/service-admin-portal#use-global-search-for-power-bi-preview)

:::image type="content" source="media/powerbi-answers/powerbi-admin.png" alt-text="Screenshot dell'impostazione per attivare o disattivare le risposte di Power BI" border="true":::

## <a name="frequently-asked-questions"></a>Domande frequenti

**D: La ricerca di Power BI è abilitata per impostazione predefinita?**

**A:** Sì. La ricerca di Power BI è abilitata per impostazione predefinita per Microsoft Search. L'amministratore tenant non richiede alcuna configurazione per la prima volta per questa funzionalità.

**D: La ricerca di Power BI può essere abilitata o disabilitata per gruppi o utenti specifici?**

**A:** Attualmente, può essere abilitato o disabilitato solo per l'intera organizzazione.

**D: Se la ricerca di Power BI è disabilitata, la pagina dei risultati della ricerca di Power BI è nascosta?**

**A:** No. Verrà visualizzata la pagina dei risultati della ricerca di Power BI con un messaggio che informa gli utenti che non è attualmente disponibile per l'organizzazione.

**D: Se non si dispone di una licenza di Power BI, verrà visualizzata la pagina dei risultati della ricerca di Power BI?**

**A:** No. Se un utente di ricerca non dispone di una licenza di Power BI, la pagina dei risultati della ricerca di Power BI non verrà visualizzata nei risultati di Microsoft Search.

**D: Verranno visualizzati i risultati della ricerca di Power BI a cui non è possibile accedere?**

**A:** No. Microsoft Search restituirà solo i risultati di Power BI a cui si ha accesso.

**D: È possibile personalizzare i risultati della ricerca di Power BI (ad esempio, il tipo di report o il proprietario del report)?**

**A:** Attualmente non è possibile personalizzare i campi inclusi nei risultati della ricerca di Power BI.