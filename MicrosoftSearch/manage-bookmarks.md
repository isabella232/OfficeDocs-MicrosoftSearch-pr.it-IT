---
title: Gestire i segnalibri
ms.author: anfowler
author: adefowler
manager: mnirkhe
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
ms.openlocfilehash: b65e61e4435e36fad5760f0a8d34bf444b51178b
ms.sourcegitcommit: ef1eb2bdf31dccd34f0fdc4aa7a0841ebd44f211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2019
ms.locfileid: "39663145"
---
# <a name="manage-bookmarks"></a>Gestire i segnalibri

È possibile creare un segnalibro in pochi passaggi. Ogni segnalibro include un titolo, URL e un set di parole chiave di attivazione. Un segnalibro può contenere diverse parole chiave e più segnalibri possono condividere la stessa parola chiave, ma la parola chiave riservata non può essere condivisa. Quando si crea o modifica un segnalibro, l'indice di ricerca viene immediatamente aggiornato e il segnalibro è reso subito disponibile agli utenti.

Se nell'organizzazione sono stati promossi i risultati configurati in SharePoint, è possibile importare i risultati promossi in **Microsoft Search** e rendere il contenuto importato disponibile per gli utenti. Si tratta di un modo semplice per inserire rapidamente i risultati della ricerca quando si configura **Microsoft Search** e renderlo più efficiente per gli utenti. È consigliabile usare i risultati alzati di livello di SharePoint come riferimento per determinare come assegnare un nome e creare i risultati della ricerca rilevanti. 

## <a name="add-or-edit-a-single-bookmark"></a>Aggiungere o modificare un singolo segnalibro
1. Passare all'**interfaccia di amministrazione di Microsoft 365**.
1. Nel riquadro di spostamento passare a **Impostazioni** e quindi selezionare **Microsoft Search**.
Per impostazione predefinita, è già selezionata la scheda **Segnalibri**.
1. Per aggiungere un segnalibro, selezionare **Aggiungi nuovo**. Per modificare un segnalibro, selezionarlo nell'elenco di segnalibri pertinente. 
1. Quando si aggiungono o modificano le informazioni, l'anteprima viene aggiornata automaticamente.
1. Salvare le modifiche.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Aggiungere o modificare il segnalibro usando le estensioni del browser
Gli amministratori della ricerca possono creare facilmente contenuti di ricerca usando le estensioni del browser. Installare l'estensione del browser e quindi passare al sito per aggiungerlo come segnalibro.

Le estensioni dei browser sono attualmente disponibili per Microsoft Edge e Chrome. 
- Per scaricare l'estensione di Microsoft Edge, passare a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) e scaricare l'app.
- Per scaricare l'estensione di Chrome, passare al [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) e scaricare l'app.

## <a name="bulk-add-or-edit-bookmarks"></a>Aggiungere o modificare in blocco i segnalibri
L'amministratore della ricerca può usare le funzionalità di importazione o esportazione per creare o modificare in blocco i segnalibri. È una funzionalità molto utile quando si vuole aggiungere o modificare un numero elevato di segnalibri. 

Usare la funzionalità di importazione/esportazione per:
- Aggiungere segnalibri in blocco: aggiungere i dettagli nel file modello del segnalibro e quindi importarlo.
- Modificare i segnalibri in blocco: esportare i segnalibri in un file CSV, quindi modificare i dettagli del segnalibro nel file CSV esportato e infine importare il file CSV aggiornato.
- Importare i siti alzati di livello da SharePoint.
- Eseguire il backup dei segnalibri: esportare i segnalibri in un file CSV.

Per importare o esportare segnalibri:
1. In alto a destra della scheda **Segnalibri**, selezionare **Importa**. Selezionare **Esporta** per scaricare tutti i segnalibri esistenti in un file CSV.
1. Nel riquadro destro, scegliere l'opzione per importare con un file CSV o da SharePoint.
Scaricare il file modello per un elenco di campi obbligatori e i dettagli. 
1. Aggiungere o modificare i dettagli del segnalibro nel file modello e quindi salvarlo nel computer. 
1. Nel riquadro **Importa segnalibri**, selezionare **Sfoglia** e quindi il file CSV da importare.
1. Selezionare **Importa**.

