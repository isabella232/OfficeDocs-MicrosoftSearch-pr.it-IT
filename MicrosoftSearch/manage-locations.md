---
title: Gestire le posizioni
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 8ab9aa00-cd74-405f-8410-9a1c3cfacdb9
description: Nel corso del tempo, potrebbe essere necessario aggiornare lo stato e il contenuto di una posizione per fare in modo che rimanga pertinente.
ms.openlocfilehash: d026e518011f3b3739beb2b6aaa044f8a5e9c0d4
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591558"
---
# <a name="manage-locations"></a>Gestire le posizioni

## <a name="location"></a>Posizione
Posizione consente agli utenti di trovare indirizzi e individuare gli edifici dell'organizzazione indicando la posizione precisa di uffici, campus ed edifici, oltre alle indicazioni di navigazione. Gli amministratori dovranno aggiungere tutte le posizioni importanti dell'organizzazione. A differenza dei segnalibri e delle domande e risposte, l'indice non verrà aggiornato immediatamente e la visualizzazione delle posizioni nuove o modificate nei risultati della ricerca può richiedere diverse ore.

### <a name="add-or-edit-a-single-location"></a>Aggiungere o modificare una singola posizione
1. Passare all'**interfaccia di amministrazione di Microsoft 365**.
1. Nel riquadro di spostamento passare a **Impostazioni** e selezionare **Microsoft Search**.
1. Selezionare la scheda **Posizioni**. Per impostazione predefinita, la scheda **Segnalibri** è selezionata nella pagina **Microsoft Search**.
1. Per aggiungere una nuova posizione, fare clic su **Aggiungi nuovo**.
1. Per modificare una posizione, selezionarla nell'elenco di posizioni pertinenti.
1. Quando si aggiungono o modificano le informazioni, l'anteprima viene aggiornata automaticamente.
1. Salvare le modifiche.

### <a name="bulk-add-or-edit-locations"></a>Aggiungere o modificare in blocco le posizioni
Gli amministratori possono usare le funzionalità di importazione o esportazione per aggiungere o modificare in blocco le posizioni. 

Usare la funzionalità di importazione/esportazione per:
1. Aggiungere posizioni in blocco: aggiungere i dettagli nel file modello delle posizioni e quindi importarlo. 
1. Modificare le posizioni in blocco: esportare le posizioni in un file CSV, quindi modificare i dettagli delle posizioni nel file CSV esportato e infine importare il file CSV aggiornato.
1. Effettuare il backup delle posizioni: esportare le posizioni esistenti in un file CSV.

Per esportare o importare posizioni:
1. In alto a destra della scheda **Posizioni**, selezionare **Importa**.
Selezionare **Esporta** per scaricare le posizioni esistenti in un file CSV.
1. Nel riquadro destro, scegliere l'opzione per importare con un file CSV. Scaricare il file modello per un elenco di campi obbligatori e i dettagli.
1. Aggiungere o modificare i dettagli della posizione nel file modello e quindi salvarlo nel computer. 
1. Nel riquadro **Importa** posizioni, selezionare **Sfoglia** e quindi il file CSV da importare.
1. Selezionare **Importa**.

Ecco alcuni punti importanti riguardanti il file modello:
- Non modificare i dati in questi campi: *Id*, *Data ultima modifica* e *Autore ultima modifica*
- Se si include l'*Id* di un segnalibro esistente, verrà sostituito con le informazioni presenti nel file di importazione.
- Se esiste un segnalibro con lo stesso titolo o URL, il segnalibro verrà aggiornato con le informazioni nel file di importazione.
- Non tutti i campi sono obbligatori nel file modello e i campi obbligatori variano in base allo stato del segnalibro.
- In base al campo *Stato*, i segnalibri saranno salvati come bozza, suggeriti o pianificati, oppure saranno pubblicati direttamente.
- Per le organizzazioni con più tenant, è possibile esportare i segnalibri da un tenant e importarli in un altro. È tuttavia necessario rimuovere i dati dalla colonna *Id* prima di importarli.

**Nota:** non è possibile importare posizioni se sono presenti errori nel file modello. Per evitare errori, verificare che il file di importazione sia formattato correttamente e che includa tutte le informazioni necessarie. 

Per altre informazioni su come evitare errori, vedere [Evitare gli errori di importazione](manage-bookmarks.md#prevent-import-errors).
