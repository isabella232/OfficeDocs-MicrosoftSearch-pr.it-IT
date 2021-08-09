---
title: Atlante jira Graph connettore per Microsoft Search
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
description: Configurare il connettore di Graph Jira di Atlante per Microsoft Search
ms.openlocfilehash: 6023e8ec4539bd37358a3e801ef81947fe9f87ff38736344347d5634d0527753
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533690"
---
# <a name="atlassian-jira-graph-connector-preview"></a>Connettore jira Graph Atlante (anteprima)

Il connettore jira Graph atlante consente all'organizzazione di indicizzare i problemi di Jira. Dopo aver configurato il connettore e il contenuto di indicizzazione dal sito jira, gli utenti finali possono cercare tali elementi in Microsoft Search.

> [!NOTE]
> Leggere [**l'articolo Setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup instructions.

Questo articolo è per chiunque configura, esegue e monitora un connettore jira Graph Atlante. Integra il processo di configurazione generale e mostra le istruzioni che si applicano solo al connettore jira Graph Atlante.

>[!IMPORTANT]
>Il connettore Graph Jira di Atlante supporta solo le istanze ospitate nel cloud di Jira. Le versioni di Jira Server e Jira Data Center non sono supportate da questo connettore.

## <a name="before-you-get-started"></a>Prima di iniziare
È necessario essere l'amministratore del tenant M365 dell'organizzazione e l'amministratore del sito Jira dell'organizzazione.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nella interfaccia di amministrazione di Microsoft 365
Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="step-2-name-the-connection"></a>Passaggio 2: assegnare un nome alla connessione
Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: Configurare le impostazioni di connessione
Per connettersi al sito di Jira, utilizzare l'URL del sito di Jira. L'URL di un sito cloud di Jira in genere è simile a *https://<organization_name>.atlassian.net/*. È possibile scegliere Autenticazione di base o OAuth 2.0 (scelta consigliata) per eseguire l'autenticazione nel sito di Jira.

### <a name="basic-auth"></a>Autenticazione di base
Immetti il nome utente dell'account (in genere l'ID di posta elettronica) e il token API per l'autenticazione tramite l'autenticazione di base. Per altre informazioni sulla generazione di un token API, fai riferimento alla documentazione di Atlassian su come gestire i token API per il [tuo account di Atlassian.](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

### <a name="oauth-20"></a>OAuth 2.0
Registra un'app in Atlassian Jira in modo che l'app Microsoft Search possa accedere all'istanza. Per ulteriori informazioni, vedere la documentazione del supporto di Atlassian su come [abilitare OAuth 2.0.](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)

I passaggi seguenti forniscono indicazioni su come registrare l'app:

1. Accedi alla console [per sviluppatori di Atlassian](https://developer.atlassian.com/console/myapps/) con il tuo account amministratore di Atlassian Jira.
2. Fare clic `Create` su e selezionare `OAuth 2.0 integration`
3. Specifica un nome appropriato per l'applicazione e crea la nuova app.
4. Passare al `Permissions` riquadro di spostamento a sinistra. Fare `Add` clic su per `Jira platform REST API` . Dopo l'aggiunta, `Configure` fare clic su e aggiungere gli ambiti seguenti: , e `View Jira issue data` `Manage Jira global settings` `View user profiles` .
5. Passare al `Authorization` riquadro di spostamento a sinistra. Aggiungere l'URL di `https://gcs.office.com/v1.0/admin/oauth/callback` richiamata e salvare le modifiche.
6. Passare al `Settings` riquadro di spostamento a sinistra. Si otterrà il `Client ID` e `Secret` da questa pagina.

Durante la registrazione dell'app con i dettagli sopra riportati, ottieni **l'ID client** e **il segreto**. Completare il passaggio delle impostazioni di connessione usando questi passaggi.

### <a name="step-3a-configure-data-select-projects"></a>Passaggio 3a: Configurare i dati: Selezionare i progetti

È possibile scegliere per la connessione di indicizzare l'intero sito di Jira o solo progetti specifici.

* Se si sceglie di indicizzare l'intero sito di Jira, i problemi di Jira in tutti i progetti nel sito verranno indicizzati. I nuovi progetti e problemi verranno indicizzati durante la successiva ricerca per indicizzazione dopo la creazione.
* Se si scelgono singoli progetti, verranno indicizzati solo i problemi di Jira in tali progetti.

È possibile scegliere di filtrare ulteriormente i problemi di Jira che verranno indicizzati in due modi.
* Specificare il **periodo di tempo modificato per il problema.** In questo modo verranno indicizzati solo i problemi di Jira creati o modificati nel periodo di tempo selezionato **in** sequenza in base alla ricerca per indicizzazione corrente.
* Specificare **JQL**. In questo modo verranno indicizzati solo i problemi di Jira restituiti dopo il filtro in base al linguaggio JQL (Jira Query Language) fornito. Per ulteriori informazioni sull'utilizzo di JQL, vedere la documentazione del supporto di Atlassian sull'utilizzo della ricerca [avanzata con Jira Query Language](https://support.atlassian.com/jira-service-management-cloud/docs/use-advanced-search-with-jira-query-language-jql/)

> [!TIP]
> È possibile utilizzare il filtro JQL per indicizzare solo tipi di problemi Jira specifici utilizzando "*issueType in (Bug,Improvement)*"

### <a name="step-3b-configure-data-select-properties"></a>Passaggio 3b: Configurare i dati: Selezionare le proprietà

Selezionare i campi che si desidera indicizzare e visualizzare in anteprima i dati in questi campi prima di procedere. Alcuni campi sono già selezionati per impostazione predefinita e non possono essere rimossi.

Il connettore di Graph Atlante jira può indicizzare sia i campi problema predefiniti che i campi dei problemi creati personalizzati.

> [!NOTE]
> Se un campo personalizzato creato selezionato non è presente in alcuni tipi di problema jira, il campo verrà ingerito come *NULL* (vuoto).

## <a name="step-4-manage-search-permissions"></a>Passaggio 4: Gestire le autorizzazioni di ricerca

Il connettore jira Graph atlante supporta le autorizzazioni di ricerca visibili a  **Tutti** o Solo gli utenti con accesso **a questa origine dati.** Se si sceglie **Tutti**, i dati indicizzati verranno visualizzati nei risultati della ricerca per tutti gli utenti. Se si sceglie **Solo gli utenti con accesso** a questa origine dati, i dati indicizzati verranno visualizzati nei risultati della ricerca per gli utenti che hanno accesso a tali origini. In Atlassian Jira, le autorizzazioni di sicurezza vengono definite utilizzando schemi di autorizzazione di progetto contenenti gruppi a livello di sito e ruoli di progetto. La sicurezza a livello di problema può essere definita anche utilizzando schemi di autorizzazione a livello di problema.

Se si sceglie **Solo** gli utenti con accesso a questa origine dati, è necessario scegliere ulteriormente se il sito di Jira dispone di utenti di cui è stato eseguito il provisioning di Azure Active Directory (AAD) o utenti non AAD.

Per identificare l'opzione adatta all'organizzazione:

1. Scegliere **l'opzione AAD** se l'ID  di posta elettronica degli utenti di Jira è uguale all'UPN (UserPrincipalName) degli utenti in AAD.
2. Scegliere **l'opzione Non-AAD** se l'ID di posta elettronica degli utenti di Jira è **diverso** dall'UPN (UserPrincipalName) degli utenti in AAD. 

>[!NOTE]
> * Se si sceglie AAD come tipo di origine dell'identità, il connettore mappa gli ID di posta elettronica degli utenti ottenuti da Jira direttamente alla proprietà UPN da AAD.
> * Se hai scelto "Non-AAD" per il tipo di identità, vedi Eseguire il mapping delle identità [non di Azure AD](map-non-aad.md) per istruzioni sul mapping delle identità. È possibile utilizzare questa opzione per fornire l'espressione regolare di mapping da ID posta elettronica a UPN.

## <a name="step-5-assign-property-labels"></a>Passaggio 5: Assegnare etichette di proprietà

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="step-6-manage-schema"></a>Passaggio 6: Gestire lo schema

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="step-7-choose-refresh-settings"></a>Passaggio 7: Scegliere le impostazioni di aggiornamento

Il connettore jira Graph atlante supporta le pianificazioni di aggiornamento per le ricerche per indicizzazione complete e incrementali.
La pianificazione consigliata è un'ora per una ricerca per indicizzazione incrementale e un giorno per una ricerca per indicizzazione completa.

## <a name="step-8-review-connection"></a>Passaggio 8: verificare la connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="troubleshooting"></a>Risoluzione dei problemi
Di seguito è riportato un elenco degli errori comuni rilevati durante la configurazione del connettore e dei possibili motivi.

| Passaggio di configurazione | Messaggio di errore | Possibili motivi |
| ------------ | ------------ | ------------ |
| Impostazioni di connessione | La richiesta non è valida o non è corretta. | URL del sito Jira non corretto |
| Impostazioni di connessione | Impossibile raggiungere il servizio cloud Jira per il sito jira. | URL del sito Jira non corretto |
| Impostazioni di connessione | Il client non dispone dell'autorizzazione per eseguire l'azione. | Token API non valido fornito per l'autenticazione di base |


## <a name="limitations"></a>Limitazioni
Di seguito sono riportate le limitazioni note del connettore Graph Jira di Atlante:
* Le versioni di Jira Server e Data Center non sono supportate.