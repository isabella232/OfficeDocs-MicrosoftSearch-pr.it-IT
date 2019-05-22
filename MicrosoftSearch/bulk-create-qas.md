---
title: Creare in blocco domande e risposte
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
description: Rispondere rapidamente alle domande frequenti con gli strumenti di importazione nel portale di amministrazione di Microsoft Search
ms.openlocfilehash: f535cb7ae843def536976cb1f05c8601de592cbb
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968305"
---
# <a name="bulk-create-qas"></a>Creare in blocco domande e risposte

> [!IMPORTANT]
> Le impostazioni di Microsoft Search in Bing sono ora disponibili nell'interfaccia di amministrazione di Microsoft 365. Per iniziare, [assegnare amministratori della ricerca](https://docs.microsoft.com/it-IT/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) nell'interfaccia di amministrazione.
    
Scaricare e usare il modello CSV per creare o modificare in blocco domande e risposte. È anche un modo semplice per salvare in blocco bozze di domande e risposte che richiedono ulteriori modifiche o aggiornamenti. Se è necessario modificare in blocco domande e risposte esistenti, esportarle dal portale di amministrazione, apportare le modifiche necessarie e quindi importarle.
  
1. Nell'angolo superiore destro della sezione Domande e risposte, fare clic su **Importa**.
    
2. Fare clic su **Scarica modello domande e risposte (CSV)**.
    
3. Salvare e aprire il file CSV
    
4. Aggiungere contenuto e impostazioni delle domande e risposte e salvare il file.

    Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione
    
5. Nell'angolo superiore destro della sezione Domande e risposte, fare clic su **Importa**.
    
6. Nel riquadro Importa domande e risposte fare clic su **Sfoglia **e passare al file CSV da importare. 
    
7. Fare clic su **Importa**.

# <a name="prevent-import-errors"></a>Evitare gli errori di importazione      
Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore. A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere. Apportare le modifiche necessarie e ritentare l'importazione del file.

> [!NOTE]
> Fino a quando non sono stati risolti tutti gli errori, non è possibile creare o modificare le domande e risposte. 

Per evitare errori, verificare che il file di importazione sia formattato correttamente, ossia che:
- Includa la riga di intestazione presente nel modello di importazione
- Includa tutte le colonne presenti nel modello di importazione
- L'ordine delle colonne equivalga a quello del modello di importazione
- Queste colonne possono essere vuote: ID, Ultima modifica e Autore ultima modifica
- La colonna Stato non può essere vuota, perché si tratta di informazioni obbligatorie  
In base al campo Stato, le domande e risposte saranno salvate come bozza, suggerite o pianificate, oppure saranno pubblicate automaticamente.

Se si include l'Id di una domanda e risposta esistente, verrà sostituito con le informazioni presenti nel file di importazione.

Per le organizzazioni con più tenant, è possibile esportare le domande e risposte da un tenant e importarle in un altro. È tuttavia necessario rimuovere i dati dalla colonna Id prima dell'importazione.

Per altre informazioni sui campi obbligatori e consigliati, vedere [Creare domande e risposte](create-qas.md).

  

