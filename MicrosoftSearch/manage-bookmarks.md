---
title: Gestire i segnalibri
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/08/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Individuare i segnalibri che devono essere aggiornati e modalità di modifica in blocco dei risultati dei segnalibri per Microsoft Search
ms.openlocfilehash: f87176c645e127e20edd9e70a74efe05dd381236
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508610"
---
# <a name="manage-bookmarks"></a>Gestire i segnalibri

Nel corso del tempo, potrebbe essere necessario aggiornare lo stato e il contenuto di un segnalibro per renderlo pertinente. 
  
## <a name="filter-bookmarks"></a>Segnalibri del filtro

Utilizzare l'opzione filtro nell'angolo in alto a destra della pagina segnalibri per individuare i segnalibri per data e gli utenti che li hanno modificati. Ad esempio, impostare il dispositivo di scorrimento data su 30 giorni e selezionare un amministratore o un editor per visualizzare l'elenco dei segnalibri creati o modificati in quel momento.
  
## <a name="change-bookmark-content-or-settings"></a>Modificare il contenuto o le impostazioni del segnalibro

1. Passare al portale di amministrazione di Microsoft Search
    
2. Nel riquadro di spostamento fare clic su **Segnalibri**
    
3. Per trovare un segnalibro, ricercare, filtrare o fare clic su uno stato del segnalibro per limitare i risultati
    
4. Per modificare o aggiornare un segnalibro, fare clic sul titolo
    
5. Apportare le modifiche o gli aggiornamenti al contenuto o alle impostazioni e visualizzare in anteprima la modalità di visualizzazione 
    
6. Fare clic su **Salva**.
    
## <a name="bulk-export-and-edit-bookmarks"></a>Esportazione e modifica in blocco di segnalibri

Non modificare mai i dati in questi campi:
  
- ID
    
- Ultima modifica
    
- Ultima modifica di
    
ID è un identificatore univoco per ogni segnalibro e non deve mai essere modificato. Gli ultimi campi modificati e modificati in base all'Ultima modifica devono essere utilizzati solo per ordinare e trovare i segnalibri.
  
1. Se si desidera esportare un sottoinsieme di segnalibri, filtrarli
    
2. Nell'angolo in alto a destra della pagina dei segnalibri fare clic su **Esporta** .
    
3. Salvare o aprire il file. csv
    
4. Modificare i dati in uno di questi campi:
   - Titolo
    
   - URL
    
   - Parole chiave
    
   - Stato
    
   - Descrizione
    
   - Parole chiave riservate
    
   - Data inizio
    
   - Data di fine
    
   - Paese/area geoGrafica
    
   - Gruppi
    
   - Sistema&amp;operativo del dispositivo
    
   - Varianti mirate
    
5. Salvare il file. csv

    Il file. csv deve essere salvato come file UTF-8 CSV, altri tipi di file e o codifiche possono causare errori di importazione
    
6. Nell'angolo in alto a destra della pagina segnalibri fare clic su **Importa** .
    
7. Nel riquadro Importa segnalibri fare clic su **Sfoglia** e selezionare il file CSV modificato 
    
8. Fare clic su **Importa**