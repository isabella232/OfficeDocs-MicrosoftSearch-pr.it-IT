---
title: Connettore condivisione file per Microsoft Search
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.date: 10/08/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore di condivisione file per Microsoft Search.
ms.openlocfilehash: d5fbc1af2868ce7baa70017f617a9731340fb19a
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949845"
---
# <a name="file-share-connector"></a>Connettore condivisione file

Con il connettore di condivisione file, gli utenti dell'organizzazione possono eseguire ricerche in condivisioni di file locali. I risultati della ricerca provenienti da queste condivisioni si fondono con i risultati di SharePoint e Microsoft OneDrive for business.

Questo articolo è per gli amministratori di Microsoft 365 o per tutti gli utenti che configurano, eseguono e monitora un connettore di condivisione file. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.

## <a name="install-a-data-gateway"></a>Installare un gateway di dati
Per accedere ai dati di terze parti, è necessario installare e configurare un gateway Microsoft Power BI. Per ulteriori informazioni, vedere [Install and on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) .  

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati
Nella pagina **Connetti a origine dati** creare una cartella e specificare un percorso per la condivisione file. Selezionare quindi il gateway precedentemente installato. Immettere le credenziali per un account utente di Windows con **accesso in lettura** a tutti i file della condivisione. È quindi possibile verificare i file presenti nella condivisione e visualizzare tutti i metadati recuperati.

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca
Il connettore di condivisione file supporta solo le autorizzazioni di ricerca visibili a **tutti**. I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione.

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento
L'intervallo di pianificazione di aggiornamento predefinito consigliato è 15 minuti, ma è possibile modificarlo in un altro intervallo preferito.

## <a name="set-up-your-search-results-page"></a>Configurare la pagina dei risultati di ricerca
Per visualizzare risultati di connessione file diversi nelle schede **tutti** e **file** , è necessario configurare una pagina dei risultati del motore di ricerca di SharePoint:
- La tabella **All** contiene i risultati combinati delle connessioni di file, file di SharePoint, file di OneDrive e siti di SharePoint. 
- La verticale dei **file** Visualizza tutti i risultati dei file delle connessioni, SharePoint e OneDrive.
I risultati delle connessioni ai file vengono aggiunti ai risultati già esistenti sia nei verticali **tutti** che in quelli dei **file** .

Per impostare la pagina dei risultati di ricerca, eseguire la procedura seguente:
1. Creare una raccolta siti di SharePoint con una pagina di ricerca moderna.

2. Installare una [Shell di gestione di SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).

3. Aprire SharePoint Online Management Shell come amministratore e importare il modulo **Microsoft. SharePoint. client. dll** presente in `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`.

> [!NOTE]
> Questo percorso potrebbe non essere lo stesso per tutti gli utenti.

Per importare il modulo, eseguire il comando seguente in SharePoint Online Management Shell:
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. Eseguire lo script seguente:
```bash
$orgName = Read-Host -prompt 'Please enter your org name'
$userName = Read-Host -prompt 'Enter user name'
$userCreds = Get-Credential -UserName $userName -Message "Type the password"
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCreds

$url = Read-Host -Prompt 'Please enter the site url'
$site = Get-SPOSite -Identity $url
Set-SPOSite $url -DenyAddAndCustomizePages 0

$pwd = Read-Host -AsSecureString 'type the password'
$context = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credential = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($userName, $pwd)
$context.Credentials = $credential
$web = $context.Web
$context.Load($web)
$web.AllProperties["AllVerticalContent"] = "Combined"
$web.Update()
$context.ExecuteQuery()
$web.AllProperties["FilesVerticalContent"] = "ConnectorsOnly"
$web.Update()
$context.ExecuteQuery()
Set-SPOSite $url -DenyAddAndCustomizePages 1

Write-Host "Success" -ForegroundColor Cyan
Read-Host -Prompt 'Press enter to exit'
```

5. Immettere i valori richiesti in PowerShell, ad esempio il nome dell'organizzazione, l'utente, la password e l'URL del sito. **Ad esempio**, se le credenziali di amministratore sono `admin@a830edad9050849823J19081300.onmicrosoft.com`, il nome dell'organizzazione è **a830edad9050849823J19081300**e l'URL del sito è `https:// a830edad9050849823J19081300.sharepoint.com`.

> [!NOTE]
> L'impostazione **allProperties** può essere completata solo a livello di raccolta siti (teams/Comms).

6. A questo punto è possibile cercare i file indicizzati e visualizzare i risultati nelle schede **tutti** e **file** .

## <a name="search-for-file-share-content-in-the-search-results-page"></a>Cercare il contenuto della condivisione file nella pagina dei risultati di ricerca
Per cercare il contenuto indicizzato, passare alla Home page di SharePoint del tenant di test. I risultati verranno visualizzati nelle schede **tutti** e **file** .

A causa di restrizioni del browser, non è possibile selezionare un risultato di file per visualizzare o aprire file dalle ricerche di condivisione file locali. Per aprire questi file, copiare il collegamento del risultato del file e incollarlo nella barra degli indirizzi del browser del sistema. Per Windows, utilizzare Esplora risorse. Successivamente, è possibile aprire il file nel sistema.

![Ricerca di SharePoint con la finestra di dialogo Copia collegamento aperta.](media/fileshare-search.png)

## <a name="troubleshooting"></a>Risoluzione dei problemi
Se si verifica un errore critico in una connessione, il relativo stato viene visualizzato come **non riuscito**. Per ottenere ulteriori informazioni sui tre tipi di errori, passare alla pagina dei **Dettagli dell'errore** e selezionare la connessione non riuscita. Per ulteriori informazioni, vedere [gestire il connettore](manage-connector.md) .
1. **Gateway non raggiungibile (codice di errore: 11)**. Il computer del gateway per la connessione è inverso. Verificare che il processo Microsoft Power BI venga eseguito nel computer gateway.
2. **Errore di autenticazione (codice di errore: 12)**. Le credenziali utilizzate per creare la connessione sono scadute o non sono più valide. Per risolvere questo errore, immettere le credenziali valide.
3. **Errore interno (codice di errore: qualsiasi valore diverso da 11 o 12)**. Si è verificato un errore nell'infrastruttura del connettore. Per informazioni su come segnalare tali errori, vedere l'articolo sui [commenti e suggerimenti](connectors-feedback.md) .

## <a name="limitations"></a>Limitazioni
Il connettore di condivisione file ha queste limitazioni nella versione di anteprima:
* È possibile indicizzare solo i file con proprietà fisse, non i file con proprietà personalizzate.
* Gli elenchi di controllo di accesso alla condivisione file (ACL) non sono attualmente supportati.
* Le identità esterne non sono supportate. È necessario eseguire il mapping delle identità di Azure Active Directory.