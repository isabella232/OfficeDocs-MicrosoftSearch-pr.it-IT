---
title: Connettore condivisione file per Microsoft Search
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore di condivisione file per Microsoft Search.
ms.openlocfilehash: 9791ee3460eb174fd7a478baa6a9beb45f1b1aab
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2019
ms.locfileid: "38310717"
---
# <a name="file-share-connector"></a>Connettore condivisione file

Con il connettore di condivisione file, gli utenti dell'organizzazione possono eseguire ricerche in condivisioni di file locali. I risultati della ricerca provenienti da queste condivisioni si fondono con i risultati di SharePoint e Microsoft OneDrive for business.

Questo articolo è per gli amministratori di Microsoft 365 o per tutti gli utenti che configurano, eseguono e monitora un connettore di condivisione file. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.

## <a name="install-a-data-gateway"></a>Installare un gateway di dati
Per accedere ai dati di terze parti, è necessario installare e configurare un gateway Microsoft Power BI. Per ulteriori informazioni, vedere [installare un gateway locale](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) .  

## <a name="content-requirements"></a>Requisiti per il contenuto
**Tipi di file**. Solo i file in questi formati possono essere indicizzati e cercati: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, xlb, xlc, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS e ZIP. Solo il contenuto testuale di questi formati è indicizzato. Tutto il contenuto multimediale viene ignorato.
 
**Limiti**relativi alle dimensioni dei file. La dimensione massima del file supportato è 100 MB. I file che superano i 100 MB vengono ignorati dall'indicizzazione. Il limite massimo di dimensioni successive all'elaborazione è pari a 4 MB. L'elaborazione si interrompe quando la dimensione di un file raggiunge i 4 MB. Di conseguenza, alcune frasi presenti nel file potrebbero non funzionare per la ricerca.

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati
Nella pagina **Connetti a origine dati** selezionare **condivisione file** e specificare il nome, l'ID di connessione e la descrizione. Nella pagina successiva, specificare il percorso della condivisione file e selezionare il gateway precedentemente installato. Immettere le credenziali per un account utente di Windows con accesso in lettura a tutti i file della condivisione. Passare attraverso le altre impostazioni e pubblicare la connessione.

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
* Gli elenchi di controllo di accesso alla condivisione file (ACL) non sono attualmente supportati. Sono supportati solo gli ACL NTFS dei file.
* Le identità esterne non sono supportate. È necessario eseguire il mapping delle identità di Azure Active Directory.
