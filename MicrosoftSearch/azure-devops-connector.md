---
title: Connettore di DevOps di Azure per Microsoft Search
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore di DevOps di Azure per Microsoft Search
ms.openlocfilehash: b9c566e3e07bfca6d4d25b14915f0160f3928b15
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367551"
---
# <a name="azure-devops-connector-preview"></a>Connettore di DevOps di Azure (anteprima)

Con il connettore di Azure DevOps, l'organizzazione può indicizzare gli elementi di lavoro nella relativa istanza del servizio DevOps di Azure. Dopo aver configurato il connettore e l'indice del contenuto da Azure DevOps, gli utenti finali possono cercare gli elementi in Microsoft Search.

Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitora un connettore di DevOps di Azure. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.

>[!IMPORTANT]
>Il connettore di Azure DevOps supporta solo il servizio cloud di DevOps di Azure. Azure DevOps server 2019, TFS 2018, TFS 2017, TFS 2015 e TFS 2013 non sono supportati da questo connettore. 

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati

Per connettersi all'istanza di Azure DevOps, è necessario il nome dell' [organizzazione](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) di Azure DevOps, il relativo ID app e il segreto client per l'autenticazione OAuth.

### <a name="register-an-app"></a>Registrare un'app

È necessario registrare un'app in Azure DevOps in modo che l'app di ricerca di Microsoft possa accedere all'istanza. Per ulteriori informazioni, vedere la documentazione di Azure DevOps su come [registrare un'app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app). 

Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di registrazione delle app:

 **Campi obbligatori** | **Descrizione**      | **Valore consigliato** 
--- | --- | --- 
| Nome della società         | Questo è il nome della società. | Utilizzare un valore appropriato   | 
| Nome applicazione     | Questo valore univoco identifica l'applicazione che si sta autorizzando.    | Microsoft Search     | 
| Sito Web dell'applicazione  | Questo campo obbligatorio è l'URL dell'applicazione che richiederà l'accesso all'istanza di Azure DevOps durante l'installazione del connettore.  | <https://gcs.office.com/>                | 
| URL di callback di autorizzazione        | Un URL di callback obbligatorio a cui il server di autorizzazione reindirizza. | <https://gcs.office.com/v1.0/admin/oauth/callback>| 
| Ambiti autorizzati | Questo è l'ambito di accesso per l'applicazione | Selezionare gli ambiti seguenti: Identity (lettura), elementi di lavoro (lettura), gruppi di variabili (lettura), progetto e team (lettura), grafico (lettura)| 

Durante la registrazione dell'app con i dettagli sopra riportati, si otterrà l' **ID app** e il **segreto client** che verrà utilizzato per configurare il connettore.

>[!NOTE]
>Per revocare l'accesso a qualsiasi applicazione registrata in Azure DevOps, passare a impostazioni utente all'inizio destro dell'istanza di DevOps di Azure. Fare clic su profilo e quindi su autorizzazioni nella sezione sicurezza del riquadro laterale. Posizionare il puntatore del mouse su un'app OAuth autorizzata per visualizzare il pulsante revoca all'angolo dei dettagli dell'app.

### <a name="connection-settings"></a>Impostazioni di connessione

Dopo la registrazione dell'app di ricerca di Microsoft con Azure DevOps, è possibile completare il passaggio delle impostazioni di connessione. Immettere il nome dell'organizzazione, l'ID app e il segreto client.

![Impostazioni dell'applicazione di connessione](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a>Selezionare progetti e campi

È possibile scegliere di indicizzare l'intera organizzazione o i progetti specifici per la connessione.

Se si sceglie di indicizzare l'intera organizzazione, gli elementi in tutti i progetti nell'organizzazione verranno indicizzati. I nuovi progetti e gli elementi verranno indicizzati durante la ricerca per indicizzazione successiva dopo la loro creazione. Se si scelgono singoli progetti, verranno indicizzati solo gli elementi di lavoro di tali progetti.

![Configurazione dei dati](media/ADO_Configure_data.png)

Successivamente, selezionare i campi in cui si desidera che la connessione indici e visualizza in anteprima i dati in questi campi prima di continuare.

![Scegliere Proprietà](media/ADO_choose_properties.png)

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca

Il connettore di Azure DevOps supporta le autorizzazioni di ricerca visibili  **solo agli utenti che dispongono dell'accesso a questa origine dati** o a **tutti**. Se si sceglie **solo persone con accesso a questa origine dati**, i dati indicizzati verranno visualizzati nei risultati di ricerca per gli utenti che dispongono dell'accesso in base alle autorizzazioni per gli utenti o i gruppi a livello dell'organizzazione, del progetto o dell'area del percorso in Azure DevOps. Se si sceglie **tutti**, i dati indicizzati verranno visualizzati nei risultati della ricerca per tutti gli utenti.

## <a name="assign-property-labels"></a>Assegnare etichette delle proprietà

È possibile assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni. Anche se questo passaggio non è obbligatorio, l'utilizzo di alcune etichette di proprietà migliorerà la pertinenza della ricerca e assicurerà risultati di ricerca più accurati per gli utenti finali.

## <a name="manage-schema"></a>Gestione dello schema

Nella schermata **Gestisci schema** è possibile modificare gli attributi dello schema (**Queryable**, **Searchable**, **Retrievable** e **per affinamento ricerca**) associati alle proprietà, aggiungere alias facoltativi e scegliere la proprietà **Content** .

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento

Il connettore di Azure DevOps supporta le pianificazioni di aggiornamento per le ricerche per indicizzazione complete e incrementali. Una ricerca per indicizzazione completa trova gli elementi di lavoro eliminati precedentemente sincronizzati con l'indice di ricerca di Microsoft. Viene eseguita una ricerca per indicizzazione completa per sincronizzare tutti gli elementi di lavoro. Per sincronizzare nuovi elementi di lavoro e aggiornamenti per gli elementi di lavoro esistenti, è necessario pianificare ricerche per indicizzazione incrementali.

La pianificazione consigliata è un'ora per una ricerca per indicizzazione incrementale e un giorno per una ricerca per indicizzazione completa. 