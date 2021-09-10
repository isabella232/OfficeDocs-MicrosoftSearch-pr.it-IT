---
title: ServiceNow Catalogo Graph connettore per Microsoft Search
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore di Graph ServiceNow per Microsoft Search
ms.openlocfilehash: c46388a086f563eec36dbd7e5492d8065b1ae296
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973448"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-catalog-graph-connector-preview"></a>ServiceNow Catalog Graph Connector (anteprima)

Con Microsoft Graph Connector for ServiceNow, l'organizzazione può utilizzare elementi del catalogo visibili a tutti gli utenti o limitati con autorizzazioni di criteri utente all'interno dell'organizzazione. [](https://www.servicenow.com/products/it-service-automation-applications/service-catalog.html) Dopo aver configurato il connettore e indicizzare il contenuto da ServiceNow, gli utenti finali possono cercare tali elementi del catalogo da qualsiasi client Microsoft Search client.

>[!NOTE]
>ServiceNow Catalog Graph Connector è in anteprima. Se si desidera ottenere l'accesso anticipato per provarlo, iscriversi utilizzando [<b>questo modulo. </b>](https://forms.office.com/r/QyYwQQY2EX)  

Questo articolo è per Microsoft 365 amministratori o chiunque configura, esegue e monitora un connettore di Graph ServiceNow Catalog. Integra le istruzioni generali fornite nell'articolo [Configurare il Graph connettore.](configure-connector.md) Se non è già stato fatto, leggere l'intero articolo Configurare il connettore Graph per comprendere il processo di configurazione generale.

