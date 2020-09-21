---
title: Gestire i segnalibri
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
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Creazione e aggiornamento di segnalibri e modalità di modifica in blocco dei risultati dei segnalibri per Microsoft Search
ms.openlocfilehash: eb65121b53ab110b91880a65a5146d868f3a7405
ms.sourcegitcommit: d88226f9c3a99540a591dc0a26408bb9960cf39a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2020
ms.locfileid: "48134168"
---
# <a name="manage-bookmarks"></a>Gestire i segnalibri

È possibile creare un segnalibro in pochi passaggi. Ogni segnalibro include un titolo, URL e un set di parole chiave di attivazione. È inoltre possibile aggiungere categorie a un segnalibro che può essere utilizzato per l'ordinamento e il filtro nel portale di amministrazione. Un segnalibro può avere più parole chiave e i segnalibri possono condividere la stessa parola chiave, ma la parola chiave riservata non può essere condivisa. Quando si crea o si modifica un segnalibro, l'indice di ricerca viene aggiornato immediatamente e il segnalibro è disponibile per gli utenti immediatamente.

Se l'organizzazione ha configurato i risultati promossi in SharePoint, è possibile importare i risultati promossi in **Microsoft Search** e rendere il contenuto importato disponibile per gli utenti. Si tratta di un modo semplice per inserire rapidamente i risultati della ricerca quando si configura **Microsoft Search** e renderlo più efficiente per gli utenti. È consigliabile utilizzare i risultati promossi da SharePoint come riferimento per comprendere come denominare e creare i risultati di ricerca rilevanti.

## <a name="add-or-edit-a-single-bookmark"></a>Aggiungere o modificare un singolo segnalibro

1. Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com), andare a [**segnalibri**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Per aggiungere un segnalibro, fare clic su **Aggiungi**.
Per modificare un segnalibro, selezionarlo nell'elenco di segnalibri pertinente.
1. Quando si aggiungono o modificano le informazioni, l'anteprima viene aggiornata automaticamente.
1. Salvare le modifiche.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Aggiungere o modificare il segnalibro usando le estensioni del browser

Gli amministratori della ricerca possono creare facilmente contenuti di ricerca usando le estensioni del browser. Installare l'estensione del browser, passare al sito che si desidera aggiungere come segnalibro e aggiungere il segnalibro.

Le estensioni dei browser sono attualmente disponibili per Microsoft Edge e Chrome.

- Per scaricare le estensioni dei server perimetrali, passare a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) e scaricare l'app.
- Per scaricare Chrome Extensions, passare a [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) e scaricare l'app.

## <a name="bulk-add-or-edit-bookmarks"></a>Aggiungere o modificare in blocco i segnalibri

Utilizzare la caratteristica di importazione o esportazione per creare o modificare in blocco i segnalibri. Rende l'aggiunta o la modifica di un numero elevato di segnalibri in modo più semplice e veloce. Utilizzarla per:

- Aggiungere segnalibri in blocco: aggiungere i dettagli nel file modello del segnalibro e quindi importarlo.
- Modificare i segnalibri in blocco: esportare i segnalibri in un file CSV, quindi modificare i dettagli del segnalibro nel file CSV esportato e infine importare il file CSV aggiornato.
- Importare i siti alzati di livello da SharePoint.
- Eseguire il backup dei segnalibri: esportare i segnalibri in un file CSV.

Per importare o esportare segnalibri:

1. In alto a destra della scheda **Segnalibri**, selezionare **Importa**.
Selezionare **Esporta** per scaricare tutti i segnalibri esistenti in un file CSV.
1. Nel riquadro destro, scegliere l'opzione per importare con un file CSV o da SharePoint.
Scaricare il file modello per un elenco di campi obbligatori e i dettagli.
1. Aggiungere o modificare i dettagli del segnalibro nel file modello e quindi salvarlo nel computer.
1. Nel riquadro **Importa segnalibri**, selezionare **Sfoglia** e quindi il file CSV da importare.
1. Selezionare **Importa**.

Di seguito sono riportate alcune considerazioni importanti sul file modello:

