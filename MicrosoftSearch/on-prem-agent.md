---
title: Su Prem Agent
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Agente on-Prem
ms.openlocfilehash: 487c5b179e09fd99fa26ae7a237e89ca38b7be4d
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408943"
---
# <a name="on-prem-agent"></a><span data-ttu-id="f55f4-103">Agente on-Prem</span><span class="sxs-lookup"><span data-stu-id="f55f4-103">On-Prem Agent</span></span>

## <a name="graph-connector-agent"></a><span data-ttu-id="f55f4-104">Agente del connettore grafico</span><span class="sxs-lookup"><span data-stu-id="f55f4-104">Graph connector agent</span></span>

<span data-ttu-id="f55f4-105">I connettori su grafico Prem richiedono l'installazione del software dell' *agente del connettore grafico* .</span><span class="sxs-lookup"><span data-stu-id="f55f4-105">On-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="f55f4-106">Consente il trasferimento rapido e sicuro dei dati tra i dati locali e i servizi cloud.</span><span class="sxs-lookup"><span data-stu-id="f55f4-106">It allows quick and secure data transfer between on-premises data and cloud services.</span></span> <span data-ttu-id="f55f4-107">In questo articolo vengono illustrati i passaggi per l'installazione e la configurazione del software.</span><span class="sxs-lookup"><span data-stu-id="f55f4-107">This article guides you through the steps of installing and configuring the software.</span></span> <span data-ttu-id="f55f4-108">Una volta configurata, sarà disponibile per la creazione di connessioni alle origini dati di su-Prem dall'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f55f4-108">Once configured, it will be available for creating connections to your on-prem data sources from the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

## <a name="installation"></a><span data-ttu-id="f55f4-109">Installazione</span><span class="sxs-lookup"><span data-stu-id="f55f4-109">Installation</span></span>

<span data-ttu-id="f55f4-110">Scaricare la versione più recente di agente del connettore grafico usando [questo collegamento](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) e installare il software utilizzando l'installazione guidata.</span><span class="sxs-lookup"><span data-stu-id="f55f4-110">Download the latest version of Graph connector agent using [this link](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) and install the software using the installation wizard.</span></span> <span data-ttu-id="f55f4-111">Con la configurazione consigliata della macchina descritta di seguito, il software può gestire facilmente fino a tre connessioni.</span><span class="sxs-lookup"><span data-stu-id="f55f4-111">With the recommended configuration of the machine described below, the software can seamlessly handle up to three connections.</span></span> <span data-ttu-id="f55f4-112">Tutte le connessioni oltre che potrebbero peggiorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f55f4-112">Any connections beyond that might degrade the performance.</span></span>

<span data-ttu-id="f55f4-113">Configurazione consigliata:</span><span class="sxs-lookup"><span data-stu-id="f55f4-113">Recommended configuration:</span></span>

* <span data-ttu-id="f55f4-114">Windows 10, Windows Server 2012 R2 e successive</span><span class="sxs-lookup"><span data-stu-id="f55f4-114">Windows 10, Windows Server 2012 R2 and above</span></span>
* <span data-ttu-id="f55f4-115">8 core, 3GHz</span><span class="sxs-lookup"><span data-stu-id="f55f4-115">8 cores, 3GHz</span></span>
* <span data-ttu-id="f55f4-116">16GB di RAM, spazio su disco da 1 GB</span><span class="sxs-lookup"><span data-stu-id="f55f4-116">16GB RAM, 1GB Disk Space</span></span>
* <span data-ttu-id="f55f4-117">Accesso alla rete all'origine dati e a Internet tramite 443</span><span class="sxs-lookup"><span data-stu-id="f55f4-117">Network access to data source and internet through 443</span></span>

## <a name="creating-app-for-the-agent"></a><span data-ttu-id="f55f4-118">Creazione di app per l'agente</span><span class="sxs-lookup"><span data-stu-id="f55f4-118">Creating App for the agent</span></span>  

<span data-ttu-id="f55f4-119">Per creare connessioni, è necessario che l'istanza dell'agente venga alimentata con alcuni parametri critici.</span><span class="sxs-lookup"><span data-stu-id="f55f4-119">The agent instance needs to be fed few critical parameters before you create connections.</span></span> <span data-ttu-id="f55f4-120">Questi parametri includono informazioni dettagliate sull'autenticazione necessarie per l'utilizzo di API di ingestione del grafico.</span><span class="sxs-lookup"><span data-stu-id="f55f4-120">These parameters include authentication details required for using Graph ingestion APIs.</span></span>  

<span data-ttu-id="f55f4-121">Passaggi per la creazione di app per l'agente.</span><span class="sxs-lookup"><span data-stu-id="f55f4-121">Steps for creating App for the agent.</span></span>

