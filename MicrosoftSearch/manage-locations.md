---
title: Gestire le posizioni
ms.author: dawholl
author: dawholl
manager: kellis
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
ms.openlocfilehash: 5e9d88fc08458e928e52988124ee94c60829c7bb71ed13f8534b71ca08e2d50c
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532876"
---
# <a name="manage-locations"></a>Gestire le posizioni

## <a name="location"></a>Posizione

Posizione consente agli utenti di trovare indirizzi e individuare gli edifici dell'organizzazione indicando la posizione precisa di uffici, campus ed edifici, oltre alle indicazioni di navigazione. Gli amministratori dovranno aggiungere tutte le posizioni importanti dell'organizzazione. A differenza dei segnalibri e delle domande e risposte, l'indice non verrà aggiornato immediatamente e la visualizzazione delle posizioni nuove o modificate nei risultati della ricerca può richiedere diverse ore.

### <a name="add-or-edit-a-single-location"></a>Aggiungere o modificare una singola posizione

1. Nel [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com), andare a [**Posizioni**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/locations)
1. Per aggiungere una nuova posizione, selezionare **Aggiungi**.
1. Per modificare una posizione, selezionarla nell'elenco di posizioni pertinenti.
1. Quando si aggiungono o modificano le informazioni, l'anteprima viene aggiornata automaticamente.
1. Salvare le modifiche.

### <a name="bulk-add-or-edit-locations"></a>Aggiungere o modificare in blocco le posizioni

Gli amministratori possono usare le funzionalità di importazione o esportazione per aggiungere o modificare in blocco le posizioni.

Usare la funzionalità di importazione/esportazione per:

1. Aggiungere posizioni in blocco: aggiungere i dettagli nel file modello delle posizioni e quindi importarlo.
1. Modificare le posizioni in blocco: esportare le posizioni in un file CSV, quindi modificare i dettagli delle posizioni nel file CSV esportato e infine importare il file CSV aggiornato.
1. Percorsi di backup: consente di esportare i percorsi esistenti in .csv file.

Per esportare o importare posizioni:

1. In alto a destra della scheda **Posizioni**, selezionare **Importa**.
Selezionare **Esporta** per scaricare le posizioni esistenti in un file CSV.
1. Nel riquadro destro, scegliere l'opzione per importare con un file CSV.
Scaricare il file modello per un elenco di campi obbligatori e i dettagli.
1. Aggiungere o modificare i dettagli della posizione nel file modello e quindi salvarlo nel computer.
1. Nel riquadro **Importa** posizioni, selezionare **Sfoglia** e quindi il file CSV da importare.
1. Selezionare **Importa**.

Ecco alcuni punti importanti riguardanti il file modello:

- Non modificare i dati in questi campi: *Id*, *Data ultima modifica* e *Autore ultima modifica*
- Se si include *l'ID* di un percorso esistente, questo verrà sostituito con le informazioni nel file di importazione.
- Se esiste un percorso esistente con lo stesso nome, il percorso verrà aggiornato con le informazioni nel file di importazione.
- Non tutti i campi nel file modello sono obbligatori e i campi obbligatori variano a seconda dello stato della posizione.
- In base al *campo Stato,* le posizioni verranno salvate come bozza, suggerite, pianificate o verranno pubblicate automaticamente.
- Per i partner che gestiscono più organizzazioni, è possibile esportare le posizioni da un'organizzazione e importarle in un'altra. È tuttavia necessario rimuovere i dati dalla colonna *Id* prima di importarli.

> [!NOTE]
> Non è possibile importare percorsi se sono presenti errori nel file modello. Per evitare errori, verificare che il file di importazione sia formattato correttamente e che includa tutte le informazioni necessarie.

Per altre informazioni su come evitare errori, vedere [Evitare gli errori di importazione](manage-bookmarks.md#prevent-import-errors).
