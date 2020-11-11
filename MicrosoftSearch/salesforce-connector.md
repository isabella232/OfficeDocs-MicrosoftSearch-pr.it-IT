---
title: Connettore Salesforce per Microsoft Search
ms.author: rusamai
author: rsamai
manager: jameslao
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Configurare il connettore Salesforce per Microsoft Search
ms.openlocfilehash: 8de7784cae7d430bc385889bd836360c69492591
ms.sourcegitcommit: 77ec27736f3c8434b2ac47e10897ac2606ee8a03
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2020
ms.locfileid: "48992915"
---
# <a name="salesforce-connector"></a><span data-ttu-id="c8701-103">Connettore Salesforce</span><span class="sxs-lookup"><span data-stu-id="c8701-103">Salesforce connector</span></span>

<span data-ttu-id="c8701-104">Con il connettore di Salesforce Graph, l'organizzazione può indicizzare i contatti, le opportunità, i lead e gli oggetti account nell'istanza di Salesforce.</span><span class="sxs-lookup"><span data-stu-id="c8701-104">With the Salesforce Graph connector, your organization can index Contacts, Opportunities, Leads and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="c8701-105">Dopo aver configurato il connettore e indicizzare il contenuto da Salesforce, gli utenti finali possono cercare gli elementi da qualsiasi client di ricerca di Microsoft</span><span class="sxs-lookup"><span data-stu-id="c8701-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client</span></span>