Ecco alcuni punti importanti da tenere presenti per il file modello:
- Non modificare i dati in questi campi: *Id*, *Data ultima modifica* e *Autore ultima modifica*
- Se si include l'*Id* di un segnalibro esistente, verrà sostituito con le informazioni presenti nel file di importazione.
- Se esiste un segnalibro con lo stesso titolo o URL, il segnalibro verrà aggiornato con le informazioni nel file di importazione.
- Non tutti i campi sono obbligatori nel file modello e i campi obbligatori variano in base allo stato del segnalibro.
- In base al campo *Stato*, i segnalibri saranno salvati come bozza, suggeriti o pianificati, oppure saranno pubblicati direttamente.
- Per i partner che gestiscono più organizzazioni, è possibile esportare i segnalibri da un'organizzazione e importarli in un altro. È tuttavia necessario rimuovere i dati dalla colonna *Id* prima di importarli.

### <a name="prevent-import-errors"></a>Evitare gli errori di importazione
Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore e viene generato un file di log con altre informazioni sulle righe e sulle colonne da correggere. Apportare le modifiche necessarie e riprovare l'importazione del file. Non è possibile importare o salvare alcun segnalibro finché non saranno stati risolti tutti gli errori.

Per evitare errori, verificare che il file di importazione sia formattato correttamente e che:

- Includa la riga di intestazione e tutte le colonne presenti nel modello di importazione
- L'ordine delle colonne equivalga a quello del modello di importazione
- Tutte le colonne contengano valori, a eccezione di tre colonne che possono essere vuote: *Id*, *Data ultima modifica* e *Autore ultima modifica* 
- La colonna *Stato* non è vuota, perché si tratta di informazioni obbligatorie

Per evitare errori di duplicazione dei segnalibri tra segnalibri, eseguire le procedure consigliate seguenti:
- Non utilizzare URL duplicati per segnalibri diversi. Se un URL è già stato assegnato a un altro segnalibro e lo si aggiunge di nuovo da un file di importazione, verrà visualizzato un messaggio di errore. Questo vale anche per gli URL duplicati di altri tipi di risposte.
- Utilizzare la colonna *ID segnalibro* per l'aggiornamento dei segnalibri esistenti. È possibile aggiornare qualsiasi altra proprietà di un segnalibro esistente, ad esempio una parola chiave o una descrizione, ma è necessario verificare che l' *ID del segnalibro* si trovi nella colonna appropriata del file di importazione. Se l' *ID del segnalibro* è presente, il servizio non lo considererà come nuova aggiunta e non verrà trattato come un errore.

## <a name="powerapps"></a>PowerApps
È possibile aiutare gli utenti a completare le attività, ad esempio immettere ferie o segnalare le spese, aggiungendo le PowerApp esistenti ai segnalibri. 

### <a name="what-are-powerapps"></a>Cosa sono le PowerApp?
PowerApps è un servizio che consente di creare applicazioni aziendali che vengono eseguite in un browser o in un telefono o tablet senza richiedere esperienza di programmazione. PowerApps funziona con qualsiasi browser e su qualsiasi dispositivo e l’aggiunta richiede meno di un minuto. Per altre informazioni su PowerApps, vedere:
- [Formazione guidata](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [Documentazione](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Home page di PowerApps](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Aggiungere una PowerApp a un segnalibro
1. Trovare l'[ID di applicazione per la PowerApp](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) da aggiungere.
1. Accedere e passare all'**interfaccia di amministrazione di Microsoft 365**.
1. Nel riquadro di spostamento passare a **Impostazioni** e quindi selezionare **Microsoft Search**.
1. Aggiungere un segnalibro o trovare un segnalibro esistente a cui si vuole aggiungere una **PowerApp**.
1. In **Impostazioni Segnalibro**, selezionare **PowerApp** e quindi **Aggiungi una PowerApp**.
1. Immettere o incollare l'**ID dell’app**.
    Vengono regolate automaticamente l'altezza e la larghezza. I segnalibri possono supportare orientamento orizzontale e verticale, ma attualmente non è possibile modificare le dimensioni. L'anteprima del segnalibro mostra una PowerApp completamente funzionante, per renderla semplice da testare.
1. Selezionare **Pubblica** o **Salva come bozza**.
