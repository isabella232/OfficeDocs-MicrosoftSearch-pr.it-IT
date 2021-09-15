---
title: Gestire i filtri
ms.author: v-revathib
author: revathi-b
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Gestire i filtri per l'utilizzo nel SERP
ms.openlocfilehash: c614d4b60c746f2e18fdb3352281891ea5134373
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375955"
---
# <a name="manage-filters"></a>Gestire i filtri

I filtri consentono agli utenti di perfezionare i risultati delle query e di visualizzare i risultati perfezionati. È possibile personalizzare i filtri disponibili per gli utenti nell'Microsoft Search utenti.

Nella pagina di ricerca sono disponibili due tipi di filtri.

- Filtri predefiniti
- Filtri personalizzati

> [!NOTE]
> I filtri personalizzati sono attualmente in anteprima per amministratori e utenti finali in Targeted Release. Per ulteriori informazioni sull'anteprima, vedere [Funzionalità di anteprima dei connettori.](connectors-overview.md#what-are-the-preview-features)

## <a name="out-of-the-box-filters"></a>Filtri predefiniti

I filtri predefiniti sono disponibili per impostazione predefinita nei verticali di ricerca, ad esempio Tutti, File, Immagini e Notizie. Nelle verticali "All" e "File" è possibile visualizzare il filtro "Tipo di file" per la proprietà FileType e il filtro "Last Modified" sulla proprietà LastModifiedTime. Questi filtri sono disponibili in SharePoint Home, Office.com, SharePoint Sites e Work vertical in Bing.

## <a name="custom-filters"></a>Filtri personalizzati

È possibile aggiungere filtri ai verticali di ricerca personalizzati a livello di organizzazione e sito. Le proprietà gestite per affinamento ricerca vengono utilizzate per configurare i filtri nella procedura guidata di amministrazione verticale.  È quindi possibile creare un filtro personalizzato all'interno di un verticale in base a una proprietà di connessione. Ad esempio, è possibile creare un filtro Published On per una connessione ServiceNow all'interno di un verticale.

I filtri configurati per i verticali nell'ambito dell'organizzazione saranno disponibili nell'ambito dell'organizzazione. I filtri possono essere configurati anche nell'ambito del sito.  

## <a name="create-organization-level-filters"></a>Creare filtri a livello di organizzazione

1. In  [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/), passare a  [**Verticali**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Selezionare il verticale preferito in cui si desidera creare un filtro e fare clic su **Modifica.**  
3. Passare al passaggio Filtri della procedura guidata del verticale.
4. Fare **clic su Aggiungi filtro** per configurare i filtri per le proprietà gestite per affinamento ricerca.
5. Dopo aver aggiunto i filtri, è possibile esaminare e salvare il verticale.

## <a name="create-sharepoint-site-level-filters"></a>Creare SharePoint a livello di sito

1. In [SharePoint di amministrazione](https://sharepoint.com/)passare a Impostazioni.
2. Cercare la sezione Microsoft Search e quindi selezionare Configura Microsoft Search **per questa raccolta siti.**
3. Nel riquadro di spostamento passare a Esperienza personalizzata e quindi selezionare  **Verticali.**
4. Selezionare il verticale preferito per creare il filtro e fare clic su **Modifica.**
5. Passare al passaggio Filtri della procedura guidata del verticale.
6. Fare **clic su Aggiungi filtro** per configurare i filtri per le proprietà gestite per affinamento ricerca.
7. Dopo aver aggiunto i filtri, è possibile esaminare e salvare il verticale.

## <a name="filter-across-multiple-properties"></a>Filtrare in più proprietà

È possibile creare verticali con una o più origini di contenuto. Quando un verticale è configurato con più origini di contenuto, l'elenco delle proprietà del criterio di affinamento mostra a quale origine di contenuto appartiene ogni proprietà per affinamento ricerca. Le proprietà gestite comuni verranno unite in base al nome (o all'alias) e al tipo di dati. I filtri possono essere configurati anche su queste proprietà comuni. A tale scopo, viene creato il filtro su un alias comune che aliasa le proprietà di origine tra le diverse connessioni. Ad esempio, è possibile creare un **filtro Autore** tra le connessioni ServiceNow e Jira creando alias come segue:

 | Connessione | Proprietà | Alias |
 | --- | --- | --- |
 | Service Now | Proprietario | Author |
 | Jira | Publisher | Author |

## <a name="important-details"></a>Dettagli importanti

- I filtri possono essere aggiunti solo a verticali personalizzati. Non è possibile aggiungere nuovi filtri a verticali predefiniti come Tutti, File, Persone, Siti, Notizie.
- I filtri sono configurabili per le proprietà Text e DateTime.
- Si è limitati a un totale di 50 filtri.
- Non è possibile modificare l'ordine dei filtri predefiniti.
- I filtri non sono supportati per OneDrive contenuto. I valori di filtro corrispondenti ai risultati della OneDrive non verranno visualizzati nei filtri.
- I valori di filtro personalizzati mostreranno le opzioni SharePoint contenuto e non dal contenuto di One Drive.Ad esempio, se si crea un filtro personalizzato per il contenuto "Autore" e il contenuto di SharePoint contiene solo i risultati di un autore, "Amy" e il contenuto di OneDrive contiene solo i risultati di un autore denominato "John", il filtro personalizzato Autore mostrerà "Amy" come unica opzione.
- Un valore di filtro visualizzato per SharePoint contenuto verrà applicato OneDrive contenuto quando usato.
