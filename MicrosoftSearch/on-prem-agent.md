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
# <a name="microsoft-graph-connector-agent"></a>Agente connettore microsoft Graph

L'utilizzo di connettori in ingresso richiede l'installazione del software *dell'agente Graph microsoft* Graph. Consente il trasferimento sicuro dei dati tra i dati locali e le API del connettore. In questo articolo viene illustrata l'installazione e la configurazione dell'agente.

## <a name="installation"></a>Installazione

Scaricare la versione più recente dell'agente Graph connettore e [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) installare il software utilizzando l'installazione guidata. Utilizzando la configurazione consigliata del computer descritto di seguito, il software può gestire fino a tre connessioni. Qualsiasi connessione oltre tale limite potrebbe compromettere le prestazioni di tutte le connessioni nell'agente.

Configurazione consigliata:

* Windows 10, Windows Server 2016 R2 e successive
* [.NET Core Desktop Runtime 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 core, 3 GHz
* 16 GB di RAM, 2 GB di spazio su disco
* Accesso di rete all'origine dati e a Internet tramite 443

Dopo aver installato l'agente, se i server proxy o i firewall dell'organizzazione bloccano la comunicazione con domini sconosciuti, aggiungere quelli seguenti all'elenco consenti.

1. *.servicebus.windows.net
2. *.events.data.microsoft.com
3. https://<span>login.microsoftonline.</span> com
4. https://<span>gcs.office.</span> com/
5. https://<span>graph.microsoft.</span> com/


## <a name="create-and-configure-an-app-for-the-agent"></a>Creare e configurare un'app per l'agente  

Innanzitutto, accedi e tieni presente che il privilegio minimo necessario per l'account è l'amministratore della ricerca. L'agente chiederà quindi di fornire i dettagli dell'autenticazione. Usa la procedura seguente per creare un'app e generare i dettagli di autenticazione necessari.

### <a name="create-an-app"></a>Creare un'app

1. Passare al portale [di Azure e](https://portal.azure.com) accedere con le credenziali di amministratore per il tenant.

2. Passare a **Azure Active Directory**  ->  **app dal** riquadro di spostamento e selezionare Nuova **registrazione.**

3. Fornisci un nome per l'app e seleziona **Registra.**

4. Prendere nota dell'ID applicazione (client).

5. Apri **autorizzazioni API** dal riquadro di spostamento e seleziona Aggiungi **un'autorizzazione.**

6. Selezionare **Microsoft Graph** e quindi Autorizzazioni **applicazione**.

7. Cercare "ExternalItem.ReadWrite.All" e "Directory.Read.All" dalle autorizzazioni e selezionare **Aggiungi autorizzazioni**.

8. Selezionare **Concedi il consenso dell'amministratore per [TenantName]** e confermare selezionando **Sì.**

9. Verificare che le autorizzazioni siano nello stato "concesso".

    :::image type="content" alt-text="Autorizzazioni visualizzate come concesse in verde nella colonna a destra." source="media/onprem-agent/granted-state.png" lightbox="media/onprem-agent/granted-state.png":::

### <a name="configure-authentication"></a>Configurare l'autenticazione

I dettagli dell'autenticazione possono essere forniti utilizzando un segreto client o un certificato. Segui i passaggi di tua scelta.

#### <a name="configuring-the-client-secret-for-authentication"></a>Configurazione del segreto client per l'autenticazione

1. Passare al portale [di Azure e](https://portal.azure.com) accedere con le credenziali di amministratore per il tenant.

2. Apri **Registrazione app** dal riquadro di spostamento e passa all'app appropriata. In **Gestisci** selezionare **Certificati e segreti.**

3. Selezionare **Nuovo segreto client** e selezionare un periodo di scadenza per il segreto. Copiare il segreto generato e salvarlo perché non verrà visualizzato di nuovo.

4. Usa questo segreto client insieme all'ID applicazione per configurare l'agente. Non è possibile utilizzare spazi vuoti nel **campo Nome** dell'agente. I caratteri numerici alfa vengono accettati.

#### <a name="using-a-certificate-for-authentication"></a>Utilizzo di un certificato per l'autenticazione

Esistono tre semplici passaggi per l'utilizzo dell'autenticazione basata su certificato:

1. Creare o ottenere un certificato
1. Upload il certificato al portale di Azure
1. Assegnare il certificato all'agente

##### <a name="step-1-get-a-certificate"></a>Passaggio 1: Ottenere un certificato

Lo script seguente può essere utilizzato per generare un certificato autofirmato. L'organizzazione potrebbe non consentire certificati autofirmati. In tal caso, utilizzare queste informazioni per comprendere i requisiti e acquisire un certificato in base ai criteri dell'organizzazione.

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Passaggio 2: Upload il certificato nel portale di Azure

1. Aprire l'applicazione e passare alla sezione certificati e segreti dal riquadro sinistro.

1. Selezionare **Upload certificato e** caricare il file cer.

1. Apri **Registrazione app** e seleziona Certificati e **segreti** nel riquadro di spostamento. Copiare l'identificazione personale del certificato.

:::image type="content" alt-text="Elenco di certificati con identificazione personale quando è selezionato Certificati e segreti nel riquadro sinistro" source="media/onprem-agent/certificates.png" lightbox="media/onprem-agent/certificates.png":::

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Passaggio 3: Assegnare il certificato all'agente

Se hai usato lo script di esempio per generare un certificato, il file PFX è disponibile nel percorso identificato nello script.

1. Scaricare il file pfx del certificato nel computer agente.

1. Fai doppio clic sul file pfx per avviare la finestra di dialogo di installazione del certificato.

1. Selezionare **Computer locale per** il percorso di archiviazione durante l'installazione del certificato.

1. Dopo aver installato il certificato, aprire **Gestisci certificati computer** tramite menu Start.

1. Selezionare il certificato appena installato in **Certificati**  >  **personali**.

1. Fai clic con il pulsante destro del mouse sul certificato e seleziona **Tutte le attività** Gestisci  >  **chiavi** private Opzione.

1. Nella finestra di dialogo delle autorizzazioni seleziona l'opzione aggiungi. Nella finestra di dialogo di selezione dell'utente, scrivi: **NT Service\GcaHostService** e fai clic su **OK.** Non fare clic sul **pulsante Controlla** nomi.

1. Fare clic su ok nella finestra di dialogo delle autorizzazioni. Il computer agente è ora configurato per l'agente per generare token usando il certificato.

## <a name="troubleshooting"></a>Risoluzione dei problemi

1. Se una connessione non riesce con l'errore "1011: L'agente connettore di Graph non è raggiungibile o offline", accedere al computer in cui è installato l'agente e avviare l'applicazione agente se non è già in esecuzione. Se la connessione continua a non riuscire, verificare che il certificato o il segreto client fornito all'agente durante la registrazione non sia scaduto e abbia le autorizzazioni necessarie.
