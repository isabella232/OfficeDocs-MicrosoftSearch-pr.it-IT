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
description: Trovare segnalibri da aggiornare e modi per modificare in blocco i risultati di segnalibri per Microsoft Search
ms.openlocfilehash: d5cebbfd5779bc8a6aa25cdbcdedb6e9b18f242e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968484"
---
# <a name="manage-bookmarks"></a>Gestire i segnalibri

> [!IMPORTANT]
> Le impostazioni di Microsoft Search in Bing sono ora disponibili nell'interfaccia di amministrazione di Microsoft 365. Per iniziare, [assegnare amministratori della ricerca](https://docs.microsoft.com/it-IT/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) nell'interfaccia di amministrazione.
    
Nel corso del tempo, potrebbe essere necessario aggiornare lo stato e il contenuto di un segnalibro per fare in modo che rimanga pertinente. 
  
## <a name="filter-bookmarks"></a>Filtrare i segnalibri

Usare l'opzione del filtro nell'angolo superiore destro della pagina dei segnalibri per trovarli in base alla data e all'autore delle modifiche. Ad esempio, impostare il dispositivo di scorrimento della data su 30 giorni e selezionare un amministratore o un editor per visualizzare l'elenco di segnalibri che ha creato o modificato in quell'intervallo di tempo.
  
## <a name="change-bookmark-content-or-settings"></a>Modificare le impostazioni o il contenuto dei segnalibri

1. Passare al portale di amministrazione di Microsoft Search
    
2. Nel riquadro di spostamento fare clic su **Segnalibri**
    
3. Per trovare un segnalibro, cercare, filtrare o selezionare lo stato dei segnalibri per limitare i risultati
    
4. Per modificare o aggiornare un segnalibro, fare clic sul titolo
    
5. Modificare o aggiornare i contenuti o le impostazioni e vederne in anteprima gli effetti. 
    
6. Fare clic su **Salva**.
    
## <a name="bulk-export-and-edit-bookmarks"></a>Esportare in blocco e modificare segnalibri

Non modificare mai i dati in questi campi:
  
- ID
    
- Ultima modifica
    
- Autore ultima modifica
    
L'ID è un identificatore univoco per ogni segnalibro e non può essere modificato. I campi Ultima modifica e Autore ultima modifica devono essere usati solo per ordinare e trovare segnalibri.
  
1. Se si desidera esportare un sottoinsieme di segnalibri, usare il filtro.
    
2. Nell'angolo superiore destro della pagina dei segnalibri, fare clic su **Esporta**.
    
3. Salvare o aprire il file CSV.
    
4. Modificare i dati in questi campi:
   - Titolo
    
   - URL
    
   - Parole chiave
    
   - Stato
    
   - Descrizione
    
   - Parole chiave riservate
    
   - Data di inizio
    
   - Data di fine
    
   - Paese/area geografica
    
   - Gruppi
    
   - Dispositivo e sistemi operativi
    
   - Varianti mirate
    
5. Salvare il file CSV

    Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione
    
6. Nell'angolo superiore destro della pagina Segnalibri fare clic su **Importa**
    
7. Nel riquadro Importa segnalibri fare clic su **Sfoglia** e selezionare il file CSV modificato 
    
8. Fare clic su **Importa**