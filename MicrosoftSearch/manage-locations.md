---
title: Gestire le posizioni
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 11/08/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 8ab9aa00-cd74-405f-8410-9a1c3cfacdb9
description: Nel corso del tempo, potrebbe essere necessario aggiornare lo stato e il contenuto di una posizione per fare in modo che rimanga pertinente.
ms.openlocfilehash: 0e23cf3d3d3d05fe86cdc3e09ce808e54242d670
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968430"
---
# <a name="manage-locations"></a>Gestire le posizioni

> [!IMPORTANT]
> Le impostazioni di Microsoft Search in Bing sono ora disponibili nell'interfaccia di amministrazione di Microsoft 365. Per iniziare, [assegnare amministratori della ricerca](https://docs.microsoft.com/it-IT/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) nell'interfaccia di amministrazione.
    
Nel corso del tempo, potrebbe essere necessario aggiornare lo stato e il contenuto di una posizione per fare in modo che rimanga pertinente. 
  
## <a name="filter-locations"></a>Filtrare le posizioni

Usare l'opzione del filtro nell'angolo superiore destro della pagina Posizioni per trovarle in base alla data e all'autore delle modifiche. Ad esempio, impostare il dispositivo di scorrimento della data su 30 giorni e selezionare un amministratore o un editor per vedere l'elenco di posizioni che ha creato o modificato in quell'intervallo di tempo.
  
## <a name="change-location-content"></a>Modificare il contenuto della posizione

1. Passare al portale di amministrazione di Microsoft Search
    
2. Nel riquadro di spostamento fare clic su **Posizioni**
    
3. Per trovare una posizione, cercare, filtrare o selezionare lo stato delle posizioni per limitare i risultati.
    
4. Per cambiare o aggiornare una posizione, fare clic sul nome.
    
5. Modificare o aggiornare il contenuto e vederne in anteprima gli effetti. 
    
6. Fare clic su **Salva**
    
## <a name="bulk-export-and-edit-locations"></a>Esportare in blocco e modificare posizioni

Non modificare mai i dati in questi campi:
  
- ID
    
- Ultima modifica
    
- Autore ultima modifica
    
L'ID è un identificatore univoco per ogni posizione e non può essere modificato. I campi Ultima modifica e Autore ultima modifica devono essere usati solo per ordinare e trovare posizioni.
  
1. Se si vuole esportare un subset di posizioni, usare il filtro.
    
2. Nell'angolo superiore destro della pagina Posizioni fare clic su **Esporta**.
    
3. Salvare o aprire il file CSV
    
4. Modificare i dati in questi campi:
    
   - Nome
    
   - Riga 1 indirizzo
    
   - Riga 2 indirizzo
    
   - Città
    
   - Provincia indirizzo
    
   - CAP
    
   - Paese
    
   - Indirizzo completo
    
   - Latitudine
    
   - Longitudine
    
   - Parole chiave
    
   - Parole chiave riservate
    
   - Stato
    
5. Salvare il file CSV

    Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione
    
6. Nell'angolo superiore destro della pagina Posizioni fare clic su **Importa**
    
7. Nel riquadro Importa posizioni fare clic su **Sfoglia **e selezionare il file CSV modificato 
    
8. Fare clic su **Importa**

  

