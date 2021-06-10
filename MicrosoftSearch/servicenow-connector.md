---
title: ServiceNow Graph connettore per Microsoft Search
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
description: Configurare il connettore di Graph ServiceNow per Microsoft Search
ms.openlocfilehash: 0b7e752ec67a7c14e4afc2e3bad32124694f8f39
ms.sourcegitcommit: 668930032e77a065c23551b3e8820dcc2c63c0f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52853815"
---
<!---Previous ms.author: kam1 --->


# <a name="servicenow-graph-connector"></a>ServiceNow Graph Connector

Con Microsoft Graph Connector for ServiceNow, l'organizzazione può indicizzare gli articoli della Knowledge Base visibili a tutti gli utenti o con restrizioni con autorizzazioni per i criteri utente all'interno dell'organizzazione. Dopo aver configurato il connettore e il contenuto dell'indice da ServiceNow, gli utenti finali possono cercare tali articoli da qualsiasi client Microsoft Search.  

Questo articolo è per Microsoft 365 amministratori o chiunque configura, esegue e monitora un connettore di Graph ServiceNow. Integra le istruzioni generali fornite nell'articolo [Set up your Graph connector.](configure-connector.md) Se non è già stato fatto, leggere l'intero articolo Configurare il connettore Graph per comprendere il processo di configurazione generale.

