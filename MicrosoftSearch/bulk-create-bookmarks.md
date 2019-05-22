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
description: Creare più segnalibri contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: 560cda6f94060d428f2d18cc61bd2430cb31b474
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968349"
---
# <a name="bulk-create-bookmarks"></a>Creare in blocco i segnalibri

> [!IMPORTANT]
> Le impostazioni di Microsoft Search in Bing sono ora disponibili nell'interfaccia di amministrazione di Microsoft 365. Per iniziare, [assegnare amministratori della ricerca](https://docs.microsoft.com/it-IT/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) nell'interfaccia di amministrazione.
    
Scaricare e usare il modello CSV per creare, modificare e salvare in blocco i segnalibri. Per modificare in blocco segnalibri esistenti, esportarli dal portale di amministrazione, apportare le modifiche necessarie e quindi importarli.
  
1. Nell'angolo superiore destro della sezione Segnalibri, fare clic su **importa**
    
2. Fare clic su **Scarica modello segnalibri (CSV)**
    
3. Salvare e aprire il file CSV
    
4. Aggiungere contenuto e impostazioni dei segnalibri e salvare il file

    Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione
    
5. Nell'angolo superiore destro della sezione Segnalibri fare clic su **Importa**
    
6. Nel riquadro Importa i segnalibri fare clic su **Sfoglia **e passare al file CSV da importare 
    
7. Fare clic su **Importa**

# <a name="prevent-import-errors"></a>Evitare gli errori di importazione      
Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore. A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere. Apportare le modifiche necessarie e ritentare l'importazione del file.

> [!NOTE]
> Fino a quando non sono stati risolti tutti gli errori, non è possibile creare o modificare i segnalibri. 

Per evitare errori, verificare che il file di importazione sia formattato correttamente, ossia che:
- Includa la riga di intestazione presente nel modello di importazione
- Includa tutte le colonne presenti nel modello di importazione
- L'ordine delle colonne equivalga a quello del modello di importazione
- Queste colonne possono essere vuote: ID, Ultima modifica e Autore ultima modifica
- La colonna Stato non può essere vuota, perché si tratta di informazioni obbligatorie  
In base al campo Stato, i segnalibri saranno salvati come bozza, suggeriti o pianificati, oppure saranno pubblicati automaticamente.

Inoltre, se si include l'Id di un segnalibro esistente, verrà sostituito con le informazioni presenti nel file di importazione.

Per le organizzazioni con più tenant, è possibile esportare i segnalibri da un tenant e importarli in un altro. È tuttavia necessario rimuovere i dati dalla colonna Id prima dell'importazione.

Per altre informazioni sui campi obbligatori e consigliati, vedere [Creare segnalibri](create-bookmarks.md).
