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
ms.openlocfilehash: 31220196849fe90ab2611e9c2b83a1cec0a02b34
ms.sourcegitcommit: a04f1df14a3221776ccd141f6060328612d80e06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876499"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="cd80c-103">Agente del connettore grafico</span><span class="sxs-lookup"><span data-stu-id="cd80c-103">Graph connector agent</span></span>

<span data-ttu-id="cd80c-104">L'utilizzo di connettori di Graph su-Prem richiede l'installazione del software dell' *agente del connettore grafico* .</span><span class="sxs-lookup"><span data-stu-id="cd80c-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="cd80c-105">Consente il trasferimento sicuro dei dati tra i dati locali e le API del connettore grafico.</span><span class="sxs-lookup"><span data-stu-id="cd80c-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="cd80c-106">In questo articolo vengono illustrate le istruzioni per l'installazione e la configurazione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="cd80c-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="cd80c-107">Installazione</span><span class="sxs-lookup"><span data-stu-id="cd80c-107">Installation</span></span>

<span data-ttu-id="cd80c-108">Scaricare la versione più recente di Graph Connector [Agent e](https://aka.ms/gcadownload) installare il software utilizzando l'installazione guidata.</span><span class="sxs-lookup"><span data-stu-id="cd80c-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="cd80c-109">Usando la configurazione consigliata della macchina descritta di seguito, il software è in grado di gestire fino a tre connessioni.</span><span class="sxs-lookup"><span data-stu-id="cd80c-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="cd80c-110">Tutte le connessioni oltre che potrebbero peggiorare le prestazioni di tutte le connessioni nell'agente.</span><span class="sxs-lookup"><span data-stu-id="cd80c-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="cd80c-111">Configurazione consigliata:</span><span class="sxs-lookup"><span data-stu-id="cd80c-111">Recommended configuration:</span></span>

* <span data-ttu-id="cd80c-112">Windows 10, Windows Server 2016 R2 e successive</span><span class="sxs-lookup"><span data-stu-id="cd80c-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="cd80c-113">Runtime desktop .NET Core 3,1 (x64)</span><span class="sxs-lookup"><span data-stu-id="cd80c-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="cd80c-114">8 core, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="cd80c-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="cd80c-115">16 GB di RAM, 2 GB di spazio su disco</span><span class="sxs-lookup"><span data-stu-id="cd80c-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="cd80c-116">Accesso alla rete all'origine dati e a Internet tramite 443</span><span class="sxs-lookup"><span data-stu-id="cd80c-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="cd80c-117">Creare e configurare un'app per l'agente</span><span class="sxs-lookup"><span data-stu-id="cd80c-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="cd80c-118">In primo luogo, accedere e tenere presente che il privilegio minimo richiesto per l'account è Search Administrator.</span><span class="sxs-lookup"><span data-stu-id="cd80c-118">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="cd80c-119">L'agente verrà quindi chiesto di fornire i dettagli dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="cd80c-119">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="cd80c-120">Utilizzare la procedura seguente per creare un'app e generare i dettagli di autenticazione necessari.</span><span class="sxs-lookup"><span data-stu-id="cd80c-120">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="cd80c-121">Creare un'app</span><span class="sxs-lookup"><span data-stu-id="cd80c-121">Create an app</span></span>

1. <span data-ttu-id="cd80c-122">Accedere al [portale di Azure](https://portal.azure.com) e accedere con le credenziali di amministratore per il tenant.</span><span class="sxs-lookup"><span data-stu-id="cd80c-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="cd80c-123">Passare alle registrazioni delle app di **Azure Active Directory**  ->   dal riquadro di spostamento e selezionare **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="cd80c-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="cd80c-124">Specificare un nome per l'app e selezionare **registra**.</span><span class="sxs-lookup"><span data-stu-id="cd80c-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="cd80c-125">Prendere nota dell'ID applicazione (client).</span><span class="sxs-lookup"><span data-stu-id="cd80c-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="cd80c-126">Aprire le **autorizzazioni API** dal riquadro di spostamento e selezionare **Aggiungi un'autorizzazione**.</span><span class="sxs-lookup"><span data-stu-id="cd80c-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="cd80c-127">Selezionare **Microsoft Graph** e quindi **autorizzazioni** per le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="cd80c-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="cd80c-128">Cercare "ExternalItem. ReadWrite. All" e "directory. Read. All" dalle autorizzazioni e selezionare **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="cd80c-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="cd80c-129">Selezionare **Concedi consenso amministratore per [TenantName]** e confermare selezionando **Sì**.</span><span class="sxs-lookup"><span data-stu-id="cd80c-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="cd80c-130">Verificare che le autorizzazioni siano nello stato "concesso".</span><span class="sxs-lookup"><span data-stu-id="cd80c-130">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="cd80c-131">![Autorizzazioni visualizzate come concesse in verde sulla colonna a destra.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="cd80c-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="cd80c-132">Configurare l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="cd80c-132">Configure Authentication</span></span>

<span data-ttu-id="cd80c-133">È possibile fornire informazioni dettagliate sull'autenticazione utilizzando un segreto client o un certificato.</span><span class="sxs-lookup"><span data-stu-id="cd80c-133">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="cd80c-134">Seguire la procedura desiderata.</span><span class="sxs-lookup"><span data-stu-id="cd80c-134">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="cd80c-135">Configurazione del segreto client per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="cd80c-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="cd80c-136">Accedere al [portale di Azure](https://portal.azure.com) e accedere con le credenziali di amministratore per il tenant.</span><span class="sxs-lookup"><span data-stu-id="cd80c-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="cd80c-137">Aprire **registrazione app** dal riquadro di spostamento e passare all'app appropriata.</span><span class="sxs-lookup"><span data-stu-id="cd80c-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="cd80c-138">In **Gestisci** selezionare **certificati e segreti**.</span><span class="sxs-lookup"><span data-stu-id="cd80c-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="cd80c-139">Selezionare **nuovo segreto client** e selezionare un periodo di scadenza per il segreto.</span><span class="sxs-lookup"><span data-stu-id="cd80c-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="cd80c-140">Copiare il segreto generato e salvarlo perché non verrà visualizzato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="cd80c-140">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="cd80c-141">Utilizzare questo segreto client insieme all'ID applicazione per configurare l'agente.</span><span class="sxs-lookup"><span data-stu-id="cd80c-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="cd80c-142">Non è possibile utilizzare spazi vuoti nel campo **nome** dell'agente.</span><span class="sxs-lookup"><span data-stu-id="cd80c-142">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="cd80c-143">Vengono accettati caratteri numerici alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="cd80c-143">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="cd80c-144">Utilizzo di un certificato per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="cd80c-144">Using a certificate for authentication</span></span>

<span data-ttu-id="cd80c-145">Sono disponibili tre semplici passaggi per l'utilizzo dell'autenticazione basata sui certificati:</span><span class="sxs-lookup"><span data-stu-id="cd80c-145">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="cd80c-146">Creare o ottenere un certificato</span><span class="sxs-lookup"><span data-stu-id="cd80c-146">Create or obtain a certificate</span></span>
1. <span data-ttu-id="cd80c-147">Caricare il certificato nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="cd80c-147">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="cd80c-148">Assegnare il certificato all'agente</span><span class="sxs-lookup"><span data-stu-id="cd80c-148">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="cd80c-149">Passaggio 1: ottenere un certificato</span><span class="sxs-lookup"><span data-stu-id="cd80c-149">Step 1: Get a certificate</span></span>

<span data-ttu-id="cd80c-150">Lo script riportato di seguito può essere utilizzato per generare un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="cd80c-150">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="cd80c-151">L'organizzazione potrebbe non consentire certificati autofirmati.</span><span class="sxs-lookup"><span data-stu-id="cd80c-151">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="cd80c-152">In tal caso, utilizzare queste informazioni per comprendere i requisiti e acquisire un certificato in base ai criteri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cd80c-152">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="cd80c-153">Passaggio 2: caricare il certificato nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="cd80c-153">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="cd80c-154">Aprire l'applicazione e passare alla sezione certificati e segreti dal riquadro sinistro</span><span class="sxs-lookup"><span data-stu-id="cd80c-154">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="cd80c-155">Selezionare ' carica certificato ' e caricare il file con estensione cer</span><span class="sxs-lookup"><span data-stu-id="cd80c-155">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="cd80c-156">Aprire **registrazione app** e selezionare **certificati e segreti** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="cd80c-156">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="cd80c-157">Copiare l'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="cd80c-157">Copy the certificate thumbprint.</span></span>

![Elenco dei certificati di thumbrint in caso di selezione di certificati e segreti nel riquadro sinistro](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="cd80c-159">Passaggio 3: assegnare il certificato all'agente</span><span class="sxs-lookup"><span data-stu-id="cd80c-159">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="cd80c-160">Se è stato utilizzato lo script di esempio per generare un certificato, è possibile trovare il file PFX nel percorso identificato nello script.</span><span class="sxs-lookup"><span data-stu-id="cd80c-160">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="cd80c-161">Scaricare il file pfx del certificato nel computer dell'agente.</span><span class="sxs-lookup"><span data-stu-id="cd80c-161">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="cd80c-162">Fare doppio clic sul file PFX per avviare la finestra di dialogo di installazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="cd80c-162">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="cd80c-163">Selezionare ' computer locale ' per la posizione dell'archivio durante l'installazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="cd80c-163">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="cd80c-164">Dopo aver installato il certificato, aprire ' Gestisci certificati computer ' tramite il menu Start</span><span class="sxs-lookup"><span data-stu-id="cd80c-164">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="cd80c-165">Selezionare il certificato appena installato in ' Personal '->' Certificates '</span><span class="sxs-lookup"><span data-stu-id="cd80c-165">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="cd80c-166">Fare clic con il pulsante destro del mouse sul cert e selezionare ' tutte le attività'->' Gestisci chiavi private.. .'</span><span class="sxs-lookup"><span data-stu-id="cd80c-166">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="cd80c-167">Opzione</span><span class="sxs-lookup"><span data-stu-id="cd80c-167">Option</span></span>
1. <span data-ttu-id="cd80c-168">Nella finestra di dialogo autorizzazioni selezionare Aggiungi opzione.</span><span class="sxs-lookup"><span data-stu-id="cd80c-168">In the permissions dialog, select add option.</span></span> <span data-ttu-id="cd80c-169">Nella finestra di dialogo Selezione utenti, scrivere:' NT Service\GcaHostService ' e fare clic su' OK '.</span><span class="sxs-lookup"><span data-stu-id="cd80c-169">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="cd80c-170">Non fare clic sul pulsante ' Controlla nomi '.</span><span class="sxs-lookup"><span data-stu-id="cd80c-170">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="cd80c-171">Fare clic su OK nella finestra di dialogo autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="cd80c-171">Click okay on the permissions dialog.</span></span> <span data-ttu-id="cd80c-172">Il computer dell'agente è ora configurato per l'agente per generare token utilizzando il certificato.</span><span class="sxs-lookup"><span data-stu-id="cd80c-172">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
