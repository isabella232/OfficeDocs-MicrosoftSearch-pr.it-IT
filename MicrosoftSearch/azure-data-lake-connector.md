---
title: Azure Data Lake Connector per Microsoft Search
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
description: Configurare il connettore Gen2 di Azure Data Lake storage per Microsoft Search
ms.openlocfilehash: 860c923c62495c7df20152fb530797e390949305
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367587"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Connettore Gen2 di archiviazione di Azure Data Lake

Con il connettore Gen2 di Azure Data Lake storage, gli utenti dell'organizzazione possono cercare i file archiviati nell' [archiviazione BLOB di Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e negli account di [archiviazione di Azure Data Lake gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) .

Questo articolo è per gli amministratori di [Microsoft 365](https://www.microsoft.com/microsoft-365) o per tutti coloro che configurano, eseguono e monitorano un connettore di Gen2 di archiviazione di Azure Data Lake. Viene fornita una panoramica delle tecniche di configurazione, funzionalità, limitazioni e risoluzione dei problemi del connettore. Nell'articolo viene utilizzato lo *spazio di archiviazione di Azure* come termine generico per l'archiviazione BLOB di [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) e l' [archiviazione di Azure Data Lake gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati

### <a name="primary-storage-connection-string"></a>Stringa di connessione di archiviazione principale

Nella schermata **autenticazione e configurazione** fornire la stringa di connessione di archiviazione principale. Tale stringa è necessaria per consentire l'accesso all'account di archiviazione. Per trovare la stringa di connessione, passare al [portale di Azure](https://ms.portal.azure.com/#home) e passare alla sezione **Keys** dell'account di archiviazione di Azure pertinente. Copiare e incollare la stringa di connessione nel campo appropriato sullo schermo.

Se non si preferisce fornire il **AccountKey** (un parametro nella stringa di connessione di archiviazione principale), è necessario concedere l'accesso al servizio dei connettori grafico per i ruoli seguenti.

* Lettore dati BLOB di archiviazione
* Collaboratore dati coda di archiviazione
* Delegante BLOB di archiviazione (solo per l'archiviazione gerarchica)

Passare alla scheda **controllo di accesso** dell'account di archiviazione di Azure e seguire le istruzioni riportate per concedere l'accesso all'app seguente:

* **ID app per la prima parte:** 56c1da01-2129-48f7-9355-af6d59d42766
* **Nome dell'app per la prima parte:** Servizio del connettore grafico

### <a name="storage-account-and-queue-notifications-optional"></a>Account di archiviazione e notifiche di coda (facoltativa)

Il supporto per l'elaborazione delle modifiche in tempo reale nel servizio dei connettori del grafico potrebbe essere aggiunto in futuro. In tal caso, verranno monitorate le notifiche di modifica di archiviazione di Azure memorizzate in una coda. Sarà necessario creare una coda nello stesso account dell'account di archiviazione di Azure.

Dopo aver creato una coda, passare alla scheda **eventi** della pagina coda per configurare la **sottoscrizione di eventi**. Scegliere tutti gli eventi BLOB che la coda riceverà e connettere la coda all'account di archiviazione di Azure.

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake gen 2

Nella schermata **Gestisci autorizzazioni di ricerca** è possibile scegliere di ingerire gli elenchi di controllo di accesso (ACL, Access Control List) dall'account di [archiviazione di Azure Data Lake gen 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) . Quando vengono impostate queste autorizzazioni di ricerca, il contenuto della ricerca viene ritagliato in base alle autorizzazioni assegnate all'utente di [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) con accesso che esegue la ricerca nel contenuto. In alternativa, è possibile scegliere di rendere tutto il contenuto indicizzato dall'account di archiviazione visibile a tutti gli utenti dell'organizzazione. In questo caso, tutti gli utenti dell'organizzazione avranno accesso a tutti i dati dell'account di archiviazione.

### <a name="azure-blob-storage"></a>Archiviazione BLOB di Azure

Per una connessione all' [archiviazione BLOB di Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), tutti i contenuti indicizzati dall'origine configurata sono visibili a tutti gli utenti dell'organizzazione. Gli elenchi di controllo di accesso non sono supportati a livello di BLOB nell'archiviazione BLOB di Azure.

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca

Il connettore Gen2 di Azure Data Lake Storage supporta le autorizzazioni di ricerca visibili a **tutti** o **solo persone con accesso all'origine dati**. I dati indicizzati che vengono visualizzati nei risultati della ricerca potrebbero essere visibili a tutti gli utenti dell'organizzazione o solo agli utenti che hanno accesso a ogni elemento.

## <a name="assign-property-labels"></a>Assegnare etichette delle proprietà

È possibile assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni. Anche se questo passaggio non è obbligatorio, l'utilizzo di alcune etichette di proprietà migliorerà la pertinenza della ricerca e assicurerà risultati di ricerca più accurati per gli utenti finali.

## <a name="manage-schema"></a>Gestione dello schema

Nella schermata **Gestisci schema** è possibile modificare gli attributi dello schema (**Queryable**, **Searchable**, **Retrievable** e **per affinamento ricerca**) associati alle proprietà, aggiungere alias facoltativi e scegliere la proprietà **Content** .

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento

Nella schermata **Aggiorna impostazioni** è possibile impostare l'intervallo di ricerca per indicizzazione incrementale e l'intervallo di ricerca per indicizzazione completo. Gli intervalli predefiniti per il connettore Gen2 di Azure Data Lake storage sono 15 minuti per una ricerca per indicizzazione incrementale e una settimana per una ricerca per indicizzazione completa.

## <a name="limitations"></a>Limitazioni

Non è possibile riconfigurare una connessione pubblicata per l'archiviazione BLOB di Azure per Azure Data Lake storage Gen2 source e viceversa. In questi scenari, si consiglia di configurare una nuova connessione.