- Non modificare mai i dati in questi campi: *ID*, *Ultima modifica*e *Ultima modifica da*
- Se si include l' *ID* di un segnalibro esistente, verrà sostituito con le informazioni contenute nel file di importazione.
- Per segnalibro esistente con lo stesso titolo o URL, il segnalibro verrà aggiornato con le informazioni contenute nel file di importazione.
- Non tutti i campi sono obbligatori nel file modello e i campi obbligatori variano in base allo stato del segnalibro.
- In base al campo *dello stato* , i segnalibri verranno salvati come bozza, suggeriti, pianificati o verranno pubblicati automaticamente.
- Per i partner che gestiscono più organizzazioni, è possibile esportare i segnalibri da un'organizzazione e importarli in un altro. È tuttavia necessario rimuovere i dati nella colonna *ID* prima di essere importati.

### <a name="prevent-import-errors"></a>Evitare gli errori di importazione

Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore e viene generato un file di log con altre informazioni sulle righe e sulle colonne da correggere. Apportare le modifiche necessarie e riprovare l'importazione del file. Non è possibile importare o salvare alcun segnalibro finché non saranno stati risolti tutti gli errori.

Per evitare errori, verificare che il file di importazione sia formattato correttamente e che:

- Includa la riga di intestazione e tutte le colonne presenti nel modello di importazione
- L'ordine delle colonne equivalga a quello del modello di importazione
- Tutte le colonne dispongono di valori, ad eccezione delle tre che possono essere vuote: *ID*, *Last modified*e *Last modified by*
- La colonna *dello stato* non è vuota, sono necessarie informazioni

Per evitare errori di duplicazione da segnalibro a segnalibro:

- Non utilizzare URL duplicati per segnalibri diversi. Se un URL viene assegnato a un altro segnalibro e si tenta di aggiungerlo nuovamente da un file di importazione, verrà visualizzato un messaggio di errore. Questo vale anche per gli URL duplicati di altri tipi di risposte.
- Quando si aggiornano i segnalibri esistenti, utilizzare la colonna *ID segnalibro* . È possibile aggiornare qualsiasi altra proprietà di un segnalibro esistente, ad esempio una parola chiave o una descrizione, ma è necessario verificare che l' *ID del segnalibro* si trovi nella colonna appropriata del file di importazione. Se l' *ID del segnalibro* è presente, non verrà trattato come nuova aggiunta e non verrà elaborato come errore.

## <a name="power-apps"></a>Power Apps

Consente agli utenti di completare le attività, ad esempio il tempo di ferie o le spese per le relazioni, aggiungendo le app di alimentazione esistenti ai segnalibri.

### <a name="power-apps-explained"></a>Spiegazioni di Power Apps

Power Apps è un servizio che consente di creare app aziendali che vengono eseguite in un browser o su un telefono o tablet senza che sia necessaria alcuna esperienza di codifica. Le app Power funzionano in qualsiasi browser e su qualsiasi dispositivo e impiegano meno di un minuto per aggiungere. Per ulteriori informazioni su Power Apps, vedere:

- [Formazione guidata](https://docs.microsoft.com/learn/browse/?terms=power%20apps)
- [Documentazione](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Home Apps di alimentazione](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-power-app-to-a-bookmark"></a>Aggiungere un'app Power a un segnalibro

1. Individuare l' [ID app per l'applicazione di alimentazione](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) che si desidera aggiungere.
1. Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com), andare a [**segnalibri**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Aggiungere un segnalibro o individuare un segnalibro esistente a cui si desidera aggiungere un' **applicazione di alimentazione** .
1. In **Impostazioni segnalibro**, selezionare **Power app**, quindi immettere o incollare l' **ID app**.
    L'altezza e la larghezza vengono regolate automaticamente in base all'orientamento che è stato selezionato quando è stata creata l'applicazione Power. I segnalibri supportano gli orientamenti verticale e orizzontale. L'anteprima del segnalibro mostra una PowerApp completamente funzionante, per renderla semplice da testare.
1. Selezionare **Pubblica** o **Salva come bozza**.
