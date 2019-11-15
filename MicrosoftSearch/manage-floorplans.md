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
ms.openlocfilehash: 9871cda3790f210dc0c406d1d29abe2c571c1085
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626793"
---
# <a name="manage-floor-plans"></a>Gestire i piani di piano

Le planimetrie di Microsoft Search aiutano gli utenti a trovare persone e sale riunioni all'interno di un edificio. Planimetrie rispondere a queste domande:
- Dove si trova Allan DeYoung ' s Office?
- Dove si trova la sala riunioni C1?

![Planimetria che individua la posizione dell'ufficio dell'utente all'interno dell'edificio.](media/floorplans-officelocation.png)

Per semplificare la ricerca di risposte a domande di questo tipo, è necessario che informazioni sugli edifici, gli uffici e le strutture di un'organizzazione debbano essere disponibili e reperibili. Le organizzazioni di grandi dimensioni hanno in genere strutture o team di gestione dello spazio e potrebbero essere già disponibili per queste informazioni. In un'organizzazione di dimensioni ridotte, potrebbe essere necessario creare e aggiungere l'amministratore della ricerca.

## <a name="48-hours-before-you-begin"></a>48 ore prima di iniziare
Prima di iniziare a caricare planimetrie, è necessario indicizzare le posizioni di Office degli utenti. A seconda delle dimensioni dell'organizzazione, è possibile richiedere fino a 48 ore per il completamento. Se si ignora questo passaggio, viene visualizzato un errore durante l'esecuzione della procedura.

![Schermata di acquisizione della pagina planimetrie con "Microsoft ha bisogno di raccogliere e organizzare le posizioni di Office prima di poter caricare i piani di piano".](media/floorplans_hydrationstep.png)

Nell'interfaccia di [Amministrazione](https://admin.microsoft.com)di Microsoft 365, passare a **Impostazioni** > **piani**di**ricerca di Microsoft Search** > , quindi selezionare **inizia**.

Se non viene visualizzato questo avviso, l'utente o un utente dell'organizzazione ha già avviato questo passaggio.

## <a name="things-to-consider"></a>Osservazioni
Per consentire agli utenti di trovare informazioni su uffici e strutture di creazione, è necessario aggiungere:

|Considerazione     |Ma perché è così importante?  |
|---------|---------|
|Posizione dell'edificio    |    È necessario aggiungere ogni edificio nei percorsi di ricerca di Microsoft. Per ogni edificio dovrebbe essere presente un formato di denominazione standard. È possibile aggiungere l'edificio utilizzando un indirizzo o le coordinate della mappa.     |
|Proprietà di **Office** in tutti gli account utente     |    Ogni account utente deve disporre della proprietà **Office** con il relativo percorso di Office. E le posizioni degli uffici devono seguire un formato standard e includere informazioni su edifici, pavimenti e sale.   <br> In Azure AD, questa proprietà è denominata **PhysicalDeliveryOfficeName**.    |
|File planimetria in formato DWG     |   È necessario disporre di una planimetria separata per ogni piano o ala dell'edificio e includere le informazioni di Office nello stesso formato utilizzato nella proprietà Office dell'utente. Il file deve essere nel formato DWG di disegno AutoCAD. |

Per ulteriori informazioni, vedere [procedure consigliate per i piani di ricerca di Microsoft Search](floorplans-bestpractices.md).

## <a name="building-location"></a>Posizione dell'edificio

Identificare gli edifici che devono essere aggiunti come percorsi. L'indirizzo della posizione e le coordinate della mappa di un edificio sono il primo punto di identificazione. Se l'edificio non è ancora stato aggiunto come percorso, l'amministratore deve aggiungerlo. Per ulteriori informazioni, vedere [Manage locations](manage-locations.md) .

## <a name="floor-plans-files"></a>File planimetrie

Dopo l'identificazione di un edificio, è possibile aggiungerne le planimetrie. Tutti i file planimetrici devono essere in formato DWG. Se l'organizzazione non è già in uso, è necessario creare le planimetrie in un'app compatibile con DWG. Le planimetrie devono mappare correttamente tutte le sale, incluse le sale conferenze o riunioni, i servizi igienici, le cucine, le sale di posta e altre strutture su ogni piano dell'edificio per abilitare la ricerca.

### <a name="office-locations"></a>Percorsi di Office

