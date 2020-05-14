---
title: Gestire i piani di piano
ms.author: rasrivas
author: rasrivas
manager: tonytha
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: La caratteristica planimetria di Microsoft Search aiuta gli utenti a trovare persone, uffici e altre amenità all'interno di un edificio.
ms.openlocfilehash: c2b148ab1bdb7ff425d5f2b4524e9770f489a92a
ms.sourcegitcommit: d40d44d01b27dfed92577446fe7a30008b28deb4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "42824845"
---
# <a name="manage-floor-plans"></a>Gestire i piani di piano

Planimetrie nella Guida di **Microsoft Search** gli utenti possono trovare persone e sale riunioni all'interno di un edificio. Planimetrie rispondere alle seguenti domande:

- Dove si trova Allan DeYoung ' s Office?
- Edificio 2 piano 3
- Trovare 2/11173

## <a name="add-floor-plans"></a>Aggiungere piani di piano

Seguire questa procedura per configurare le risposte ai piani di piano in **Microsoft Search**.

### <a name="step-1-determine-your-building-codes"></a>Passaggio 1: determinare i codici di costruzione

I codici predefiniti vengono utilizzati come parte di una posizione di Office dell'utente. Questi codici vengono utilizzati per l'aggiornamento dei profili utente. Si supponga che l'organizzazione disponga di un edificio in questa posizione: *Building 2, 350 5th Avenue, New York City, NY 10016*

Di seguito sono riportati alcuni esempi validi per il codice di questo edificio: 2, B2, Building2, Building 2 o NYCB2. Ogni edificio deve disporre di un codice univoco.

### <a name="step-2-review-your-floor-plans"></a>Passaggio 2: esaminare le planimetrie

I file planimetrici devono essere in formato DWG; I file DWG possono contenere etichette di testo. Quando un'etichetta di testo contrassegna una stanza, viene definita etichetta della sala. Il file DWG deve disporre **di almeno 10 sale** contrassegnate con etichette. Di seguito sono riportati alcuni esempi di file DWG con tipi di etichette diversi:

|**Etichette di testo incluse le etichette delle sale**|**Etichette di testo ma senza etichette sala**|**Nessuna etichetta di testo**|
|:-----:|:-----:|:-----:|
|![floorplans-textandroomlabels. png](media/floorplans-textandroomlabels.png)|![floorplans-textnoroomlabels. png](media/floorplans-textnoroomlabels.png)|![floorplans-nolabels. png](media/floorplans-nolabels.png)|

Per informazioni sulla visualizzazione e l'aggiornamento dei file DWG, vedere la sezione [FAQ](#frequently-asked-questions) .

### <a name="step-3-update-office-locations-on-user-profiles"></a>Passaggio 3: aggiornare i percorsi di Office nei profili utente

L'ubicazione dell'ufficio di un utente è una combinazione di un codice edilizio e di un'etichetta sala. Ad esempio, se il codice di costruzione è *2* e l'etichetta della sala è *1173*, la posizione di Office sarebbe *2/1173*.

