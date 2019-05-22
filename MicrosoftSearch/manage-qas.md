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
description: Trovare e aggiornare le risposte singolarmente oppure usare gli strumenti di Microsoft Search disponibili per modificarle tutte contemporaneamente
ms.openlocfilehash: ee239aa73d4e650289f39d33c63c3e2df4f100cc
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968468"
---
# <a name="manage-qas"></a>Gestire le domande e risposte

> [!IMPORTANT]
> Le impostazioni di Microsoft Search in Bing sono ora disponibili nell'interfaccia di amministrazione di Microsoft 365. Per iniziare, [assegnare amministratori della ricerca](https://docs.microsoft.com/it-IT/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) nell'interfaccia di amministrazione.
    
Nel corso del tempo, potrebbe essere necessario aggiornare lo stato e il contenuto di domande e risposte per fare in modo che rimangano pertinenti.
  
## <a name="filter-qas"></a>Filtrare domande e risposte

Usare l'opzione del filtro nell'angolo superiore destro della pagina delle domande e risposte per trovarle in base alla data e all'autore delle modifiche. Ad esempio, impostare il dispositivo di scorrimento della data su 30 giorni e selezionare un amministratore o un editor per visualizzare l'elenco di domande e risposte che ha creato o modificato in quell'intervallo di tempo.
  
## <a name="change-qa-content-or-settings"></a>Modificare le impostazioni o il contenuto delle domande e risposte

1. Passare al portale di amministrazione di Microsoft Search
    
2. Nel riquadro di spostamento fare clic su **Domande e risposte**
    
3. Per trovare domande e risposte specifiche, cercare, filtrare o selezionare lo stato delle domande e risposte per limitare i risultati.
    
4. Per modificare o aggiornare domande e risposte specifiche, fare clic sul titolo.
    
5. Modificare o aggiornare i contenuti o le impostazioni e vederne in anteprima gli effetti.
    
6. Fare clic su **Salva**.
    
## <a name="bulk-export-and-edit-qas"></a>Esportare in blocco e modificare domande e risposte

Non modificare mai i dati in questi campi:
  
- ID
    
- Ultima modifica
    
- Autore ultima modifica
    
L'ID è un identificatore univoco per ogni domanda e risposta e non può essere modificato. I campi Ultima modifica e Autore ultima modifica vanno usati solo per ordinare e trovare domande e risposte.
  
1. Se si vuole esportare un subset di domande e risposte, usare il filtro
    
2. Nell'angolo superiore destro della pagina delle domande e risposte, fare clic su **Esporta**.
    
3. Salvare o aprire il file CSV.
    
4. Modificare i dati in questi campi:
    
   - Domanda
    
   - URL
      
   - Parole chiave
    
   - Stato
    
   - Descrizione della risposta
    
   - Parole chiave riservate
    
   - Data di inizio
    
   - Data di fine
    
   - Paese/area geografica
    
   - Gruppi
    
   - Dispositivo e sistemi operativi
    
   - Varianti mirate
    
5. Salvare il file CSV

    Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione
    
6. Nell'angolo superiore destro della pagina Domande e risposte fare clic su **Importa**
    
7. Nel riquadro Importa domande e risposte fare clic su **Sfoglia** e selezionare il file CSV modificato 
    
8. Fare clic su **Importa**
    
Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore. A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere. Apportare le modifiche necessarie e ritentare l'importazione del file.
  
> [!NOTE]
> Fino a quando non sono stati risolti tutti gli errori, non è possibile creare o modificare le domande e risposte. 
  
Non tutti i campi sono obbligatori e i campi obbligatori variano in base allo stato delle domande e risposte. In base al campo Stato, le domande e risposte saranno salvate come bozza, suggerite o pianificate, oppure saranno pubblicate automaticamente. Per altre informazioni sui campi obbligatori e consigliati, vedere [Creare domande e risposte](create-qas.md).

  