Per essere mappato a planimetrie, tutte le posizioni di Office e i dati di Office dei dipendenti devono essere nell'account dell'utente. Nella planimetria, i percorsi di Office devono essere univoci e non possono essere ripetuti. Ad esempio, se due persone condividono Office 2/1173, **2/1173** può avere solo un'istanza univoca nelle planimetrie, ma gli account utente in Azure ad avranno la stessa posizione di Office.

![floorplans-peoplecard. png](media/floorplans-peoplecard.png)

 > [!Note] 
 > Quando un utente cerca una posizione in una stanza o in un'ufficio di un collega, i numeri di sala nei piani di pavimento vengono confrontati con le posizioni di Office in Azure AD. Se viene trovata una corrispondenza, viene mostrata la mappa.

## <a name="add-floor-plan"></a>Aggiungere una planimetria

 La prima volta che si passa a un piano, potrebbe essere visualizzata una nota nella parte superiore della pagina che indica che *Microsoft deve raccogliere e organizzare le posizioni di Office prima di poter caricare i piani*di base. Selezionare iniziare a indicizzare le posizioni di **Azure ad Office** . 

1. Nell'interfaccia [di amministrazione](https://admin.microsoft.com), passare a **Impostazioni** > **piani**di**Microsoft Search** >, quindi selezionare **Aggiungi planimetrie**.
4. Selezionare l'edificio nell'elenco a discesa e quindi fare clic su **Avanti**. Se l'edificio non è elencato, è necessario aggiungerlo nelle posizioni. Per altre informazioni, vedere [Manage locations](manage-locations.md) .
6. Selezionare **Carica file**e quindi selezionare la planimetria che si desidera caricare. 
1. Dopo aver eseguito il caricamento del file, è necessario identificare il numero di piano o l'ala rappresentata. 
7. Immettere il codice che identifica l'edificio. Il codice dell'edificio può essere trovato nell'account dell'utente nella proprietà **posizione di Office** . Ad esempio, se l'ubicazione dell'ufficio dell'utente è **2/1173**, il codice di compilazione è **2**. 
9. Esaminare e identificare i modelli di posizione per tutti i piani di pavimento caricati, quindi selezionare **Avanti**.
10. Quando si è pronti, selezionare **pubblica** per rendere ricercabile la planimetria.

> [!Note] 
> Quando una planimetria si trova in uno stato di sformo, è incompleta. Una bozza consente alle parti interessate di coordinare il caricamento e la creazione di planimetrie. Consente inoltre di distribuire piani di piano in fasi.

## <a name="edit-floor-plans"></a>Modificare i piani di piano

1. Nell'interfaccia di [Amministrazione](https://admin.microsoft.com), passare a **Impostazioni** > **piani**di**ricerca di Microsoft Search** > . 
1. Selezionare **pubblicato** o **bozza**, selezionare la planimetria che si desidera modificare e quindi scegliere **modifica**.
5. Apportare le modifiche, quindi selezionare **Salva**.

## <a name="troubleshoot-errors"></a>Risoluzione dei problemi relativi agli errori

Non è possibile passare al passaggio successivo della definizione di informazioni su piano, ala e sala finché non vengono corretti tutti gli errori. Nella tabella seguente sono elencati i messaggi di errore per il caricamento dei file e le azioni per risolvere i problemi.

| Messaggio di errore   | Tipo    | Azione       |
|:----------------| :--------- | :-------------- |
| Impossibile leggere CC_1. dwg. Ricaricare o eliminare la planimetria. | Errore |  Provare a caricare di nuovo il file. Se non funziona, eliminare il file e quindi riprovare. |
| Sono disponibili due file denominati CC_1. dwg. Si prega di eliminare uno di essi o di ricaricare con un altro nome.| Errore | Se il nome del file non è corretto, rendere il nome del file univoco aggiungendo informazioni su piano o ala e quindi caricare di nuovo il file. <br><br>Se lo stesso file è stato aggiunto due volte per sbaglio, è sufficiente eliminarlo. |
| Nessun dato trovato. | Errore | Controllare il file per assicurarsi che sia quello corretto, quindi caricarlo di nuovo oppure eliminarlo. |
| I riferimenti esterni sono mancanti in questo file. Caricare "CC_1_furniture. dwg" o eliminare il file. | Avviso | Caricare i file di riferimento esterni o eliminare.|
| Non è stato possibile leggere i numeri o i tag delle sale nel file DWG. Eliminare il file. | Avviso | Controllare il file DWG per assicurarsi che siano inclusi i dati, quindi eliminare il file e riprovare. |
