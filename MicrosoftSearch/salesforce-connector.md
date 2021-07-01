---
title: Connettore di Graph Salesforce per Microsoft Search
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
description: Configurare il connettore di Graph Salesforce per Microsoft Search
ms.openlocfilehash: 4bef771538934722deaa5deac3959f21246e4529
ms.sourcegitcommit: 93fc70f0073ab45b4dbd702441ac2fc07a7668bc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230935"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="afd4f-103">Connettore Graph Salesforce (anteprima)</span><span class="sxs-lookup"><span data-stu-id="afd4f-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="afd4f-104">Il connettore di Graph Salesforce consente all'organizzazione di indicizzare gli oggetti Contatti, Opportunità, Lead e Account nell'istanza di Salesforce.</span><span class="sxs-lookup"><span data-stu-id="afd4f-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="afd4f-105">Dopo aver configurato il connettore e il contenuto dell'indice da Salesforce, gli utenti finali possono cercare tali elementi da qualsiasi client Microsoft Search client.</span><span class="sxs-lookup"><span data-stu-id="afd4f-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="afd4f-106">Leggere [**l'articolo Setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup instructions.</span><span class="sxs-lookup"><span data-stu-id="afd4f-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="afd4f-107">Questo articolo è per chiunque configura, esegue e monitora un connettore Graph Salesforce.</span><span class="sxs-lookup"><span data-stu-id="afd4f-107">This article is for anyone who configures, runs, and monitors a Salesforce Graph connector.</span></span> <span data-ttu-id="afd4f-108">Integra il processo di configurazione generale e mostra le istruzioni che si applicano solo al connettore di Graph Salesforce.</span><span class="sxs-lookup"><span data-stu-id="afd4f-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="afd4f-109">In questo articolo sono inoltre incluse informazioni [sulle limitazioni](#limitations).</span><span class="sxs-lookup"><span data-stu-id="afd4f-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="afd4f-110">Il connettore di Graph Salesforce attualmente supporta Estate '19 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="afd4f-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="afd4f-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="afd4f-111">Before you get started</span></span>

<span data-ttu-id="afd4f-112">Per connettersi all'istanza di Salesforce, è necessario l'URL dell'istanza di Salesforce, l'ID client e il segreto client per l'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="afd4f-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="afd4f-113">I passaggi seguenti illustrano come l'utente o l'amministratore di Salesforce può ottenere queste informazioni dall'account Salesforce:</span><span class="sxs-lookup"><span data-stu-id="afd4f-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="afd4f-114">Accedere all'istanza di Salesforce e passare a Installazione</span><span class="sxs-lookup"><span data-stu-id="afd4f-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="afd4f-115">Passa a App -> App Manager.</span><span class="sxs-lookup"><span data-stu-id="afd4f-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="afd4f-116">Seleziona **Nuova app connessa.**</span><span class="sxs-lookup"><span data-stu-id="afd4f-116">Select **New connected app**.</span></span>

- <span data-ttu-id="afd4f-117">Completare la sezione API come segue:</span><span class="sxs-lookup"><span data-stu-id="afd4f-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="afd4f-118">Selezionare la casella di controllo **Abilita Oauth Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="afd4f-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="afd4f-119">Specificare l'URL di richiamata come: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="afd4f-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="afd4f-120">Selezionare questi ambiti OAuth necessari.</span><span class="sxs-lookup"><span data-stu-id="afd4f-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="afd4f-121">Accedere e gestire i dati (api)</span><span class="sxs-lookup"><span data-stu-id="afd4f-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="afd4f-122">Eseguire richieste per conto dell'utente in qualsiasi momento (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="afd4f-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="afd4f-123">Selezionare la casella di controllo **Richiedi segreto per il flusso del server Web.**</span><span class="sxs-lookup"><span data-stu-id="afd4f-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="afd4f-124">Salva l'app.</span><span class="sxs-lookup"><span data-stu-id="afd4f-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="afd4f-125">![Sezione API nell'istanza di Salesforce dopo che l'amministratore ha immesso tutte le configurazioni necessarie elencate in precedenza.](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="afd4f-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="afd4f-126">Copiare la chiave consumer e il segreto consumer.</span><span class="sxs-lookup"><span data-stu-id="afd4f-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="afd4f-127">Queste informazioni verranno utilizzate come ID client e segreto client quando si configura il Impostazioni di connessione per il connettore di Graph nel portale di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="afd4f-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="afd4f-128">![Risultati restituiti dalla sezione API nell'istanza di Salesforce dopo che l'amministratore ha inviato tutte le configurazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="afd4f-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="afd4f-129">La chiave consumer si trova nella parte superiore della colonna sinistra e Consumer Secret è in cima alla colonna destra.](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="afd4f-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="afd4f-130">Prima di chiudere l'istanza di Salesforce, segui questi passaggi per assicurarti che i token di aggiornamento non scadono:</span><span class="sxs-lookup"><span data-stu-id="afd4f-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="afd4f-131">Passare a App -> App Manager</span><span class="sxs-lookup"><span data-stu-id="afd4f-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="afd4f-132">Trova l'app creata e seleziona l'elenco a discesa a destra.</span><span class="sxs-lookup"><span data-stu-id="afd4f-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="afd4f-133">Selezionare **Gestisci**</span><span class="sxs-lookup"><span data-stu-id="afd4f-133">Select **Manage**</span></span>
    - <span data-ttu-id="afd4f-134">Selezionare **Modifica criteri**</span><span class="sxs-lookup"><span data-stu-id="afd4f-134">Select **edit policies**</span></span>
    - <span data-ttu-id="afd4f-135">Per i criteri di token di aggiornamento, selezionare **Il token di aggiornamento è valido fino a quando non viene revocato**</span><span class="sxs-lookup"><span data-stu-id="afd4f-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="afd4f-136">![Selezionare il criterio token di aggiornamento denominato "Il token di aggiornamento è valido fino alla revoca"](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="afd4f-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="afd4f-137">È ora possibile utilizzare Amministrazione Microsoft 365 [Center](https://admin.microsoft.com/) per completare il resto del processo di configurazione per il connettore Graph connettore.</span><span class="sxs-lookup"><span data-stu-id="afd4f-137">You can now use the [Microsoft 365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="afd4f-138">Passaggio 1: Aggiungere un connettore Graph nella interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="afd4f-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="afd4f-139">Seguire le istruzioni generali [per l'installazione](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="afd4f-139">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="afd4f-140">Passaggio 2: assegnare un nome alla connessione</span><span class="sxs-lookup"><span data-stu-id="afd4f-140">Step 2: Name the connection</span></span>

<span data-ttu-id="afd4f-141">Seguire le istruzioni generali [per l'installazione](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="afd4f-141">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="afd4f-142">Passaggio 3: Configurare le impostazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="afd4f-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="afd4f-143">Per l'URL dell'istanza, usa https://[dominio].my.salesforce.com dove dominio sarebbe il dominio Salesforce per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="afd4f-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="afd4f-144">Immetti l'ID client e il segreto client ottenuti dall'istanza di Salesforce e seleziona Accedi.</span><span class="sxs-lookup"><span data-stu-id="afd4f-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="afd4f-145">La prima volta che si tenta di accedere con queste impostazioni, verrà visualizzato un popup che richiede di accedere a Salesforce con il nome utente e la password dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="afd4f-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="afd4f-146">Lo screenshot seguente mostra il popup.</span><span class="sxs-lookup"><span data-stu-id="afd4f-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="afd4f-147">Immetti le credenziali e seleziona "Accedi".</span><span class="sxs-lookup"><span data-stu-id="afd4f-147">Enter your credentials and select "Log In".</span></span>

  ![Popup di accesso che richiede nome utente e password.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="afd4f-149">Se il popup non viene visualizzato, potrebbe essere bloccato nel browser, quindi devi consentire i popup e i reindirizzamenti.</span><span class="sxs-lookup"><span data-stu-id="afd4f-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="afd4f-150">Verifica che la connessione sia stata eseguita correttamente cercando un banner verde che indica "Connessione riuscita" come illustrato nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="afd4f-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="afd4f-151">![Screenshot dell'accesso riuscito.</span><span class="sxs-lookup"><span data-stu-id="afd4f-151">![Screenshot of successful login.</span></span> <span data-ttu-id="afd4f-152">Il banner verde "Connessione riuscita" si trova sotto il campo per l'URL dell'istanza di Salesforce](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="afd4f-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="afd4f-153">Passaggio 4: Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="afd4f-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="afd4f-154">Dovrai scegliere quali utenti potranno visualizzare i risultati della ricerca da questa origine dati.</span><span class="sxs-lookup"><span data-stu-id="afd4f-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="afd4f-155">Se si consente solo a determinati utenti di Azure Active Directory (Azure AD) o non di Azure AD di visualizzare i risultati della ricerca, assicurarsi di mappare le identità.</span><span class="sxs-lookup"><span data-stu-id="afd4f-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

### <a name="step-4a-select-permissions"></a><span data-ttu-id="afd4f-156">Passaggio 4.a: Selezionare le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="afd4f-156">Step 4.a: Select permissions</span></span>

<span data-ttu-id="afd4f-157">Puoi scegliere di inserire elenchi di controllo di accesso (ACL) dall'istanza di Salesforce o consentire a tutti gli utenti dell'organizzazione di visualizzare i risultati della ricerca da questa origine dati.</span><span class="sxs-lookup"><span data-stu-id="afd4f-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="afd4f-158">Gli elenchi di controllo di accesso possono includere identità di Azure Active Directory (AAD) (utenti federati da Azure AD a Salesforce), identità non azure AD (utenti salesforce nativi che hanno identità corrispondenti in Azure AD) o entrambi.</span><span class="sxs-lookup"><span data-stu-id="afd4f-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="afd4f-159">Se usi un provider di identità di terze parti come ID ping o secureAuth, devi selezionare "non-AAD" come tipo di identità.</span><span class="sxs-lookup"><span data-stu-id="afd4f-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="afd4f-160">![Schermata Di selezione delle autorizzazioni completata da un amministratore. L'amministratore ha selezionato l'opzione "Solo le persone con accesso a questa origine dati" e ha anche selezionato "AAD" da un menu a discesa di tipi di identità.](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="afd4f-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="afd4f-161">Se si è scelto di inserire un ACL dall'istanza di Salesforce e si è selezionato "non-AAD" per il tipo di identità, vedere Eseguire il mapping delle identità [non di Azure AD](map-non-aad.md) per istruzioni sul mapping delle identità.</span><span class="sxs-lookup"><span data-stu-id="afd4f-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="step-4b-map-aad-identities"></a><span data-ttu-id="afd4f-162">Passaggio 4.b: Mappare le identità AAD</span><span class="sxs-lookup"><span data-stu-id="afd4f-162">Step 4.b: Map AAD identities</span></span>

<span data-ttu-id="afd4f-163">Se si è scelto di inserire un ACL dall'istanza di Salesforce e si è selezionato "AAD" per il tipo di identità, vedere Eseguire il mapping delle identità di [Azure AD](map-aad.md) per istruzioni sul mapping delle identità.</span><span class="sxs-lookup"><span data-stu-id="afd4f-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="afd4f-164">Per informazioni su come configurare Azure AD SSO per Salesforce, vedere questa [esercitazione.](/azure/active-directory/saas-apps/salesforce-tutorial)</span><span class="sxs-lookup"><span data-stu-id="afd4f-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

### <a name="apply-user-mapping-to-sync-your-salesforce-identities-to-azure-ad-identities"></a><span data-ttu-id="afd4f-165">Applicare il mapping degli utenti per sincronizzare le identità di Salesforce con le identità di Azure AD</span><span class="sxs-lookup"><span data-stu-id="afd4f-165">Apply user mapping to sync your Salesforce identities to Azure AD identities</span></span>

<span data-ttu-id="afd4f-166">In questo video è possibile visualizzare il processo di autenticazione nell'istanza di Salesforce, sincronizzare le identità non di Azure Active Directory con le identità di Azure Active Directory e applicare le appropriate limitazione per motivi di sicurezza agli elementi di Salesforce.</span><span class="sxs-lookup"><span data-stu-id="afd4f-166">In this video you can see the process to authenticate to your Salesforce instance, sync your non-Azure Active Directory identities to your Azure Active Directory identities, and apply the proper security trimmings to your Salesforce items.</span></span>

> [!VIDEO https://www.youtube-nocookie.com/embed/SZYiFxZMKcM]

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="afd4f-167">Passaggio 5: Assegnare etichette di proprietà</span><span class="sxs-lookup"><span data-stu-id="afd4f-167">Step 5: Assign property labels</span></span>

<span data-ttu-id="afd4f-168">È possibile assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni.</span><span class="sxs-lookup"><span data-stu-id="afd4f-168">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="afd4f-169">Anche se questo passaggio non è obbligatorio, la presenza di alcune etichette di proprietà migliorerà la pertinenza della ricerca e garantirà risultati di ricerca migliori per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="afd4f-169">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="afd4f-170">Per impostazione predefinita, ad alcune etichette come "Title", "URL", "CreatedBy" e "LastModifiedBy" sono già state assegnate proprietà di origine.</span><span class="sxs-lookup"><span data-stu-id="afd4f-170">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="afd4f-171">Passaggio 6: Gestire lo schema</span><span class="sxs-lookup"><span data-stu-id="afd4f-171">Step 6: Manage schema</span></span>

<span data-ttu-id="afd4f-172">È possibile selezionare le proprietà di origine da indicizzare in modo che siano visualizzate nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="afd4f-172">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="afd4f-173">Per impostazione predefinita, la connessione guidata seleziona uno schema di ricerca basato su un set di proprietà di origine.</span><span class="sxs-lookup"><span data-stu-id="afd4f-173">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="afd4f-174">È possibile modificarlo selezionando le caselle di controllo per ogni proprietà e attributo nella pagina dello schema di ricerca.</span><span class="sxs-lookup"><span data-stu-id="afd4f-174">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="afd4f-175">Gli attributi dello schema di ricerca includono Search, Query, Retrieve e Refine.</span><span class="sxs-lookup"><span data-stu-id="afd4f-175">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="afd4f-176">Affinamento consente di definire le proprietà che possono essere successivamente utilizzate come criteri di affinamento ricerca personalizzati o filtri nell'esperienza di ricerca.</span><span class="sxs-lookup"><span data-stu-id="afd4f-176">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="afd4f-177">![Selezionare lo schema per ogni proprietà di origine.</span><span class="sxs-lookup"><span data-stu-id="afd4f-177">![Select the schema for each source property.</span></span> <span data-ttu-id="afd4f-178">Le opzioni sono Query, Search, Retrieve e Refine](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="afd4f-178">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="afd4f-179">Passaggio 7: Impostare la pianificazione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="afd4f-179">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="afd4f-180">Il connettore Salesforce supporta solo le pianificazioni di aggiornamento per le ricerche per indicizzazione complete attualmente.</span><span class="sxs-lookup"><span data-stu-id="afd4f-180">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="afd4f-181">Una ricerca per indicizzazione completa consente di trovare gli oggetti eliminati e gli utenti precedentemente sincronizzati con l'Microsoft Search indice.</span><span class="sxs-lookup"><span data-stu-id="afd4f-181">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="afd4f-182">La pianificazione consigliata è di una settimana per una ricerca per indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="afd4f-182">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="afd4f-183">Passaggio 8: verificare la connessione</span><span class="sxs-lookup"><span data-stu-id="afd4f-183">Step 8: Review connection</span></span>

<span data-ttu-id="afd4f-184">Seguire le istruzioni generali [per l'installazione](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="afd4f-184">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="afd4f-185">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="afd4f-185">Limitations</span></span>

- <span data-ttu-id="afd4f-186">Il Graph non supporta attualmente la condivisione e la condivisione basate su apex in base al territorio tramite i gruppi personali di Salesforce.</span><span class="sxs-lookup"><span data-stu-id="afd4f-186">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="afd4f-187">Esiste un bug noto nell'API Salesforce utilizzata dal connettore di Graph, in cui le impostazioni predefinite private a livello di organizzazione per i lead non sono attualmente rispettate.</span><span class="sxs-lookup"><span data-stu-id="afd4f-187">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="afd4f-188">Se per un profilo è impostata la sicurezza a livello di campo (FLS, Field Level Security), il connettore di Graph non ingestirà tale campo per i profili nell'organizzazione Salesforce. Di conseguenza, gli utenti non saranno in grado di cercare valori per tali campi e non verranno visualizzati nei risultati.</span><span class="sxs-lookup"><span data-stu-id="afd4f-188">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="afd4f-189">Nella schermata Gestisci schema questi nomi di proprietà standard comuni sono elencati una sola volta, le opzioni sono **Query,** **Cerca,** **Recupera** e Affina e si applicano a tutti o a nessuno.</span><span class="sxs-lookup"><span data-stu-id="afd4f-189">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="afd4f-190">Nome</span><span class="sxs-lookup"><span data-stu-id="afd4f-190">Name</span></span>
    - <span data-ttu-id="afd4f-191">URL</span><span class="sxs-lookup"><span data-stu-id="afd4f-191">Url</span></span>
    - <span data-ttu-id="afd4f-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afd4f-192">Description</span></span>
    - <span data-ttu-id="afd4f-193">Fax</span><span class="sxs-lookup"><span data-stu-id="afd4f-193">Fax</span></span>
    - <span data-ttu-id="afd4f-194">Telefono</span><span class="sxs-lookup"><span data-stu-id="afd4f-194">Phone</span></span>
    - <span data-ttu-id="afd4f-195">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="afd4f-195">MobilePhone</span></span>
    - <span data-ttu-id="afd4f-196">Posta elettronica</span><span class="sxs-lookup"><span data-stu-id="afd4f-196">Email</span></span>
    - <span data-ttu-id="afd4f-197">Tipo</span><span class="sxs-lookup"><span data-stu-id="afd4f-197">Type</span></span>
    - <span data-ttu-id="afd4f-198">Titolo</span><span class="sxs-lookup"><span data-stu-id="afd4f-198">Title</span></span>
    - <span data-ttu-id="afd4f-199">AccountId</span><span class="sxs-lookup"><span data-stu-id="afd4f-199">AccountId</span></span>
    - <span data-ttu-id="afd4f-200">AccountName</span><span class="sxs-lookup"><span data-stu-id="afd4f-200">AccountName</span></span>
    - <span data-ttu-id="afd4f-201">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="afd4f-201">AccountUrl</span></span>
    - <span data-ttu-id="afd4f-202">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="afd4f-202">AccountOwner</span></span>
    - <span data-ttu-id="afd4f-203">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="afd4f-203">AccountOwnerUrl</span></span>
    - <span data-ttu-id="afd4f-204">Proprietario</span><span class="sxs-lookup"><span data-stu-id="afd4f-204">Owner</span></span>
    - <span data-ttu-id="afd4f-205">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="afd4f-205">OwnerUrl</span></span>
    - <span data-ttu-id="afd4f-206">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="afd4f-206">CreatedBy</span></span>
    - <span data-ttu-id="afd4f-207">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="afd4f-207">CreatedByUrl</span></span>
    - <span data-ttu-id="afd4f-208">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="afd4f-208">LastModifiedBy</span></span>
    - <span data-ttu-id="afd4f-209">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="afd4f-209">LastModifiedByUrl</span></span>
    - <span data-ttu-id="afd4f-210">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="afd4f-210">LastModifiedDate</span></span>
    - <span data-ttu-id="afd4f-211">ObjectName</span><span class="sxs-lookup"><span data-stu-id="afd4f-211">ObjectName</span></span>
