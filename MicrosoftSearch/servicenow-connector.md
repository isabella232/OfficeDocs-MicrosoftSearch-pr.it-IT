---
title: Connettore ServiceNow per Microsoft Search
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore ServiceNow per Microsoft Search
ms.openlocfilehash: b60583e61687b13c7fd631cd1c4a9f6d663724e8
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927199"
---
# <a name="servicenow-connector"></a>Connettore ServiceNow

Con il connettore ServiceNow, l'organizzazione può indicizzare gli articoli della Knowledge base che sono visibili a tutti gli utenti all'interno dell'organizzazione. Dopo aver configurato il connettore e l'indicizzazione del contenuto da ServiceNow, gli utenti finali possono cercare tali articoli da qualsiasi client di ricerca di Microsoft.  

Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitorano un connettore di ServiceNow. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.

Informazioni su come accedere ai connettori Microsoft built dal [set up del connettore Microsoft-built per Microsoft Search](https://docs.microsoft.com/microsoftsearch/configure-connector). La configurazione specifica del connettore di ServiceNow è illustrata nell'articolo seguente.

## <a name="connection-settings"></a>Impostazioni di connessione
Per connettersi ai dati di ServiceNow, è necessario l'URL dell' **istanza di ServiceNow** dell'organizzazione, le credenziali per questo account e l'ID client e il segreto client per l'autenticazione OAuth.  

L'URL dell' **istanza di ServiceNow** dell'organizzazione è in genere simile a **https:// &lt; Your-Organization-Domain>. Service-Now.com**. Insieme a questo URL, è necessario un account per la configurazione della connessione a ServiceNow, nonché per consentire a Microsoft Search di aggiornare periodicamente gli articoli da ServiceNow in base alla pianificazione di aggiornamento. L'account deve disporre del ruolo <em>conoscenza</em> . [Informazioni su come assegnare un ruolo per gli account di ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

Per eseguire l'autenticazione e la sincronizzazione del contenuto da ServiceNow, scegliere **uno dei tre** metodi supportati:
1. Autenticazione di base 
2. ServiceNow OAuth (scelta consigliata)
3. Azure AD OpenID Connect

#### <a name="basic-authentication"></a>Autenticazione di base
Immettere il nome utente e la password dell'account di ServiceNow con il ruolo <em>conoscenza</em> per eseguire l'autenticazione nell'istanza.
#### <a name="servicenow-oauth"></a>ServiceNow OAuth

Per utilizzare ServiceNow OAuth per l'autenticazione, un amministratore di ServiceNow deve eseguire il provisioning di un endpoint nell'istanza di ServiceNow, in modo che l'app di ricerca di Microsoft possa accedere all'istanza. Per ulteriori informazioni, vedere [creare un endpoint per i client per accedere all'istanza](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) nella documentazione di ServiceNow.

Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di creazione dell'endpoint:

**Campo** | **Descrizione** | **Valore consigliato**
--- | --- | ---
Nome | Questo valore univoco identifica l'applicazione per la quale è necessario l'accesso OAuth. | Microsoft Search
ID client | ID univoco di sola lettura e generato automaticamente per l'applicazione. L'istanza utilizza l'ID client quando richiede un token di accesso. | ND
Segreto client | Con questa stringa segreta condivisa, l'istanza di ServiceNow e Microsoft Search autorizzano le comunicazioni tra loro. | Seguire le procedure consigliate per la sicurezza trattando questa come una password.
URL di Reindirizzamento | Un URL di callback obbligatorio a cui il server di autorizzazione reindirizza. | https://gcs.office.com/v1.0/admin/oauth/callback
URL logo | URL che contiene l'immagine per il logo dell'applicazione. | ND
Attivazione | Selezionare la casella di controllo per rendere attivo il registro di sistema dell'applicazione. | Impostata su attivo
Aggiornare la durata del token | Il numero di secondi in cui un token di aggiornamento è valido. Per impostazione predefinita, i token di aggiornamento scadono in 100 giorni (8640000 secondi). | 31.536.000 (1 anno)
Durata del token di accesso | Il numero di secondi in cui un token di accesso è valido. | 43.200 (12 ore)

Immettere l'ID client e il segreto client per la connessione all'istanza. Dopo la connessione, utilizzare una credenziale account ServiceNow per autenticare le autorizzazioni per la ricerca per indicizzazione. L'account deve disporre del ruolo <em>conoscenza</em> . 

#### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

Per utilizzare Azure AD OpenID Connect per l'autenticazione, attenersi alla procedura riportata di seguito.

###### <a name="step-1-register-a-new-application-in-azure-active-directory"></a>Passaggio 1: registrare una nuova applicazione in Azure Active Directory

Per ulteriori informazioni sulla registrazione di una nuova applicazione in Azure Active Directory, vedere [registrazione di un'applicazione](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application). Selezionare la directory organizzativa single tenant. L'URI di reindirizzamento non è necessario. Dopo la registrazione, annotare l'ID (client) ID e la directory (tenant) dell'applicazione.

###### <a name="step-2-create-a-client-secret"></a>Passaggio 2: creare un segreto client

Per ulteriori informazioni sulla creazione di un segreto client, vedere [creazione di un segreto client](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret). Prendere nota del segreto client.

###### <a name="step-3-retrieve-service-principal-object-identifier"></a>Passaggio 3: recuperare l'identificatore dell'oggetto Principal del servizio

Seguire la procedura per recuperare l'identificatore dell'oggetto Principal del servizio

1. Eseguire PowerShell
2. Installare Azure PowerShell utilizzando il seguente comando
```<language>
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
```
3. Connettersi ad Azure
```<language>
    Connect-AzAccount
```
4. Ottenere l'identificatore dell'oggetto Principal del servizio
```<language>
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
```
Sostituire "Application-ID" con l'ID dell'applicazione (client) (senza virgolette) dell'applicazione che è stata registrata nel passaggio 1. Annotare il valore dell'oggetto ID dall'output di PowerShell. È l'ID dell'entità servizio.

A questo punto si dispone di tutte le informazioni necessarie dal portale di Azure. Un breve riepilogo delle informazioni è riportato nella tabella seguente.

**Proprietà** | **Descrizione**
--- | ---
ID directory (ID tenant) | Si tratta di un ID univoco che fa riferimento al tenant di Azure Active Directory (dal passaggio 1).
ID applicazione (ID client) | Si tratta di un ID univoco che fa riferimento all'applicazione registrata nel passaggio 1.
Segreto client | Questa è la chiave segreta dell'applicazione (dal passaggio 2). Trattarlo come una password.
ID dell'entità servizio | Identità dell'applicazione in esecuzione come servizio. (dal passaggio 3)

###### <a name="step-4-register-servicenow-application"></a>Passaggio 4: registrare l'applicazione ServiceNow

È necessario eseguire la configurazione seguente nell'istanza di ServiceNow.

1. Registrare una nuova entità OIDC OAuth. Per ulteriori informazioni, vedere [Create an OAuth OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).
2. Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di registrazione del provider di OIDC

**Campo** | **Descrizione** | **Valore consigliato**
--- | --- | ---
Nome | Nome univoco che identifica l'entità OIDC OAuth. | Azure AD
ID client | ID client dell'applicazione registrata nel server OAuth OIDC di terze parti. L'istanza utilizza l'ID client per la richiesta di un token di accesso. | ID applicazione (client) del passaggio 1
Segreto client | Il segreto client dell'applicazione registrata nel server OAuth OIDC di terze parti. | Segreto client del passaggio 2

Tutti gli altri valori possono essere predefiniti.

3. Nel modulo di registrazione provider di OIDC è necessario aggiungere una nuova configurazione del provider di OIDC. Fare clic sull'icona di ricerca sul campo di *configurazione del provider OAuth OIDC* per aprire i record delle configurazioni di OIDC. Fare clic su Nuova regola.
4. Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di configurazione del provider di OIDC

**Campo** | **Valore consigliato**
--- | ---
Provider OIDC |  Azure AD
URL dei metadati di OIDC | Deve trovarsi nel formato https \: //login.microsoftonline.com/"tenandId"/.well-known/OpenID-Configuration <br/>Sostituire "tenantID" con l'ID directory (tenant) del passaggio 1 (senza virgolette).
Durata della cache di configurazione di OIDC |  120
Applicazione | Globale
Attestazione dell'utente | secondaria
Campo utente | ID utente
Abilitare la verifica delle attestazioni ITC | Disattivato

5. Fare clic su Invia e aggiornare il modulo entità OIDC OAuth.

###### <a name="step-5-create-a-servicenow-account"></a>Passaggio 5: creare un account ServiceNow

Fare riferimento alle istruzioni per creare un account ServiceNow, [creare un utente in ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

Nella tabella seguente vengono fornite indicazioni su come compilare la registrazione dell'account utente di ServiceNow

**Campo** | **Valore consigliato**
--- | ---
ID utente | ID dell'entità servizio del passaggio 3
Solo accesso ai servizi Web | Estratto

Tutti gli altri valori possono essere lasciati all'impostazione predefinita.

###### <a name="step-6-enable-knowledge-role-for-the-servicenow-account"></a>Passaggio 6: abilitare il ruolo conoscenza per l'account ServiceNow

Accedere all'account ServiceNow creato con l'ID entità ServiceNow come ID utente e assegnare il ruolo conoscenza. Le istruzioni per l'assegnazione di un ruolo a un account di ServiceNow sono disponibili qui, [assegnare un ruolo a un utente](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

Utilizzare l'ID applicazione come ID client (dal passaggio 1) e il client Secret (dal passaggio 2) nella procedura guidata di configurazione dell'interfaccia di amministrazione per eseguire l'autenticazione all'istanza di ServiceNow utilizzando Azure AD OpenID Connect.

## <a name="filter-data"></a>Filtrare i dati 
Con una stringa di query di ServiceNow, è possibile specificare le condizioni per la sincronizzazione degli articoli. È come una clausola **where** in un'istruzione **SQL SELECT** . Ad esempio, è possibile scegliere di indicizzare solo gli articoli pubblicati e attivi. Per ulteriori informazioni sulla creazione di una stringa di query personalizzata, vedere [generare una stringa di query codificata utilizzando un filtro](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca
Il connettore ServiceNow supporta solo le autorizzazioni di ricerca visibili a **tutti**. I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione.

## <a name="manage-the-search-schema"></a>Gestire lo schema di ricerca
Dopo la connessione completata, configurare il mapping dello schema di ricerca. È possibile scegliere quali proprietà rendere **querybili** **, reperibili e** **recuperabili**. Per ulteriori informazioni sulla gestione dello schema di ricerca, vedere [gestire lo schema di ricerca](https://docs.microsoft.com/microsoftsearch/configure-connector#manage-the-search-schema).

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento
Il connettore ServiceNow supporta le pianificazioni di aggiornamento per le ricerche per indicizzazione complete e incrementali. È consigliabile impostare entrambi.

Una pianificazione di ricerca per indicizzazione completa trova gli articoli eliminati precedentemente sincronizzati con l'indice Microsoft Search e tutti gli articoli che sono stati spostati dal filtro di sincronizzazione. Quando si esegue la connessione a ServiceNow, viene eseguita una ricerca per indicizzazione completa per sincronizzare tutti gli articoli della Knowledge base. Per sincronizzare nuovi elementi e rendere gli aggiornamenti, è necessario pianificare ricerche per indicizzazione incrementali.

Il valore predefinito consigliato è un giorno per una ricerca per indicizzazione completa e quattro ore per una ricerca per indicizzazione incrementale.

## <a name="review-and-publish"></a>Revisione e pubblicazione
Dopo aver configurato il connettore, è possibile rivedere e pubblicare la connessione.

## <a name="next-steps"></a>Passaggi successivi
Dopo la pubblicazione della connessione, è necessario personalizzare la pagina dei risultati di ricerca. Per ulteriori informazioni sulla personalizzazione dei risultati della ricerca, vedere [Customize the search results page](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).