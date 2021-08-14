---
title: Gestire filtri personalizzati
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gestire filtri personalizzati
ms.openlocfilehash: 256cf9748aa3050aacf48c3562f6f84b4ba2e460
ms.sourcegitcommit: 5151bcd8fd929ef37239b7c229e2fa33b1e0e0b7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235928"
---
# <a name="manage-custom-filters"></a>Gestire filtri personalizzati

Puoi usare i filtri per personalizzare l'esperienza Microsoft Search personalizzata. I filtri consentono agli utenti di perfezionare rapidamente il set di risultati della query di ricerca.

È possibile creare un filtro personalizzato all'interno di un verticale in base a una proprietà di connessione. Ad esempio, è possibile creare un filtro **Published On** per la connessione ServiceNow all'interno di un verticale.

> [!NOTE]
> I filtri personalizzati sono attualmente in anteprima per amministratori e utenti finali in Targeted Release. Per ulteriori informazioni sull'anteprima, vedere [Funzionalità di anteprima dei connettori.](connectors-overview.md#what-are-the-preview-features)

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>Creare un filtro in un verticale a livello di organizzazione

Per creare un filtro in Microsoft Search, eseguire la procedura seguente:

1. Nella finestra interfaccia di amministrazione di Microsoft 365, andare a [Verticali](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
1. Creare/modificare il verticale in cui si desidera creare il filtro
1. Passare al passaggio "Filtri" della procedura guidata
1. Fai clic su "Aggiungi filtro" e inizia
1. Dopo aver aggiunto i filtri, è possibile esaminare e salvare il verticale.

## <a name="things-to-consider"></a>Osservazioni

1. Nel contenuto della connessione sono disponibili ulteriori funzionalità di filtro.

    - È inoltre possibile creare un filtro su un alias per le proprietà dell'origine del connettore
    - Se una verticale ha più connessioni, è possibile creare un filtro comune tra queste connessioni. A tale scopo, è possibile creare il filtro su un alias comune che aliasi le proprietà di origine tra le diverse connessioni. Ad esempio, è possibile creare un **filtro Autore** in un ServiceNow e in una connessione Jira creando alias come segue:

    | Connessione | Proprietà | Alias |
    | --- | --- | --- |
    | Service Now | Proprietario | Author |
    | Jira | Publisher | Author |

1. I filtri sono presenti nell'ambito di un verticale.

    - Se viene creato un filtro in un verticale a livello di organizzazione, il filtro sarà visibile solo a livello di organizzazione
    - Se viene creato un filtro in un verticale a livello di sito, il filtro sarà visibile solo a livello di sito.

## <a name="known-limitations"></a>Limitazioni note

1. È attualmente possibile creare filtri solo per le proprietà gestite & tipo di data.
1. Non è possibile creare filtri gerarchici.

## <a name="resources"></a>Risorse

[Gestire le tipologie di verticali e i tipi di risultati](customize-search-page.md)
