---
title: Connettore Azure Data Lake per Microsoft Search
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore Azure Data Lake Storage Gen2 per Microsoft Search
ms.openlocfilehash: 8891c9a1fdf5397c397a941b5131f014db9e7a54
ms.sourcegitcommit: 597c338bf9c1c425747ac74a9a1ae57c5e8957ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49920723"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Connettore Azure Data Lake Storage Gen2

Con il connettore Azure Data Lake Storage Gen2, gli utenti dell'organizzazione possono cercare i file archiviati negli account di archiviazione BLOB di [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e azure [Data Lake Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

Questo articolo è per gli amministratori di [Microsoft 365](https://www.microsoft.com/microsoft-365) o chiunque configura, esegue e monitora un connettore Azure Data Lake Storage Gen2. Offre una panoramica della configurazione del connettore, delle funzionalità, delle limitazioni e delle tecniche di risoluzione dei problemi. Nell'articolo viene utilizzato *Archiviazione di Azure* come termine generico per Archiviazione BLOB di [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e Archiviazione Azure Data Lake [Gen 2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati

### <a name="primary-storage-connection-string"></a>Stringa di connessione di archiviazione principale

Nella schermata **Autenticazione e configurazione** specificare la stringa di connessione di archiviazione principale. Tale stringa è necessaria per consentire l'accesso all'account di archiviazione. Per trovare la stringa di connessione, passare al portale [di Azure](https://ms.portal.azure.com/#home) e passare alla **sezione** Chiavi dell'account di archiviazione di Azure pertinente. Copiare e incollare la stringa di connessione nel campo appropriato sullo schermo.

Se non si preferisce fornire **AccountKey** (un parametro nella stringa di connessione di archiviazione principale), sarà necessario concedere l'accesso al servizio connettori Graph per i ruoli seguenti. Questa funzionalità è supportata solo per l'archiviazione gerarchica. L'archiviazione BLOB tradizionale dovrà fornire AccountKey.
* Lettore dati BLOB di archiviazione
* Collaboratore dati coda di archiviazione
* Delegatore BLOB di archiviazione

Passare alla scheda **Controllo di accesso** dell'account di archiviazione di Azure e seguire le istruzioni per concedere l'accesso all'app seguente:

* ID app di prima **parte:** 56c1da01-2129-48f7-9355-af6d59d42766
* **Nome app di prima parte:** Servizio connettore grafico

### <a name="storage-account-and-queue-notifications-optional"></a>Notifiche sull'account di archiviazione e sulla coda (facoltativo)

Il supporto per elaborare le modifiche in tempo reale nel servizio connettori graph potrebbe essere aggiunto in futuro. In tal caso, verranno monitorate le notifiche di modifica di Archiviazione di Azure archiviate in una coda. Dovrai creare una coda nello stesso account dell'account di archiviazione di Azure.

Dopo aver creato una coda, passare alla scheda **Eventi** nella pagina della coda per configurare la **sottoscrizione di evento.** Scegliere tutti gli eventi BLOB che la coda riceverà e connettere la coda all'account di archiviazione di Azure.

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Nella schermata **Gestisci autorizzazioni di** ricerca è possibile scegliere di inserire gli elenchi di controllo di accesso (ACL) dall'account di archiviazione di Azure Data Lake Gen [2.](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) Quando queste autorizzazioni di ricerca sono impostate, il contenuto della ricerca viene tagliato in base alle autorizzazioni assegnate all'utente di [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) connesso che esegue la ricerca nel contenuto. In alternativa, è possibile scegliere di rendere tutto il contenuto indicizzato dall'account di archiviazione visibile a tutti gli utenti dell'organizzazione. In questo caso, tutti gli utenti dell'organizzazione avranno accesso a tutti i dati nell'account di archiviazione.

### <a name="azure-blob-storage"></a>Archiviazione BLOB di Azure

Per una connessione [all'archiviazione BLOB di Azure,](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)tutto il contenuto indicizzato dall'origine configurata è visibile a tutti gli utenti dell'organizzazione. Gli elenchi di controllo di accesso non sono supportati a livello blob in Archiviazione BLOB di Azure.

## <a name="search-permissions"></a>Autorizzazioni di ricerca

Il connettore Azure Data Lake Storage Gen2 supporta le autorizzazioni di ricerca visibili per **tutti** gli utenti o solo per gli utenti con **accesso a questa origine dati.** I dati indicizzati visualizzati nei risultati della ricerca potrebbero essere visibili a tutti gli utenti dell'organizzazione o solo agli utenti che hanno accesso a ogni elemento.

## <a name="assign-property-labels"></a>Assegnare etichette di proprietà

Puoi assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni. Anche se questo passaggio non è obbligatorio, la presenza di alcune etichette di proprietà migliorerà la pertinenza della ricerca e garantirà risultati di ricerca più accurati per gli utenti finali.

## <a name="manage-schema"></a>Gestire lo schema

Nella schermata Gestisci **schema** è possibile modificare gli attributi dello schema **(** disponibili per **query,** **ricercabili,** recuperabili e per affinamento **ricerca)** associati alle proprietà, aggiungere alias facoltativi e scegliere la proprietà **Content.**

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione dell'aggiornamento

Nella schermata **Impostazioni aggiornamento è** possibile impostare l'intervallo di ricerca per indicizzazione incrementale e l'intervallo di ricerca per indicizzazione completa. Gli intervalli predefiniti per il connettore Azure Data Lake Storage Gen2 sono di 15 minuti per una ricerca per indicizzazione incrementale e di una settimana per una ricerca per indicizzazione completa.

## <a name="limitations"></a>Limitazioni

Una connessione pubblicata per l'archiviazione BLOB di Azure non può essere riconfigurata per l'origine di Azure Data Lake Storage Gen2 e viceversa. In questi scenari, è consigliabile configurare una nuova connessione.
