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
description: Aggiungere un numero elevato di posizioni contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: 3c7e43b03b97b46769d5e73f20ddae47b3459b59
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901809"
---
# <a name="bulk-create-locations"></a>Creare posizioni in blocco

Scaricare e utilizzare il modello. csv per creare, modificare e salvare in blocco le posizioni. 
  
1. Nell'angolo in alto a destra della sezione posizioni fare clic su **Importa** .
    
2. Fare clic su **download template locations (. csv)**
    
3. Salvare e aprire il file. csv
    
4. Aggiungere il contenuto del percorso e salvare il file

    Il file. csv deve essere salvato come file UTF-8 CSV, altri tipi di file e o codifiche possono causare errori di importazione
    
5. Nell'angolo in alto a destra della sezione posizioni fare clic su **Importa** .
    
6. Nel riquadro Importa percorsi fare clic su **Sfoglia** e passare al file CSV che si desidera importare. 
    
7. Fare clic su **Importa**

I campi nei modelli delle posizioni di importazione ed esportazione sono gli stessi. È possibile esportare, modificare in blocco e importare le modifiche o iniziare con un modello vuoto per creare in blocco nuove posizioni. Per modificare in blocco le posizioni esistenti, esportarle dal portale di amministrazione, apportare le modifiche necessarie e quindi importarle.

# <a name="prevent-import-errors"></a>Prevenire gli errori di importazione  
Se i dati richiesti sono mancanti o non validi, verrà visualizzato un messaggio di errore. A seconda dell'errore, è possibile che venga generato un file di registro con ulteriori informazioni sulle righe e le colonne che devono essere corrette. Apportare le modifiche necessarie e provare a importare di nuovo il file.
  
> [!NOTE]
> Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare posizioni. 

Per evitare errori, verificare che il file di importazione sia formattato correttamente:
- Include la riga di intestazione inclusa nel modello di importazione
- Include tutte le colonne incluse nel modello di importazione
- L'ordine di colonna è lo stesso del modello di importazione
- Tali colonne possono essere vuote: ID, last modified, last modified by e Lat/Long  
Si cercherà di determinare Lat/Long in base all'indirizzo se il campo è vuoto.
- La colonna dello stato non può essere vuota, queste informazioni sono obbligatorie  
In base al campo dello stato, i percorsi verranno salvati come bozza, suggeriti, pianificati o verranno pubblicati automaticamente.

Inoltre, se si include l'ID di un percorso esistente, verrà sostituito con le informazioni contenute nel file di importazione.

Per le organizzazioni con tenant di più, è possibile esportare i percorsi da un tenant e importarli in un altro. È tuttavia necessario rimuovere tutti i dati nella colonna ID prima di essere importati.
  
Per ulteriori informazioni sui campi richiesti e consigliati, vedere [aggiungere un percorso](add-a-location.md).

  

