---
title: Creare in blocco i segnalibri
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
ROBOTS: NoIndex
description: Creare un numero elevato di segnalibri contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311713"
---
# <a name="bulk-create-bookmarks"></a>Creare in blocco i segnalibri

> [!IMPORTANT]
> Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing. Il portale di amministrazione di Microsoft Search in Bing sta per essere trasferito nell'interfaccia di amministrazione di Microsoft 365 e successivamente verrà rimosso. Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365. [Panoramica di Microsoft Search](overview-microsoft-search.md).
    
Scaricare e utilizzare il modello. csv per creare, modificare e salvare in blocco i segnalibri. Per modificare in blocco i segnalibri esistenti, esportarli dal portale di amministrazione, apportare le modifiche necessarie e quindi importarli.
  
1. Nell'angolo in alto a destra della sezione Segnalibri fare clic su **Importa** .
    
2. Fare clic su **Scarica modello di segnalibri (. csv)**
    
3. Salvare e aprire il file CSV
    
4. Aggiungere il contenuto e le impostazioni dei segnalibri e salvare il file

    Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione
    
5. Nell'angolo in alto a destra della sezione Segnalibri fare clic su **Importa** .
    
6. Nel riquadro Importa segnalibri fare clic su **Sfoglia** e passare al file CSV che si desidera importare. 
    
7. Fare clic su **Importa**.

## <a name="prevent-import-errors"></a>Evitare gli errori di importazione      
Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore. A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere. Apportare le modifiche necessarie e ritentare l'importazione del file.

> [!NOTE]
> Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare i segnalibri. 

Per evitare errori, verificare che il file di importazione sia formattato correttamente, ossia che:
- Includa la riga di intestazione presente nel modello di importazione
- Includa tutte le colonne presenti nel modello di importazione
- L'ordine delle colonne equivalga a quello del modello di importazione
- Queste colonne possono essere vuote: ID, Ultima modifica e Autore ultima modifica
- La colonna Stato non può essere vuota, perché si tratta di informazioni obbligatorie  
In base al campo Stato, i segnalibri saranno salvati come bozza, suggeriti o pianificati, oppure saranno pubblicati direttamente.

Inoltre, se si include l'ID di un segnalibro esistente, verrà sostituito con le informazioni contenute nel file di importazione.

Per i partner che gestiscono più organizzazioni, è possibile esportare i segnalibri da un'organizzazione e importarli in un altro. È tuttavia necessario rimuovere i dati dalla colonna Id prima dell'importazione.

Per ulteriori informazioni sui campi richiesti e consigliati, vedere [creare segnalibri](create-bookmarks.md).
