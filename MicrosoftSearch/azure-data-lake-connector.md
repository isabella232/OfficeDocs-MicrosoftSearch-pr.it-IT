---
title: Azure Data Lake Connector per Microsoft Search
ms.author: mounika.narayanan
author: monaray
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
ms.openlocfilehash: f8cb94e806e619d6dae7258b6c2d708d93afb9a8
ms.sourcegitcommit: 7eda9b621def0659d7e7bc8b989f8adc929cce93
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "44861077"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Connettore Gen2 di archiviazione di Azure Data Lake

Con il connettore [Gen2 di Azure Data Lake storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) , gli utenti dell'organizzazione possono cercare file e il relativo contenuto. Questo connettore accede ai dati archiviati nei contenitori BLOB di Azure e nelle cartelle abilitate alla gerarchia all'interno di un account di Azure Data Lake storage gen 2.

Questo articolo è per gli amministratori di [Microsoft 365](https://www.microsoft.com/microsoft-365) o per tutti coloro che configurano, eseguono e monitorano un connettore di Gen2 di archiviazione di Azure Data Lake. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati

### <a name="primary-storage-connection-string"></a>Stringa di connessione di archiviazione principale 
Nella schermata **autenticazione e configurazione** fornire la stringa di connessione di archiviazione principale. Tale stringa è necessaria per consentire l'accesso all'account di archiviazione. Per trovare la stringa di connessione, passare al [portale di Azure](https://ms.portal.azure.com/#home) e passare alla sezione **Keys** dell'account [Gen2 di Azure Data Lake storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) . Copiare e incollare la stringa di connessione nel campo appropriato sullo schermo.

Se non si desidera fornire il **AccountKey** (un parametro nella stringa di connessione di archiviazione principale), è necessario concedere l'accesso in lettura al servizio dei connettori del grafico. Nella scheda **controllo di accesso** dell'account di archiviazione di Gen2 di Azure Data Lake, seguire le istruzioni riportate in tale pagina per concedere l'accesso all'app seguente:
* **ID app per la prima parte:** 56c1da01-2129-48f7-9355-af6d59d42766
* **Nome dell'app per la prima parte:** Servizio del connettore grafico

### <a name="storage-account-and-queue-notifications-optional"></a>Account di archiviazione e notifiche di coda (facoltativa)
Il supporto per l'elaborazione delle modifiche in tempo reale nel servizio dei connettori del grafico potrebbe essere aggiunto in futuro. In tal caso, verranno monitorate le notifiche di modifica di [Gen2 di Azure Data Lake storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) memorizzate in una coda. Sarà necessario creare una coda nello stesso account del Gen2 di archiviazione di Azure Data Lake o in un altro account di archiviazione.

Dopo aver creato una coda, passare alla scheda **eventi** della pagina coda per configurare la **sottoscrizione di eventi**. Scegliere tutti gli eventi BLOB che la coda riceverà e connettere la coda all'account Gen2 di Azure Data Lake storage.

## <a name="manage-the-search-schema"></a>Gestire lo schema di ricerca
Nella schermata **Gestisci schema** è possibile modificare gli attributi dello schema (**Queryable**, **Searchable**e **Retrievable**) associati alle proprietà gestite. Questi attributi delle proprietà gestite sono dati indicizzati dall'account [Gen2 di Azure Data Lake storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) .

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca
Nella schermata **Gestisci autorizzazioni di ricerca** è possibile scegliere di ingerire gli elenchi di controllo di accesso (ACL, Access Control List) dall'account di archiviazione. Quando vengono impostate queste autorizzazioni di ricerca, il contenuto della ricerca viene ritagliato in base alle autorizzazioni assegnate all'utente di [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) con accesso che esegue la ricerca nel contenuto. In alternativa, è possibile scegliere di rendere tutto il contenuto indicizzato dall'account di archiviazione visibile a tutti gli utenti dell'organizzazione. In questo caso, tutti gli utenti dell'organizzazione avranno accesso a tutti i dati dell'account di archiviazione.
 
## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento
Nella schermata **Aggiorna impostazioni** è possibile impostare l'intervallo di ricerca per indicizzazione incrementale e l'intervallo di ricerca per indicizzazione completo. Gli intervalli predefiniti per il connettore [Gen2 di Azure Data Lake storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) sono 15 minuti per una ricerca per indicizzazione incrementale e una settimana per una ricerca per indicizzazione completa.
 
## <a name="limitations"></a>Limitazioni
Attualmente, [Azure Data Lake storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) Multi-Protocol Access è disponibile solo negli Stati Uniti centrali, West Central US, Canada centrale, East US, East Asia, North Europe, East US2, sud-est asiatico, West Europe, West US, Australia Est, Giappone est, West US2 e Brasile sud.

Per ulteriori informazioni, vedere [Multi-Protocol Access on Azure Data Lake Storage (Preview)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-multi-protocol-access).


