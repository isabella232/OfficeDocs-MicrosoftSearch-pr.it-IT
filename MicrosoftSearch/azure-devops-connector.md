---
title: Connettore Azure DevOps Graph per Microsoft Search
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
description: Configurare il connettore di Azure DevOps Graph per Microsoft Search
ms.openlocfilehash: 9307aabbf5ea1565e083abfefb90c590d356ae58
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508861"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Connettore Azure DevOps Graph (anteprima)

Il connettore Azure DevOps Graph consente all'organizzazione di indicizzare gli elementi di lavoro nella relativa istanza del servizio Azure DevOps. Dopo aver configurato il connettore e il contenuto dell'indice da Azure DevOps, gli utenti finali possono cercare tali elementi in Microsoft Search.

> [!NOTE]
> Leggere [**l'articolo setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup instructions.

Questo articolo è per tutti gli utenti che configurano, eseguiti e monitorano un connettore Azure DevOps Graph. Integra il processo di configurazione generale e mostra le istruzioni applicabili solo per il connettore Azure DevOps Graph.

>[!IMPORTANT]
>Il connettore Azure DevOps supporta solo il servizio cloud Azure DevOps. Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 e TFS 2013 non sono supportati da questo connettore.

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nell'interfaccia di amministrazione di Microsoft 365

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>Passaggio 2: assegnare un nome alla connessione

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: Configurare le impostazioni di connessione

Per connettersi all'istanza di Azure DevOps, [](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) è necessario il nome dell'organizzazione di Azure DevOps, il relativo ID app e il segreto client per l'autenticazione OAuth.

### <a name="register-an-app"></a>Registrare un'app

Registrare un'app in Azure DevOps in modo che l'app Microsoft Search possa accedere all'istanza. Per altre informazioni, vedi la documentazione di Azure DevOps su come [registrare un'app.](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true)

La tabella seguente fornisce indicazioni su come compilare il modulo di registrazione dell'app:

Campi obbligatori | Descrizione | Valore consigliato
--- | --- | ---
| Nome società         | Nome della società. | Utilizzare un valore appropriato   |
| Nome applicazione     | Valore univoco che identifica l'applicazione che si sta autorizzando.    | Microsoft Search     |
| Sito Web dell'applicazione  | URL dell'applicazione che richiederà l'accesso all'istanza di Azure DevOps durante la configurazione del connettore. (Obbligatorio).  | https://<span>gcs.office.</span> com/
| URL di richiamata dell'autorizzazione        | URL di richiamata obbligatorio a cui il server di autorizzazione reindirizza. | https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback|
| Ambiti autorizzati | Ambito di accesso per l'applicazione | Selezionare gli ambiti seguenti: Identità (lettura), Elementi di lavoro (lettura), Gruppi di variabili (lettura), Progetto e team (lettura), Grafico (lettura)|

Durante la registrazione dell'app con i dettagli precedenti, si otterrà **l'ID app** e il segreto **client** che verranno usati per configurare il connettore.

>[!NOTE]
>Per revocare l'accesso a qualsiasi app registrata in Azure DevOps, vai a Impostazioni utente nella parte superiore destra dell'istanza di Azure DevOps. Selezionare Profilo e quindi Autorizzazioni nella sezione Sicurezza del riquadro laterale. Passa il mouse su un'app OAuth autorizzata per visualizzare il pulsante Revoca nell'angolo dei dettagli dell'app.

### <a name="connection-settings"></a>Impostazioni di connessione

Dopo aver registrato l'app Microsoft Search con Azure DevOps, puoi completare il passaggio delle impostazioni di connessione. Immetti il nome dell'organizzazione, l'ID app e il segreto client.

![Impostazioni applicazione di connessione](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>Configurare i dati: selezionare progetti e campi

È possibile scegliere per la connessione di indicizzare l'intera organizzazione o progetti specifici.

Se si sceglie di indicizzare l'intera organizzazione, gli elementi di tutti i progetti dell'organizzazione verranno indicizzati. I nuovi progetti e gli elementi verranno indicizzati durante la successiva ricerca per indicizzazione dopo la creazione.

Se si scelgono singoli progetti, verranno indicizzati solo gli elementi di lavoro in tali progetti.

![Configurare i dati](media/ADO_Configure_data.png)

Selezionare quindi i campi che si desidera indicizzare e visualizzare in anteprima i dati in questi campi prima di procedere.

![Scegliere le proprietà](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>Passaggio 4: Gestire le autorizzazioni di ricerca

Il connettore Azure DevOps supporta le autorizzazioni di ricerca visibili solo agli utenti con accesso a  **questa origine dati** o a **Tutti.** Se si sceglie Solo gli utenti con accesso a questa origine **dati,** i dati indicizzati verranno visualizzati nei risultati della ricerca per gli utenti che hanno accesso a tali utenti in base alle autorizzazioni per utenti o gruppi a livello di percorso organizzazione, progetto o area in Azure DevOps. Se si sceglie **Tutti,** i dati indicizzati verranno visualizzati nei risultati della ricerca per tutti gli utenti.

## <a name="step-5-assign-property-labels"></a>Passaggio 5: Assegnare etichette di proprietà

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)

## <a name="step-6-manage-schema"></a>Passaggio 6: Gestire lo schema

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)

## <a name="step-7-choose-refresh-settings"></a>Passaggio 7: Scegliere le impostazioni di aggiornamento

Il connettore DevOps di Azure supporta le pianificazioni di aggiornamento sia per le ricerche per indicizzazione complete che per le ricerche per indicizzazione incrementali.
La pianificazione consigliata è un'ora per una ricerca per indicizzazione incrementale e un giorno per una ricerca per indicizzazione completa.

## <a name="step-8-review-connection"></a>Passaggio 8: esaminare la connessione

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
