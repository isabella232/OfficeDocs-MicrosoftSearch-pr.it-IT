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
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790335"
---
# <a name="manage-custom-filters"></a>Gestire filtri personalizzati

È possibile utilizzare i filtri per personalizzare l'esperienza di ricerca di Microsoft. I filtri consentono agli utenti di affinare rapidamente il set di risultati della query di ricerca.

Un filtro personalizzato può essere creato all'interno di un verticale in base a una proprietà di connessione. Ad esempio, è possibile creare un filtro **pubblicato su** per la connessione ServiceNow all'interno di un verticale.

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>Creare un filtro in un livello di organizzazione verticale

Per creare un filtro in Microsoft Search, attenersi alla seguente procedura:

1. Nell'interfaccia di amministrazione di Microsoft 365, andare a [verticali](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
1. Creare/modificare la verticale in cui si desidera creare il filtro
1. Passare al passaggio ' filters ' nella procedura guidata
1. Fare clic su' Aggiungi filtro ' e iniziare
1. Dopo aver aggiunto i filtri, è possibile rivedere e salvare il verticale.

## <a name="things-to-consider"></a>Osservazioni

1. Sono disponibili ulteriori funzionalità di filtro per il contenuto della connessione.

    - È inoltre possibile creare un filtro su un alias per le proprietà dell'origine del connettore
    - Se un verticale dispone di più connessioni, è possibile creare un filtro comune tra queste connessioni. A tale scopo, è possibile creare il filtro su un alias comune che consente di alias le proprietà di origine in tutte le diverse connessioni. Ad esempio, è possibile creare un filtro **autore** tra ServiceNow e una connessione JIRA creando alias come indicato di seguito:

    | Connessione | Proprietà | Alias |
    | --- | --- | --- |
    | Servizio ora | Proprietario | Author |
    | JIRA | Publisher | Author |

1. I filtri esistono nell'ambito di un verticale.

    - Se un filtro viene creato in un verticale a livello organizzativo, il filtro verrebbe visualizzato solo a livello di organizzazione.
    - Se un filtro viene creato in un verticale a livello di sito, il filtro verrebbe visualizzato solo a livello di sito.

## <a name="known-limitations"></a>Limitazioni note

1. È attualmente possibile creare filtri solo sulla stringa & proprietà gestite tipo di data.
1. Non è possibile creare filtri gerarchici.

## <a name="resources"></a>Risorse

[Gestire le tipologie di verticali e i tipi di risultati](customize-search-page.md)
