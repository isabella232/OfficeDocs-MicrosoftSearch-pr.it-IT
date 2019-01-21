---
title: Gestire Q&As
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
description: Trovare e aggiornare singolarmente risposte o utilizzare gli strumenti di Microsoft Search disponibili per la modifica con un'unica operazione
ms.openlocfilehash: c0f6b42aa1e0ad8c4736d37ec4dcc8cff6025dbc
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378905"
---
# <a name="manage-qas"></a>Gestire Q&As

Nel corso del tempo, potrebbe essere necessario aggiornare lo stato e del contenuto per mantenere pertinenti un Q&A.
  
## <a name="filter-qas"></a>Filtro Q&As

Utilizzare l'opzione di filtro nell'angolo superiore destro della pagina Q&As per trovare Q&As per data e che ha modificato. Ad esempio, impostare il dispositivo di scorrimento data 30 giorni e selezionare un amministratore o un editor per visualizzare l'elenco di Q&As è stato creato o modificato in quel momento.
  
## <a name="change-qa-content-or-settings"></a>Modificare le impostazioni o Q&A contenuto

1. Accedere al portale di amministrazione di ricerca Microsoft
    
2. Nel riquadro di spostamento fare clic su **Q&As**
    
3. Per trovare un Q&A, di ricerca e filtro oppure fare clic su uno stato Q&A per restringere i risultati
    
4. Per modificare o aggiornare un Q&A, fare clic sul titolo
    
5. Apportare le modifiche o aggiornamenti del contenuto o le impostazioni e anteprima come verranno visualizzate
    
6. Fare clic su **Salva**.
    
## <a name="bulk-export-and-edit-qas"></a>Esportazione in blocco e la modifica Q&As

Non modificare i dati in tali campi:
  
- Id
    
- Ultima modifica
    
- Autore ultima modificata
    
ID è un identificatore univoco per ogni Q&A e non deve mai essere modificati. I campi Data ultima modifica e Autore ultima modifica devono essere utilizzati solo di ordinare e cercare Q&As.
  
1. Se si desidera esportare un sottoinsieme del Q&As, filtrarli
    
2. Nell'angolo superiore destro della pagina Q&As, fare clic su **Esporta**
    
3. Salva o si apre il file CSV
    
4. Modificare i dati in uno di questi campi:
    
   - Domanda
    
   - URL
      
   - Parole chiave
    
   - Stato
    
   - Descrizione di risposta
    
   - Parole chiave riservate
    
   - Data inizio
    
   - Data di fine
    
   - Paese
    
   - Gruppi
    
   - Dispositivo&amp;sistema operativo
    
   - Varianti di destinazione
    
5. Salvare il file CSV
    
6. Nell'angolo superiore destro della pagina Q&As fare clic su **Importa**
    
7. Nel riquadro Q&As importazione fare clic su **Sfoglia** e selezionare il file CSV modificate 
    
8. Fare clic su **Importa**
    
Verrà visualizzato un errore se i dati necessari sono mancante o non valido. A seconda dell'errore, un file di registro può essere generato con ulteriori informazioni sulle righe e colonne da correggere. Apportare eventuali modifiche necessarie e riprovare l'importazione del file.
  
> [!NOTE]
> Fino a quando non vengono risolti tutti gli errori, è Impossibile creare o modificare qualsiasi Q&As. 
  
Non tutti i campi obbligatori e campi obbligatori variano in base allo stato Q&A. In base al campo dello stato, Q&As verrà salvato come bozza suggerito, pianificate o verranno pubblicati automaticamente. Per ulteriori informazioni sui campi obbligatori e consigliati [creare Q&As](create-qas.md).

  

