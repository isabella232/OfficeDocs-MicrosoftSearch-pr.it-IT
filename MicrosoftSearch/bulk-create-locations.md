---
title: Creare posizioni in blocco
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
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
description: Aggiungere più posizioni contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: 1d360fda2851083def0bcbd8fcffd77cfa15240e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968292"
---
# <a name="bulk-create-locations"></a>Creare posizioni in blocco

> [!IMPORTANT]
> Le impostazioni di Microsoft Search in Bing sono ora disponibili nell'interfaccia di amministrazione di Microsoft 365. Per iniziare, [assegnare amministratori della ricerca](https://docs.microsoft.com/it-IT/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) nell'interfaccia di amministrazione.
    
Scaricare e usare il modello CSV per creare, modificare e salvare in blocco le posizioni. 
  
1. Nell'angolo superiore destro della sezione Posizioni, fare clic su **Importa**.
    
2. Fare clic su **Scarica il modello delle posizioni (.CSV)**
    
3. Salvare e aprire il file CSV
    
4. Aggiungere il contenuto della posizione e salvare il file

    Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione
    
5. Nell'angolo superiore destro della sezione Posizioni, fare clic su **Importa**.
    
6. Nel riquadro Importa posizioni fare clic su **Sfoglia **e passare al file CSV da importare. 
    
7. Fare clic su **Importa**.

I campi nei modelli di importazione ed esportazione sono gli stessi. È possibile esportare, modificare in blocco e importare le modifiche oppure iniziare con un modello vuoto per creare in blocco nuove posizioni. Per modificare in blocco posizioni esistenti, esportarle dal portale di amministrazione, apportare le modifiche necessarie e quindi importarle.

# <a name="prevent-import-errors"></a>Evitare gli errori di importazione  
Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore. A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere. Apportare le modifiche necessarie e ritentare l'importazione del file.
  
> [!NOTE]
> Fino a quando non sono stati risolti tutti gli errori, non è possibile creare o modificare le posizioni. 

Per evitare errori, verificare che il file di importazione sia formattato correttamente, ossia che:
- Includa la riga di intestazione presente nel modello di importazione
- Includa tutte le colonne presenti nel modello di importazione
- L'ordine delle colonne equivalga a quello del modello di importazione
- Queste colonne possono essere vuote: ID, Ultima modifica, Autore ultima modifica e Latitudine/longitudine  
Sse il campo è vuoto, si proverà a determinare la latitudine e la longitudine in base all'indirizzo
- La colonna Stato non può essere vuota, perché si tratta di informazioni obbligatorie  
In base al campo Stato, le posizioni saranno salvate come bozza, suggerite o pianificate, oppure saranno pubblicate automaticamente.

Se si include l'Id di una posizione esistente, verrà sostituito con le informazioni presenti nel file di importazione.

Per le organizzazioni con più tenant, è possibile esportare le posizioni da un tenant e importarle in un altro. È tuttavia necessario rimuovere i dati dalla colonna Id prima dell'importazione.
  
Per altre informazioni sui campi obbligatori e consigliati, vedere [Aggiungere una posizione](add-a-location.md).

  

