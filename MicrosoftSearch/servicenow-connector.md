---
title: Connettore ServiceNow Graph per Microsoft Search
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
description: Configurare il connettore ServiceNow Graph per Microsoft Search
ms.openlocfilehash: eaf8014876b03c0b64c012cf7e83c4e4b84838b9
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508680"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a>ServiceNow Graph Connector

Il connettore ServiceNow Graph consente all'organizzazione di indicizzare articoli basati sulla knowledge base visibili agli utenti in base alle autorizzazioni dei criteri utente all'interno dell'organizzazione. Dopo aver configurato il connettore e il contenuto dell'indice da ServiceNow, gli utenti possono cercare gli articoli da qualsiasi client Microsoft Search.

> [!NOTE]
> Leggere [**l'articolo setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup instructions.

Questo articolo è per tutti gli utenti che configurano, eseguiti e monitorano un connettore ServiceNow Graph. Integra il processo di configurazione generale e mostra le istruzioni applicabili solo al connettore ServiceNow Graph. In questo articolo sono inoltre incluse informazioni sulla [risoluzione dei](#troubleshooting) problemi e [sulle limitazioni.](#limitations)
  
## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nell'interfaccia di amministrazione di Microsoft 365

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Passaggio 2: Assegnare un nome alla connessione

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a>Passaggio 3: Impostazioni di connessione

Per connettersi ai dati ServiceNow, utilizzare le credenziali dell'URL dell'istanza **ServiceNow** dell'organizzazione per questo account, l'ID client e il segreto client per l'autenticazione OAuth.  

L'URL dell'istanza **ServiceNow** dell'organizzazione https:// in genere **&lt;>.service-now.com**. Insieme a questo URL, è necessario un account per configurare la connessione a ServiceNow e per consentire a Microsoft Search di aggiornare gli articoli di ServiceNow in base alla pianificazione dell'aggiornamento. L'account deve avere almeno un <em>ruolo</em> di conoscenza. [Informazioni su come assegnare il ruolo per gli account ServiceNow.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

>[!NOTE]
>Se si desidera eseguire la ricerca per indicizzazione delle identità di utenti e gruppi per rispettare le autorizzazioni di accesso degli articoli della Knowledge Base nei risultati di Microsoft Search, l'account deve avere accesso per leggere i record della tabella seguenti in ServiceNow:
>* kb_uc_can_contribute_mtom
>* kb_uc_can_read_mtom
>* kb_uc_cannot_read_mtom
>* kb_uc_cannot_contribute_mtom
>* sys_user
>* sys_user_has_role
>* sys_user_grmember
>* user_criteria
>* kb_knowledge_base  
> È possibile creare e assegnare un ruolo per l'account utilizzato per connettersi a Microsoft Search. L'accesso in lettura alle tabelle può essere assegnato a tale ruolo. Per informazioni sull'impostazione dell'accesso in lettura ai record di tabella, [vedere Securing Table Records.](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)

Per autenticare e sincronizzare il contenuto da ServiceNow, scegliere **uno dei tre** metodi supportati:

1. Autenticazione di base
1. ServiceNow OAuth (scelta consigliata)
1. Azure AD OpenID Connect

### <a name="basic-authentication"></a>Autenticazione di base

Immettere il nome utente e la password dell'account ServiceNow con **ruolo di** conoscenza per l'autenticazione nell'istanza.

### <a name="servicenow-oauth"></a>ServiceNow OAuth

Per usare ServiceNow OAuth per l'autenticazione, esegui il provisioning di un endpoint nell'istanza ServiceNow. L'app Microsoft Search la utilizzerà per accedere all'istanza. Per altre informazioni, vedi [Creare un endpoint per i client che accedono all'istanza](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) nella documentazione ServiceNow.

La tabella seguente fornisce indicazioni su come compilare il modulo di creazione dell'endpoint:

Campo | Descrizione | Valore consigliato 
--- | --- | ---
Nome | Valore univoco che identifica l'applicazione per cui è necessario l'accesso OAuth. | Microsoft Search
Client ID | ID univoco generato automaticamente di sola lettura per l'applicazione. L'istanza usa l'ID client quando richiede un token di accesso. | ND
Segreto client | Con questa stringa segreta condivisa, l'istanza ServiceNow e Microsoft Search autorizzano le comunicazioni tra loro. | Seguire le procedure consigliate per la sicurezza trattando il segreto come una password.
URL di reindirizzamento | URL di richiamata obbligatorio a cui il server di autorizzazione reindirizza. | https://gcs.office.com/v1.0/admin/oauth/callback
URL logo | URL che contiene l'immagine per il logo dell'applicazione. | ND
Attivazione | Selezionare la casella di controllo per rendere attivo il Registro di sistema dell'applicazione. | Impostato su attivo
Durata del token di aggiornamento | Numero di secondi per cui un token di aggiornamento è valido. Per impostazione predefinita, i token di aggiornamento scadono tra 100 giorni (8.640.000 secondi). | 31.536.000 (1 anno)
Durata del token di accesso | Numero di secondi in cui un token di accesso è valido. | 43.200 (12 ore)

Immettere l'ID client e il segreto client per connettersi all'istanza. Dopo la connessione, utilizzare le credenziali dell'account ServiceNow per autenticare l'autorizzazione per la ricerca per indicizzazione. L'account deve avere almeno un **ruolo** di conoscenza.

### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

Per usare Azure AD OpenID Connect per l'autenticazione, segui i passaggi seguenti.

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a>Passaggio 3.a: Registrare una nuova applicazione in Azure Active Directory

Per informazioni sulla registrazione di una nuova applicazione in Azure Active Directory, vedere [Registrare un'applicazione.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application) Selezionare una singola directory organizzativa tenant. L'URI di reindirizzamento non è necessario. Dopo la registrazione, prendere nota dell'ID applicazione (client) e dell'ID directory (tenant).

## <a name="step-3b-create-a-client-secret"></a>Passaggio 3.b: Creare un segreto client

Per informazioni sulla creazione di un segreto client, vedere [Creazione di un segreto client.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) Prendere nota del segreto client.

## <a name="step-3c-retrieve-service-principal-object-identifier"></a>Passaggio 3.c: Recuperare l'identificatore dell'oggetto entità servizio

Seguire i passaggi per recuperare l'identificatore dell'oggetto entità servizio

1. Eseguire PowerShell.

2. Installare Azure PowerShell utilizzando il comando seguente.

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Connettersi ad Azure.

   ```powershell
   Connect-AzAccount
   ```

4. Ottenere l'identificatore dell'oggetto entità servizio.

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   Sostituire "Application-ID" con l'ID applicazione (client) (senza virgolette) dell'applicazione registrata nel passaggio 3.a. Si noti il valore dell'oggetto ID dall'output di PowerShell. Si tratta dell'ID entità servizio.

Ora hai tutte le informazioni necessarie dal portale di Azure. Nella tabella seguente è riportato un breve riepilogo delle informazioni.

Proprietà | Descrizione 
--- | ---
ID directory (ID tenant) | ID univoco del tenant di Azure Active Directory, dal passaggio 3.a.
ID applicazione (ID client) | ID univoco dell'applicazione registrata nel passaggio 3.a.
Segreto client | Chiave privata dell'applicazione (dal passaggio 3.b). Consideralo come una password.
ID entità servizio | Identità per l'applicazione in esecuzione come servizio. (dal passaggio 3.c)

## <a name="step-3d-register-servicenow-application"></a>Passaggio 3.d: Registrare l'applicazione ServiceNow

L'istanza ServiceNow richiede la configurazione seguente:

1. Registrare una nuova entità OAuth OIDC. Per ulteriori informazioni, vedere [Creare un provider OIDC OAuth.](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)

2. Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di registrazione del provider OIDC

   Campo | Descrizione | Valore consigliato
   --- | --- | ---
   Nome | Nome univoco che identifica l'entità OIDC OAuth. | Azure AD
   Client ID | ID client dell'applicazione registrata nel server OIDC OAuth di terze parti. L'istanza usa l'ID client quando richiede un token di accesso. | ID applicazione (client) del passaggio 3.a
   Segreto client | Il segreto client dell'applicazione registrata nel server OIDC OAuth di terze parti. | Segreto client dal passaggio 3.b

   Tutti gli altri valori possono essere predefiniti.

3. Nel modulo di registrazione del provider OIDC è necessario aggiungere una nuova configurazione del provider OIDC. Selezionare l'icona di ricerca *nel campo OAuth OIDC Provider Configuration* per aprire i record delle configurazioni OIDC. Selezionare Nuovo.

4. Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di configurazione del provider OIDC

   Campo | Valore consigliato
   --- | ---
   OIDC Provider |  Azure AD
   URL metadati OIDC | L'URL deve essere nel formato https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration <br/>Sostituire "tenantID" con l'ID directory (tenant) del passaggio 3.a.
   Durata cache di configurazione OIDC |  120
   Applicazione | Globale
   Attestazione utente | sub
   Campo utente | ID utente
   Abilitare la verifica delle attestazioni JTI | Disattivato

5. Selezionare Invia e aggiorna il modulo entità OIDC OAuth.

## <a name="step-3e-create-a-servicenow-account"></a>Passaggio 3.e: Creare un account ServiceNow

Fare riferimento alle istruzioni per creare un account ServiceNow, [creare un utente in ServiceNow.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)

Nella tabella seguente vengono fornite indicazioni su come compilare la registrazione dell'account utente ServiceNow

Campo | Valore consigliato
--- | ---
ID utente | ID entità servizio del passaggio 3.c
Solo accesso al servizio Web | Selezionata

Tutti gli altri valori possono essere lasciati come predefiniti.

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a>Passaggio 3.f: Abilitare il ruolo Conoscenza per l'account ServiceNow

Accedere all'account ServiceNow creato con l'ID entità ServiceNow come ID utente e assegnare il ruolo di conoscenza. Le istruzioni per assegnare un ruolo a un account ServiceNow sono disponibili qui: [assegnare un ruolo a un utente.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

Usa l'ID applicazione come ID client dal passaggio 3.a e il segreto client del passaggio 3.b per eseguire l'autenticazione nell'istanza di ServiceNow con Azure AD OpenID Connect.

## <a name="step-4-select-properties-and-filter-data"></a>Passaggio 4: Selezionare le proprietà e filtrare i dati

In questo passaggio è possibile aggiungere o rimuovere le proprietà disponibili dall'origine dati ServiceNow. Microsoft 365 ha già selezionato alcune proprietà per impostazione predefinita.

Con una stringa di query ServiceNow, è possibile specificare le condizioni per la sincronizzazione degli articoli. È simile a una **clausola Where** in un'istruzione **SQL Select.** Ad esempio, è possibile scegliere di indicizzare solo gli articoli pubblicati e attivi. Per informazioni sulla creazione di una stringa di query personalizzata, vedere Generare una stringa [di query codificata utilizzando un filtro.](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)

Utilizzare il pulsante dei risultati di anteprima per verificare i valori di esempio delle proprietà selezionate e del filtro di query.

## <a name="step-5-manage-search-permissions"></a>Passaggio 5: Gestire le autorizzazioni di ricerca

Il connettore ServiceNow supporta le autorizzazioni di ricerca visibili per **tutti gli** utenti o solo per gli utenti con accesso a questa **origine dati.** I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile agli utenti dell'organizzazione che hanno accesso a essi rispettivamente. ServiceNow Connector supporta le autorizzazioni dei criteri utente predefinite senza script avanzati. Quando il connettore trova un criterio utente con script avanzato, tutti i dati che utilizzano tali criteri utente non verranno visualizzati nei risultati della ricerca.

Se si seleziona Solo gli utenti con accesso a questa origine **dati,** è necessario scegliere ulteriormente se l'istanza di ServiceNow dispone di utenti di Azure Active Directory (AAD) o utenti non AAD.

>[!NOTE]
>Il connettore ServiceNow è in **anteprima** se si sceglie **Solo gli utenti con accesso a questa origine dati.**

>[!NOTE]
>Se si sceglie AAD come tipo di origine dell'identità, assicurarsi di assegnare la proprietà di origine UPN alla proprietà di destinazione della posta elettronica in ServiceNow. Per verificare o modificare i mapping, vedere Personalizzazione dei mapping degli attributi di provisioning degli utenti per le applicazioni [SaaS in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes)

Se si è scelto di inserire un elenco di controllo di accesso dall'istanza di ServiceNow e si è selezionato "non-AAD" per il tipo di identità, vedere Eseguire il mapping delle identità [non Azure AD](map-non-aad.md) per istruzioni sul mapping delle identità.

## <a name="step-6-assign-property-labels"></a>Passaggio 6: Assegnare etichette di proprietà

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a>Passaggio 7: Gestire lo schema

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a>Passaggio 8: Scegliere le impostazioni di aggiornamento

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
>Per le identità, verrà applicata solo la ricerca per indicizzazione completa pianificata.

## <a name="step-9-review-connection"></a>Passaggio 9: esaminare la connessione

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>Risoluzione dei problemi

Dopo aver pubblicato la connessione, personalizzando la pagina dei risultati, è possibile esaminare lo stato nella scheda **Connettori** [nell'interfaccia di amministrazione.](https://admin.microsoft.com) Per informazioni su come apportare aggiornamenti ed eliminazioni, vedere [Gestire il connettore.](manage-connector.md)

## <a name="limitations"></a>Limitazioni

ServiceNow Graph connector has the following limitations in its latest release:

- L'indicizzazione degli articoli della Knowledge Base disponibili per tutti gli utenti di un'organizzazione è una funzionalità disponibile in generale.
- *Solo gli utenti che hanno accesso a questa funzionalità dell'origine* dati nel passaggio Gestisci autorizzazioni di ricerca sono in anteprima ed elaborano solo le [autorizzazioni dei criteri](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) utente. Qualsiasi altro tipo di autorizzazione di accesso non verrà applicato nei risultati della ricerca.
- I criteri utente con script avanzati non sono supportati nella versione di anteprima corrente. Gli articoli della Knowledge Base con una restrizione di accesso verranno indicizzati negando l'accesso a tutti gli utenti e non verranno visualizzati nei risultati della ricerca per alcun utente finché non vengono supportati.