1. <span data-ttu-id="f55f4-122">Accedere al [portale di Azure](https://portal.azure.com) e accedere con le credenziali di amministratore per il tenant.</span><span class="sxs-lookup"><span data-stu-id="f55f4-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="f55f4-123">Passare alle registrazioni delle app di **Azure Active Directory**  ->  **App registrations** dal riquadro di spostamento e selezionare **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="f55f4-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="f55f4-124">Specificare un nome per l'app e selezionare **registra**.</span><span class="sxs-lookup"><span data-stu-id="f55f4-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="f55f4-125">Prendere nota dell'ID applicazione (client).</span><span class="sxs-lookup"><span data-stu-id="f55f4-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="f55f4-126">Aprire le **autorizzazioni API** dal riquadro di spostamento e selezionare **Aggiungi un'autorizzazione**.</span><span class="sxs-lookup"><span data-stu-id="f55f4-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="f55f4-127">Selezionare **Microsoft Graph** e quindi **autorizzazioni** per le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f55f4-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="f55f4-128">Cercare "ExternalItem. ReadWrite. All" e "directory. Read. All" dalle autorizzazioni e selezionare **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="f55f4-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="f55f4-129">Selezionare **Concedi consenso amministratore per [TenantName]** e confermare selezionando **Sì**.</span><span class="sxs-lookup"><span data-stu-id="f55f4-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="f55f4-130">Verificare che le autorizzazioni siano nello stato concesso.</span><span class="sxs-lookup"><span data-stu-id="f55f4-130">Check that the permissions are in the granted state.</span></span>
     <span data-ttu-id="f55f4-131">![Autorizzazioni visualizzate come concesse in verde sulla colonna a destra.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="f55f4-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

## <a name="configuring-graph-connector-agent"></a><span data-ttu-id="f55f4-132">Configurazione dell'agente del connettore grafico</span><span class="sxs-lookup"><span data-stu-id="f55f4-132">Configuring Graph connector agent</span></span>

<span data-ttu-id="f55f4-133">Dopo aver creato l'applicazione per l'agente, è necessario configurare l'agente con i dettagli di autenticazione corretti.</span><span class="sxs-lookup"><span data-stu-id="f55f4-133">Once you have created the App for the agent, you must configure the agent with appropriate authentication details.</span></span>

<span data-ttu-id="f55f4-134">È possibile fornire informazioni dettagliate sull'autenticazione in uno dei moduli seguenti.</span><span class="sxs-lookup"><span data-stu-id="f55f4-134">Authentication details can be provided in one of the following forms.</span></span>

### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="f55f4-135">Configurazione del segreto client per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="f55f4-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="f55f4-136">Accedere al [portale di Azure](https://portal.azure.com) e accedere con le credenziali di amministratore per il tenant.</span><span class="sxs-lookup"><span data-stu-id="f55f4-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="f55f4-137">Aprire **registrazione app** dal riquadro di spostamento e passare all'app appropriata.</span><span class="sxs-lookup"><span data-stu-id="f55f4-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="f55f4-138">In **Gestisci** selezionare **certificati e segreti**.</span><span class="sxs-lookup"><span data-stu-id="f55f4-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="f55f4-139">Selezionare **nuovo segreto client** e selezionare un periodo di scadenza per il segreto.</span><span class="sxs-lookup"><span data-stu-id="f55f4-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="f55f4-140">Copiare il segreto generato e salvarlo perché non verrà visualizzato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f55f4-140">Copy the generated secret and save it because it will not be shown again.</span></span>
4. <span data-ttu-id="f55f4-141">Utilizzare questo segreto client insieme all'ID applicazione per configurare l'agente.</span><span class="sxs-lookup"><span data-stu-id="f55f4-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="f55f4-142">Non utilizzare spazi vuoti nel campo **nome** dell'agente.</span><span class="sxs-lookup"><span data-stu-id="f55f4-142">Do not use any blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="f55f4-143">Vengono accettati caratteri numerici alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="f55f4-143">Alpha numeric characters are accepted.</span></span>

## <a name="using-thumbprint-certificate-for-authentication"></a><span data-ttu-id="f55f4-144">Utilizzo del certificato di identificazione personale per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="f55f4-144">Using thumbprint certificate for authentication</span></span>

<span data-ttu-id="f55f4-145">Se sono già stati configurati i dettagli dell'autenticazione seguendo [la configurazione del segreto client per l'autenticazione](#configuring-the-client-secret-for-authentication) , è possibile passare direttamente alla [Panoramica dell'installazione](configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="f55f4-145">If you have already configured the authentication details by following [Configuring the client secret for authentication](#configuring-the-client-secret-for-authentication) , then you can jump directly to [Setup overview](configure-connector.md).</span></span>

1. <span data-ttu-id="f55f4-146">Aprire **registrazione app** e selezionare **certificati e segreti** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="f55f4-146">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="f55f4-147">Copiare l'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="f55f4-147">Copy the certificate thumbprint.</span></span>
<span data-ttu-id="f55f4-148">![Elenco dei certificati di thumbrint in caso di selezione di certificati e segreti nel riquadro sinistro](media/onprem-agent/certificates.png)</span><span class="sxs-lookup"><span data-stu-id="f55f4-148">![List of thumbrint certificates when Certificates and secrets is selected in the left pane](media/onprem-agent/certificates.png)</span></span>
2. <span data-ttu-id="f55f4-149">Utilizzare il segreto client o l'identificazione personale per registrare l'agente del connettore grafico.</span><span class="sxs-lookup"><span data-stu-id="f55f4-149">Use either the client secret or thumbprint to register the Graph connector agent.</span></span>
<span data-ttu-id="f55f4-150">![Modulo di registrazione per il nome, l'ID app, il tipo di credenziale e il certificato](media/onprem-agent/register.png)</span><span class="sxs-lookup"><span data-stu-id="f55f4-150">![Register form asking for name, app id, credential type, and certificate](media/onprem-agent/register.png)</span></span>
