---
title: Gestire le domande e risposte
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Trovare e aggiornare le risposte singolarmente o utilizzare gli strumenti di ricerca di Microsoft disponibili per modificarli contemporaneamente
ms.openlocfilehash: 47882deeb95133cfc19f4eec6417fc20fb7203de
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508818"
---
# <a name="manage-qas"></a>Gestire le domande e risposte

Nel tempo, potrebbe essere necessario aggiornare lo stato e il contenuto di Q&A's in modo da renderlo pertinente.
  
## <a name="filter-qas"></a>Filtro Q&As

Utilizzare l'opzione filtro nell'angolo in alto a destra della pagina Q&As per trovare Q&As per data e gli utenti che li hanno modificati. Ad esempio, impostare il dispositivo di scorrimento data su 30 giorni e selezionare un amministratore o un editor per visualizzare l'elenco di Q&As che sono stati creati o modificati in quel momento.
  
## <a name="change-qa-content-or-settings"></a>Modificare il contenuto o le impostazioni di Q&A

1. Passare al portale di amministrazione di Microsoft Search
    
2. Nel riquadro di spostamento fare clic su **Domande e risposte**
    
3. Per trovare un Q&A, ricercare, filtrare o fare clic su uno stato di Q&A per limitare i risultati
    
4. Per modificare o aggiornare un Q&A, fare clic sul titolo
    
5. Apportare le modifiche o gli aggiornamenti al contenuto o alle impostazioni e visualizzare in anteprima la modalità di visualizzazione
    
6. Fare clic su **Salva**.
    
## <a name="bulk-export-and-edit-qas"></a>Esportazione e modifica in blocco di Q&As

Non modificare mai i dati in questi campi:
  
- ID
    
- Ultima modifica
    
- Ultima modifica di
    
ID è un identificatore univoco per ogni Q&A e non deve mai essere modificato. Gli ultimi campi modificati e modificati per l'ultima volta devono essere utilizzati solo per ordinare e trovare Q&As.
  
1. Se si desidera esportare un sottoinsieme di Q&As, filtrarli
    
2. Nell'angolo in alto a destra della pagina Q&As fare clic su **Esporta**
    
3. Salvare o aprire il file. csv
    
4. Modificare i dati in uno di questi campi:
    
   - Domanda
    
   - URL
      
   - Parole chiave
    
   - Stato
    
   - Descrizione della risposta
    
   - Parole chiave riservate
    
   - Data inizio
    
   - Data di fine
    
   - Paese/area geoGrafica
    
   - Gruppi
    
   - Sistema&amp;operativo del dispositivo
    
   - Varianti mirate
    
5. Salvare il file. csv

    Il file. csv deve essere salvato come file UTF-8 CSV, altri tipi di file e o codifiche possono causare errori di importazione
    
6. Nell'angolo in alto a destra della pagina Q&As fare clic su **Importa** .
    
7. Nel riquadro Importa Q&As, fare clic su **Sfoglia** e selezionare il file CSV modificato 
    
8. Fare clic su **Importa**
    
Se i dati richiesti sono mancanti o non validi, verrà visualizzato un messaggio di errore. A seconda dell'errore, è possibile che venga generato un file di registro con ulteriori informazioni sulle righe e le colonne che devono essere corrette. Apportare le modifiche necessarie e provare a importare di nuovo il file.
  
> [!NOTE]
> Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare Q&As. 
  
Non tutti i campi sono obbligatori e i campi obbligatori variano a seconda dello stato Q&A. In base al campo dello stato, Q&As verrà salvato come bozza, suggerito, pianificato o verrà pubblicato automaticamente. Per ulteriori informazioni sui campi richiesti e consigliati, vedere [create Q&As](create-qas.md).

  

