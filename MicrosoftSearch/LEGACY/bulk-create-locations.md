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
ROBOTS: NoIndex
description: Aggiungere un numero elevato di posizioni contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311697"
---
# <a name="bulk-create-locations"></a>Creare posizioni in blocco

> [!IMPORTANT]
> Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing. Il portale di amministrazione di Microsoft Search in Bing sta per essere trasferito nell'interfaccia di amministrazione di Microsoft 365 e successivamente verrà rimosso. Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365. [Panoramica di Microsoft Search](overview-microsoft-search.md).
    
Scaricare e utilizzare il modello. csv per creare, modificare e salvare in blocco le posizioni. 
  
1. Nell'angolo in alto a destra della sezione posizioni fare clic su **Importa** .
    
2. Fare clic su **download template locations (. csv)**
    
3. Salvare e aprire il file CSV
    
4. Aggiungere il contenuto del percorso e salvare il file

    Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione
    
5. Nell'angolo in alto a destra della sezione posizioni fare clic su **Importa** .
    
6. Nel riquadro Importa percorsi fare clic su **Sfoglia** e passare al file CSV che si desidera importare. 
    
7. Fare clic su **Importa**.

I campi nei modelli delle posizioni di importazione ed esportazione sono gli stessi. È possibile esportare, modificare in blocco e importare le modifiche o iniziare con un modello vuoto per creare in blocco nuove posizioni. Per modificare in blocco le posizioni esistenti, esportarle dal portale di amministrazione, apportare le modifiche necessarie e quindi importarle.

## <a name="prevent-import-errors"></a>Evitare gli errori di importazione  
Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore. A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere. Apportare le modifiche necessarie e ritentare l'importazione del file.
  
> [!NOTE]
> Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare posizioni. 

Per evitare errori, verificare che il file di importazione sia formattato correttamente, ossia che:
- Includa la riga di intestazione presente nel modello di importazione
- Includa tutte le colonne presenti nel modello di importazione
- L'ordine delle colonne equivalga a quello del modello di importazione
- Tali colonne possono essere vuote: ID, last modified, last modified by e Lat/Long  
Si cercherà di determinare Lat/Long in base all'indirizzo se il campo è vuoto.
- La colonna Stato non può essere vuota, perché si tratta di informazioni obbligatorie  
In base al campo dello stato, i percorsi verranno salvati come bozza, suggeriti, pianificati o verranno pubblicati automaticamente.

Inoltre, se si include l'ID di un percorso esistente, verrà sostituito con le informazioni contenute nel file di importazione.

Per i partner che gestiscono più organizzazioni, è possibile esportare i percorsi da un org e importarli in un altro. È tuttavia necessario rimuovere i dati dalla colonna Id prima dell'importazione.
  
Per ulteriori informazioni sui campi richiesti e consigliati, vedere [aggiungere un percorso](add-a-location.md).

  