Aggiungere o aggiornare le posizioni di Office per ogni utente dell'organizzazione. È possibile modificare il percorso di Office nel profilo utente nell'interfaccia di [Amministrazione](https://admin.microsoft.com) di Microsoft 365 oppure cambiare in Active Directory locale per la sincronizzazione in Azure Active Directory. *PhysicalDeliveryOfficeName* è il campo utilizzato per la posizione di Office. Se le etichette delle chat room non includono i numeri di piano, vedere le domande frequenti sui suggerimenti.

In questo esempio, l'ufficio di Allan è nella sala 1173 al piano 1 dell'edificio 2.
![floorplans-userlestview. png](media/floorplans-userlistview.png)

> [!NOTE]
> Per visualizzare le posizioni di Office aggiornate durante la ricerca di planimetrie, è necessario aggiornare le posizioni di Office per **almeno 10 persone** su ogni piano.

### <a name="step-4-verify-office-location"></a>Passaggio 4: verificare la posizione di Office

Utilizzare **Microsoft Search** per trovare un utente e verificare che la posizione dell'ufficio venga visualizzata correttamente. Se le posizioni sono appena aggiornate, potrebbe essere necessario attendere fino a **72 ore** affinché gli aggiornamenti vengano visualizzati nei risultati della ricerca.

![floorplans-peoplecard. png](media/floorplans-peoplecard.png)

### <a name="step-5-add-building-locations"></a>Passaggio 5: aggiungere percorsi di compilazione

Planimetrie utilizza le [posizioni](manage-locations.md) per definire gli edifici. Nell'interfaccia di [Amministrazione](https://admin.microsoft.com)di Microsoft 365, andare a **Settings**  >  **Microsoft Search**  >  **locations**, quindi selezionare **Aggiungi**. Immettere il nome, l'indirizzo e le parole chiave per l'edificio. Aggiungere il numero di edifici necessari.

![floorplans-locations. png](media/floorplans-locations.png)

Per ulteriori informazioni sulle posizioni, vedere [Manage locations](manage-locations.md)

### <a name="step-6-gather-and-organize-office-locations"></a>Passaggio 6: raccogliere e organizzare percorsi di Office

Prima di poter utilizzare planimetrie, le posizioni di Office devono essere indicizzate. Si tratta di un'operazione di una tantum che può richiedere fino a 48 ore per il completamento. Il tempo totale dipenderà dalle dimensioni dell'organizzazione.

In interfaccia di [Amministrazione](https://admin.microsoft.com), andare a **Impostazioni**  >  piano di**ricerca di Microsoft Search**  >  **Floor plans**, quindi selezionare **inizia**. Se non viene visualizzato questo avviso, questo passaggio è già stato completato per l'organizzazione

![floorplans_hydrationstep. png](media/floorplans_hydrationstep.png)

### <a name="step-7-upload-floor-plans"></a>Passaggio 7: caricare planimetrie

1. Nell'interfaccia di [Amministrazione](https://admin.microsoft.com), passare a **Impostazioni**  >  piano di**ricerca di Microsoft Search**  >  **Floor plans**, quindi selezionare **Aggiungi**.
2. Selezionare un edificio nell'elenco a discesa e quindi fare clic su **Avanti**. Se l'edificio non è elencato, tornare indietro e [aggiungere le posizioni degli edifici](#step-5-add-building-locations).
3. Selezionare **Carica file**e quindi scegliere la planimetria da caricare.
4. Al termine del caricamento, è necessario immettere il numero di piano rappresentato nel file planimetria. Quindi, scegliere **Avanti**.
5. Optional Se il tuo piano ha ali o zone, Inserisci quel dettaglio.
6. Immettere il codice predefinito per la planimetria. Il codice di costruzione può essere trovato nella proprietà posizione di Office degli utenti. Ad esempio, se l'ubicazione dell'ufficio di un utente è **2/1173**, il codice di costruzione è **2**.
7. Optional Esaminare e identificare i modelli di posizione per tutti i piani di pavimento caricati e quindi selezionare **Avanti**.
8. Verrà visualizzata una schermata di revisione in cui viene elencato il numero di percorsi di Office mappati alle planimetrie. Selezionare **Dettagli** per assicurarsi che il mapping sia corretto.
9. Quando si è pronti, selezionare **pubblica** per rendere disponibile la planimetria in **Microsoft Search**.

> [!NOTE]
> **Sono necessarie 48 ore per la pubblicazione delle planimetrie.** Dopo di che gli utenti visualizzeranno un piano di base simile a quello riportato di seguito quando eseguono la ricerca di un ufficio del collega.

![floorplans-OfficeLocation. png](media/floorplans-officelocation.png)

### <a name="step-8-optional-specify-location-patterns"></a>Passaggio 8: (facoltativo) specificare i modelli di posizione

Dopo aver caricato una planimetria, le etichette di testo verranno confrontate con le posizioni di Office nei profili degli utenti. Se sono presenti meno di 10 corrispondenze, viene visualizzata la schermata **specifica percorsi percorso** . I modelli di posizione vengono utilizzati per estrarre le informazioni relative a pavimento, ala e sala dalle posizioni di Office.

![floorplans-locationpattern. png](media/floorplans-locationpattern.png)

È richiesta solo la sala, il piano e l'ala sono facoltativi ed è possibile ignorare le posizioni in base alle esigenze.

## <a name="edit-floor-plans"></a>Modificare i piani di piano

Per aggiornare una planimetria esistente, selezionare la planimetria che si desidera modificare e quindi fare clic su **modifica**. Apportare le modifiche e salvarle.

## <a name="troubleshooting"></a>Risoluzione dei problemi

|**Fase**
|**Messaggio di errore**|**Tipo**|**Azione**|
|:-----|:-----|:-----|:-----|
|Caricare planimetrie|Impossibile leggere CC_1. dwg. Ricaricare o eliminare la planimetria.|Error|Provare a caricare di nuovo il file. Se non funziona, eliminare il file e riprovare.|
|Caricare planimetrie|Sono disponibili due file denominati CC_1. dwg. Si prega di eliminare uno di essi o di ricaricare con un altro nome.|Error|Se il nome del file non è corretto, rendere il nome del file univoco aggiungendo informazioni su piano o ala e quindi caricare di nuovo il file. Se è stato aggiunto per sbaglio lo stesso file due volte basta eliminarlo.|
|Caricare planimetrie|Nessun dato trovato.|Error|Controllare il file per assicurarsi che sia quello corretto e quindi caricarlo di nuovo oppure eliminarlo.|
|Caricare planimetrie|I riferimenti esterni sono mancanti in questo file. Caricare CC_1_furniture. DWG o eliminare il file.|Avviso|Caricare i file di riferimento esterni o eliminare.|
|Caricare planimetrie|Non è stato possibile leggere i numeri o i tag delle sale nel file DWG. Eliminare il file.|Avviso|Controllare il file DWG per assicurarsi che i dati siano inclusi e quindi eliminare il file e riprovare.|
|Collegamento tra percorsi di Office|Nessuna posizione di Office trovata in AAD. Aggiungere i dati della posizione a AAD prima di impostare planimetrie.|Error|[Aggiornare le posizioni di Office nei profili utente](#step-3-update-office-locations-on-user-profiles) |

## <a name="frequently-asked-questions"></a>Domande frequenti

**D:** Come visualizzare e modificare i file DWG?

**A:** Utilizzare una o più delle seguenti opzioni per visualizzare i file DWG:

- Caricare il file in SharePoint e aprirlo.
- Aprire il file in [Microsoft Visio](https://support.office.com/article/Open-insert-convert-and-save-DWG-and-DXF-AutoCAD-drawings-60cab691-0f4c-4fc9-b775-583273c8dac5) o [Autodesk DWG TrueView](https://www.autodesk.com/products/dwg).
- Caricare il file su [Autodesk online Viewer](https://viewer.autodesk.com/).

**D:** Come si aggiungono le etichette di testo alle sale non contrassegnate?

**A:** Aprire il file DWG in un editor e [aggiungere le etichette della sala](https://knowledge.autodesk.com/support/autocad-map-3d/learn-explore/caas/CloudHelp/cloudhelp/2019/ENU/MAP3D-Learn/files/GUID-4854F184-6279-4E0C-9487-34A4759017F6-htm.html).

**D:** Come creare o modificare file DWG a scopo di testing?

**A:** Creare un file DWG in Microsoft Visio, Autodesk AutoCAD o qualsiasi altro editor DWG. Verificare che 10 o più sale siano etichettate nel file.

**D:** * * qual è il formato migliore per le etichette di testo nei file DWG?

**A:** Per ottenere risultati ottimali, le etichette di testo devono contenere numeri di piano e numeri di stanza. Negli esempi riportati di seguito viene utilizzato 2 o SC per il codice di costruzione.
<!-- markdownlint-disable no-inline-html -->
|Tipi di etichetta sala|Piano|Room|Etichetta di testo di esempio|Posizione di Office (codice di costruzione/etichetta di testo)|
|:-----|:-----|:-----|:-----|:-----|
|Ha il piano e il numero della sala|1 |173|1173|2/1173|
|| 21|45|21045|2/21045|
||23|100K|23-100K|2/23-100K|
||1 |G06-07|1G06-07|2/1G06-07|
||2 |1024A|02.1024 a|2/02.1024 a|
||2 |1024A|02.1024 a|2/02.1024 a|
||2 |105,01|2105,01|2/2105.01|
|Contiene codice di costruzione, piano e numero di sala|0|X-11-M-12|2-0-X-11-M-12|2/2-0-X-11-M-12<br/>2-0-X-11-M-12|
||2 |128A|22128A|2/22128A<br/>22128A|
||1 |B2-11|21-B2-11|2/21-B2-11<br/>21-B2-11|
||2 |45|SC2045|SC/SC2045<br/>SC2045|

**D:** È possibile utilizzare un file DWG che non include I numeri di piano?

**A:** Sì, è possibile. Quando si aggiornano le posizioni di Office nel profilo AAD dell'utente, includere il numero di piano come parte del numero di stanza, anche se non è presente nel file DWG. Dopo aver caricato il file, viene visualizzata la schermata Specifica percorso modelli che consente di indicare entrambi i valori.

Ad esempio, un file DWG che include numeri di stanza, ma senza numeri di piano, può essere simile al seguente:

![floorplans-nofloors. png](media/floorplans-nofloors.png)

La posizione di Office nel profilo dell'utente deve essere 2/1175, dove ' 2' è il codice dell'edificio,' 1' è il numero di piano è 175' è il numero della sala.
