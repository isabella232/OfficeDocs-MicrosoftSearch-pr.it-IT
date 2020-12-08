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
ms.openlocfilehash: 5dbca392fefdcc11de253fd244cc98a6adcee68a
ms.sourcegitcommit: e8d770fa72ac83e074a5de57098cb55d06d8db07
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588368"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="f451a-103">Agente del connettore grafico</span><span class="sxs-lookup"><span data-stu-id="f451a-103">Graph connector agent</span></span>

<span data-ttu-id="f451a-104">L'utilizzo di connettori di Graph su-Prem richiede l'installazione del software dell' *agente del connettore grafico* .</span><span class="sxs-lookup"><span data-stu-id="f451a-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="f451a-105">Consente il trasferimento sicuro dei dati tra i dati locali e le API del connettore grafico.</span><span class="sxs-lookup"><span data-stu-id="f451a-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="f451a-106">In questo articolo vengono illustrate le istruzioni per l'installazione e la configurazione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="f451a-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="f451a-107">Installazione</span><span class="sxs-lookup"><span data-stu-id="f451a-107">Installation</span></span>

<span data-ttu-id="f451a-108">Scaricare la versione più recente di Graph Connector [Agent e](https://aka.ms/gcadownload) installare il software utilizzando l'installazione guidata.</span><span class="sxs-lookup"><span data-stu-id="f451a-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="f451a-109">Usando la configurazione consigliata della macchina descritta di seguito, il software è in grado di gestire fino a tre connessioni.</span><span class="sxs-lookup"><span data-stu-id="f451a-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="f451a-110">Tutte le connessioni oltre che potrebbero peggiorare le prestazioni di tutte le connessioni nell'agente.</span><span class="sxs-lookup"><span data-stu-id="f451a-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="f451a-111">Configurazione consigliata:</span><span class="sxs-lookup"><span data-stu-id="f451a-111">Recommended configuration:</span></span>

* <span data-ttu-id="f451a-112">Windows 10, Windows Server 2016 R2 e successive</span><span class="sxs-lookup"><span data-stu-id="f451a-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="f451a-113">Runtime desktop .NET Core 3,1 (x64)</span><span class="sxs-lookup"><span data-stu-id="f451a-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="f451a-114">8 core, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="f451a-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="f451a-115">16 GB di RAM, 2 GB di spazio su disco</span><span class="sxs-lookup"><span data-stu-id="f451a-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="f451a-116">Accesso alla rete all'origine dati e a Internet tramite 443</span><span class="sxs-lookup"><span data-stu-id="f451a-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="f451a-117">Creare e configurare un'app per l'agente</span><span class="sxs-lookup"><span data-stu-id="f451a-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="f451a-118">Prima di utilizzare l'agente, è necessario creare un'app e configurare i dettagli dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f451a-118">Before using the agent, you must create an app and configure the authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="f451a-119">Creare un'app</span><span class="sxs-lookup"><span data-stu-id="f451a-119">Create an app</span></span>

1. <span data-ttu-id="f451a-120">Accedere al [portale di Azure](https://portal.azure.com) e accedere con le credenziali di amministratore per il tenant.</span><span class="sxs-lookup"><span data-stu-id="f451a-120">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="f451a-121">Passare alle registrazioni delle app di **Azure Active Directory**  ->  **App registrations** dal riquadro di spostamento e selezionare **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="f451a-121">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="f451a-122">Specificare un nome per l'app e selezionare **registra**.</span><span class="sxs-lookup"><span data-stu-id="f451a-122">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="f451a-123">Prendere nota dell'ID applicazione (client).</span><span class="sxs-lookup"><span data-stu-id="f451a-123">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="f451a-124">Aprire le **autorizzazioni API** dal riquadro di spostamento e selezionare **Aggiungi un'autorizzazione**.</span><span class="sxs-lookup"><span data-stu-id="f451a-124">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="f451a-125">Selezionare **Microsoft Graph** e quindi **autorizzazioni** per le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f451a-125">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="f451a-126">Cercare "ExternalItem. ReadWrite. All" e "directory. Read. All" dalle autorizzazioni e selezionare **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="f451a-126">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="f451a-127">Selezionare **Concedi consenso amministratore per [TenantName]** e confermare selezionando **Sì**.</span><span class="sxs-lookup"><span data-stu-id="f451a-127">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="f451a-128">Verificare che le autorizzazioni siano nello stato "concesso".</span><span class="sxs-lookup"><span data-stu-id="f451a-128">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="f451a-129">![Autorizzazioni visualizzate come concesse in verde sulla colonna a destra.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="f451a-129">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="f451a-130">Configurare l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="f451a-130">Configure Authentication</span></span>

<span data-ttu-id="f451a-131">È possibile fornire informazioni dettagliate sull'autenticazione utilizzando un segreto client o un certificato.</span><span class="sxs-lookup"><span data-stu-id="f451a-131">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="f451a-132">Segui i passaggi per la tua scelta.</span><span class="sxs-lookup"><span data-stu-id="f451a-132">Follow the steps for your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="f451a-133">Configurazione del segreto client per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="f451a-133">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="f451a-134">Accedere al [portale di Azure](https://portal.azure.com) e accedere con le credenziali di amministratore per il tenant.</span><span class="sxs-lookup"><span data-stu-id="f451a-134">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="f451a-135">Aprire **registrazione app** dal riquadro di spostamento e passare all'app appropriata.</span><span class="sxs-lookup"><span data-stu-id="f451a-135">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="f451a-136">In **Gestisci** selezionare **certificati e segreti**.</span><span class="sxs-lookup"><span data-stu-id="f451a-136">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="f451a-137">Selezionare **nuovo segreto client** e selezionare un periodo di scadenza per il segreto.</span><span class="sxs-lookup"><span data-stu-id="f451a-137">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="f451a-138">Copiare il segreto generato e salvarlo perché non verrà visualizzato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f451a-138">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="f451a-139">Utilizzare questo segreto client insieme all'ID applicazione per configurare l'agente.</span><span class="sxs-lookup"><span data-stu-id="f451a-139">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="f451a-140">Non è possibile utilizzare spazi vuoti nel campo **nome** dell'agente.</span><span class="sxs-lookup"><span data-stu-id="f451a-140">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="f451a-141">Vengono accettati caratteri numerici alfanumerici.</span><span class="sxs-lookup"><span data-stu-id="f451a-141">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="f451a-142">Utilizzo di un certificato per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="f451a-142">Using a certificate for authentication</span></span>

<span data-ttu-id="f451a-143">Sono disponibili tre semplici passaggi per l'utilizzo dell'autenticazione basata sui certificati:</span><span class="sxs-lookup"><span data-stu-id="f451a-143">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="f451a-144">Creare o ottenere un certificato</span><span class="sxs-lookup"><span data-stu-id="f451a-144">Create or obtain a certificate</span></span>
1. <span data-ttu-id="f451a-145">Caricare il certificato nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="f451a-145">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="f451a-146">Assegnare il certificato all'agente</span><span class="sxs-lookup"><span data-stu-id="f451a-146">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="f451a-147">Passaggio 1: ottenere un certificato</span><span class="sxs-lookup"><span data-stu-id="f451a-147">Step 1: Get a certificate</span></span>

<span data-ttu-id="f451a-148">Lo script riportato di seguito può essere utilizzato per generare un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="f451a-148">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="f451a-149">L'organizzazione potrebbe non consentire certificati autofirmati.</span><span class="sxs-lookup"><span data-stu-id="f451a-149">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="f451a-150">In tal caso, utilizzare queste informazioni per comprendere i requisiti e acquisire un certificato in base ai criteri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f451a-150">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="f451a-151">Passaggio 2: caricare il certificato nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="f451a-151">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="f451a-152">Aprire l'applicazione e passare alla sezione certificati e segreti dal riquadro sinistro</span><span class="sxs-lookup"><span data-stu-id="f451a-152">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="f451a-153">Selezionare ' carica certificato ' e caricare il file con estensione cer</span><span class="sxs-lookup"><span data-stu-id="f451a-153">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="f451a-154">Aprire **registrazione app** e selezionare **certificati e segreti** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="f451a-154">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="f451a-155">Copiare l'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="f451a-155">Copy the certificate thumbprint.</span></span>

![Elenco dei certificati di thumbrint in caso di selezione di certificati e segreti nel riquadro sinistro](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="f451a-157">Passaggio 3: assegnare il certificato all'agente</span><span class="sxs-lookup"><span data-stu-id="f451a-157">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="f451a-158">Se è stato utilizzato lo script di esempio per generare un certificato, è possibile trovare il file PFX nel percorso identificato nello script.</span><span class="sxs-lookup"><span data-stu-id="f451a-158">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="f451a-159">Scaricare il file pfx del certificato nel computer dell'agente.</span><span class="sxs-lookup"><span data-stu-id="f451a-159">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="f451a-160">Fare doppio clic sul file PFX per avviare la finestra di dialogo di installazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="f451a-160">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="f451a-161">Selezionare ' computer locale ' per la posizione dell'archivio durante l'installazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="f451a-161">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="f451a-162">Dopo aver installato il certificato, aprire ' Gestisci certificati computer ' tramite il menu Start</span><span class="sxs-lookup"><span data-stu-id="f451a-162">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="f451a-163">Selezionare il certificato appena installato in ' Personal '->' Certificates '</span><span class="sxs-lookup"><span data-stu-id="f451a-163">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="f451a-164">Fare clic con il pulsante destro del mouse sul cert e selezionare ' tutte le attività'->' Gestisci chiavi private.. .'</span><span class="sxs-lookup"><span data-stu-id="f451a-164">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="f451a-165">Opzione</span><span class="sxs-lookup"><span data-stu-id="f451a-165">Option</span></span>
1. <span data-ttu-id="f451a-166">Nella finestra di dialogo autorizzazioni selezionare Aggiungi opzione.</span><span class="sxs-lookup"><span data-stu-id="f451a-166">In the permissions dialog, select add option.</span></span> <span data-ttu-id="f451a-167">Nella finestra di dialogo Selezione utenti, scrivere:' NT Service\GcaHostService ' e fare clic su' OK '.</span><span class="sxs-lookup"><span data-stu-id="f451a-167">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="f451a-168">Non fare clic sul pulsante ' Controlla nomi '.</span><span class="sxs-lookup"><span data-stu-id="f451a-168">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="f451a-169">Fare clic su OK nella finestra di dialogo autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="f451a-169">Click okay on the permissions dialog.</span></span> <span data-ttu-id="f451a-170">Il computer dell'agente è ora configurato per l'agente per generare token utilizzando il certificato.</span><span class="sxs-lookup"><span data-stu-id="f451a-170">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