Ogni passaggio del processo di installazione è elencato di seguito insieme a una nota che indica che è necessario seguire le [](#troubleshooting) istruzioni di configurazione generali o altre istruzioni che si applicano solo al connettore di Graph ServiceNow, incluse informazioni su Risoluzione dei problemi e [limitazioni.](#limitations)

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nella interfaccia di amministrazione di Microsoft 365.
Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="step-2-name-the-connection"></a>Passaggio 2: assegnare un nome alla connessione.
Seguire le istruzioni generali [per l'installazione](./configure-connector.md).


## <a name="step-3-connection-settings"></a>Passaggio 3: Connessione Impostazioni
Per connettersi ai dati ServiceNow, è necessario l'URL dell'istanza **ServiceNow dell'organizzazione.** L'URL dell'istanza ServiceNow dell'organizzazione in genere **https:// &lt; dominio-organizzazione>.service-now.com**. 

Insieme a questo URL, è necessario un **account** di servizio per configurare la connessione a ServiceNow e per consentire a Microsoft Search di aggiornare periodicamente gli elementi del catalogo in base alla pianificazione dell'aggiornamento. L'account del servizio dovrà disporre dell'accesso in lettura ai record della tabella **ServiceNow** seguenti per eseguire correttamente la ricerca per indicizzazione di varie entità.

Funzionalità | Tabelle necessarie per l'accesso in lettura | Descrizione
--- | --- | ---
Indicizzare gli elementi del catalogo disponibili per <em>tutti gli utenti</em> | sc_cat_item | Per la ricerca per indicizzazione degli elementi del catalogo
Indicizzare e supportare le autorizzazioni dei criteri utente | sc_cat_item_user_criteria_mtom | Who può accedere a questo elemento del catalogo
| | sc_cat_item_user_criteria_no_mtom | Who accesso a questo elemento del catalogo
| | sys_user | Lettura tabella utenti
| | sys_user_has_role | Leggere le informazioni sui ruoli degli utenti
| | sys_user_grmember | Lettura dell'appartenenza a un gruppo di utenti
| | user_criteria | Autorizzazioni per la lettura dei criteri utente

È possibile **creare e assegnare un ruolo per** l'account di servizio utilizzato per connettersi a Microsoft Search. [Informazioni su come assegnare il ruolo per gli account ServiceNow.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html) L'accesso in lettura alle tabelle può essere assegnato al ruolo creato. Per informazioni sull'impostazione dell'accesso in lettura ai record di tabella, vedere [Securing Table Records.](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls) 


>[!NOTE]
> ServiceNow Catalog Graph Connector può indicizzare gli elementi del catalogo e le autorizzazioni dei criteri utente senza script avanzati. Se un criterio utente contiene uno script avanzato, tutti gli elementi del catalogo correlati verranno nascosti dai risultati della ricerca.

Per autenticare e sincronizzare il contenuto da ServiceNow, scegliere **uno dei tre** metodi supportati: 
 
- Autenticazione di base 
- ServiceNow OAuth (scelta consigliata)
- Azure AD OpenID Connessione

## <a name="step-31-basic-authentication"></a>Passaggio 3.1: Autenticazione di base

Immettere il nome utente e la password dell'account ServiceNow con ruolo **di catalogo** per eseguire l'autenticazione nell'istanza.

## <a name="step-32-servicenow-oauth"></a>Passaggio 3.2: ServiceNow OAuth

Per usare ServiceNow OAuth per l'autenticazione, un amministratore di ServiceNow deve effettuare il provisioning di un endpoint nell'istanza serviceNow, in modo che l'app Microsoft Search possa accedervi. Per ulteriori informazioni, vedere [Create an endpoint for clients to access the instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) nella documentazione ServiceNow.

Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di creazione degli endpoint:

Campo | Descrizione | Valore consigliato 
--- | --- | ---
Nome | Valore univoco che identifica l'applicazione per cui è necessario l'accesso OAuth. | Microsoft Search
ID client | ID univoco generato automaticamente e di sola lettura per l'applicazione. L'istanza usa l'ID client quando richiede un token di accesso. | ND
Segreto client | Con questa stringa segreta condivisa, l'istanza ServiceNow e Microsoft Search le comunicazioni tra loro. | Seguire le procedure consigliate per la sicurezza trattando il segreto come password.
URL di reindirizzamento | URL di richiamata obbligatorio a cui il server di autorizzazione reindirizza. | https://gcs.office.com/v1.0/admin/oauth/callback
Logo URL | URL contenente l'immagine per il logo dell'applicazione. | ND
Attivo | Selezionare la casella di controllo per rendere attivo il Registro di sistema dell'applicazione. | Impostato su attivo
Durata token di aggiornamento | Numero di secondi in cui un token di aggiornamento è valido. Per impostazione predefinita, i token di aggiornamento scadono tra 100 giorni (8.640.000 secondi). | 31.536.000 (1 anno)
Durata token di accesso | Numero di secondi in cui un token di accesso è valido. | 43.200 (12 ore)

Immettere l'ID client e il segreto client per connettersi all'istanza. Dopo la connessione, utilizzare una credenziale dell'account ServiceNow per autenticare l'autorizzazione per la ricerca per indicizzazione. L'account deve avere almeno il **ruolo di** catalogo. Fare riferimento alla tabella all'inizio del [passaggio 3:](#step-3-connection-settings) impostazioni di connessione per fornire l'accesso in lettura a più record della tabella ServiceNow e indicizzare le autorizzazioni per i criteri utente.

## <a name="step-33-azure-ad-openid-connect"></a>Passaggio 3.3: Azure AD OpenID Connessione

Per usare Azure AD OpenID Connessione per l'autenticazione, seguire la procedura seguente.

### <a name="step-331-register-a-new-application-in-azure-active-directory"></a>Passaggio 3.3.1: Registrare una nuova applicazione in Azure Active Directory

Per informazioni sulla registrazione di una nuova applicazione in Azure Active Directory, vedere [Register an application](/azure/active-directory/develop/quickstart-register-app#register-an-application). Selezionare la directory organizzativa del tenant singolo. Uri di reindirizzamento non necessario. Dopo la registrazione, annotare l'ID applicazione (client) e l'ID directory (tenant).

### <a name="step-332-create-a-client-secret"></a>Passaggio 3.3.2: Creare un segreto client

Per informazioni sulla creazione di un segreto client, vedere [Creazione di un segreto client.](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) Prendere nota del segreto client.

### <a name="step-333-retrieve-service-principal-object-identifier"></a>Passaggio 3.3.3: Recuperare l'identificatore dell'oggetto entità servizio

Seguire i passaggi per recuperare l'identificatore dell'oggetto entità servizio

1. Eseguire PowerShell.

2. Installare Azure PowerShell utilizzando il comando seguente.

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Connessione ad Azure.

   ```powershell
   Connect-AzAccount
   ```

4. Ottenere l'identificatore dell'oggetto entità servizio.

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   Sostituire "APPLICATION-ID" con l'ID applicazione (client) (senza virgolette) dell'applicazione registrata nel passaggio 3.a. Nota il valore dell'oggetto ID dall'output di PowerShell. È l'ID entità servizio.

Ora hai tutte le informazioni necessarie dal portale di Azure. Nella tabella seguente viene fornito un breve riepilogo delle informazioni.

Proprietà | Descrizione 
--- | ---
ID directory (ID tenant) | ID univoco del Azure Active Directory tenant, dal passaggio 3.a.
ID applicazione (ID client) | ID univoco dell'applicazione registrata nel passaggio 3.a.
Segreto client | Chiave privata dell'applicazione (dal passaggio 3.b). Consideralo come una password.
ID entità servizio | Identità per l'applicazione in esecuzione come servizio. (dal passaggio 3.c)

### <a name="step-334-register-servicenow-application"></a>Passaggio 3.3.4: Registrare l'applicazione ServiceNow

L'istanza ServiceNow richiede la configurazione seguente:

1. Registrare una nuova entità OAuth OIDC. Per informazioni, vedere [Create an OAuth OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).

2. Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di registrazione del provider OIDC

   Campo | Descrizione | Valore consigliato
   --- | --- | ---
   Nome | Nome univoco che identifica l'entità OIDC OAuth. | Azure AD
   ID client | ID client dell'applicazione registrata nel server OIDC OAuth di terze parti. L'istanza usa l'ID client quando richiede un token di accesso. | ID applicazione (client) dal passaggio 3.a
   Segreto client | Il segreto client dell'applicazione registrata nel server OIDC OAuth di terze parti. | Segreto client dal passaggio 3.b

   Tutti gli altri valori possono essere predefiniti.

3. Nel modulo di registrazione del provider OIDC è necessario aggiungere una nuova configurazione del provider OIDC. Selezionare l'icona di ricerca *nel campo Configurazione provider OIDC OAuth* per aprire i record delle configurazioni OIDC. Selezionare Nuovo.

4. Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di configurazione del provider OIDC

   Campo | Valore consigliato
   --- | ---
   OIDC Provider |  Azure AD
   URL metadati OIDC | L'URL deve essere nel formato https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration <br/>Sostituire "tenantID" con l'ID directory (tenant) del passaggio 3.a.
   Durata cache di configurazione OIDC |  120
   Applicazione | Globale
   Attestazione utente | sub
   User, campo | ID utente
   Abilitare la verifica delle attestazioni JTI | Disattivato

5. Selezionare Invia e aggiorna il modulo Entità OAuth OIDC.

### <a name="step-335-create-a-servicenow-account"></a>Passaggio 3.3.5: Creare un account ServiceNow

Fare riferimento alle istruzioni per creare un account ServiceNow, [creare un utente in ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

Nella tabella seguente vengono fornite indicazioni su come compilare la registrazione dell'account utente ServiceNow

Campo | Valore consigliato
--- | ---
ID utente | ID entità servizio dal passaggio 3.c
Solo accesso al servizio Web | Selezionato

Tutti gli altri valori possono essere lasciati per impostazione predefinita.

### <a name="step-336-enable-catalog-role-for-the-servicenow-account"></a>Passaggio 3.3.6: Abilitare il ruolo del catalogo per l'account ServiceNow

Accedere all'account ServiceNow creato con l'ID entità ServiceNow come ID utente e assegnare il ruolo di catalogo. Le istruzioni per assegnare un ruolo a un account ServiceNow sono disponibili qui, [assegnare un ruolo a un utente](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html). Fare riferimento alla tabella all'inizio del [passaggio 3:](#step-3-connection-settings) impostazioni di connessione per fornire l'accesso in lettura a più record della tabella ServiceNow e indicizzare le autorizzazioni per i criteri utente.

Usa ID applicazione come ID client (dal passaggio 3.a) e Segreto client (dal passaggio 3.b) nella configurazione guidata dell'interfaccia di amministrazione per eseguire l'autenticazione nell'istanza di ServiceNow usando Azure AD OpenID Connessione.

## <a name="step-4-select-properties-and-filter-data"></a>Passaggio 4: Selezionare le proprietà e filtrare i dati

In questo passaggio è possibile aggiungere o rimuovere le proprietà disponibili dall'origine dati ServiceNow. Microsoft 365 sono già state selezionate alcune proprietà per impostazione predefinita.

Con una stringa di query ServiceNow è possibile specificare le condizioni per la sincronizzazione degli articoli. È come una clausola **Where** in un'istruzione **SQL Select.** Ad esempio, è possibile scegliere di indicizzare solo gli elementi attivi. Per informazioni sulla creazione di una stringa di query personalizzata, vedere [Generate an encoded query string using a filter](https://docs.servicenow.com/bundle/rome-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).

Utilizzare il pulsante Anteprima risultati per verificare i valori di esempio delle proprietà selezionate e del filtro query.

## <a name="step-5-manage-search-permissions"></a>Passaggio 5: Gestire le autorizzazioni di ricerca

Il connettore ServiceNow supporta le autorizzazioni di ricerca visibili a **Tutti** o Solo gli utenti **con accesso a questa origine dati.** I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione o agli utenti che hanno accesso a tali dati rispettivamente tramite l'autorizzazione criteri utente. Se un elemento del catalogo non è abilitato con criteri utente, verrà visualizzato nei risultati di ricerca di tutti gli utenti dell'organizzazione.

ServiceNow Catalog Graph Connector supporta le autorizzazioni dei criteri utente predefinite senza script avanzati. Quando il connettore rileva un criterio utente con script avanzato, tutti i dati che utilizzano tali criteri utente non verranno visualizzati nei risultati della ricerca.

Se si **sceglie** Solo gli utenti con accesso a questa origine dati, è necessario scegliere ulteriormente se l'istanza di ServiceNow dispone di utenti di cui è stato eseguito il provisioning Azure Active Directory (AAD) o utenti non AAD.

Per identificare l'opzione adatta all'organizzazione:

1. Scegliere **l'opzione AAD** se l'ID  di posta elettronica degli utenti di ServiceNow è uguale all'UPN (UserPrincipalName) degli utenti in AAD.
2. Scegliere **l'opzione Non-AAD** se l'ID di posta elettronica degli utenti di ServiceNow è **diverso** da UserPrincipalName (UPN) degli utenti in AAD. 

>[!NOTE]
> * Se si sceglie AAD come tipo di origine dell'identità, il connettore mappa gli ID di posta elettronica degli utenti ottenuti da ServiceNow direttamente alla proprietà UPN da AAD.
> * Se hai scelto "Non-AAD" per il tipo di identità, vedi Eseguire il mapping delle identità [non di Azure AD](map-non-aad.md) per istruzioni sul mapping delle identità. È possibile utilizzare questa opzione per fornire l'espressione regolare di mapping da ID posta elettronica a UPN.

## <a name="step-6-assign-property-labels"></a>Passaggio 6: Assegnare etichette di proprietà

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="step-7-manage-schema"></a>Passaggio 7: Gestire lo schema

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="step-8-choose-refresh-settings"></a>Passaggio 8: Scegliere le impostazioni di aggiornamento

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

>[!NOTE]
>Per le identità, verrà applicata solo la ricerca per indicizzazione completa pianificata.

## <a name="step-9-review-connection"></a>Passaggio 9: Esaminare la connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

Dopo aver pubblicato la connessione, è necessario personalizzare la pagina dei risultati della ricerca. Per informazioni sulla personalizzazione dei risultati della ricerca, vedere [Personalizzare la pagina dei risultati della ricerca.](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)

## <a name="limitations"></a>Limitazioni
ServiceNow Catalog Graph connector presenta le limitazioni seguenti nella versione più recente:

- *Solo gli utenti che hanno accesso a questa funzionalità dell'origine* dati nel passaggio Gestisci autorizzazioni di ricerca elaborano solo [le autorizzazioni dei criteri](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) utente. Qualsiasi altro tipo di autorizzazioni di accesso non verrà applicato nei risultati della ricerca.
- Le autorizzazioni dei criteri utente configurate nella categoria del catalogo non sono supportate. 
- I criteri utente con script avanzati non sono supportati nella versione corrente. Tutti gli elementi del catalogo con una restrizione di accesso di questo tipo verranno indicizzati negando a tutti l'accesso, ad esempio non verranno visualizzati nei risultati della ricerca per alcun utente finché non vengono supportati.

## <a name="troubleshooting"></a>Risoluzione dei problemi
Dopo aver pubblicato la connessione, personalizzando la pagina dei risultati, è possibile esaminare lo stato nella **scheda Origini** dati nell'interfaccia [di amministrazione.](https://admin.microsoft.com) Per informazioni su come apportare aggiornamenti ed eliminazioni, vedere [Manage your connector](manage-connector.md).
Di seguito sono riportati i passaggi per la risoluzione dei problemi più comuni.
### <a name="1-unable-to-login-due-to-single-sign-on-enabled-servicenow-instance"></a>1. Impossibile eseguire l'accesso a causa di un'Sign-On ServiceNow abilitata per single Sign-On

Se l'organizzazione ha abilitato Single Sign-On (SSO) a ServiceNow, potrebbe verificarsi un problema di accesso con l'account di servizio. Puoi visualizzare l'accesso basato su <em> `login.do` </em> nome utente e password aggiungendo l'URL dell'istanza serviceNow. Esempio. `https://<your-organization-domain>.service-now.com./login.do` 

### <a name="2-unauthorized-or-forbidden-response-to-api-request"></a>2. Risposta non autorizzata o non consentita alla richiesta API

#### <a name="21-check-table-access-permissions"></a>2.1. Controllare le autorizzazioni di accesso alle tabelle
Se viene visualizzata una risposta non consentita o non autorizzata nello stato di connessione, verificare se l'account di servizio ha richiesto l'accesso alle tabelle menzionate nel [passaggio 3: impostazioni di connessione](#step-3-connection-settings). Verificare se tutte le colonne delle tabelle dispongono dell'accesso in lettura.

#### <a name="22-check-if-servicenow-instance-behind-firewall"></a>2.2. Verificare se l'istanza serviceNow è dietro il firewall
Graph Il connettore potrebbe non essere in grado di raggiungere l'istanza di ServiceNow se è dietro un firewall di rete. Sarà necessario consentire esplicitamente l'accesso al Graph Connector. È possibile trovare l'intervallo di indirizzi IP pubblici Graph Connector Service nella tabella seguente. In base all'area del tenant, aggiungerlo all'elenco consenti rete di istanze serviceNow.

 Ambiente | Area geografica | Intervallo
--- | --- | ---
PROD | Nord America | 52.250.92.252/30, 52.224.250.216/30
PROD | Europa | 20.54.41.208/30, 51.105.159.88/30 
PROD | Asia Pacifico | 52.139.188.212/30, 20.43.146.44/30 

#### <a name="23-access-permissions-not-working-as-expected"></a>2.3. Autorizzazioni di accesso non funzionanti come previsto
Se si osservano discrepanze nelle autorizzazioni di accesso applicate ai risultati della ricerca, verificare la configurazione dei criteri utente nell'applicazione dei criteri utente [agli elementi del catalogo.](https://docs.servicenow.com/bundle/orlando-it-service-management/page/product/service-catalog-management/task/t_AppUserCritItemsCat.html)

Se hai altri problemi o vuoi inviare commenti e suggerimenti, scrivici [aka.ms/TalkToGraphConnectors](https://aka.ms/TalkToGraphConnectors)
