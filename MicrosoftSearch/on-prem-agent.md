---
title: Agente locale
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
ms.openlocfilehash: 763904f8dd96c5db8b0633e36795443502afe7d0
ms.sourcegitcommit: 0ed8ec8b3c4e0f5f669005081fd8b2219f07b4f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420834"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="ab30f-103">Agente del connettore grafico</span><span class="sxs-lookup"><span data-stu-id="ab30f-103">Graph connector agent</span></span>

<span data-ttu-id="ab30f-104">L'utilizzo di connettori di Graph su-Prem richiede l'installazione del software dell' *agente del connettore grafico* .</span><span class="sxs-lookup"><span data-stu-id="ab30f-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="ab30f-105">Consente il trasferimento sicuro dei dati tra i dati locali e le API del connettore grafico.</span><span class="sxs-lookup"><span data-stu-id="ab30f-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="ab30f-106">In questo articolo vengono illustrate le istruzioni per l'installazione e la configurazione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ab30f-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="ab30f-107">Installazione</span><span class="sxs-lookup"><span data-stu-id="ab30f-107">Installation</span></span>

<span data-ttu-id="ab30f-108">Scaricare la versione più recente di Graph Connector [Agent e](https://aka.ms/gcadownload) installare il software utilizzando l'installazione guidata.</span><span class="sxs-lookup"><span data-stu-id="ab30f-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="ab30f-109">Usando la configurazione consigliata della macchina descritta di seguito, il software è in grado di gestire fino a tre connessioni.</span><span class="sxs-lookup"><span data-stu-id="ab30f-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="ab30f-110">Tutte le connessioni oltre che potrebbero peggiorare le prestazioni di tutte le connessioni nell'agente.</span><span class="sxs-lookup"><span data-stu-id="ab30f-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="ab30f-111">Configurazione consigliata:</span><span class="sxs-lookup"><span data-stu-id="ab30f-111">Recommended configuration:</span></span>

* <span data-ttu-id="ab30f-112">Windows 10, Windows Server 2016 R2 e successive</span><span class="sxs-lookup"><span data-stu-id="ab30f-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* <span data-ttu-id="ab30f-113">8 core, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="ab30f-113">8 cores, 3 GHz</span></span>
* <span data-ttu-id="ab30f-114">16 GB di RAM, 2 GB di spazio su disco</span><span class="sxs-lookup"><span data-stu-id="ab30f-114">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="ab30f-115">Accesso alla rete all'origine dati e a Internet tramite 443</span><span class="sxs-lookup"><span data-stu-id="ab30f-115">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="ab30f-116">Creare e configurare un'app per l'agente</span><span class="sxs-lookup"><span data-stu-id="ab30f-116">Create and configure an App for the agent</span></span>  

<span data-ttu-id="ab30f-117">Prima di utilizzare l'agente, è necessario creare un'app e configurare i dettagli dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="ab30f-117">Before using the agent, you must create an app and configure the authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="ab30f-118">Creare un'app</span><span class="sxs-lookup"><span data-stu-id="ab30f-118">Create an app</span></span>

1. <span data-ttu-id="ab30f-119">Accedere al [portale di Azure](https://portal.azure.com) e accedere con le credenziali di amministratore per il tenant.</span><span class="sxs-lookup"><span data-stu-id="ab30f-119">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="ab30f-120">Passare alle registrazioni delle app di **Azure Active Directory**  ->  **App registrations** dal riquadro di spostamento e selezionare **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="ab30f-120">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="ab30f-121">Specificare un nome per l'app e selezionare **registra**.</span><span class="sxs-lookup"><span data-stu-id="ab30f-121">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="ab30f-122">Prendere nota dell'ID applicazione (client).</span><span class="sxs-lookup"><span data-stu-id="ab30f-122">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="ab30f-123">Aprire le **autorizzazioni API** dal riquadro di spostamento e selezionare **Aggiungi un'autorizzazione**.</span><span class="sxs-lookup"><span data-stu-id="ab30f-123">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="ab30f-124">Selezionare **Microsoft Graph** e quindi **autorizzazioni** per le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="ab30f-124">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="ab30f-125">Cercare "ExternalItem. ReadWrite. All" e "directory. Read. All" dalle autorizzazioni e selezionare **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="ab30f-125">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="ab30f-126">Selezionare **Concedi consenso amministratore per [TenantName]** e confermare selezionando **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ab30f-126">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="ab30f-127">Verificare che le autorizzazioni siano nello stato "concesso".</span><span class="sxs-lookup"><span data-stu-id="ab30f-127">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="ab30f-128">![Autorizzazioni visualizzate come concesse in verde sulla colonna a destra.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="ab30f-128">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="ab30f-129">Configurare l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="ab30f-129">Configure Authentication</span></span>

<span data-ttu-id="ab30f-130">È possibile fornire informazioni dettagliate sull'autenticazione utilizzando un segreto client o un certificato.</span><span class="sxs-lookup"><span data-stu-id="ab30f-130">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="ab30f-131">Segui i passaggi per la tua scelta.</span><span class="sxs-lookup"><span data-stu-id="ab30f-131">Follow the steps for your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="ab30f-132">Configurazione del segreto client per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="ab30f-132">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="ab30f-133">Accedere al [portale di Azure](https://portal.azure.com) e accedere con le credenziali di amministratore per il tenant.</span><span class="sxs-lookup"><span data-stu-id="ab30f-133">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="ab30f-134">Aprire **registrazione app** dal riquadro di spostamento e passare all'app appropriata.</span><span class="sxs-lookup"><span data-stu-id="ab30f-134">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="ab30f-135">In **Gestisci** selezionare **certificati e segreti**.</span><span class="sxs-lookup"><span data-stu-id="ab30f-135">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="ab30f-136">Selezionare **nuovo segreto client** e selezionare un periodo di scadenza per il segreto.</span><span class="sxs-lookup"><span data-stu-id="ab30f-136">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="ab30f-137">Copiare il segreto generato e salvarlo perché non verrà visualizzato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="ab30f-137">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="ab30f-138">Utilizzare questo segreto client insieme all'ID applicazione per configurare l'agente.</span><span class="sxs-lookup"><span data-stu-id="ab30f-138">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="ab30f-139">Non è possibile utilizzare spazi vuoti nel campo **nome** dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ab30f-139">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="ab30f-140">Vengono accettati caratteri numerici alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="ab30f-140">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="ab30f-141">Utilizzo di un certificato per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="ab30f-141">Using a certificate for authentication</span></span>

<span data-ttu-id="ab30f-142">Sono disponibili tre semplici passaggi per l'utilizzo dell'autenticazione basata sui certificati:</span><span class="sxs-lookup"><span data-stu-id="ab30f-142">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="ab30f-143">Creare o ottenere un certificato</span><span class="sxs-lookup"><span data-stu-id="ab30f-143">Create or obtain a certificate</span></span>
1. <span data-ttu-id="ab30f-144">Caricare il certificato nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="ab30f-144">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="ab30f-145">Assegnare il certificato all'agente</span><span class="sxs-lookup"><span data-stu-id="ab30f-145">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="ab30f-146">Passaggio 1: ottenere un certificato</span><span class="sxs-lookup"><span data-stu-id="ab30f-146">Step 1: Get a certificate</span></span>

<span data-ttu-id="ab30f-147">Lo script riportato di seguito può essere utilizzato per generare un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="ab30f-147">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="ab30f-148">L'organizzazione potrebbe non consentire certificati autofirmati.</span><span class="sxs-lookup"><span data-stu-id="ab30f-148">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="ab30f-149">In tal caso, utilizzare queste informazioni per comprendere i requisiti e acquisire un certificato in base ai criteri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ab30f-149">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

```Powershell
$dnsName = "<TenantDomain like agent.onmicrosoft.com>" # Your DNS name
$password = "<password>" # Certificate password
$folderPath = "D:\New folder\" # Where do you want the files to get saved to? The folder needs to exist.
$fileName = "agentcert" # What do you want to call the cert files? without the file extension
$yearsValid = 10 # Number of years until you need to renew the certificate
$certStoreLocation = "cert:\LocalMachine\My"
$expirationDate = (Get-Date).AddYears($yearsValid)
$certificate = New-SelfSignedCertificate -DnsName $dnsName -CertStoreLocation $certStoreLocation -NotAfter $expirationDate -KeyExportPolicy Exportable -KeySpec Signature
$certificatePath = $certStoreLocation + '\' + $certificate.Thumbprint
$filePath = $folderPath + '\' + $fileName
$securePassword = ConvertTo-SecureString -String $password -Force -AsPlainText
Export-Certificate -Cert $certificatePath -FilePath ($filePath + '.cer')
Export-PfxCertificate -Cert $certificatePath -FilePath ($filePath + '.pfx') -Password $securePassword
```

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="ab30f-150">Passaggio 2: caricare il certificato nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="ab30f-150">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="ab30f-151">Aprire l'applicazione e passare alla sezione certificati e segreti dal riquadro sinistro</span><span class="sxs-lookup"><span data-stu-id="ab30f-151">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="ab30f-152">Selezionare ' carica certificato ' e caricare il file con estensione cer</span><span class="sxs-lookup"><span data-stu-id="ab30f-152">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="ab30f-153">Aprire **registrazione app** e selezionare **certificati e segreti** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="ab30f-153">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="ab30f-154">Copiare l'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="ab30f-154">Copy the certificate thumbprint.</span></span>

![Elenco dei certificati di thumbrint in caso di selezione di certificati e segreti nel riquadro sinistro](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="ab30f-156">Passaggio 3: assegnare il certificato all'agente</span><span class="sxs-lookup"><span data-stu-id="ab30f-156">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="ab30f-157">Se è stato utilizzato lo script di esempio per generare un certificato, è possibile trovare il file PFX nel percorso identificato nello script.</span><span class="sxs-lookup"><span data-stu-id="ab30f-157">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="ab30f-158">Scaricare il file pfx del certificato nel computer dell'agente.</span><span class="sxs-lookup"><span data-stu-id="ab30f-158">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="ab30f-159">Fare doppio clic sul file PFX per avviare la finestra di dialogo di installazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="ab30f-159">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="ab30f-160">Selezionare ' computer locale ' per la posizione dell'archivio durante l'installazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="ab30f-160">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="ab30f-161">Dopo aver installato il certificato, aprire ' Gestisci certificati computer ' tramite il menu Start</span><span class="sxs-lookup"><span data-stu-id="ab30f-161">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="ab30f-162">Selezionare il certificato appena installato in ' Personal '->' Certificates '</span><span class="sxs-lookup"><span data-stu-id="ab30f-162">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="ab30f-163">Fare clic con il pulsante destro del mouse sul cert e selezionare ' tutte le attività'->' Gestisci chiavi private.. .'</span><span class="sxs-lookup"><span data-stu-id="ab30f-163">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="ab30f-164">Opzione</span><span class="sxs-lookup"><span data-stu-id="ab30f-164">Option</span></span>
1. <span data-ttu-id="ab30f-165">Nella finestra di dialogo autorizzazioni selezionare Aggiungi opzione.</span><span class="sxs-lookup"><span data-stu-id="ab30f-165">In the permissions dialog, select add option.</span></span> <span data-ttu-id="ab30f-166">Nella finestra di dialogo Selezione utenti, scrivere:' NT Service\GcaHostService ' e fare clic su' OK '.</span><span class="sxs-lookup"><span data-stu-id="ab30f-166">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="ab30f-167">Non fare clic sul pulsante ' Controlla nomi '.</span><span class="sxs-lookup"><span data-stu-id="ab30f-167">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="ab30f-168">Fare clic su OK nella finestra di dialogo autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="ab30f-168">Click okay on the permissions dialog.</span></span> <span data-ttu-id="ab30f-169">Il computer dell'agente è ora configurato per l'agente per generare token utilizzando il certificato.</span><span class="sxs-lookup"><span data-stu-id="ab30f-169">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
