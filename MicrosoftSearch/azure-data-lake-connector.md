---
title: Connettore Graph Azure Data Lake per Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore di Graph Azure Data Lake Archiviazione Gen2 per Microsoft Search
ms.openlocfilehash: 10bccfc0af144c22f280819d96e21be13ae1c2aad273364499296b6289d3a1e5
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533366"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Connettore di Graph Azure Data Lake Archiviazione Gen2

Il connettore di Graph Azure Data Lake Archiviazione Gen2 consente agli utenti dell'organizzazione di cercare i file archiviati negli account Archiviazione BLOB di [Azure](/azure/storage/blobs/storage-blobs-introduction) e [Azure Data Lake Gen 2 Archiviazione.](/azure/storage/blobs/data-lake-storage-introduction)

> [!NOTE]
> Leggere [**l'articolo Setup your Graph connector**](configure-connector.md) to understand the general Graph connectors setup instructions.

Questo articolo è per chiunque configura, esegue e monitora un connettore Azure Data Lake Archiviazione Gen2. Integra il processo di configurazione generale e mostra le istruzioni che si applicano solo al connettore Azure Data Lake Archiviazione Gen2. In questo articolo sono inoltre incluse informazioni [sulle limitazioni](#limitations).

Nell'articolo viene utilizzato *Archiviazione di Azure* termine generico per Azure [Blob Archiviazione](/azure/storage/blobs/storage-blobs-introduction) e Azure Data Lake [Gen 2 Archiviazione](/azure/storage/blobs/data-lake-storage-introduction).

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nella interfaccia di amministrazione di Microsoft 365

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Passaggio 2: assegnare un nome alla connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: Configurare le impostazioni di connessione

Immettere la stringa di connessione di archiviazione principale. Questa stringa è necessaria per consentire l'accesso all'account di archiviazione. Per trovare la stringa di connessione, passare al [portale di Azure](https://ms.portal.azure.com/#home) e passare alla sezione **Chiavi** dell'account Archiviazione di Azure pertinente.

Se si preferisce non fornire **AccountKey** (un parametro nella stringa di connessione di archiviazione principale), concedere l'accesso al servizio connettori di Graph per i ruoli seguenti:

* Archiviazione Lettore dati BLOB
* Archiviazione Collaboratore dati coda
* Archiviazione Blob Delegar

Passa alla scheda **Controllo di accesso** del tuo account Archiviazione di Azure e segui le istruzioni per concedere l'accesso all'app seguente:

* **ID app di** prima parte: 56c1da01-2129-48f7-9355-af6d59d42766
* **First Party App Name:** Graph Connector Service

### <a name="storage-account-and-queue-notifications-optional"></a>Archiviazione di account e code (facoltativo)

Il supporto per elaborare le modifiche in tempo reale nel Graph connettori potrebbe essere aggiunto in futuro. In tal caso, verranno monitorate le Archiviazione di Azure di modifica archiviate in una coda. Dovrai creare una coda nello stesso account dell'account Archiviazione di Azure account.

Dopo aver creato una coda, passare alla **scheda Eventi** nella pagina della coda per configurare **Sottoscrizione eventi.** Scegliere tutti gli eventi BLOB che la coda riceverà e connettere la coda all Archiviazione di Azure account.

## <a name="step-4-assign-property-labels"></a>Passaggio 4: Assegnare etichette di proprietà

È possibile assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni. Anche se questo passaggio non è obbligatorio, la presenza di alcune etichette di proprietà migliorerà la pertinenza della ricerca e garantirà risultati di ricerca migliori per gli utenti finali.

## <a name="step-5-manage-schema"></a>Passaggio 5: Gestire lo schema

Nella schermata **Gestisci schema** è possibile modificare gli attributi dello schema associati alle proprietà, le opzioni disponibili sono **Query,** **Ricerca,** **Recupera** e **Affina.** È inoltre possibile aggiungere alias facoltativi e scegliere la **proprietà Content.**

## <a name="step-6-manage-search-permissions"></a>Passaggio 6: Gestire le autorizzazioni di ricerca

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Puoi scegliere di inserire gli elenchi di controllo di accesso (ACL) dal tuo account [azure Data Lake Gen 2 Archiviazione.](/azure/storage/blobs/data-lake-storage-introduction) Quando vengono impostate queste autorizzazioni di ricerca, il contenuto della ricerca viene tagliato in base alle autorizzazioni dell'utente che ha eseguito [l'accesso Azure Active Directory](/azure/active-directory/). In alternativa, è possibile scegliere di rendere tutto il contenuto indicizzato dall'account di archiviazione visibile a tutti gli utenti dell'organizzazione. In questo caso, tutti gli utenti dell'organizzazione avranno accesso a tutti i dati nell'account di archiviazione.

Il connettore di Graph Azure Data Lake Archiviazione Gen2 supporta le autorizzazioni di ricerca visibili a **Tutti** o Solo gli utenti con accesso a **questa origine dati.** I dati indicizzati visualizzati nei risultati della ricerca potrebbero essere visibili agli utenti dell'organizzazione che hanno accesso a ogni elemento.

### <a name="azure-blob-storage"></a>Archiviazione BLOB di Azure

Per una connessione a [Blob di Azure Archiviazione](/azure/storage/blobs/storage-blobs-introduction), tutto il contenuto indicizzato dall'origine configurata è visibile a tutti gli utenti dell'organizzazione. Gli elenchi di controllo di accesso non sono supportati a livello di BLOB in Azure Blob Archiviazione.

## <a name="step-7-set-the-refresh-schedule"></a>Passaggio 7: Impostare la pianificazione dell'aggiornamento

Nella schermata **Aggiorna Impostazioni** è possibile impostare l'intervallo di ricerca per indicizzazione incrementale e l'intervallo di ricerca per indicizzazione completo. Gli intervalli predefiniti per il connettore Azure Data Lake Archiviazione Gen2 sono 15 minuti per una ricerca per indicizzazione incrementale e una settimana per una ricerca per indicizzazione completa.

## <a name="step-8-review-connection"></a>Passaggio 8: verificare la connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitazioni

Non è possibile riconfigurare una connessione pubblicata per Archiviazione Blob di Azure per l'origine di Azure Data Lake Archiviazione Gen2 e così via. In questi scenari, è consigliabile configurare una nuova connessione.

Inoltre, le dimensioni dei file devono essere di almeno 4 MB per poter essere sottoposte a ricerca per indicizzazione. I tipi di file attualmente supportati sono:

* Word (docx, docm, dotx, dotm)
* PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)
* Excel (.xlsx, xlsm)
* Formati Office legacy (.doc, dot e così via)
* Testo (.txt)
* HTML
* PDF

I file binari come immagini (.jpg, .bmp e così via) non sono supportati. Ad esempio, se un file .docx contiene solo immagini, potrebbe essere ignorato perché non ha restituito alcun contenuto.