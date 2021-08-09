---
title: Gestire le domande e risposte
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Trovare e aggiornare le risposte singolarmente o usare gli strumenti Microsoft Search disponibili per modificare le domande&come tutte contemporaneamente.
ms.openlocfilehash: 2e54169a6196ec78bd96b33aa1ba71fc498b6ff13d8d872ad06ca0db1d9fc2c0
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532867"
---
# <a name="manage-qas"></a>Gestire le domande e risposte

Creare domande e risposte è simile alla creazione di segnalibri. D&Consente di rispondere alle domande dell'utente invece di fornire semplicemente un collegamento a una pagina Web. È inoltre possibile formattare la risposta in formato RTF. Se un segnalibro e un&A condividono la stessa parola chiave, il risultato del segnalibro viene visualizzato per primo. Come i segnalibri, l'&domande e risposte viene aggiornato immediatamente dopo l'aggiunta o la modifica di un&domande e risposte.

## <a name="add-or-edit-a-single-qa"></a>Aggiungere o modificare una singola domanda con risposta

1. Nella finestra [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com), passare a [**Domande&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. Per aggiungere una domanda&A, selezionare **Aggiungi**.
Per modificare una domanda con risposta, selezionarla nell'elenco di domande e risposte pertinente. Quando si aggiungono o modificano le informazioni, l'anteprima viene aggiornata automaticamente.
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

## <a name="add-or-edit-qas-using-browser-extensions"></a>Aggiungere o modificare domande&come usando le estensioni del browser

Gli amministratori della ricerca possono creare facilmente contenuti di ricerca usando le estensioni del browser. Installare l'estensione del browser e quindi passare al sito da cui si desidera generare una domanda&A. È quindi possibile creare le domande&A e includere un collegamento al sito di origine.

Attualmente, le estensioni del browser sono disponibili per Microsoft Edge e Chrome.

- Per scaricare le estensioni per Edge (legacy), vai a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Per scaricare le estensioni Chrome o Edge (Chromium), vai [all'archivio Web Chrome.](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)

## <a name="bulk-add-or-edit-qas"></a>Aggiungere o modificare in blocco le domande e risposte

Gli amministratori possono utilizzare le funzionalità di importazione ed esportazione per creare o modificare in blocco le domande&as.

Utilizzare la Importazione/Esportazione per:

- Aggiungere domande&in blocco - Aggiungere i dettagli nel file di&un file modello e quindi importarlo.
- Modifica in blocco Q&As - Export Q&As to a .csv file, edit the Q&A details in the exported file, and then import the file.
- Eseguire il backup di domande&as - Esportare domande&in un file .csv file.

Per importare o esportare domande&come:

1. In alto a destra della scheda Domande e risposte, selezionare **Importa**.
Selezionare **Esporta** per scaricare tutte le domande&come in un file .csv file.
1. Nel riquadro destro selezionare l'opzione per l'importazione utilizzando un .csv file. Scarica il file modello per ottenere un elenco dei campi e dei dettagli obbligatori.
1. Aggiungere o modificare domande&dettagli A nel file modello e salvarli nel computer.
1. Nel riquadro **Importa domande&A** selezionare Sfoglia e quindi selezionare il .csv file che si desidera importare. 
1. Selezionare **Importa**.

Suggerimenti importanti per i file di modello:

- Non modificare i dati in questi campi: **Id**, **Data ultima modifica** e **Autore ultima modifica**
- Se si include l'**Id** di un segnalibro esistente, verrà sostituito con le informazioni presenti nel file di importazione.
- Se esiste un segnalibro con lo stesso titolo o URL, il segnalibro verrà aggiornato con le informazioni nel file di importazione.
- Non tutti i campi nel file modello sono obbligatori e i campi obbligatori variano a seconda dello stato del segnalibro.
- In base al **campo Stato,** i segnalibri vengono salvati come bozza, suggeriti o *pianificati* oppure vengono pubblicati automaticamente.
- Per i partner che gestiscono più organizzazioni: è possibile esportare i segnalibri da un'organizzazione e importarli in un'altra. È tuttavia necessario rimuovere i dati dalla colonna **Id** prima di importarli.

> [!NOTE]
> Non è possibile importare domande&come se si verificano errori nel file modello. Per evitare errori, verificare che il file di importazione sia formattato correttamente e includere tutte le informazioni necessarie.

Per ulteriori informazioni su come evitare errori, vedere [Prevent import errors.](manage-bookmarks.md#prevent-import-errors)
