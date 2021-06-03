---
title: Azure DevOps Graph connettore per Microsoft Search
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
description: Configurare il connettore Azure DevOps Graph per Microsoft Search
ms.openlocfilehash: bfe04a022360a968424b673ad03ba05f27c8c333
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720953"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="2e225-103">Azure DevOps Graph connettore (anteprima)</span><span class="sxs-lookup"><span data-stu-id="2e225-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="2e225-104">Il connettore Azure DevOps Graph consente all'organizzazione di indicizzare gli elementi di lavoro nell'istanza del servizio Azure DevOps locale.</span><span class="sxs-lookup"><span data-stu-id="2e225-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="2e225-105">Dopo aver configurato il connettore e il contenuto dell'Azure DevOps, gli utenti finali possono cercare tali elementi in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="2e225-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="2e225-106">Leggere [**l'articolo Setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup instructions.</span><span class="sxs-lookup"><span data-stu-id="2e225-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="2e225-107">Questo articolo è per tutti gli utenti che configurano, esere e monitorano un Azure DevOps Graph connettore.</span><span class="sxs-lookup"><span data-stu-id="2e225-107">This article is for anyone who configures, runs, and monitors an Azure DevOps Graph connector.</span></span> <span data-ttu-id="2e225-108">Integra il processo di installazione generale e mostra le istruzioni che si applicano solo al connettore Azure DevOps Graph rete.</span><span class="sxs-lookup"><span data-stu-id="2e225-108">It supplements the general setup process, and shows instructions that apply only for the Azure DevOps Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="2e225-109">Il connettore Azure DevOps supporta solo il Azure DevOps cloud.</span><span class="sxs-lookup"><span data-stu-id="2e225-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="2e225-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015 e TFS 2013 non sono supportati da questo connettore.</span><span class="sxs-lookup"><span data-stu-id="2e225-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="2e225-111">Passaggio 1: Aggiungere un connettore di Graph nell'Microsoft 365 di amministrazione</span><span class="sxs-lookup"><span data-stu-id="2e225-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="2e225-112">Seguire le istruzioni generali [per l'installazione](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="2e225-112">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="2e225-113">Passaggio 2: assegnare un nome alla connessione</span><span class="sxs-lookup"><span data-stu-id="2e225-113">Step 2: Name the connection</span></span>

<span data-ttu-id="2e225-114">Seguire le istruzioni generali [per l'installazione](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="2e225-114">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="2e225-115">Passaggio 3: Configurare le impostazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="2e225-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="2e225-116">Per connettersi all'istanza Azure DevOps, è necessario [](/azure/devops/organizations/accounts/create-organization) il nome dell'Azure DevOps, l'ID app e il segreto client per l'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="2e225-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="2e225-117">Registrare un'app</span><span class="sxs-lookup"><span data-stu-id="2e225-117">Register an app</span></span>

<span data-ttu-id="2e225-118">Registra un'app in Azure DevOps in modo che l'app Microsoft Search possa accedere all'istanza.</span><span class="sxs-lookup"><span data-stu-id="2e225-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="2e225-119">Per altre informazioni, vedi la Azure DevOps su come [registrare un'app.](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)</span><span class="sxs-lookup"><span data-stu-id="2e225-119">To learn more, see Azure DevOps documentation on how to [register an app](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="2e225-120">La tabella seguente fornisce indicazioni su come compilare il modulo di registrazione dell'app:</span><span class="sxs-lookup"><span data-stu-id="2e225-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="2e225-121">Campi obbligatori</span><span class="sxs-lookup"><span data-stu-id="2e225-121">Mandatory Fields</span></span> | <span data-ttu-id="2e225-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e225-122">Description</span></span> | <span data-ttu-id="2e225-123">Valore consigliato</span><span class="sxs-lookup"><span data-stu-id="2e225-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="2e225-124">Nome società</span><span class="sxs-lookup"><span data-stu-id="2e225-124">Company Name</span></span>         | <span data-ttu-id="2e225-125">Nome della società.</span><span class="sxs-lookup"><span data-stu-id="2e225-125">The name of your company.</span></span> | <span data-ttu-id="2e225-126">Utilizzare un valore appropriato</span><span class="sxs-lookup"><span data-stu-id="2e225-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="2e225-127">Nome applicazione</span><span class="sxs-lookup"><span data-stu-id="2e225-127">Application name</span></span>     | <span data-ttu-id="2e225-128">Valore univoco che identifica l'applicazione che si sta autorizzando.</span><span class="sxs-lookup"><span data-stu-id="2e225-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="2e225-129">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="2e225-129">Microsoft Search</span></span>     |
| <span data-ttu-id="2e225-130">Sito Web dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="2e225-130">Application website</span></span>  | <span data-ttu-id="2e225-131">URL dell'applicazione che richiederà l'accesso all'istanza Azure DevOps durante l'installazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="2e225-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="2e225-132">(Obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="2e225-132">(Required).</span></span>  | <span data-ttu-id="2e225-133"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="2e225-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="2e225-134">URL richiamata autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2e225-134">Authorization callback URL</span></span>        | <span data-ttu-id="2e225-135">URL di richiamata obbligatorio a cui il server di autorizzazione reindirizza.</span><span class="sxs-lookup"><span data-stu-id="2e225-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="2e225-136"> https://<span>gcs.office.</span> com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="2e225-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="2e225-137">Ambiti autorizzati</span><span class="sxs-lookup"><span data-stu-id="2e225-137">Authorized scopes</span></span> | <span data-ttu-id="2e225-138">Ambito di accesso per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="2e225-138">The scope of access for the application</span></span> | <span data-ttu-id="2e225-139">Selezionare gli ambiti seguenti: Identità (lettura), Elementi di lavoro (lettura), Gruppi di variabili (lettura), Project e team (lettura), Graph (lettura)</span><span class="sxs-lookup"><span data-stu-id="2e225-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

>[!IMPORTANT]
><span data-ttu-id="2e225-140">Gli ambiti autorizzati selezionati per l'app devono corrispondere agli ambiti esattamente come indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2e225-140">The authorized scopes that you select for the app should match the scopes exactly as listed above.</span></span> <span data-ttu-id="2e225-141">Se si omette uno degli ambiti autorizzati nell'elenco o si aggiunge un altro ambito, l'autorizzazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2e225-141">If you omit one of the authorized scopes in the list, or add another scope, the authorization will fail.</span></span>

<span data-ttu-id="2e225-142">Durante la registrazione dell'app con i dettagli sopra riportati, ottieni **l'ID app** e il **segreto client** che verranno usati per configurare il connettore.</span><span class="sxs-lookup"><span data-stu-id="2e225-142">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="2e225-143">Per revocare l'accesso a qualsiasi app registrata in Azure DevOps, vai a Impostazioni utente nella parte superiore destra dell'Azure DevOps istanza.</span><span class="sxs-lookup"><span data-stu-id="2e225-143">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="2e225-144">Selezionare Profilo e quindi Autorizzazioni nella sezione Sicurezza del riquadro laterale.</span><span class="sxs-lookup"><span data-stu-id="2e225-144">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="2e225-145">Passa il mouse su un'app OAuth autorizzata per visualizzare il pulsante Revoca nell'angolo dei dettagli dell'app.</span><span class="sxs-lookup"><span data-stu-id="2e225-145">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="2e225-146">Impostazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="2e225-146">Connection settings</span></span>

<span data-ttu-id="2e225-147">Dopo aver registrato l'app Microsoft Search con Azure DevOps, puoi completare il passaggio delle impostazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="2e225-147">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="2e225-148">Immetti il nome dell'organizzazione, l'ID app e il segreto client.</span><span class="sxs-lookup"><span data-stu-id="2e225-148">Enter your organization name, App ID, and Client secret.</span></span>

![Applicazione di connessione Impostazioni](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="2e225-150">Configurare i dati: selezionare progetti e campi</span><span class="sxs-lookup"><span data-stu-id="2e225-150">Configure data: select projects and fields</span></span>

<span data-ttu-id="2e225-151">È possibile scegliere per la connessione di indicizzare l'intera organizzazione o progetti specifici.</span><span class="sxs-lookup"><span data-stu-id="2e225-151">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="2e225-152">Se si sceglie di indicizzare l'intera organizzazione, gli elementi in tutti i progetti dell'organizzazione verranno indicizzati.</span><span class="sxs-lookup"><span data-stu-id="2e225-152">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="2e225-153">I nuovi progetti e gli elementi verranno indicizzati durante la successiva ricerca per indicizzazione dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="2e225-153">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="2e225-154">Se si scelgono singoli progetti, verranno indicizzati solo gli elementi di lavoro in tali progetti.</span><span class="sxs-lookup"><span data-stu-id="2e225-154">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Configurare i dati](media/ADO_Configure_data.png)

<span data-ttu-id="2e225-156">Selezionare quindi i campi che si desidera indicizzare e visualizzare in anteprima i dati in questi campi prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="2e225-156">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Scegliere le proprietà](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="2e225-158">Passaggio 4: Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="2e225-158">Step 4: Manage search permissions</span></span>

<span data-ttu-id="2e225-159">Il connettore Azure DevOps supporta le autorizzazioni di ricerca visibili solo agli utenti con  **accesso a questa origine dati** o a **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="2e225-159">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="2e225-160">Se si sceglie Solo gli utenti con accesso a questa origine **dati,** i dati indicizzati verranno visualizzati nei risultati della ricerca per gli utenti che hanno accesso a tali utenti in base alle autorizzazioni per utenti o gruppi a livello di organizzazione, Project o percorso area in Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="2e225-160">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="2e225-161">Se si sceglie **Tutti**, i dati indicizzati verranno visualizzati nei risultati della ricerca per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2e225-161">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="2e225-162">Passaggio 5: Assegnare etichette di proprietà</span><span class="sxs-lookup"><span data-stu-id="2e225-162">Step 5: Assign property labels</span></span>

<span data-ttu-id="2e225-163">Seguire le istruzioni generali [per l'installazione](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="2e225-163">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="2e225-164">Passaggio 6: Gestire lo schema</span><span class="sxs-lookup"><span data-stu-id="2e225-164">Step 6: Manage schema</span></span>

<span data-ttu-id="2e225-165">Seguire le istruzioni generali [per l'installazione](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="2e225-165">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="2e225-166">Passaggio 7: Scegliere le impostazioni di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="2e225-166">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="2e225-167">Il connettore Azure DevOps supporta le pianificazioni di aggiornamento per le ricerche per indicizzazione complete e incrementali.</span><span class="sxs-lookup"><span data-stu-id="2e225-167">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="2e225-168">La pianificazione consigliata è un'ora per una ricerca per indicizzazione incrementale e un giorno per una ricerca per indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="2e225-168">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="2e225-169">Passaggio 8: verificare la connessione</span><span class="sxs-lookup"><span data-stu-id="2e225-169">Step 8: Review connection</span></span>

<span data-ttu-id="2e225-170">Seguire le istruzioni generali [per l'installazione](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="2e225-170">Follow the general [setup instructions](./configure-connector.md).</span></span>

>[!TIP]
><span data-ttu-id="2e225-171">**Tipo di risultato predefinito**</span><span class="sxs-lookup"><span data-stu-id="2e225-171">**Default Result type**</span></span>
>* <span data-ttu-id="2e225-172">Il Azure DevOps registra automaticamente un [tipo di risultato](./customize-search-page.md#step-2-create-the-result-types) dopo la pubblicazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="2e225-172">The Azure DevOps connector automatically registers a [result type](./customize-search-page.md#step-2-create-the-result-types) once the connector is published.</span></span> <span data-ttu-id="2e225-173">Il tipo di risultato utilizza un layout dei [risultati](./customize-results-layout.md) generato dinamicamente in base ai campi selezionati nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="2e225-173">The result type uses a dynamically generated [result layout](./customize-results-layout.md) based on the fields selected in step 3.</span></span> 
>* <span data-ttu-id="2e225-174">È possibile gestire il tipo di risultati accedendo a [**Tipi di risultati**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) nell'Microsoft 365 di [amministrazione.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="2e225-174">You can manage the result type by navigating to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="2e225-175">Il tipo di risultato predefinito verrà denominato `ConnectionId` "Default".</span><span class="sxs-lookup"><span data-stu-id="2e225-175">The default result type will be named as "`ConnectionId`Default".</span></span> <span data-ttu-id="2e225-176">Ad esempio, se l'ID di connessione è , il layout dei risultati `AzureDevOps` sarà denominato: "AzureDevOpsDefault"</span><span class="sxs-lookup"><span data-stu-id="2e225-176">For example, if your connection id is `AzureDevOps`, your result layout will be named: "AzureDevOpsDefault"</span></span>
>* <span data-ttu-id="2e225-177">È inoltre possibile scegliere di creare un tipo di risultato personalizzato, se necessario.</span><span class="sxs-lookup"><span data-stu-id="2e225-177">Also, you can choose to create your own result type if needed.</span></span>

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->