<span data-ttu-id="c8701-106">Questo articolo è per gli amministratori di [Microsoft 365](https://www.microsoft.com/microsoft-365) o per tutti coloro che configurano, eseguono e monitorano un connettore Salesforce.</span><span class="sxs-lookup"><span data-stu-id="c8701-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors a Salesforce connector.</span></span> <span data-ttu-id="c8701-107">In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="c8701-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c8701-108">Il connettore di Salesforce Graph supporta attualmente le versioni Summer '20, Spring '20, Winter '20 e Summer '19.</span><span class="sxs-lookup"><span data-stu-id="c8701-108">The Salesforce Graph connector currently supports Summer ’20, Spring’20, Winter’20, and Summer ’19 versions.</span></span>

## <a name="connection-settings"></a><span data-ttu-id="c8701-109">Impostazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="c8701-109">Connection settings</span></span>

<span data-ttu-id="c8701-110">Per connettersi all'istanza di Salesforce, è necessario l'URL dell'istanza di Salesforce, l'ID client e il segreto client per l'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="c8701-110">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="c8701-111">Nei passaggi seguenti viene illustrato come l'amministratore di Salesforce può ottenere queste informazioni dall'account Salesforce:</span><span class="sxs-lookup"><span data-stu-id="c8701-111">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="c8701-112">Accedere all'istanza di Salesforce e passare a installazione</span><span class="sxs-lookup"><span data-stu-id="c8701-112">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="c8701-113">Accedere a Apps-> App Manager.</span><span class="sxs-lookup"><span data-stu-id="c8701-113">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="c8701-114">Seleziona **nuova app connessa**.</span><span class="sxs-lookup"><span data-stu-id="c8701-114">Select **New connected app**.</span></span>

- <span data-ttu-id="c8701-115">Completare la sezione API come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c8701-115">Complete the API section as follows:</span></span>

    - <span data-ttu-id="c8701-116">Selezionare la casella di controllo per **abilitare le impostazioni OAuth**.</span><span class="sxs-lookup"><span data-stu-id="c8701-116">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="c8701-117">Specificare l'URL di callback come: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="c8701-117">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="c8701-118">Selezionare gli ambiti OAuth necessari.</span><span class="sxs-lookup"><span data-stu-id="c8701-118">Select these required OAuth scopes.</span></span> 

        - <span data-ttu-id="c8701-119">Accedere e gestire i dati (API)</span><span class="sxs-lookup"><span data-stu-id="c8701-119">Access and manage your data (api)</span></span> 

        - <span data-ttu-id="c8701-120">Eseguire richieste per conto dell'utente in qualsiasi momento (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="c8701-120">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span> 

    - <span data-ttu-id="c8701-121">Selezionare la casella di controllo **Richiedi segreto per il flusso del server Web**.</span><span class="sxs-lookup"><span data-stu-id="c8701-121">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="c8701-122">Salvare l'app.</span><span class="sxs-lookup"><span data-stu-id="c8701-122">Save the app.</span></span>
    
      ![Sezione API nell'istanza di Salesforce dopo che l'amministratore ha immesso tutte le configurazioni richieste sopra elencate.](media/salesforce-connector/sf1.png)

- <span data-ttu-id="c8701-124">Copiare la chiave consumer e il segreto del consumer.</span><span class="sxs-lookup"><span data-stu-id="c8701-124">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="c8701-125">Queste verranno utilizzate come ID client e segreto client quando si configurano le impostazioni di connessione per il connettore grafico nel portale di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c8701-125">These will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  ![Risultati restituiti dalla sezione API nell'istanza di Salesforce dopo che l'amministratore ha inviato tutte le configurazioni necessarie.](media/salesforce-connector/clientsecret.png)
- <span data-ttu-id="c8701-128">Prima di chiudere l'istanza di Salesforce, attenersi alla procedura seguente per verificare che i token di aggiornamento non scadano:</span><span class="sxs-lookup"><span data-stu-id="c8701-128">Before closing your Salesforce instance, perform the following steps to ensure that refresh tokens do not expire:</span></span> 
    - <span data-ttu-id="c8701-129">Andare a Apps-> App Manager</span><span class="sxs-lookup"><span data-stu-id="c8701-129">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="c8701-130">Individuare l'app appena creata e selezionare l'elenco a discesa a destra.</span><span class="sxs-lookup"><span data-stu-id="c8701-130">Find the app you just created and select the drop down on the right.</span></span> <span data-ttu-id="c8701-131">Selezionare **Gestisci**</span><span class="sxs-lookup"><span data-stu-id="c8701-131">Select **Manage**</span></span>
    - <span data-ttu-id="c8701-132">Selezionare **modifica criteri**</span><span class="sxs-lookup"><span data-stu-id="c8701-132">Select **edit policies**</span></span>
    - <span data-ttu-id="c8701-133">Per i criteri token di aggiornamento, selezionare **Aggiorna token è valido finché non è stato revocato** .</span><span class="sxs-lookup"><span data-stu-id="c8701-133">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  ![Selezionare il criterio token di aggiornamento denominato "il token di aggiornamento è valido finché non è stato revocato"](media/salesforce-connector/oauthpolicies.png)

<span data-ttu-id="c8701-135">È ora possibile utilizzare l'interfaccia di [amministrazione di M365](https://admin.microsoft.com/) per completare il resto del processo di installazione per il connettore grafico.</span><span class="sxs-lookup"><span data-stu-id="c8701-135">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>  

<span data-ttu-id="c8701-136">Configurare le impostazioni di connessione per il connettore grafico come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c8701-136">Configure the Connection settings for your Graph connector as follows:</span></span>

- <span data-ttu-id="c8701-137">Per l'URL dell'istanza, utilizzare https://[Domain]. My. salesforce. com, dove Domain sarebbe il dominio Salesforce per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c8701-137">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span> 
- <span data-ttu-id="c8701-138">Immettere l'ID client e il segreto client ottenuti dall'istanza di Salesforce e selezionare Accedi.</span><span class="sxs-lookup"><span data-stu-id="c8701-138">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>
- <span data-ttu-id="c8701-139">Se è la prima volta che si cerca di accedere con queste impostazioni, viene visualizzato un pop up che richiede l'accesso a Salesforce con il nome utente e la password di amministratore.</span><span class="sxs-lookup"><span data-stu-id="c8701-139">If this is the first time you have attempted to Sign in with these settings, you will get a pop up asking you to login to Salesforce with your admin username and password.</span></span> <span data-ttu-id="c8701-140">Nella schermata seguente viene visualizzato il popup.</span><span class="sxs-lookup"><span data-stu-id="c8701-140">The screenshot below shows the popup.</span></span> <span data-ttu-id="c8701-141">Immettere le credenziali e selezionare Accedi.</span><span class="sxs-lookup"><span data-stu-id="c8701-141">Enter your credentials and select Log in.</span></span>

  ![Login pop up per richiedere nome utente e password.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="c8701-143">Se il pop-up non viene visualizzato, potrebbe essere bloccato nel browser, quindi è necessario consentire popup e reindirizzamenti.</span><span class="sxs-lookup"><span data-stu-id="c8701-143">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

  >[!NOTE]
  ><span data-ttu-id="c8701-144">Se nell'organizzazione viene utilizzato il servizio Single Sign-on (SSO), è possibile selezionare **Usa dominio personalizzato** nell'angolo inferiore destro dell'interfaccia di accesso.</span><span class="sxs-lookup"><span data-stu-id="c8701-144">If your organization uses single sign-on (SSO), you can select **Use Custom Domain** in the bottom, right-hand corner of the login interface.</span></span> <span data-ttu-id="c8701-145">Immettere il dominio e quindi fare clic su **continua**.</span><span class="sxs-lookup"><span data-stu-id="c8701-145">Enter the domain and then select **Continue**.</span></span> <span data-ttu-id="c8701-146">Passerà alla pagina di accesso specifica dell'organizzazione in cui si avrà la possibilità di accedere con SSO.</span><span class="sxs-lookup"><span data-stu-id="c8701-146">It will go to your organization specific login page where you will have an option to login with SSO.</span></span>

- <span data-ttu-id="c8701-147">Verificare che la connessione abbia avuto esito positivo tramite la ricerca di un banner verde che dica "connessione completata" come mostrato nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="c8701-147">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  ![Schermata di accesso con esito positivo.](media/salesforce-connector/sf5.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="c8701-150">Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="c8701-150">Manage search permissions</span></span>
<span data-ttu-id="c8701-151">Sarà necessario scegliere gli utenti che vedranno i risultati della ricerca da questa origine dati.</span><span class="sxs-lookup"><span data-stu-id="c8701-151">You will need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="c8701-152">Se si consente solo a determinati utenti di Azure Active Directory (AAD) o non AAD di visualizzare i risultati della ricerca, sarà necessario eseguire il mapping delle identità.</span><span class="sxs-lookup"><span data-stu-id="c8701-152">If you allow only certain Azure Active Directory (AAD) or Non-AAD users to see the search results, you will then need to map the identities.</span></span>

### <a name="select-permissions"></a><span data-ttu-id="c8701-153">Selezionare le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c8701-153">Select Permissions</span></span>
<span data-ttu-id="c8701-154">È possibile scegliere di gestire gli elenchi di controllo di accesso (ACL, Access Control List) dall'istanza di Salesforce oppure consentire a tutti gli utenti dell'organizzazione di visualizzare i risultati della ricerca dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c8701-154">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or you can allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="c8701-155">Gli elenchi ACL possono includere le identità di Azure Active Directory (AAD), le identità non AAD o entrambe.</span><span class="sxs-lookup"><span data-stu-id="c8701-155">ACLs can include Azure Active Directory (AAD) identities, Non-AAD identities, or both.</span></span>

![Selezionare le autorizzazioni per la schermata completata da un amministratore. L'amministratore ha selezionato l'opzione "solo utenti con accesso all'origine dati" e ha anche selezionato "AAD" da un menu a discesa dei tipi di identità.](media/salesforce-connector/sf6.png)

### <a name="map-non-aad-identities"></a><span data-ttu-id="c8701-157">Mapping delle identità non AAD</span><span class="sxs-lookup"><span data-stu-id="c8701-157">Map non-AAD identities</span></span> 
<span data-ttu-id="c8701-158">Se si è scelto di ingerire un elenco di controllo di accesso dall'istanza di Salesforce e "non AAD" selezionato per il tipo di identità, vedere [Map Your non-Azure ad ](map-non-aad.md) identitys per istruzioni sul mapping delle identità.</span><span class="sxs-lookup"><span data-stu-id="c8701-158">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type see [Map your non-Azure AD Identities ](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="map-aad-identities"></a><span data-ttu-id="c8701-159">Mapping delle identità di AAD</span><span class="sxs-lookup"><span data-stu-id="c8701-159">Map AAD identities</span></span>
<span data-ttu-id="c8701-160">Se si è scelto di ingerire un elenco di controllo di accesso dall'istanza di Salesforce e "AAD" selezionato per il tipo di identità, vedere [mappare le identità di Azure ad](map-aad.md) per istruzioni sul mapping delle identità.</span><span class="sxs-lookup"><span data-stu-id="c8701-160">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="c8701-161">Assegnare etichette delle proprietà</span><span class="sxs-lookup"><span data-stu-id="c8701-161">Assign property labels</span></span> 
<span data-ttu-id="c8701-162">È possibile assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni.</span><span class="sxs-lookup"><span data-stu-id="c8701-162">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="c8701-163">Anche se questo passaggio non è obbligatorio, l'utilizzo di alcune etichette di proprietà migliorerà la pertinenza della ricerca e assicurerà risultati di ricerca più accurati per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="c8701-163">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span> <span data-ttu-id="c8701-164">Per impostazione predefinita, alcune delle etichette come "title", "URL" e "LastModifiedBy" sono già state assegnate proprietà di origine.</span><span class="sxs-lookup"><span data-stu-id="c8701-164">By default, some of the Labels like ”Title”, “url”, and  “LastModifiedBy” have already been assigned source properties.</span></span>

![Assegnare la schermata etichette proprietà per visualizzare le proprietà di origine predefinite.](media/salesforce-connector/sf8.png)

## <a name="manage-schema"></a><span data-ttu-id="c8701-166">Gestione dello schema</span><span class="sxs-lookup"><span data-stu-id="c8701-166">Manage Schema</span></span>
<span data-ttu-id="c8701-167">È possibile selezionare le proprietà di origine che devono essere indicizzate in modo che possano essere visualizzate nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="c8701-167">You can select what source properties should be indexed so that they can show up in search results.</span></span> <span data-ttu-id="c8701-168">Per impostazione predefinita, la connessione guidata consente di selezionare uno schema di ricerca basato su un insieme di proprietà di origine.</span><span class="sxs-lookup"><span data-stu-id="c8701-168">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="c8701-169">È possibile modificarlo selezionando le caselle di controllo per ogni proprietà e attributo nella pagina schema di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c8701-169">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="c8701-170">Gli attributi dello schema di ricerca includono ricerca, query, recupero e affinamento.</span><span class="sxs-lookup"><span data-stu-id="c8701-170">Search schema attributes include Search, Query, Retrieve and Refine.</span></span> <span data-ttu-id="c8701-171">Affina consente di definire le proprietà che possono essere utilizzate in un secondo momento come affinamenti o filtri personalizzati nell'esperienza di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c8701-171">Refine allows you to define the properties which can be later used as custom refiners or filters in the search experience.</span></span>  

![Selezionare lo schema per ogni proprietà di origine.](media/salesforce-connector/sf9.png)

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="c8701-174">Impostare la pianificazione di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c8701-174">Set the refresh schedule</span></span>

<span data-ttu-id="c8701-175">Il connettore Salesforce supporta solo le pianificazioni di aggiornamento per le ricerche per indicizzazione complete attualmente.</span><span class="sxs-lookup"><span data-stu-id="c8701-175">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c8701-176">Una ricerca per indicizzazione completa trova gli oggetti eliminati e gli utenti precedentemente sincronizzati con l'indice di ricerca di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8701-176">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="c8701-177">La pianificazione consigliata è una settimana per una ricerca per indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="c8701-177">The recommended schedule is one week for a full crawl.</span></span>

## <a name="limitations"></a><span data-ttu-id="c8701-178">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="c8701-178">Limitations</span></span>

- <span data-ttu-id="c8701-179">Il connettore grafico attualmente non supporta la condivisione e la condivisione basate sul territorio e l'utilizzo di gruppi personali da Salesforce.</span><span class="sxs-lookup"><span data-stu-id="c8701-179">The Graph connector does not currently support Apex based , territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="c8701-180">Nell'API di Salesforce è presente un bug noto che il connettore grafico utilizza in cui le impostazioni predefinite per i lead non sono attualmente rispettate.</span><span class="sxs-lookup"><span data-stu-id="c8701-180">There is a known bug in the Salesforce API that the Graph connector uses where the private org wide defaults for leads is not honored currently.</span></span>  
- <span data-ttu-id="c8701-181">Se per un profilo è impostato un campo di sicurezza a livello di campo (FLS), il connettore grafico non inventerà tale campo per i profili di Salesforce org. Gli utenti non potranno quindi eseguire ricerche nei valori per tali campi e non verranno visualizzati nei risultati.</span><span class="sxs-lookup"><span data-stu-id="c8701-181">If a field has field level security (FLS) set for a profile, the Graph connector will not ingest that field for any profiles in that Salesforce org. Users will thus not be able to search on values for those fields, nor will it  show up in the results.</span></span>  
- <span data-ttu-id="c8701-182">Gli eventuali FLS configurati verranno rispettati durante le sincronizzazioni complete del connettore.</span><span class="sxs-lookup"><span data-stu-id="c8701-182">Any FLS set up will be honored during the Full syncs of the connector.</span></span>
- <span data-ttu-id="c8701-183">Nella schermata Gestisci schema questi nomi di proprietà comuni standard sono elencati una volta e la selezione eseguita per renderli disponibili per query, ricercabili e recuperabili si applica a tutti o nessuno.</span><span class="sxs-lookup"><span data-stu-id="c8701-183">In the Manage Schema screen these common standard property names are listed once and the selection done to make them queryable, searchable and retrievable apply to all or none.</span></span>
    - <span data-ttu-id="c8701-184">Nome</span><span class="sxs-lookup"><span data-stu-id="c8701-184">Name</span></span>
    - <span data-ttu-id="c8701-185">URL</span><span class="sxs-lookup"><span data-stu-id="c8701-185">Url</span></span> 
    - <span data-ttu-id="c8701-186">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8701-186">Description</span></span>
    - <span data-ttu-id="c8701-187">Fax</span><span class="sxs-lookup"><span data-stu-id="c8701-187">Fax</span></span>
    - <span data-ttu-id="c8701-188">Telefono</span><span class="sxs-lookup"><span data-stu-id="c8701-188">Phone</span></span>
    - <span data-ttu-id="c8701-189">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="c8701-189">MobilePhone</span></span>
    - <span data-ttu-id="c8701-190">Posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c8701-190">Email</span></span>
    - <span data-ttu-id="c8701-191">Tipo</span><span class="sxs-lookup"><span data-stu-id="c8701-191">Type</span></span>
    - <span data-ttu-id="c8701-192">Titolo</span><span class="sxs-lookup"><span data-stu-id="c8701-192">Title</span></span>
    - <span data-ttu-id="c8701-193">AccountId</span><span class="sxs-lookup"><span data-stu-id="c8701-193">AccountId</span></span>
    - <span data-ttu-id="c8701-194">AccountName</span><span class="sxs-lookup"><span data-stu-id="c8701-194">AccountName</span></span>
    - <span data-ttu-id="c8701-195">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="c8701-195">AccountUrl</span></span>
    - <span data-ttu-id="c8701-196">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="c8701-196">AccountOwner</span></span>
    - <span data-ttu-id="c8701-197">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="c8701-197">AccountOwnerUrl</span></span>
    - <span data-ttu-id="c8701-198">Proprietario</span><span class="sxs-lookup"><span data-stu-id="c8701-198">Owner</span></span>
    - <span data-ttu-id="c8701-199">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="c8701-199">OwnerUrl</span></span>
    - <span data-ttu-id="c8701-200">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="c8701-200">CreatedBy</span></span> 
    - <span data-ttu-id="c8701-201">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="c8701-201">CreatedByUrl</span></span> 
    - <span data-ttu-id="c8701-202">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="c8701-202">LastModifiedBy</span></span> 
    - <span data-ttu-id="c8701-203">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="c8701-203">LastModifiedByUrl</span></span> 
    - <span data-ttu-id="c8701-204">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="c8701-204">LastModifiedDate</span></span>
    - <span data-ttu-id="c8701-205">ObjectName</span><span class="sxs-lookup"><span data-stu-id="c8701-205">ObjectName</span></span> 
