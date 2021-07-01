---
title: Agente locale
ms.author: rusamai
author: rsamai
manager: jameslau
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Agente in-prem
ms.openlocfilehash: d6dabbbb5ee34acedd92166564f560bbc64c7da7
ms.sourcegitcommit: 93fc70f0073ab45b4dbd702441ac2fc07a7668bc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230926"
---
# <a name="microsoft-graph-connector-agent"></a><span data-ttu-id="c7df5-103">Agente connettore microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="c7df5-103">Microsoft Graph connector agent</span></span>

<span data-ttu-id="c7df5-104">L'utilizzo di connettori in ingresso richiede l'installazione del software *dell'agente Graph microsoft* Graph.</span><span class="sxs-lookup"><span data-stu-id="c7df5-104">Using on-prem connectors require you to install *Microsoft Graph connector agent* software.</span></span> <span data-ttu-id="c7df5-105">Consente il trasferimento sicuro dei dati tra i dati locali e le API del connettore.</span><span class="sxs-lookup"><span data-stu-id="c7df5-105">It allows for secure data transfer between on-premises data and the connector APIs.</span></span> <span data-ttu-id="c7df5-106">In questo articolo viene illustrata l'installazione e la configurazione dell'agente.</span><span class="sxs-lookup"><span data-stu-id="c7df5-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="c7df5-107">Installazione</span><span class="sxs-lookup"><span data-stu-id="c7df5-107">Installation</span></span>

<span data-ttu-id="c7df5-108">Scaricare la versione più recente dell'agente Graph connettore e [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) installare il software utilizzando l'installazione guidata.</span><span class="sxs-lookup"><span data-stu-id="c7df5-108">Download the latest version of the Graph connector agent from [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) and install the software by using the installation wizard.</span></span> <span data-ttu-id="c7df5-109">Utilizzando la configurazione consigliata del computer descritto di seguito, il software può gestire fino a tre connessioni.</span><span class="sxs-lookup"><span data-stu-id="c7df5-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="c7df5-110">Qualsiasi connessione oltre tale limite potrebbe compromettere le prestazioni di tutte le connessioni nell'agente.</span><span class="sxs-lookup"><span data-stu-id="c7df5-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="c7df5-111">Configurazione consigliata:</span><span class="sxs-lookup"><span data-stu-id="c7df5-111">Recommended configuration:</span></span>

* <span data-ttu-id="c7df5-112">Windows 10, Windows Server 2016 R2 e successive</span><span class="sxs-lookup"><span data-stu-id="c7df5-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="c7df5-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="c7df5-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="c7df5-114">8 core, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="c7df5-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="c7df5-115">16 GB di RAM, 2 GB di spazio su disco</span><span class="sxs-lookup"><span data-stu-id="c7df5-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="c7df5-116">Accesso di rete all'origine dati e a Internet tramite 443</span><span class="sxs-lookup"><span data-stu-id="c7df5-116">Network access to data source and internet through 443</span></span>

<span data-ttu-id="c7df5-117">Dopo aver installato l'agente, se i server proxy o i firewall dell'organizzazione bloccano la comunicazione con domini sconosciuti, aggiungere quelli seguenti all'elenco consenti.</span><span class="sxs-lookup"><span data-stu-id="c7df5-117">After you install the agent, if your organization's proxy servers or firewalls block communication to unknown domains, please add below ones to the allow list.</span></span>

1. <span data-ttu-id="c7df5-118">\*.servicebus.windows.net</span><span class="sxs-lookup"><span data-stu-id="c7df5-118">\*.servicebus.windows.net</span></span>
2. <span data-ttu-id="c7df5-119">\*.events.data.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c7df5-119">\*.events.data.microsoft.com</span></span>
3. <span data-ttu-id="c7df5-120"> https://<span>login.microsoftonline.</span> com</span><span class="sxs-lookup"><span data-stu-id="c7df5-120">https://<span>login.microsoftonline.</span>com</span></span>
4. <span data-ttu-id="c7df5-121"> https://<span>gcs.office.</span> com/</span><span class="sxs-lookup"><span data-stu-id="c7df5-121">https://<span>gcs.office.</span>com/</span></span>
5. <span data-ttu-id="c7df5-122"> https://<span>graph.microsoft.</span> com/</span><span class="sxs-lookup"><span data-stu-id="c7df5-122">https://<span>graph.microsoft.</span>com/</span></span>


## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="c7df5-123">Creare e configurare un'app per l'agente</span><span class="sxs-lookup"><span data-stu-id="c7df5-123">Create and configure an App for the agent</span></span>  

<span data-ttu-id="c7df5-124">Innanzitutto, accedi e tieni presente che il privilegio minimo necessario per l'account è l'amministratore della ricerca.</span><span class="sxs-lookup"><span data-stu-id="c7df5-124">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="c7df5-125">L'agente chiederà quindi di fornire i dettagli dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="c7df5-125">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="c7df5-126">Usa la procedura seguente per creare un'app e generare i dettagli di autenticazione necessari.</span><span class="sxs-lookup"><span data-stu-id="c7df5-126">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="c7df5-127">Creare un'app</span><span class="sxs-lookup"><span data-stu-id="c7df5-127">Create an app</span></span>

1. <span data-ttu-id="c7df5-128">Passare al portale [di Azure e](https://portal.azure.com) accedere con le credenziali di amministratore per il tenant.</span><span class="sxs-lookup"><span data-stu-id="c7df5-128">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>

2. <span data-ttu-id="c7df5-129">Passare a **Azure Active Directory**  ->  **app dal** riquadro di spostamento e selezionare Nuova **registrazione.**</span><span class="sxs-lookup"><span data-stu-id="c7df5-129">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>

3. <span data-ttu-id="c7df5-130">Fornisci un nome per l'app e seleziona **Registra.**</span><span class="sxs-lookup"><span data-stu-id="c7df5-130">Provide a name for the app and select **Register**.</span></span>

4. <span data-ttu-id="c7df5-131">Prendere nota dell'ID applicazione (client).</span><span class="sxs-lookup"><span data-stu-id="c7df5-131">Make a note of the Application (client) ID.</span></span>

5. <span data-ttu-id="c7df5-132">Apri **autorizzazioni API** dal riquadro di spostamento e seleziona Aggiungi **un'autorizzazione.**</span><span class="sxs-lookup"><span data-stu-id="c7df5-132">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>

6. <span data-ttu-id="c7df5-133">Selezionare **Microsoft Graph** e quindi Autorizzazioni **applicazione**.</span><span class="sxs-lookup"><span data-stu-id="c7df5-133">Select **Microsoft Graph** and then **Application permissions**.</span></span>

7. <span data-ttu-id="c7df5-134">Cercare "ExternalItem.ReadWrite.All" e "Directory.Read.All" dalle autorizzazioni e selezionare **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="c7df5-134">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>

8. <span data-ttu-id="c7df5-135">Selezionare **Concedi il consenso dell'amministratore per [TenantName]** e confermare selezionando **Sì.**</span><span class="sxs-lookup"><span data-stu-id="c7df5-135">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>

9. <span data-ttu-id="c7df5-136">Verificare che le autorizzazioni siano nello stato "concesso".</span><span class="sxs-lookup"><span data-stu-id="c7df5-136">Check that the permissions are in the "granted" state.</span></span>

    :::image type="content" alt-text="Autorizzazioni visualizzate come concesse in verde nella colonna a destra." source="media/onprem-agent/granted-state.png" lightbox="media/onprem-agent/granted-state.png":::

### <a name="configure-authentication"></a><span data-ttu-id="c7df5-138">Configurare l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="c7df5-138">Configure Authentication</span></span>

<span data-ttu-id="c7df5-139">I dettagli dell'autenticazione possono essere forniti utilizzando un segreto client o un certificato.</span><span class="sxs-lookup"><span data-stu-id="c7df5-139">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="c7df5-140">Segui i passaggi di tua scelta.</span><span class="sxs-lookup"><span data-stu-id="c7df5-140">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="c7df5-141">Configurazione del segreto client per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="c7df5-141">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="c7df5-142">Passare al portale [di Azure e](https://portal.azure.com) accedere con le credenziali di amministratore per il tenant.</span><span class="sxs-lookup"><span data-stu-id="c7df5-142">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>

2. <span data-ttu-id="c7df5-143">Apri **Registrazione app** dal riquadro di spostamento e passa all'app appropriata.</span><span class="sxs-lookup"><span data-stu-id="c7df5-143">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="c7df5-144">In **Gestisci** selezionare **Certificati e segreti.**</span><span class="sxs-lookup"><span data-stu-id="c7df5-144">Under **Manage**, select **Certificates and secrets**.</span></span>

3. <span data-ttu-id="c7df5-145">Selezionare **Nuovo segreto client** e selezionare un periodo di scadenza per il segreto.</span><span class="sxs-lookup"><span data-stu-id="c7df5-145">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="c7df5-146">Copiare il segreto generato e salvarlo perché non verrà visualizzato di nuovo.</span><span class="sxs-lookup"><span data-stu-id="c7df5-146">Copy the generated secret and save it because it won't be shown again.</span></span>

4. <span data-ttu-id="c7df5-147">Usa questo segreto client insieme all'ID applicazione per configurare l'agente.</span><span class="sxs-lookup"><span data-stu-id="c7df5-147">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="c7df5-148">Non è possibile utilizzare spazi vuoti nel **campo Nome** dell'agente.</span><span class="sxs-lookup"><span data-stu-id="c7df5-148">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="c7df5-149">I caratteri numerici alfa vengono accettati.</span><span class="sxs-lookup"><span data-stu-id="c7df5-149">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="c7df5-150">Utilizzo di un certificato per l'autenticazione</span><span class="sxs-lookup"><span data-stu-id="c7df5-150">Using a certificate for authentication</span></span>

<span data-ttu-id="c7df5-151">Esistono tre semplici passaggi per l'utilizzo dell'autenticazione basata su certificato:</span><span class="sxs-lookup"><span data-stu-id="c7df5-151">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="c7df5-152">Creare o ottenere un certificato</span><span class="sxs-lookup"><span data-stu-id="c7df5-152">Create or obtain a certificate</span></span>
1. <span data-ttu-id="c7df5-153">Upload il certificato al portale di Azure</span><span class="sxs-lookup"><span data-stu-id="c7df5-153">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="c7df5-154">Assegnare il certificato all'agente</span><span class="sxs-lookup"><span data-stu-id="c7df5-154">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="c7df5-155">Passaggio 1: Ottenere un certificato</span><span class="sxs-lookup"><span data-stu-id="c7df5-155">Step 1: Get a certificate</span></span>

<span data-ttu-id="c7df5-156">Lo script seguente può essere utilizzato per generare un certificato autofirmato.</span><span class="sxs-lookup"><span data-stu-id="c7df5-156">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="c7df5-157">L'organizzazione potrebbe non consentire certificati autofirmati.</span><span class="sxs-lookup"><span data-stu-id="c7df5-157">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="c7df5-158">In tal caso, utilizzare queste informazioni per comprendere i requisiti e acquisire un certificato in base ai criteri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c7df5-158">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

```powershell
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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="c7df5-159">Passaggio 2: Upload il certificato nel portale di Azure</span><span class="sxs-lookup"><span data-stu-id="c7df5-159">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="c7df5-160">Aprire l'applicazione e passare alla sezione certificati e segreti dal riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="c7df5-160">Open the application and navigate to certificates and secrets section from left pane.</span></span>

1. <span data-ttu-id="c7df5-161">Selezionare **Upload certificato e** caricare il file cer.</span><span class="sxs-lookup"><span data-stu-id="c7df5-161">Select **Upload certificate** and upload the .cer file.</span></span>

1. <span data-ttu-id="c7df5-162">Apri **Registrazione app** e seleziona Certificati e **segreti** nel riquadro di spostamento.</span><span class="sxs-lookup"><span data-stu-id="c7df5-162">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="c7df5-163">Copiare l'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="c7df5-163">Copy the certificate thumbprint.</span></span>

:::image type="content" alt-text="Elenco di certificati con identificazione personale quando è selezionato Certificati e segreti nel riquadro sinistro" source="media/onprem-agent/certificates.png" lightbox="media/onprem-agent/certificates.png":::

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="c7df5-165">Passaggio 3: Assegnare il certificato all'agente</span><span class="sxs-lookup"><span data-stu-id="c7df5-165">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="c7df5-166">Se hai usato lo script di esempio per generare un certificato, il file PFX è disponibile nel percorso identificato nello script.</span><span class="sxs-lookup"><span data-stu-id="c7df5-166">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="c7df5-167">Scaricare il file pfx del certificato nel computer agente.</span><span class="sxs-lookup"><span data-stu-id="c7df5-167">Download the certificate pfx file onto the Agent machine.</span></span>

1. <span data-ttu-id="c7df5-168">Fai doppio clic sul file pfx per avviare la finestra di dialogo di installazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="c7df5-168">Double-click the pfx file to launch the certificate installation dialog.</span></span>

1. <span data-ttu-id="c7df5-169">Selezionare **Computer locale per** il percorso di archiviazione durante l'installazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="c7df5-169">Select **Local Machine** for store location while installing the certificate.</span></span>

1. <span data-ttu-id="c7df5-170">Dopo aver installato il certificato, aprire **Gestisci certificati computer** tramite menu Start.</span><span class="sxs-lookup"><span data-stu-id="c7df5-170">After installing the certificate, open **Manage computer certificates** through Start menu.</span></span>

1. <span data-ttu-id="c7df5-171">Selezionare il certificato appena installato in **Certificati**  >  **personali**.</span><span class="sxs-lookup"><span data-stu-id="c7df5-171">Select the newly installed certificate under **Personal** > **Certificates**.</span></span>

1. <span data-ttu-id="c7df5-172">Fai clic con il pulsante destro del mouse sul certificato e seleziona **Tutte le attività** Gestisci  >  **chiavi** private Opzione.</span><span class="sxs-lookup"><span data-stu-id="c7df5-172">Right click on the cert and select **All Tasks** > **Manage Private Keys** Option.</span></span>

1. <span data-ttu-id="c7df5-173">Nella finestra di dialogo delle autorizzazioni seleziona l'opzione aggiungi.</span><span class="sxs-lookup"><span data-stu-id="c7df5-173">In the permissions dialog, select add option.</span></span> <span data-ttu-id="c7df5-174">Nella finestra di dialogo di selezione dell'utente, scrivi: **NT Service\GcaHostService** e fai clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="c7df5-174">In the user selection dialog, write: **NT Service\GcaHostService** and click **OK**.</span></span> <span data-ttu-id="c7df5-175">Non fare clic sul **pulsante Controlla** nomi.</span><span class="sxs-lookup"><span data-stu-id="c7df5-175">Don't click the **Check Names** button.</span></span>

1. <span data-ttu-id="c7df5-176">Fare clic su ok nella finestra di dialogo delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="c7df5-176">Click okay on the permissions dialog.</span></span> <span data-ttu-id="c7df5-177">Il computer agente è ora configurato per l'agente per generare token usando il certificato.</span><span class="sxs-lookup"><span data-stu-id="c7df5-177">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c7df5-178">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="c7df5-178">Troubleshooting</span></span>

1. <span data-ttu-id="c7df5-179">Se una connessione non riesce con l'errore "1011: L'agente connettore di Graph non è raggiungibile o offline", accedere al computer in cui è installato l'agente e avviare l'applicazione agente se non è già in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c7df5-179">If a connection fails with the error "1011: The Graph connector agent is not reachable or offline.", log in to the machine where agent is installed and start the agent application if it isn't running already.</span></span> <span data-ttu-id="c7df5-180">Se la connessione continua a non riuscire, verificare che il certificato o il segreto client fornito all'agente durante la registrazione non sia scaduto e abbia le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="c7df5-180">If the connection continues to fail, verify that the certificate or client secret provided to the agent during registration hasn't expired and has required permissions.</span></span>
