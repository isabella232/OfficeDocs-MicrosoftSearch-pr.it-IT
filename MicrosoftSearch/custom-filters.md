---
title: Gestione di filtri personalizzati
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
description: Gestione di filtri personalizzati
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927383"
---
# <a name="create-custom-filters"></a>Creare filtri personalizzati

È possibile creare filtri per personalizzare l'esperienza di ricerca che gli utenti visualizzano quando eseguono la ricerca in Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com)e Microsoft Search in [Bing](https://bing.com). I filtri consentono agli utenti di affinare rapidamente il set di risultati della query di ricerca.

Un filtro personalizzato può essere creato all'interno di un verticale in base a una proprietà di connessione. Ad esempio, è possibile creare un filtro **pubblicato su** per la connessione ServiceNow all'interno di un verticale personalizzato.

## <a name="things-to-consider"></a>Osservazioni

1. Per la creazione di un filtro personalizzato sull'origine di contenuto della connessione, vengono fornite alcune funzionalità aggiuntive:
- È inoltre possibile creare un filtro su un alias per le proprietà dell'origine del connettore
- Nel caso in cui la verticale disponga di più connessioni, è possibile creare un filtro comune tra queste connessioni. A tale scopo, è possibile creare il filtro su un alias comune che consente di alias le proprietà di origine tra diverse connessioni. Ad esempio, è possibile creare un filtro **autore** in una ServiceNow & una connessione JIRA creando alias come indicato di seguito:

| Connessione | Proprietà | Alias |
| --- | --- | --- |
| Servizio ora | Proprietario | Author |
| JIRA | Publisher | Author |

2. I filtri sono presenti nell'ambito della verticale. Quindi  
- Se un filtro viene creato in un verticale a livello organizzativo, il filtro verrebbe visualizzato solo a livello di organizzazione.
- Se un filtro viene creato in un verticale a livello di sito, il filtro verrebbe visualizzato solo a livello di sito.

## <a name="steps-to-create-custom-filter"></a>Procedura per la creazione di un filtro personalizzato

### <a name="create-filter-in-organizational-level-vertical"></a>Creare un filtro in verticale a livello organizzativo:

Per creare un filtro in Microsoft Search, attenersi alla seguente procedura:

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina [verticali](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) .
2. Creare/modificare la verticale in cui si desidera creare il filtro
3. Passare al passaggio ' filters ' nella procedura guidata
4. Fare clic su' Aggiungi filtro ' e iniziare dopo l'aggiunta dei filtri, è possibile rivedere e salvare la verticale.

## <a name="known-limitations"></a>Limitazioni note

1. È attualmente possibile creare filtri solo sulla stringa & proprietà gestite tipo di data.
2. Non è possibile creare filtri gerarchici

## <a name="resources"></a>Risorse

[Personalizzare la pagina dei risultati di ricerca](customize-search-page.md)