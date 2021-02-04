---
title: Connettore Salesforce Graph per Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore Salesforce Graph per Microsoft Search
ms.openlocfilehash: 6771bc0b234bc2570a8b1fa7174b9b9244cf3958
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097449"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="bcc2b-103">Connettore grafico Salesforce (anteprima)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="bcc2b-104">Il connettore Grafico Salesforce consente all'organizzazione di indicizzare gli oggetti Contatti, Opportunità, Lead e Account nell'istanza salesforce.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="bcc2b-105">Dopo aver configurato il connettore e il contenuto dell'indice da Salesforce, gli utenti finali possono cercare tali elementi da qualsiasi client Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="bcc2b-106">Leggere [**l'articolo setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup process.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="bcc2b-107">Questo articolo è per tutti gli utenti che configurano, eseere e monitorano un connettore Grafico Salesforce.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-107">This article is for anyone who configures, runs, and monitors a Salesforce Graph connector.</span></span> <span data-ttu-id="bcc2b-108">Integra il processo di configurazione generale e mostra le istruzioni applicabili solo per il connettore Grafico Salesforce.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="bcc2b-109">In questo articolo sono inoltre incluse informazioni [sulle limitazioni.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="bcc2b-110">Il connettore Salesforce Graph attualmente supporta Estate '19 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="bcc2b-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="bcc2b-111">Before you get started</span></span>

<span data-ttu-id="bcc2b-112">Per connettersi all'istanza di Salesforce, è necessario l'URL dell'istanza di Salesforce, l'ID client e il segreto client per l'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="bcc2b-113">La procedura seguente illustra come l'utente o l'amministratore di Salesforce può ottenere queste informazioni dall'account Salesforce:</span><span class="sxs-lookup"><span data-stu-id="bcc2b-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="bcc2b-114">Accedere all'istanza di Salesforce e passare al programma di installazione</span><span class="sxs-lookup"><span data-stu-id="bcc2b-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="bcc2b-115">Passa a App -> App Manager.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="bcc2b-116">Selezionare **Nuova app connessa.**</span><span class="sxs-lookup"><span data-stu-id="bcc2b-116">Select **New connected app**.</span></span>

- <span data-ttu-id="bcc2b-117">Completare la sezione API come segue:</span><span class="sxs-lookup"><span data-stu-id="bcc2b-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="bcc2b-118">Selezionare la casella di controllo **Abilita impostazioni Oauth.**</span><span class="sxs-lookup"><span data-stu-id="bcc2b-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="bcc2b-119">Specificare l'URL di richiamata come: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="bcc2b-120">Selezionare questi ambiti OAuth necessari.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="bcc2b-121">Accedere e gestire i dati (api)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="bcc2b-122">Eseguire richieste per conto dell'utente in qualsiasi momento (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="bcc2b-123">Selezionare la casella di controllo **Richiedi segreto per il flusso del server Web.**</span><span class="sxs-lookup"><span data-stu-id="bcc2b-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="bcc2b-124">Salva l'app.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="bcc2b-125">![Sezione API nell'istanza salesforce dopo che l'amministratore ha immesso tutte le configurazioni necessarie elencate in precedenza.](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="bcc2b-126">Copiare la chiave consumer e il segreto consumer.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="bcc2b-127">Queste informazioni verranno utilizzate come ID client e segreto client quando si configurano le impostazioni di connessione per il connettore Graph nel portale di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="bcc2b-128">![Risultati restituiti dalla sezione API nell'istanza salesforce dopo che l'amministratore ha inviato tutte le configurazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="bcc2b-129">Consumer Key si trova nella parte superiore della colonna sinistra e Consumer Secret si trova nella parte superiore della colonna destra.](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="bcc2b-130">Prima di chiudere l'istanza di Salesforce, segui questi passaggi per assicurarti che i token di aggiornamento non scadono:</span><span class="sxs-lookup"><span data-stu-id="bcc2b-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="bcc2b-131">Passare ad App -> App Manager</span><span class="sxs-lookup"><span data-stu-id="bcc2b-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="bcc2b-132">Trova l'app creata e seleziona l'elenco a discesa a destra.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="bcc2b-133">Selezionare **Gestisci**</span><span class="sxs-lookup"><span data-stu-id="bcc2b-133">Select **Manage**</span></span>
    - <span data-ttu-id="bcc2b-134">Selezionare **i criteri di modifica**</span><span class="sxs-lookup"><span data-stu-id="bcc2b-134">Select **edit policies**</span></span>
    - <span data-ttu-id="bcc2b-135">Per i criteri di token di aggiornamento, selezionare **Aggiorna token valido fino a quando non viene revocato**</span><span class="sxs-lookup"><span data-stu-id="bcc2b-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="bcc2b-136">![Selezionare il criterio di aggiornamento token denominato "Il token di aggiornamento è valido fino a quando non viene revocato"](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="bcc2b-137">È ora possibile utilizzare [l'interfaccia di amministrazione di M365](https://admin.microsoft.com/) per completare il resto del processo di configurazione per il connettore Graph.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-137">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="bcc2b-138">Passaggio 1: Aggiungere un connettore Graph nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bcc2b-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="bcc2b-139">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-139">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="bcc2b-140">Passaggio 2: Assegnare un nome alla connessione</span><span class="sxs-lookup"><span data-stu-id="bcc2b-140">Step 2: Name the connection</span></span>

<span data-ttu-id="bcc2b-141">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-141">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="bcc2b-142">Passaggio 3: Configurare le impostazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="bcc2b-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="bcc2b-143">Per l'URL dell'istanza, utilizzare https://[dominio].my.salesforce.com dove dominio sarebbe il dominio Salesforce per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="bcc2b-144">Immetti l'ID client e il segreto client ottenuti dall'istanza di Salesforce e seleziona Accedi.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="bcc2b-145">La prima volta che si tenta di accedere con queste impostazioni, viene visualizzato un popup che richiede di accedere a Salesforce con il nome utente e la password di amministratore.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="bcc2b-146">Lo screenshot seguente mostra il popup.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="bcc2b-147">Immetti le credenziali e seleziona "Accedi".</span><span class="sxs-lookup"><span data-stu-id="bcc2b-147">Enter your credentials and select "Log In".</span></span>

  ![Login pop up asking for Username and password.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="bcc2b-149">Se il popup non viene visualizzato, è possibile che venga bloccato nel browser, pertanto è necessario consentire i popup e i reindirizzamenti.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="bcc2b-150">Verificare che la connessione sia stata eseguita correttamente cercando un banner verde che indica "Connessione riuscita" come illustrato nello screenshot seguente.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="bcc2b-151">![Screenshot dell'accesso riuscito.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-151">![Screenshot of successful login.</span></span> <span data-ttu-id="bcc2b-152">Il banner verde che indica "Connessione riuscita" si trova sotto il campo per l'URL dell'istanza salesforce](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="bcc2b-153">Passaggio 4: Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="bcc2b-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="bcc2b-154">Sarà necessario scegliere quali utenti potranno visualizzare i risultati della ricerca da questa origine dati.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="bcc2b-155">Se si consente solo a determinati utenti di Azure Active Directory (Azure AD) o non di Azure AD di visualizzare i risultati della ricerca, assicurarsi di mappare le identità.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

## <a name="step-4a-select-permissions"></a><span data-ttu-id="bcc2b-156">Passaggio 4a: Selezionare le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="bcc2b-156">Step 4a: Select permissions</span></span>

<span data-ttu-id="bcc2b-157">È possibile scegliere di inserire elenchi di controllo di accesso (ACL) dall'istanza salesforce oppure consentire a tutti gli utenti dell'organizzazione di visualizzare i risultati della ricerca da questa origine dati.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="bcc2b-158">Gli elenchi di controllo di accesso possono includere identità di Azure Active Directory (AAD) (utenti federati da Azure AD a Salesforce), identità non Azure AD (utenti Salesforce nativi con identità corrispondenti in Azure AD) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="bcc2b-159">Se si utilizza un provider di identità di terze parti come ID ping o secureAuth, è necessario selezionare "non AAD" come tipo di identità.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bcc2b-160">![Schermata Di selezione delle autorizzazioni completata da un amministratore. L'amministratore ha selezionato l'opzione "Solo le persone con accesso a questa origine dati" e ha anche selezionato "AAD" da un menu a discesa di tipi di identità.](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="bcc2b-161">Se si è scelto di inserire un elenco di controllo di accesso dall'istanza di Salesforce e si è selezionato "non-AAD" per il tipo di identità, vedere Eseguire il mapping delle identità [non azure AD](map-non-aad.md) per istruzioni sul mapping delle identità.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

## <a name="step-4b-map-aad-identities"></a><span data-ttu-id="bcc2b-162">Passaggio 4b: Mappare le identità AAD</span><span class="sxs-lookup"><span data-stu-id="bcc2b-162">Step 4b: Map AAD identities</span></span>

<span data-ttu-id="bcc2b-163">Se si è scelto di inserire un elenco di controllo di accesso dall'istanza di Salesforce e si è selezionato "AAD" per il tipo di identità, vedere Eseguire il mapping delle identità di [Azure AD](map-aad.md) per istruzioni sul mapping delle identità.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="bcc2b-164">Per informazioni su come configurare Azure AD SSO per Salesforce, vedere questa [esercitazione.](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="bcc2b-165">Passaggio 5: Assegnare etichette di proprietà</span><span class="sxs-lookup"><span data-stu-id="bcc2b-165">Step 5: Assign property labels</span></span>

<span data-ttu-id="bcc2b-166">Puoi assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-166">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="bcc2b-167">Anche se questo passaggio non è obbligatorio, la presenza di alcune etichette di proprietà migliorerà la pertinenza della ricerca e garantirà risultati di ricerca migliori per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-167">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="bcc2b-168">Per impostazione predefinita, ad alcune etichette come "Title", "URL", "CreatedBy" e "LastModifiedBy" sono già state assegnate proprietà di origine.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-168">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="bcc2b-169">Passaggio 6: Gestire lo schema</span><span class="sxs-lookup"><span data-stu-id="bcc2b-169">Step 6: Manage schema</span></span>

<span data-ttu-id="bcc2b-170">È possibile selezionare le proprietà di origine da indicizzare in modo che siano visualizzate nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-170">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="bcc2b-171">Per impostazione predefinita, la Connessione guidata seleziona uno schema di ricerca basato su un set di proprietà di origine.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-171">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="bcc2b-172">È possibile modificarlo selezionando le caselle di controllo per ogni proprietà e attributo nella pagina dello schema di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-172">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="bcc2b-173">Gli attributi dello schema di ricerca includono ricerca, query, recupero e affinamento ricerca.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-173">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="bcc2b-174">Affinamento consente di definire le proprietà che possono essere successivamente utilizzate come criteri di affinamento ricerca o filtri personalizzati nell'esperienza di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-174">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bcc2b-175">![Selezionare lo schema per ogni proprietà di origine.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-175">![Select the schema for each source property.</span></span> <span data-ttu-id="bcc2b-176">Le opzioni sono Query, Ricerca, Recupera e Affina](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-176">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="bcc2b-177">Passaggio 7: Impostare la pianificazione dell'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="bcc2b-177">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="bcc2b-178">Il connettore Salesforce supporta solo le pianificazioni di aggiornamento per le ricerche per indicizzazione complete attualmente.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-178">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="bcc2b-179">Una ricerca per indicizzazione completa consente di individuare gli oggetti eliminati e gli utenti precedentemente sincronizzati con l'indice di Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-179">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="bcc2b-180">La pianificazione consigliata è una settimana per una ricerca per indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-180">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="bcc2b-181">Passaggio 8: esaminare la connessione</span><span class="sxs-lookup"><span data-stu-id="bcc2b-181">Step 8: Review connection</span></span>

<span data-ttu-id="bcc2b-182">Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="bcc2b-182">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="bcc2b-183">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="bcc2b-183">Limitations</span></span>

- <span data-ttu-id="bcc2b-184">Il connettore Graph attualmente non supporta la condivisione e la condivisione basata sul territorio basata su Apex tramite gruppi personali di Salesforce.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-184">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="bcc2b-185">Esiste un bug noto nell'API Salesforce utilizzata dal connettore Graph, in cui le impostazioni predefinite private a livello di organizzazione per i lead non sono attualmente rispettate.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-185">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="bcc2b-186">Se per un profilo è impostata la sicurezza a livello di campo (FLS, Field Level Security), il connettore Graph non inserisce tale campo per i profili nell'organizzazione Salesforce. Di conseguenza, gli utenti non saranno in grado di cercare valori per tali campi, né verranno visualizzati nei risultati.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-186">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="bcc2b-187">Nella schermata Gestisci schema questi nomi di proprietà standard comuni sono elencati una sola volta, le opzioni sono **Query,** **Ricerca,** Recupera e Affina e si applicano a tutti o nessuno.</span><span class="sxs-lookup"><span data-stu-id="bcc2b-187">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="bcc2b-188">Nome</span><span class="sxs-lookup"><span data-stu-id="bcc2b-188">Name</span></span>
    - <span data-ttu-id="bcc2b-189">URL</span><span class="sxs-lookup"><span data-stu-id="bcc2b-189">Url</span></span>
    - <span data-ttu-id="bcc2b-190">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bcc2b-190">Description</span></span>
    - <span data-ttu-id="bcc2b-191">Fax</span><span class="sxs-lookup"><span data-stu-id="bcc2b-191">Fax</span></span>
    - <span data-ttu-id="bcc2b-192">Telefono</span><span class="sxs-lookup"><span data-stu-id="bcc2b-192">Phone</span></span>
    - <span data-ttu-id="bcc2b-193">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="bcc2b-193">MobilePhone</span></span>
    - <span data-ttu-id="bcc2b-194">Posta elettronica</span><span class="sxs-lookup"><span data-stu-id="bcc2b-194">Email</span></span>
    - <span data-ttu-id="bcc2b-195">Tipo</span><span class="sxs-lookup"><span data-stu-id="bcc2b-195">Type</span></span>
    - <span data-ttu-id="bcc2b-196">Titolo</span><span class="sxs-lookup"><span data-stu-id="bcc2b-196">Title</span></span>
    - <span data-ttu-id="bcc2b-197">AccountId</span><span class="sxs-lookup"><span data-stu-id="bcc2b-197">AccountId</span></span>
    - <span data-ttu-id="bcc2b-198">AccountName</span><span class="sxs-lookup"><span data-stu-id="bcc2b-198">AccountName</span></span>
    - <span data-ttu-id="bcc2b-199">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="bcc2b-199">AccountUrl</span></span>
    - <span data-ttu-id="bcc2b-200">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="bcc2b-200">AccountOwner</span></span>
    - <span data-ttu-id="bcc2b-201">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="bcc2b-201">AccountOwnerUrl</span></span>
    - <span data-ttu-id="bcc2b-202">Proprietario</span><span class="sxs-lookup"><span data-stu-id="bcc2b-202">Owner</span></span>
    - <span data-ttu-id="bcc2b-203">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="bcc2b-203">OwnerUrl</span></span>
    - <span data-ttu-id="bcc2b-204">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="bcc2b-204">CreatedBy</span></span>
    - <span data-ttu-id="bcc2b-205">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="bcc2b-205">CreatedByUrl</span></span>
    - <span data-ttu-id="bcc2b-206">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="bcc2b-206">LastModifiedBy</span></span>
    - <span data-ttu-id="bcc2b-207">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="bcc2b-207">LastModifiedByUrl</span></span>
    - <span data-ttu-id="bcc2b-208">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="bcc2b-208">LastModifiedDate</span></span>
    - <span data-ttu-id="bcc2b-209">ObjectName</span><span class="sxs-lookup"><span data-stu-id="bcc2b-209">ObjectName</span></span>
