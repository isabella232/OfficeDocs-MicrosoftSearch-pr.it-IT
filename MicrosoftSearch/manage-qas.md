---
title: Gestire le domande e risposte
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Trovare e aggiornare le risposte singolarmente oppure usare gli strumenti di Microsoft Search disponibili per modificarle tutte contemporaneamente
ms.openlocfilehash: 8620842e64a40eb32467c42a289bdec3b67d303b
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591522"
---
# <a name="manage-qas"></a>Gestire le domande e risposte

Creare domande e risposte è simile alla creazione di segnalibri. Le Domande e risposte consentono di rispondere alla domanda di un utente anziché limitarsi a fornire un collegamento a una pagina Web. È possibile formattare la risposta in testo RTF con gli strumenti disponibili. Se un segnalibro e una domanda con risposta condividono la stessa parola chiave, il risultato del segnalibro viene visualizzato per primo. Come per i segnalibri, l'indice delle domande e risposte verrà aggiornato immediatamente dopo che è stata aggiunta o modificata una domanda con risposta. 

## <a name="add-or-edit-a-single-qa"></a>Aggiungere o modificare una singola domanda con risposta
1. Passare all'**interfaccia di amministrazione di Microsoft 365**.
1. Nel riquadro di spostamento passare a **Impostazioni** e selezionare **Microsoft Search**.
1. Selezionare la scheda **Domande e risposte**. Per impostazione predefinita, è già selezionata la prima scheda (**Segnalibri**).
1. Per aggiungere una domanda con risposta, selezionare **Aggiungi nuovo**.
Per modificare una domanda con risposta, selezionarla nell'elenco di domande e risposte pertinente.
1. Quando si aggiungono o modificano le informazioni, l'anteprima viene aggiornata automaticamente.
1. Salvare le modifiche.

### <a name="supported-html-tags"></a>Tag HTML supportati
È possibile usare contenuto HTML esistente o aggiungere tag HTML alla risposta (descrizione). I tag non supportati vengono ignorati.  
Sono supportati i tag HTML seguenti:
- blockquote
- div
- em
- h1, h2, h3, and h4
- ol, ul, and li
- p
- pre
- span
- strong
- table, thead, tbody, tr, th, and td
- u
- a
- code
- br
- hr
- img

## <a name="bulk-add-or-edit-qas"></a>Aggiungere o modificare in blocco le domande e risposte
Gli amministratori possono usare le funzionalità di importazione o esportazione per creare o modificare in blocco le domande e risposte. È una funzionalità utile quando gli amministratori devono aggiungere o modificare un numero elevato di domande e risposte. 

Usare la funzionalità di importazione/esportazione per:
1. Aggiungere domande e risposte in blocco: aggiungere i dettagli nel file modello delle domande e risposte e quindi importarlo.
1. Modificare domande e risposte in blocco: esportare le domande e risposte in un file CSV, quindi modificare i relativi dettagli nel file CSV esportato e infine importare il file CSV aggiornato.
1. Eseguire il backup di domande e risposte: esportare le domande e risposte in un file CSV.

Per importare o esportare domande e risposte:
1. In alto a destra della scheda Domande e risposte, selezionare **Importa**. Selezionare **Esporta** per scaricare tutte le domande e risposte esistenti in un file CSV.
1. Nel riquadro destro, scegliere l'opzione per importare con un file CSV.
Scaricare il file modello per un elenco di campi obbligatori e i dettagli. 
1. Aggiungere o modificare i dettagli delle domande e risposte nel file modello e salvarlo nel computer. 
1. Nel riquadro di **importazione domande e risposte**, selezionare **Sfoglia** e quindi il file CSV da importare.
1. Selezionare **Importa**.

Ecco alcuni punti importanti riguardanti il file modello:
- Non modificare i dati in questi campi: *Id*, *Data ultima modifica* e *Autore ultima modifica*
- Se si include l'*Id* di un segnalibro esistente, verrà sostituito con le informazioni presenti nel file di importazione.
- Se esiste un segnalibro con lo stesso titolo o URL, il segnalibro verrà aggiornato con le informazioni nel file di importazione.
- Non tutti i campi sono obbligatori nel file modello e i campi obbligatori variano in base allo stato del segnalibro.
- In base al campo Stato, i segnalibri saranno salvati come bozza, suggeriti o pianificati, oppure saranno pubblicati direttamente.
- Per le organizzazioni con più tenant, è possibile esportare i segnalibri da un tenant e importarli in un altro. È tuttavia necessario rimuovere i dati dalla colonna *Id* prima di importarli.

**Nota:** non è possibile importare domande e risposte se sono presenti errori nel file modello. Per evitare errori, verificare che il file di importazione sia formattato correttamente e che includa tutte le informazioni necessarie. 

Per altre informazioni su come evitare errori, vedere [Evitare gli errori di importazione](manage-bookmarks.md#prevent-import-errors).