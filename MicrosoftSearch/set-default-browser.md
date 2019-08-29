---
title: Impostare il browser predefinito
ms.author: anfowler
author: adefowler
manager: shohara
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
ROBOTS: NOINDEX
description: Impostare il browser predefinito su Microsoft Edge o Internet Explorer per gli utenti di Microsoft Search.
ms.openlocfilehash: ed145a1811aba0b58158ed04dd3bf8dc089a0682
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639740"
---
# <a name="make-microsoft-edge-the-default-browser"></a>Impostare Microsoft Edge come browser predefinito
  
Per offrire agli utenti l'esperienza migliore con la ricerca Microsoft, è possibile impostare Microsoft Edge come browser predefinito. Questa opzione consentirà di impostare Microsoft Edge come browser predefinito solo per gli utenti dell'organizzazione, mentre i singoli utenti potranno comunque selezionare un browser diverso.
  
  
## <a name="windows-8-and-later"></a>Windows 8 e versioni successive

Queste istruzioni spiegano come impostare Microsoft Edge o Internet Explorer come browser predefinito per computer che eseguono Windows 8 o versioni successive. Gli utenti potranno modificare il browser dopo aver impostato questi criteri.
  
### <a name="step-1-create-the-default-associations-file"></a>PASSAGGIO 1: Creare il file delle associazioni predefinite
Creare il file delle associazioni predefinite nella cartella SYSVOL del controller di dominio.

1. Aprire una console di amministrazione di PowerShell.
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a>PASSAGGIO 2: Aggiungere o modificare il file delle associazione predefinite

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. Modificare le voci seguenti (con estensione htm, html, http, https) e rimuovere altre voci se non sono necessarie.
  - **Microsoft Edge**
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a>Passaggio 3: Modificare i Criteri di gruppo

1. Aprire **Console Gestione Criteri di gruppo** (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.
1. Passare a **Configurazione computer\Modelli amministrativi\Componenti di Windows\Esplora file**.
1. Fare doppio clic su **Imposta file di configurazione delle associazioni predefinite**, impostarlo su **Abilitato** e immettere il percorso del file AppAssoc.xml (ad esempio %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml). Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.

  
## <a name="windows-7"></a>Windows 7

1. Configurare il computer locale che verrà usato per impostare l'oggetto Criteri di gruppo.
    
1. Aprire **Pannello di controllo\Programmi\Programmi predefiniti\Imposta programmi predefiniti** e impostare Internet Explorer come predefinito. 
    
2. Aprire Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.
    
1. Passare a **\<Computer/Utente\> Configurazione\Criteri\Preferenze\Impostazioni di Windows**.
    
2. Fare clic con il pulsante destro del mouse su **Registro\Nuovo** e selezionare **Creazione guidata Registro di sistema**.
    
3. Nella finestra Visualizzatore Registro di sistema selezionare **Computer locale** e fare clic su **Avanti**.
    
4. Passare a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selezionare il valore ProgId. Assicurarsi che il valore sia simile al seguente: 
    
    ![Selezionare il valore ProgID in Modifica stringa](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. Passare a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selezionare il valore ProgId. Assicurarsi che il valore sia simile al seguente: 
    
    ![Selezionare il valore ProgID per HTTPS in Modifica stringa](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.
    