Ogni passaggio del processo di installazione è elencato di seguito insieme a una nota che indica che è necessario seguire le [](#troubleshooting) istruzioni di configurazione generali o altre istruzioni che si applicano solo al connettore di Graph ServiceNow, incluse informazioni su Risoluzione dei problemi e [limitazioni.](#limitations)  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nell'Microsoft 365 di amministrazione.
Seguire le istruzioni generali per l'installazione.

## <a name="step-2-name-the-connection"></a>Passaggio 2: assegnare un nome alla connessione.
Seguire le istruzioni generali per l'installazione.


## <a name="step-3-connection-settings"></a>Passaggio 3: Connessione Impostazioni
Per connettersi ai dati ServiceNow, è necessario l'URL dell'istanza **ServiceNow dell'organizzazione.** L'URL dell'istanza ServiceNow dell'organizzazione in genere **https:// &lt; dominio-organizzazione>.service-now.com**. 

Insieme a questo URL, è necessario un **account** di servizio per configurare la connessione a ServiceNow e per consentire a Microsoft Search di aggiornare periodicamente gli articoli della Knowledge Base in base alla pianificazione dell'aggiornamento. L'account del servizio dovrà disporre dell'accesso in lettura ai record della tabella **ServiceNow** seguenti per eseguire correttamente la ricerca per indicizzazione di varie entità.

**Caratteristica** | **Tabelle necessarie per l'accesso in lettura** | **Descrizione**
--- | --- | ---
Indicizzare gli articoli della Knowledge Base disponibili per <em>tutti gli utenti</em> | kb_knowledge | Per la ricerca per indicizzazione di articoli della Knowledge Base
Indicizzare e supportare le autorizzazioni dei criteri utente | kb_uc_can_read_mtom | Who può leggere questa Knowledge Base
| | kb_uc_can_contribute_mtom | Who può contribuire a questa knowledge base
| | kb_uc_cannot_read_mtom | Who leggere questa Knowledge Base
| | kb_uc_cannot_contribute_mtom | Who non può contribuire a questa Knowledge Base
| | sys_user | Lettura tabella utenti
| | sys_user_has_role | Leggere le informazioni sui ruoli degli utenti
| | sys_user_grmember | Lettura dell'appartenenza a un gruppo di utenti
| | user_criteria | Autorizzazioni per la lettura dei criteri utente
| | kb_knowledge_base | Leggere le informazioni della Knowledge Base

È possibile **creare e assegnare un ruolo per** l'account di servizio utilizzato per connettersi a Microsoft Search. [Informazioni su come assegnare il ruolo per gli account ServiceNow.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html) L'accesso in lettura alle tabelle può essere assegnato al ruolo creato. Per informazioni sull'impostazione dell'accesso in lettura ai record di tabella, vedere [Securing Table Records.](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls) 


>[!NOTE]
> ServiceNow Graph Connector può indicizzare gli articoli della Knowledge Base e le autorizzazioni dei criteri utente senza script avanzati. Se un criterio utente contiene uno script avanzato, tutti gli articoli della Knowledge Base correlati verranno nascosti dai risultati della ricerca.

Per autenticare e sincronizzare il contenuto da ServiceNow, scegliere **uno dei tre** metodi supportati: 
 
1. Autenticazione di base 
1. ServiceNow OAuth (scelta consigliata)
1. Azure AD OpenID Connessione

### <a name="basic-authentication"></a>Autenticazione di base

Immettere il nome utente e la password dell'account ServiceNow con **ruolo knowledge** per eseguire l'autenticazione nell'istanza.

### <a name="servicenow-oauth"></a>ServiceNow OAuth

Per usare ServiceNow OAuth per l'autenticazione, un amministratore di ServiceNow deve effettuare il provisioning di un endpoint nell'istanza serviceNow, in modo che l'app Microsoft Search possa accedervi. Per ulteriori informazioni, vedere [Create an endpoint for clients to access the instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) nella documentazione ServiceNow.

Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di creazione degli endpoint:

Campo | Descrizione | Valore consigliato 
--- | --- | ---
Nome | Valore univoco che identifica l'applicazione per cui è necessario l'accesso OAuth. | Microsoft Search
ID client | ID univoco generato automaticamente e di sola lettura per l'applicazione. L'istanza usa l'ID client quando richiede un token di accesso. | ND
Segreto client | Con questa stringa segreta condivisa, l'istanza ServiceNow e Microsoft Search autorizzano le comunicazioni tra loro. | Seguire le procedure consigliate per la sicurezza trattando il segreto come password.
URL di reindirizzamento | URL di richiamata obbligatorio a cui il server di autorizzazione reindirizza. | https://gcs.office.com/v1.0/admin/oauth/callback
Logo URL | URL contenente l'immagine per il logo dell'applicazione. | ND
Attivazione | Selezionare la casella di controllo per rendere attivo il Registro di sistema dell'applicazione. | Impostato su attivo
Durata token di aggiornamento | Numero di secondi in cui un token di aggiornamento è valido. Per impostazione predefinita, i token di aggiornamento scadono tra 100 giorni (8.640.000 secondi). | 31.536.000 (1 anno)
Durata token di accesso | Numero di secondi in cui un token di accesso è valido. | 43.200 (12 ore)

Immettere l'ID client e il segreto client per connettersi all'istanza. Dopo la connessione, utilizzare una credenziale dell'account ServiceNow per autenticare l'autorizzazione per la ricerca per indicizzazione. L'account deve avere almeno **un ruolo** di conoscenza. Fare riferimento alla tabella all'inizio del [passaggio 3: impostazioni](#step-3-connection-settings) di connessione per fornire l'accesso in lettura a più record della tabella ServiceNow e indicizzare le autorizzazioni per i criteri utente.

### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connessione

Per usare Azure AD OpenID Connessione per l'autenticazione, seguire la procedura seguente.

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a>Passaggio 3.a: Registrare una nuova applicazione in Azure Active Directory

Per informazioni sulla registrazione di una nuova applicazione in Azure Active Directory, vedere [Register an application](/azure/active-directory/develop/quickstart-register-app#register-an-application). Selezionare la directory organizzativa del tenant singolo. Uri di reindirizzamento non necessario. Dopo la registrazione, annotare l'ID applicazione (client) e l'ID directory (tenant).

## <a name="step-3b-create-a-client-secret"></a>Passaggio 3.b: Creare un segreto client

Per informazioni sulla creazione di un segreto client, vedere [Creazione di un segreto client.](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) Prendere nota del segreto client.

## <a name="step-3c-retrieve-service-principal-object-identifier"></a>Passaggio 3.c: Recuperare l'identificatore dell'oggetto entità servizio

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
   Sostituire "APPLICATION-ID" con Application (client) ID (senza virgolette) dell'applicazione registrata nel passaggio 3.a. Nota il valore dell'oggetto ID dall'output di PowerShell. È l'ID entità servizio.

Ora hai tutte le informazioni necessarie dal portale di Azure. Nella tabella seguente viene fornito un breve riepilogo delle informazioni.

Proprietà | Descrizione 
--- | ---
ID directory (ID tenant) | ID univoco del tenant Azure Active Directory, dal passaggio 3.a.
ID applicazione (ID client) | ID univoco dell'applicazione registrata nel passaggio 3.a.
Segreto client | Chiave privata dell'applicazione (dal passaggio 3.b). Consideralo come una password.
ID entità servizio | Identità per l'applicazione in esecuzione come servizio. (dal passaggio 3.c)

## <a name="step-3d-register-servicenow-application"></a>Passaggio 3.d: Registrare l'applicazione ServiceNow

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

## <a name="step-3e-create-a-servicenow-account"></a>Passaggio 3.e: Creare un account ServiceNow

Fare riferimento alle istruzioni per creare un account ServiceNow, [creare un utente in ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

Nella tabella seguente vengono fornite indicazioni su come compilare la registrazione dell'account utente ServiceNow

Campo | Valore consigliato
--- | ---
ID utente | ID entità servizio dal passaggio 3.c
Solo accesso al servizio Web | Selezionato

Tutti gli altri valori possono essere lasciati per impostazione predefinita.

##### <a name="step-36-enable-knowledge-role-for-the-servicenow-account"></a>Passaggio 3.6: Abilitare il ruolo Conoscenza per l'account ServiceNow

Accedere all'account ServiceNow creato con l'ID entità ServiceNow come ID utente e assegnare il ruolo knowledge. Le istruzioni per assegnare un ruolo a un account ServiceNow sono disponibili qui, [assegnare un ruolo a un utente](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html). Fare riferimento alla tabella all'inizio del [passaggio 3: impostazioni](#step-3-connection-settings) di connessione per fornire l'accesso in lettura a più record della tabella ServiceNow e indicizzare le autorizzazioni per i criteri utente.

Usa ID applicazione come ID client (dal passaggio 3.a) e Segreto client (dal passaggio 3.b) nella configurazione guidata dell'interfaccia di amministrazione per eseguire l'autenticazione nell'istanza di ServiceNow usando Azure AD OpenID Connessione.

## <a name="step-4-select-properties-and-filter-data"></a>Passaggio 4: Selezionare le proprietà e filtrare i dati

In questo passaggio è possibile aggiungere o rimuovere le proprietà disponibili dall'origine dati ServiceNow. Microsoft 365 sono già state selezionate alcune proprietà per impostazione predefinita.

Con una stringa di query ServiceNow è possibile specificare le condizioni per la sincronizzazione degli articoli. È come una clausola **Where** in un'istruzione **select SQL Select.** Ad esempio, è possibile scegliere di indicizzare solo gli articoli pubblicati e attivi. Per informazioni sulla creazione di una stringa di query personalizzata, vedere [Generate an encoded query string using a filter](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).

Utilizzare il pulsante Anteprima risultati per verificare i valori di esempio delle proprietà selezionate e del filtro query.

## <a name="step-5-manage-search-permissions"></a>Passaggio 5: Gestire le autorizzazioni di ricerca

Il connettore ServiceNow supporta le autorizzazioni di ricerca visibili a **Tutti** o Solo gli utenti **con accesso a questa origine dati.** I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione o agli utenti che hanno accesso a tali dati rispettivamente tramite l'autorizzazione criteri utente. Se un articolo della Knowledge Base non è abilitato con criteri utente, verrà visualizzato nei risultati di ricerca di tutti gli utenti dell'organizzazione.

ServiceNow Graph Connector supporta le autorizzazioni dei criteri utente predefinite senza script avanzati. Quando il connettore rileva un criterio utente con script avanzato, tutti i dati che utilizzano tali criteri utente non verranno visualizzati nei risultati della ricerca.

>[!NOTE]
>Per scegliere **Solo gli utenti con accesso a questa origine dati,** abilitare gli aggiornamenti di rilascio mirati nel tenant. Per informazioni sulla configurazione del rilascio mirato, vedere [Setup Targeted release options.](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)

Se si sceglie Solo gli utenti con accesso a questa origine **dati,** è necessario scegliere ulteriormente se l'istanza di ServiceNow dispone di utenti di cui è stato eseguito il provisioning di Azure Active Directory (AAD) o utenti non AAD.

>[!NOTE]
>Se scegli AAD come tipo di origine dell'identità, assicurati di assegnare la proprietà di origine UserPrincipalName (UPN) alla proprietà di destinazione della posta elettronica in ServiceNow. Per verificare o modificare i mapping, vedere [Customizing user provisioning attribute-mappings for SaaS applications in Azure Active Directory](/azure/active-directory/app-provisioning/customize-application-attributes).

Se è stato scelto "non AAD" per il tipo di identità, vedere Eseguire il mapping delle identità [non di Azure AD](map-non-aad.md) per istruzioni sul mapping delle identità. 

Puoi anche fare riferimento al video seguente per altre informazioni sulla gestione delle autorizzazioni di ricerca.

[![Gestione delle autorizzazioni di ricerca in Microsoft Graph Connector for ServiceNow](https://img.youtube.com/vi/TVSkJpk1RiE/hqdefault.jpg)](https://www.youtube.com/watch?v=TVSkJpk1RiE)

## <a name="step-6-assign-property-labels"></a>Passaggio 6: Assegnare etichette di proprietà

Seguire le istruzioni generali per l'installazione.

## <a name="step-7-manage-schema"></a>Passaggio 7: Gestire lo schema

Seguire le istruzioni generali per l'installazione.

## <a name="step-8-choose-refresh-settings"></a>Passaggio 8: Scegliere le impostazioni di aggiornamento

Seguire le istruzioni generali per l'installazione.

>[!NOTE]
>Per le identità, verrà applicata solo la ricerca per indicizzazione completa pianificata.

## <a name="step-9-review-connection"></a>Passaggio 9: Esaminare la connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

ServiceNow Graph connettore presenta le limitazioni seguenti nella versione più recente:

Dopo aver pubblicato la connessione, è necessario personalizzare la pagina dei risultati della ricerca. Per informazioni sulla personalizzazione dei risultati della ricerca, vedere [Personalizzare la pagina dei risultati della ricerca.](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)

## <a name="limitations"></a>Limitazioni
ServiceNow Graph connettore presenta le limitazioni seguenti nella versione più recente:
- L'indicizzazione degli articoli della Knowledge Base disponibili per tutti gli utenti di un'organizzazione è una funzionalità generalmente disponibile.
- *Solo gli utenti che hanno accesso a questa funzionalità dell'origine* dati nel passaggio Gestisci autorizzazioni di ricerca si trova nel canale di rilascio di destinazione ed elabora solo le [autorizzazioni dei criteri utente.](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) Qualsiasi altro tipo di autorizzazioni di accesso non verrà applicato nei risultati della ricerca.
- I criteri utente con script avanzati non sono supportati nella versione corrente. Tutti gli articoli della Knowledge Base con una restrizione di accesso di questo tipo verranno indicizzati negando a tutti l'accesso, ad esempio non verranno visualizzati nei risultati della ricerca per alcun utente finché non vengono supportati.

## <a name="troubleshooting"></a>Risoluzione dei problemi
Dopo aver pubblicato la connessione, personalizzando la pagina dei risultati, è possibile esaminare lo stato nella **scheda Origini** dati nell'interfaccia [di amministrazione.](https://admin.microsoft.com) Per informazioni su come apportare aggiornamenti ed eliminazioni, vedere [Manage your connector](manage-connector.md).
Di seguito sono riportati i passaggi per la risoluzione dei problemi più comuni.
### <a name="1-unable-to-login-due-to-single-sign-on-enabled-servicenow-instance"></a>1. Impossibile eseguire l'accesso a causa di un'Sign-On ServiceNow abilitata per single Sign-On

Se l'organizzazione ha abilitato Single Sign-On (SSO) a ServiceNow, potrebbe verificarsi un problema di accesso con l'account di servizio. Puoi visualizzare l'account di accesso <em> `login.do` </em> basato su nome utente e password aggiungendo l'URL dell'istanza serviceNow. Esempio. `https://<your-organization-domain>.service-now.com./login.do` 

### <a name="2-unauthorized-or-forbidden-response-to-api-request"></a>2. Risposta non autorizzata o non consentita alla richiesta API

#### <a name="21-check-table-access-permissions"></a>2.1. Controllare le autorizzazioni di accesso alle tabelle
Se viene visualizzata una risposta non consentita o non autorizzata nello stato di connessione, verificare se l'account di servizio ha richiesto l'accesso alle tabelle menzionate nel [passaggio 3: impostazioni di connessione](#step-3-connection-settings). Verificare se tutte le colonne delle tabelle dispongono dell'accesso in lettura.

#### <a name="22-check-if-servicenow-instance-behind-firewall"></a>2.2. Verificare se l'istanza di ServiceNow è dietro il firewall
Graph Il connettore potrebbe non essere in grado di raggiungere l'istanza di ServiceNow se è dietro un firewall di rete. Sarà necessario consentire esplicitamente l'accesso Graph Connector. È possibile trovare l'intervallo di indirizzi IP pubblici Graph Connector Service nella tabella seguente. In base all'area del tenant, aggiungerlo all'elenco dei whitelist di rete dell'istanza di ServiceNow.

**Ambiente** | **Area** | **Range**
--- | --- | ---
PROD | Nord America | 52.250.92.252/30, 52.224.250.216/30
PROD | Europa | 20.54.41.208/30, 51.105.159.88/30 
PROD | Asia Pacifico | 52.139.188.212/30, 20.43.146.44/30 


Se hai altri problemi o vuoi fornire feedback, scrivici aka.ms/TalkToGraphConnectors
