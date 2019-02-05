---
title: Impostare il browser predefinito
ms.author: dawholl
author: dawholl
manager: kellis
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
description: Informazioni su come configurare un browser predefinito per la società con Microsoft Search.
ms.openlocfilehash: 160dbbef9981127b74c51f54f86428667ecd4471
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612474"
---
# <a name="set-default-browser"></a>Impostare il browser predefinito

La configurazione del browser predefinito, del motore di ricerca predefinito e della home page predefinita consente agli utenti di scoprire le funzionalità di Microsoft Search, incoraggiarli a un utilizzo maggiore e fornire loro un'esperienza ottimale.
  
Per impostare il browser predefinito per l'organizzazione, eseguire la procedura seguente.
  
## <a name="windows-8-and-above"></a>Windows 8 e versioni successive

Per impostare Internet Explorer o Microsoft Edge come browser predefinito, eseguire la procedura seguente:
  
### <a name="create-default-associations-file"></a>Creare il file delle associazioni predefinite

1. Aprire una console di amministrazione di PowerShell.
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
Questa procedura prova a creare il file delle associazioni predefinite nella cartella SYSVOL del controller di dominio.
  
### <a name="add-or-edit-the-default-associations-file"></a>Aggiungere o modificare il file delle associazione predefinite

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. Modificare le voci seguenti (con estensione htm, html, http, https) e rimuovere altre voci se non sono necessarie.
    
  - **Microsoft Edge**
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. Aprire Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.
    
1. Passare a **Configurazione computer\Modelli amministrativi\Componenti di Windows\Esplora file**
    
2. Fare doppio clic su **Imposta file di configurazione delle associazioni predefinite**, impostarlo su **Abilitato** e immettere il percorso del file AppAssoc.xml (ad esempio %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)
    
4. Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.
    
Gli utenti potranno modificare il browser dopo aver impostato il criterio.
  
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
    
Gli utenti potranno modificare il browser dopo aver impostato il criterio.