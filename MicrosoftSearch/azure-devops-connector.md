---
title: Connettore di DevOps di Azure per Microsoft Search
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore di DevOps di Azure per Microsoft Search
ms.openlocfilehash: e2698d7d4a50c15bf765aa4eeada20fbc7328772
ms.sourcegitcommit: 7eda9b621def0659d7e7bc8b989f8adc929cce93
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "44861104"
---
# <a name="azure-devops-connector"></a><span data-ttu-id="c518d-103">Connettore DevOps di Azure</span><span class="sxs-lookup"><span data-stu-id="c518d-103">Azure DevOps connector</span></span>

<span data-ttu-id="c518d-104">Con il connettore di Azure DevOps, l'organizzazione può indicizzare gli elementi di lavoro nella relativa istanza del servizio DevOps di Azure.</span><span class="sxs-lookup"><span data-stu-id="c518d-104">With the Azure DevOps connector, your organization can index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="c518d-105">Dopo aver configurato il connettore e l'indice del contenuto da Azure DevOps, gli utenti finali possono cercare gli elementi in Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="c518d-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

<span data-ttu-id="c518d-106">Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitora un connettore di DevOps di Azure.</span><span class="sxs-lookup"><span data-stu-id="c518d-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Azure DevOps connector.</span></span> <span data-ttu-id="c518d-107">In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="c518d-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c518d-108">Il connettore di Azure DevOps supporta solo il servizio cloud di DevOps di Azure.</span><span class="sxs-lookup"><span data-stu-id="c518d-108">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="c518d-109">Azure DevOps server 2019, TFS 2018, TFS 2017, TFS 2015 e TFS 2013 non sono supportati da questo connettore.</span><span class="sxs-lookup"><span data-stu-id="c518d-109">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="c518d-110">Connettersi a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="c518d-110">Connect to a data source</span></span>

<span data-ttu-id="c518d-111">Per connettersi all'istanza di Azure DevOps, è necessario il nome dell' [organizzazione](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) di Azure DevOps, il relativo ID app e il segreto client per l'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="c518d-111">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="c518d-112">Registrare un'app</span><span class="sxs-lookup"><span data-stu-id="c518d-112">Register an app</span></span>

<span data-ttu-id="c518d-113">È necessario registrare un'app in Azure DevOps in modo che l'app di ricerca di Microsoft possa accedere all'istanza.</span><span class="sxs-lookup"><span data-stu-id="c518d-113">You must register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="c518d-114">Per ulteriori informazioni, vedere la documentazione di Azure DevOps su come [registrare un'app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span><span class="sxs-lookup"><span data-stu-id="c518d-114">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="c518d-115">Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di registrazione delle app:</span><span class="sxs-lookup"><span data-stu-id="c518d-115">The following table provides guidance on how to fill out the app registration form:</span></span>

 <span data-ttu-id="c518d-116">**Campi obbligatori**</span><span class="sxs-lookup"><span data-stu-id="c518d-116">**Mandatory Fields**</span></span> | <span data-ttu-id="c518d-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c518d-117">**Description**</span></span>      | <span data-ttu-id="c518d-118">**Valore consigliato**</span><span class="sxs-lookup"><span data-stu-id="c518d-118">**Recommended Value**</span></span>
--- | --- | ---
| <span data-ttu-id="c518d-119">Nome della società</span><span class="sxs-lookup"><span data-stu-id="c518d-119">Company Name</span></span>         | <span data-ttu-id="c518d-120">Questo è il nome della società.</span><span class="sxs-lookup"><span data-stu-id="c518d-120">This is the name of your company.</span></span> | <span data-ttu-id="c518d-121">Utilizzare un valore appropriato</span><span class="sxs-lookup"><span data-stu-id="c518d-121">Use an appropriate value</span></span>   |
| <span data-ttu-id="c518d-122">Nome applicazione</span><span class="sxs-lookup"><span data-stu-id="c518d-122">Application name</span></span>     | <span data-ttu-id="c518d-123">Questo valore univoco identifica l'applicazione che si sta autorizzando.</span><span class="sxs-lookup"><span data-stu-id="c518d-123">This unique value identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="c518d-124">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="c518d-124">Microsoft Search</span></span>     |
| <span data-ttu-id="c518d-125">Sito Web dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="c518d-125">Application website</span></span>  | <span data-ttu-id="c518d-126">Questo campo obbligatorio è l'URL dell'applicazione che richiederà l'accesso all'istanza di Azure DevOps durante l'installazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="c518d-126">This required field is the URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span>  | <https://gcs.office.com/>                |
| <span data-ttu-id="c518d-127">URL di callback di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c518d-127">Authorization callback URL</span></span>        | <span data-ttu-id="c518d-128">Un URL di callback obbligatorio a cui il server di autorizzazione reindirizza.</span><span class="sxs-lookup"><span data-stu-id="c518d-128">A required callback URL that the authorization server redirects to.</span></span> | <https://gcs.office.com/v1.0/admin/oauth/callback>|
| <span data-ttu-id="c518d-129">Ambiti autorizzati</span><span class="sxs-lookup"><span data-stu-id="c518d-129">Authorized scopes</span></span> | <span data-ttu-id="c518d-130">Questo è l'ambito di accesso per l'applicazione</span><span class="sxs-lookup"><span data-stu-id="c518d-130">This is the scope of access for the application</span></span> | <span data-ttu-id="c518d-131">Selezionare gli ambiti seguenti: Identity (lettura), elementi di lavoro (lettura), gruppi di variabili (lettura), progetto e team (lettura)</span><span class="sxs-lookup"><span data-stu-id="c518d-131">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read)</span></span>|

