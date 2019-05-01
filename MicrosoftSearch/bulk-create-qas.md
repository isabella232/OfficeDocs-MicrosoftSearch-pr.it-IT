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
description: Aggiungere rapidamente le risposte alle domande frequenti con gli strumenti di importazione nel portale di amministrazione di Microsoft Search
ms.openlocfilehash: 28fcf57c44f809e7f9b0c1b27042f4549067a0f8
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508674"
---
# <a name="bulk-create-qas"></a>Creare in blocco domande e risposte

Scaricare e utilizzare il modello. csv per creare o modificare in blocco la massa di Q&As. È anche un modo semplice per salvare in blocco Draft Q&As che richiedono ulteriori modifiche o aggiornamenti. Se è necessario modificare in blocco i Q&As esistenti, esportarli dal portale di amministrazione, apportare le modifiche necessarie e quindi importarli.
  
1. Nell'angolo in alto a destra della sezione Q&As, fare clic su **Importa**
    
2. Fare clic su **Scarica modello di Q&A (. csv)**
    
3. Salvare e aprire il file. csv
    
4. Aggiungere il contenuto e le impostazioni di Q&A e salvare il file

    Il file. csv deve essere salvato come file UTF-8 CSV, altri tipi di file e o codifiche possono causare errori di importazione
    
5. Nell'angolo in alto a destra della sezione Q&As, fare clic su **Importa**
    
6. Nel riquadro Importa Q&As, fare clic su **Sfoglia** e passare al file. csv che si desidera importare. 
    
7. Fare clic su **Importa**

# <a name="prevent-import-errors"></a>Prevenire gli errori di importazione      
Se i dati richiesti sono mancanti o non validi, verrà visualizzato un messaggio di errore. A seconda dell'errore, è possibile che venga generato un file di registro con ulteriori informazioni sulle righe e le colonne che devono essere corrette. Apportare le modifiche necessarie e provare a importare di nuovo il file.

> [!NOTE]
> Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare Q&As. 

Per evitare errori, verificare che il file di importazione sia formattato correttamente:
- Include la riga di intestazione inclusa nel modello di importazione
- Include tutte le colonne incluse nel modello di importazione
- L'ordine di colonna è lo stesso del modello di importazione
- Tali colonne possono essere vuote: ID, Ultima modifica e Ultima modifica da
- La colonna dello stato non può essere vuota, queste informazioni sono obbligatorie  
In base al campo dello stato, Q&As verrà salvato come bozza, suggerito, pianificato o verrà pubblicato automaticamente.

Inoltre, se si include l'ID di un Q&A esistente, verrà sostituito con le informazioni contenute nel file di importazione.

Per le organizzazioni con tenant di più, è possibile esportare i Q&As da un tenant e importarli in un altro. È tuttavia necessario rimuovere tutti i dati nella colonna ID prima di essere importati.

Per ulteriori informazioni sui campi richiesti e consigliati, vedere [create Q&As](create-qas.md).

  

