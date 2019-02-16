---
title: Creare segnalibri in blocco
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
description: Creare un numero elevato di segnalibri contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: 07694de1f546a1431f371fa24ffc5721ea66337c
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068403"
---
# <a name="bulk-create-bookmarks"></a>Creare segnalibri in blocco

Scaricare e utilizzare il modello. csv per creare, modificare e salvare in blocco i segnalibri. Per modificare in blocco i segnalibri esistenti, esportarli dal portale di amministrazione, apportare le modifiche necessarie e quindi importarli.
  
1. Nell'angolo in alto a destra della sezione Segnalibri fare clic su **Importa** .
    
2. Fare clic su **Scarica modello di segnalibri (. csv)**
    
3. Salvare e aprire il file. csv
    
4. Aggiungere il contenuto e le impostazioni dei segnalibri e salvare il file
    
5. Nell'angolo in alto a destra della sezione Segnalibri fare clic su **Importa** .
    
6. Nel riquadro Importa segnalibri fare clic su **Sfoglia** e passare al file CSV che si desidera importare. 
    
7. Fare clic su **Importa**

# <a name="prevent-import-errors"></a>Prevenire gli errori di importazione      
Se i dati richiesti sono mancanti o non validi, verrà visualizzato un messaggio di errore. A seconda dell'errore, è possibile che venga generato un file di registro con ulteriori informazioni sulle righe e le colonne che devono essere corrette. Apportare le modifiche necessarie e provare a importare di nuovo il file.

> [!NOTE]
> Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare i segnalibri. 

Per evitare errori, verificare che il file di importazione sia formattato correttamente:
- Include la riga di intestazione inclusa nel modello di importazione
- Include tutte le colonne incluse nel modello di importazione
- L'ordine di colonna è lo stesso del modello di importazione
- Tali colonne possono essere vuote: ID, Ultima modifica e Ultima modifica da
- La colonna dello stato non può essere vuota, queste informazioni sono obbligatorie  
In base al campo dello stato, i segnalibri verranno salvati come bozza, suggeriti, pianificati o verranno pubblicati automaticamente.

Inoltre, se si include l'ID di un segnalibro esistente, verrà sostituito con le informazioni contenute nel file di importazione.

Per le organizzazioni con tenant di più, è possibile esportare i segnalibri da un tenant e importarli in un altro. È tuttavia necessario rimuovere tutti i dati nella colonna ID prima di essere importati.

Per ulteriori informazioni sui campi richiesti e consigliati, vedere [creare segnalibri](create-bookmarks.md).
