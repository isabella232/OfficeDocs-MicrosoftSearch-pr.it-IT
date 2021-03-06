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
ms.openlocfilehash: 5134c0c4459f9d38825451f274e67469956756d2
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508806"
---
# <a name="graph-connector-agent"></a>Agente connettore grafico

L'utilizzo di connettori Graph in rete richiede l'installazione del software *agente connettore Graph.* Consente il trasferimento sicuro dei dati tra i dati locali e le API del connettore Graph. In questo articolo viene illustrata l'installazione e la configurazione dell'agente.

## <a name="installation"></a>Installazione

Scaricare la versione più recente dell'agente del connettore Graph [qui](https://aka.ms/gcadownload) e installare il software utilizzando l'installazione guidata. Usando la configurazione consigliata del computer descritto di seguito, il software può gestire fino a tre connessioni. Eventuali connessioni oltre tale limite potrebbero compromettere le prestazioni di tutte le connessioni nell'agente.

Configurazione consigliata:

* Windows 10, Windows Server 2016 R2 e successive
* [.NET Core Desktop Runtime 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 core, 3 GHz
* 16 GB di RAM, 2 GB di spazio su disco
* Accesso di rete all'origine dati e a Internet tramite 443

Dopo aver installato l'agente, se i server proxy o i firewall dell'organizzazione bloccano la comunicazione con domini sconosciuti, aggiungere quelli seguenti all'elenco Consenti.

1. *.servicebus.windows.net
2. *.events.data.microsoft.com
3. https://<span>login.microsoftonline.</span>com
4. https://<span>gcs.office.</span> com/
5. https://<span>graph.microsoft.</span> com/


## <a name="create-and-configure-an-app-for-the-agent"></a>Creare e configurare un'app per l'agente  

Prima di tutto, accedere e tenere presente che il privilegio minimo necessario per l'account è l'amministratore della ricerca. L'agente chiederà quindi di fornire i dettagli dell'autenticazione. Usa la procedura seguente per creare un'app e generare i dettagli di autenticazione necessari.

### <a name="create-an-app"></a>Creare un'app

1. Passare al portale [di Azure e](https://portal.azure.com) accedere con le credenziali di amministratore per il tenant.
2. Passare alle **registrazioni delle** app di Azure Active Directory  ->   dal riquadro di spostamento e selezionare **Nuova registrazione.**
3. Fornisci un nome per l'app e seleziona **Registra.**
4. Prendere nota dell'ID applicazione (client).
5. Apri **le autorizzazioni API** dal riquadro di spostamento e seleziona Aggiungi **un'autorizzazione.**
6. Selezionare **Microsoft Graph e** quindi Autorizzazioni **applicazione.**
7. Cercare "ExternalItem.ReadWrite.All" e "Directory.Read.All" nelle autorizzazioni e selezionare **Aggiungi autorizzazioni.**
8. Selezionare **Concedi il consenso dell'amministratore per [TenantName]** e confermare selezionando **Sì.**
9. Verificare che le autorizzazioni siano nello stato "concesso".
     ![Autorizzazioni visualizzate come concesse in verde nella colonna a destra.](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>Configurare l'autenticazione

I dettagli di autenticazione possono essere forniti utilizzando un segreto client o un certificato. Seguire i passaggi di propria scelta.

#### <a name="configuring-the-client-secret-for-authentication"></a>Configurazione del segreto client per l'autenticazione

1. Passare al portale [di Azure e](https://portal.azure.com) accedere con le credenziali di amministratore per il tenant.
2. Apri **Registrazione app** dal riquadro di spostamento e passa all'app appropriata. In **Gestisci** selezionare **Certificati e segreti.**
3. Selezionare **Nuovo segreto client** e selezionare un periodo di scadenza per il segreto. Copia il segreto generato e salvalo perché non verrà visualizzato di nuovo.
4. Utilizzare questo segreto client insieme all'ID applicazione per configurare l'agente. Non è possibile utilizzare spazi vuoti nel **campo Nome** dell'agente. I caratteri numerici alfa vengono accettati.

#### <a name="using-a-certificate-for-authentication"></a>Utilizzo di un certificato per l'autenticazione

Esistono tre semplici passaggi per l'utilizzo dell'autenticazione basata su certificati:

1. Creare o ottenere un certificato
1. Caricare il certificato nel portale di Azure
1. Assegnare il certificato all'agente

##### <a name="step-1-get-a-certificate"></a>Passaggio 1: Ottenere un certificato

Lo script seguente può essere utilizzato per generare un certificato autofirmato. L'organizzazione potrebbe non consentire certificati autofirmati. In tal caso, utilizzare queste informazioni per comprendere i requisiti e acquisire un certificato in conformità ai criteri dell'organizzazione.

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Passaggio 2: Caricare il certificato nel portale di Azure

1. Aprire l'applicazione e passare alla sezione certificati e segreti dal riquadro sinistro
1. Selezionare "Carica certificato" e caricare il file cer
1. Apri **la registrazione dell'app** e **seleziona Certificati e** segreti nel riquadro di spostamento. Copiare l'identificazione personale del certificato.

![Elenco dei certificati di identificazione personale quando è selezionato Certificati e segreti nel riquadro sinistro](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Passaggio 3: Assegnare il certificato all'agente

Se hai usato lo script di esempio per generare un certificato, il file PFX è disponibile nel percorso identificato nello script.

1. Scaricare il file pfx del certificato nel computer agente.
1. Fai doppio clic sul file pfx per avviare la finestra di dialogo di installazione del certificato.
1. Seleziona "Computer locale" per il percorso dell'archivio durante l'installazione del certificato.
1. Dopo aver installato il certificato, apri "Gestisci certificati computer" dal menu Start
1. Selezionare il certificato appena installato in "Personale" -> 'Certificati'
1. Fai clic con il pulsante destro del mouse sul certificato e seleziona "Tutte le attività" -> 'Gestisci chiavi private...' Opzione
1. Nella finestra di dialogo delle autorizzazioni, selezionare l'opzione aggiungi. Nella finestra di dialogo di selezione dell'utente, scrivi: "NT Service\GcaHostService" e fai clic su "OK". Non fare clic sul pulsante "Controlla nomi".
1. Fare clic su Ok nella finestra di dialogo delle autorizzazioni. Il computer agente è ora configurato per l'agente per generare token usando il certificato.

## <a name="troubleshooting"></a>Risoluzione dei problemi
1. Se una connessione non riesce con l'errore "1011: L'agente connettore Graph non è raggiungibile o offline", accedere al computer in cui è installato l'agente e avviare l'applicazione agente se non è già in esecuzione. Se la connessione continua a non riuscire, verificare che il certificato o il segreto client fornito all'agente durante la registrazione non sia scaduto e abbia le autorizzazioni necessarie.
