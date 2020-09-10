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
description: Trovare e aggiornare le risposte singolarmente o utilizzare gli strumenti di ricerca di Microsoft disponibili per modificare&come tutti insieme.
ms.openlocfilehash: 2a8b0727ef3540a35d617cf6c8bae7b0d99767a8
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2020
ms.locfileid: "47423001"
---
# <a name="manage-qas"></a>Gestire le domande e risposte

Creare domande e risposte è simile alla creazione di segnalibri. Q&come consentono di rispondere alle domande dell'utente invece di fornire solo un collegamento a una pagina Web. È inoltre possibile formattare la risposta in testo RTF. Se un segnalibro e un Q&condividono la stessa parola chiave, il risultato del segnalibro viene visualizzato per primo. Analogamente ai segnalibri, la Q&un indice viene aggiornato subito dopo l'aggiunta o la modifica di una Q&A.

## <a name="add-or-edit-a-single-qa"></a>Aggiungere o modificare una singola domanda con risposta

1. Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com), passare a [**Q&a**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. Per aggiungere una Q&A, selezionare **Aggiungi**.
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

## <a name="add-or-edit-qas-using-browser-extensions"></a>Aggiungere o modificare la&Q come utilizzo delle estensioni del browser

Gli amministratori della ricerca possono creare facilmente contenuti di ricerca usando le estensioni del browser. Installare l'estensione del browser, quindi passare al sito da cui si desidera generare una Q&A. È quindi possibile creare il&A e includere un collegamento al sito di origine.

Attualmente, le estensioni del browser sono disponibili per Microsoft Edge e Chrome.

- Per scaricare le estensioni per Edge (legacy), andare a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Per scaricare le estensioni Chrome o Edge (cromo), passare a [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="bulk-add-or-edit-qas"></a>Aggiungere o modificare in blocco le domande e risposte

Gli amministratori possono utilizzare le funzionalità di importazione ed esportazione per creare o modificare in blocco Q&As.

Utilizzare la caratteristica di importazione/esportazione per:

- Aggiungere in blocco&come aggiungere i dettagli in Q&un file modello e quindi importarlo.
- Modifica in blocco Q&As-Export Q&come in un file. csv, modificare la&di un dettaglio nel file esportato e quindi importare il file.
- Eseguire il backup di Q&come-Export Q&come in un file. csv.

Per importare o esportare Q&come:

1. In alto a destra della scheda Domande e risposte, selezionare **Importa**.
Selezionare **Esporta** per scaricare tutte le&Q esistenti come in un file. csv.
1. Nel riquadro destro selezionare l'opzione da importare utilizzando un file. csv. Scaricare il file modello per ottenere un elenco di campi e dettagli necessari.
1. Aggiungere o modificare Q&un dettaglio nel file modello e salvarlo nel computer.
1. Nel riquadro **Importa Q&a** , selezionare **Sfoglia**e quindi selezionare il file. csv che si desidera importare.
1. Selezionare **Importa**.

Suggerimenti importanti per i file del modello:

- Non modificare i dati in questi campi: **Id**, **Data ultima modifica** e **Autore ultima modifica**
- Se si include l'**Id** di un segnalibro esistente, verrà sostituito con le informazioni presenti nel file di importazione.
- Se è presente un segnalibro esistente con lo stesso titolo o URL, il segnalibro verrà aggiornato con le informazioni contenute nel file di importazione.
- Non tutti i campi del file modello sono obbligatori e i campi richiesti variano a seconda dello stato del segnalibro.
- In base al campo **dello stato** , i segnalibri vengono salvati come *bozza*, *suggerita*o *pianificata*oppure vengono pubblicati automaticamente.
- Per i partner che gestiscono più organizzazioni: è possibile esportare i segnalibri da un'organizzazione e importarli in un altro. È tuttavia necessario rimuovere i dati dalla colonna **Id** prima di importarli.

> [!NOTE]
> Non è possibile importare la&Q come se si verificassero errori nel file modello. Per evitare errori, verificare che il file di importazione sia formattato correttamente e includere tutte le informazioni necessarie.

Per ulteriori informazioni sull'evitare errori, vedere [prevenire gli errori di importazione](manage-bookmarks.md#prevent-import-errors).
