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
# <a name="graph-connector-agent"></a>Agente del connettore grafico

L'utilizzo di connettori di Graph su-Prem richiede l'installazione del software dell' *agente del connettore grafico* . Consente il trasferimento sicuro dei dati tra i dati locali e le API del connettore grafico. In questo articolo vengono illustrate le istruzioni per l'installazione e la configurazione dell'agente.

## <a name="installation"></a>Installazione

Scaricare la versione più recente di Graph Connector [Agent e](https://aka.ms/gcadownload) installare il software utilizzando l'installazione guidata. Usando la configurazione consigliata della macchina descritta di seguito, il software è in grado di gestire fino a tre connessioni. Tutte le connessioni oltre che potrebbero peggiorare le prestazioni di tutte le connessioni nell'agente.

Configurazione consigliata:

* Windows 10, Windows Server 2016 R2 e successive
* 8 core, 3 GHz
* 16 GB di RAM, 2 GB di spazio su disco
* Accesso alla rete all'origine dati e a Internet tramite 443

## <a name="create-and-configure-an-app-for-the-agent"></a>Creare e configurare un'app per l'agente  

Prima di utilizzare l'agente, è necessario creare un'app e configurare i dettagli dell'autenticazione.

### <a name="create-an-app"></a>Creare un'app

1. Accedere al [portale di Azure](https://portal.azure.com) e accedere con le credenziali di amministratore per il tenant.
2. Passare alle registrazioni delle app di **Azure Active Directory**  ->  **App registrations** dal riquadro di spostamento e selezionare **nuova registrazione**.
3. Specificare un nome per l'app e selezionare **registra**.
4. Prendere nota dell'ID applicazione (client).
5. Aprire le **autorizzazioni API** dal riquadro di spostamento e selezionare **Aggiungi un'autorizzazione**.
6. Selezionare **Microsoft Graph** e quindi **autorizzazioni** per le applicazioni.
7. Cercare "ExternalItem. ReadWrite. All" e "directory. Read. All" dalle autorizzazioni e selezionare **Aggiungi autorizzazioni**.
8. Selezionare **Concedi consenso amministratore per [TenantName]** e confermare selezionando **Sì**.
9. Verificare che le autorizzazioni siano nello stato "concesso".
     ![Autorizzazioni visualizzate come concesse in verde sulla colonna a destra.](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>Configurare l'autenticazione

È possibile fornire informazioni dettagliate sull'autenticazione utilizzando un segreto client o un certificato. Segui i passaggi per la tua scelta.

#### <a name="configuring-the-client-secret-for-authentication"></a>Configurazione del segreto client per l'autenticazione

1. Accedere al [portale di Azure](https://portal.azure.com) e accedere con le credenziali di amministratore per il tenant.
2. Aprire **registrazione app** dal riquadro di spostamento e passare all'app appropriata. In **Gestisci** selezionare **certificati e segreti**.
3. Selezionare **nuovo segreto client** e selezionare un periodo di scadenza per il segreto. Copiare il segreto generato e salvarlo perché non verrà visualizzato di nuovo.
4. Utilizzare questo segreto client insieme all'ID applicazione per configurare l'agente. Non è possibile utilizzare spazi vuoti nel campo **nome** dell'agente. Vengono accettati caratteri numerici alfanumerici.

#### <a name="using-a-certificate-for-authentication"></a>Utilizzo di un certificato per l'autenticazione

Sono disponibili tre semplici passaggi per l'utilizzo dell'autenticazione basata sui certificati:

1. Creare o ottenere un certificato
1. Caricare il certificato nel portale di Azure
1. Assegnare il certificato all'agente

##### <a name="step-1-get-a-certificate"></a>Passaggio 1: ottenere un certificato

Lo script riportato di seguito può essere utilizzato per generare un certificato autofirmato. L'organizzazione potrebbe non consentire certificati autofirmati. In tal caso, utilizzare queste informazioni per comprendere i requisiti e acquisire un certificato in base ai criteri dell'organizzazione.

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Passaggio 2: caricare il certificato nel portale di Azure

1. Aprire l'applicazione e passare alla sezione certificati e segreti dal riquadro sinistro
1. Selezionare ' carica certificato ' e caricare il file con estensione cer
1. Aprire **registrazione app** e selezionare **certificati e segreti** nel riquadro di spostamento. Copiare l'identificazione personale del certificato.

![Elenco dei certificati di thumbrint in caso di selezione di certificati e segreti nel riquadro sinistro](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Passaggio 3: assegnare il certificato all'agente

Se è stato utilizzato lo script di esempio per generare un certificato, è possibile trovare il file PFX nel percorso identificato nello script.

1. Scaricare il file pfx del certificato nel computer dell'agente.
1. Fare doppio clic sul file PFX per avviare la finestra di dialogo di installazione del certificato.
1. Selezionare ' computer locale ' per la posizione dell'archivio durante l'installazione del certificato.
1. Dopo aver installato il certificato, aprire ' Gestisci certificati computer ' tramite il menu Start
1. Selezionare il certificato appena installato in ' Personal '->' Certificates '
1. Fare clic con il pulsante destro del mouse sul cert e selezionare ' tutte le attività'->' Gestisci chiavi private.. .' Opzione
1. Nella finestra di dialogo autorizzazioni selezionare Aggiungi opzione. Nella finestra di dialogo Selezione utenti, scrivere:' NT Service\GcaHostService ' e fare clic su' OK '. Non fare clic sul pulsante ' Controlla nomi '.
1. Fare clic su OK nella finestra di dialogo autorizzazioni. Il computer dell'agente è ora configurato per l'agente per generare token utilizzando il certificato.
