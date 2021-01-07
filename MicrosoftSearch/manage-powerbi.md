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
description: Gestire il modo in cui i report e i dati Power BI vengono visualizzati nei risultati della ricerca
ms.openlocfilehash: e78b8b5d22f7a91d80832fb4f5b536afc277fb6c
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773046"
---
# <a name="manage-power-bi-answers"></a>Gestire le risposte di Power BI

Per semplificare l'individuazione dei dati e delle analisi necessarie per gli utenti, Microsoft Search ha aggiunto il supporto per i report e i dashboard di Power BI. Di seguito sono illustrati alcuni dei vantaggi di Power BI Search:

* **Facile da usare:** Questa esperienza di ricerca fuori campo consente agli utenti di trovare facilmente e rapidamente i dashboard Power BI e i report all'interno dell'organizzazione.
* **Contenuto più completo:** Per rendere più utili i risultati della ricerca Power BI, includono informazioni chiave quali il tipo di contenuto, ovvero il dashboard o il report, e il team o la persona che la possiede.
* **Protezione dei dati integrata:** I risultati di Power BI verranno visualizzati solo per gli utenti che hanno accesso al dashboard o al report.
* **Esperienza di ricerca unificata:** Per mantenere un'esperienza coesa, i risultati di Power BI sono coerenti tra tutti i punti di accesso alla ricerca. Ogni volta che si cerca, si otterranno gli stessi risultati con lo stesso aspetto.

## <a name="what-users-experience"></a>Esperienza degli utenti

Gli utenti di Microsoft Search possono trovare risultati di Power BI eseguendo una ricerca dalla casella di ricerca di Windows, SharePoint, Office 365 e Bing. Gli utenti possono cercare report e dashboard con query simili alle seguenti:

* Informazioni su Power BI `<topic>`
* Power BI per `<topic>`
* `<topic>` Dashboard Power BI o dashboard Power BI `<topic>`
* `<topic>` Report di Power BI o rapporto Power BI `<topic>`
* `<topic>` Metriche Power BI o metriche Power BI `<topic>`
* `<topic>` Scorecard Power BI o Power BI scorecard `<topic>`

Sostituisci `<topic>` negli esempi precedenti con le informazioni che stai cercando, come Sales, Usage, Capacity, 2021, Q1 e altro, per visualizzare i risultati rilevanti di Power bi.

:::image type="content" source="media/powerbi-answers/powerbi-serp.png" alt-text="Schermata di una SERP con risposte Power BI e verticale" border="true":::

## <a name="turn-power-bi-search-on-or-off"></a>Attivazione o disattivazione della ricerca di Power BI

I risultati di Power BI sono abilitati per l'organizzazione per impostazione predefinita. L'amministratore di Power BI può disabilitarlo in qualsiasi momento. Nel portale di amministrazione di Power BI, passare a impostazioni tenant e disabilitare l'impostazione **Usa ricerca globale per Power bi** . Per ulteriori informazioni, vedere [Administering Power bi nel portale di amministrazione](https://docs.microsoft.com/power-bi/admin/service-admin-portal#use-global-search-for-power-bi-preview).

:::image type="content" source="media/powerbi-answers/powerbi-admin.png" alt-text="Schermata dell'impostazione per abilitare o disabilitare le risposte di Power BI" border="true":::

## <a name="frequently-asked-questions"></a>Domande frequenti

**D: Power BI Search è abilitato per impostazione predefinita?**

**A:** Sì. Power BI Search è abilitato per impostazione predefinita per Microsoft Search. Non è necessaria alcuna configurazione per la prima volta dall'amministratore del tenant per questa funzionalità.

**D: è possibile abilitare o disabilitare la ricerca di Power BI per gruppi o utenti specifici?**

**A:** Attualmente, può essere abilitata o disabilitata solo per l'intera organizzazione.

**D: se Power BI Search è disabilitato, è nascosta la pagina dei risultati della ricerca di Power BI?**

**A:** No. La pagina dei risultati della ricerca di Power BI verrà visualizzata con un messaggio che informa gli utenti che non è attualmente disponibile per la propria organizzazione.

**D: verrà visualizzata la pagina dei risultati di ricerca di Power BI se non si dispone di una licenza Power BI?**

**A:** No. Se un utente di ricerca non dispone di una licenza di Power BI, la pagina dei risultati di ricerca di Power BI non viene visualizzata in Microsoft Search Results.

**D: verranno visualizzati i risultati della ricerca Power BI a cui non è possibile accedere?**

**A:** No. Microsoft Search restituirà solo i risultati di Power BI a cui è possibile accedere.

**D: è possibile personalizzare i risultati della ricerca di Power BI (ad esempio, il tipo di rapporto o il proprietario del report)?**

**A:** Attualmente non è supportata la personalizzazione dei campi inclusi nei risultati della ricerca di Power BI.