<span data-ttu-id="c518d-132">Durante la registrazione dell'app con i dettagli sopra riportati, si otterrà l' **ID app** e il **segreto client** che verrà utilizzato per configurare il connettore.</span><span class="sxs-lookup"><span data-stu-id="c518d-132">On registering the app with the details above, you will get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="c518d-133">Per revocare l'accesso a qualsiasi applicazione registrata in Azure DevOps, passare a impostazioni utente all'inizio destro dell'istanza di DevOps di Azure.</span><span class="sxs-lookup"><span data-stu-id="c518d-133">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="c518d-134">Fare clic su profilo e quindi su autorizzazioni nella sezione sicurezza del riquadro laterale.</span><span class="sxs-lookup"><span data-stu-id="c518d-134">Click on Profile and then click on Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="c518d-135">Posizionare il puntatore del mouse su un'app OAuth autorizzata per visualizzare il pulsante revoca all'angolo dei dettagli dell'app.</span><span class="sxs-lookup"><span data-stu-id="c518d-135">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="c518d-136">Impostazioni di connessione</span><span class="sxs-lookup"><span data-stu-id="c518d-136">Connection settings</span></span>

<span data-ttu-id="c518d-137">Dopo la registrazione dell'app di ricerca di Microsoft con Azure DevOps, è possibile completare il passaggio delle impostazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="c518d-137">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="c518d-138">Immettere il nome dell'organizzazione, l'ID app e il segreto client.</span><span class="sxs-lookup"><span data-stu-id="c518d-138">Enter your organization name, App ID, and Client secret.</span></span>

![Impostazioni dell'applicazione di connessione](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a><span data-ttu-id="c518d-140">Selezionare progetti e campi</span><span class="sxs-lookup"><span data-stu-id="c518d-140">Select projects and fields</span></span>

<span data-ttu-id="c518d-141">È possibile scegliere di indicizzare l'intera organizzazione o i progetti specifici per la connessione.</span><span class="sxs-lookup"><span data-stu-id="c518d-141">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="c518d-142">Se si sceglie di indicizzare l'intera organizzazione, gli elementi in tutti i progetti nell'organizzazione verranno indicizzati.</span><span class="sxs-lookup"><span data-stu-id="c518d-142">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="c518d-143">I nuovi progetti e gli elementi verranno indicizzati durante la ricerca per indicizzazione successiva dopo la loro creazione.</span><span class="sxs-lookup"><span data-stu-id="c518d-143">New projects and items will be indexed during the next crawl after they are created.</span></span> <span data-ttu-id="c518d-144">Se si scelgono singoli progetti, verranno indicizzati solo gli elementi di lavoro di tali progetti.</span><span class="sxs-lookup"><span data-stu-id="c518d-144">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![Configurazione dei dati](media/ADO_Configure_data.png)

<span data-ttu-id="c518d-146">Successivamente, selezionare i campi in cui si desidera che la connessione indici e visualizza in anteprima i dati in questi campi prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="c518d-146">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![Scegliere Proprietà](media/ADO_choose_properties.png)

## <a name="manage-the-search-schema"></a><span data-ttu-id="c518d-148">Gestire lo schema di ricerca</span><span class="sxs-lookup"><span data-stu-id="c518d-148">Manage the search schema</span></span>

<span data-ttu-id="c518d-149">Configurare il mapping dello schema di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c518d-149">Configure the search schema mapping.</span></span> <span data-ttu-id="c518d-150">È possibile scegliere quali proprietà rendere **Queryable**, **searchable** **reperibili e recuperabili**.</span><span class="sxs-lookup"><span data-stu-id="c518d-150">You can choose which properties to make **queryable**, **searchable** and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="c518d-151">Gestire le autorizzazioni di ricerca</span><span class="sxs-lookup"><span data-stu-id="c518d-151">Manage search permissions</span></span>

<span data-ttu-id="c518d-152">Il connettore di Azure DevOps attualmente supporta solo le autorizzazioni **di ricerca visibili a tutti**.</span><span class="sxs-lookup"><span data-stu-id="c518d-152">The Azure DevOps connector currently only supports search permissions **Visible to Everyone**.</span></span> <span data-ttu-id="c518d-153">I dati indicizzati verranno visualizzati nei risultati della ricerca per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c518d-153">Indexed data will appear in the search results for all users.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="c518d-154">Impostare la pianificazione di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c518d-154">Set the refresh schedule</span></span>

<span data-ttu-id="c518d-155">Il connettore di Azure DevOps supporta le pianificazioni di aggiornamento per le ricerche per indicizzazione complete e incrementali.</span><span class="sxs-lookup"><span data-stu-id="c518d-155">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="c518d-156">Una ricerca per indicizzazione completa trova gli elementi di lavoro eliminati precedentemente sincronizzati con l'indice di ricerca di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c518d-156">A full crawl finds deleted work items that were previously synced to the Microsoft Search index.</span></span> <span data-ttu-id="c518d-157">Viene eseguita una ricerca per indicizzazione completa per sincronizzare tutti gli elementi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c518d-157">A full crawl runs to sync all the work items.</span></span> <span data-ttu-id="c518d-158">Per sincronizzare nuovi elementi di lavoro e aggiornamenti per gli elementi di lavoro esistenti, è necessario pianificare ricerche per indicizzazione incrementali.</span><span class="sxs-lookup"><span data-stu-id="c518d-158">To sync new work items and updates to existing work items, you need to schedule incremental crawls.</span></span>

<span data-ttu-id="c518d-159">La pianificazione consigliata è un'ora per una ricerca per indicizzazione incrementale e un giorno per una ricerca per indicizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="c518d-159">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>