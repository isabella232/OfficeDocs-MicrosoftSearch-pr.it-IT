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
description: Informazioni su come configurare un browser predefinito per la propria azienda con Microsoft Search.
ms.openlocfilehash: 160dbbef9981127b74c51f54f86428667ecd4471
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612474"
---
# <a name="set-default-browser"></a>Impostare il browser predefinito

Configurazione il browser predefinito, motore di ricerca predefinito e home page predefinita consente agli utenti individuare funzionalità Microsoft Search, incoraggiare altri dati di utilizzo e offrire un'esperienza più uniforme.
  
Per impostare il browser predefinito per l'organizzazione, attenersi alla procedura seguente.
  
## <a name="windows-8-and-above"></a>Windows 8 e versioni superiori

Per configurare Internet Explorer o Microsoft Edge come browser predefinito, eseguire la procedura seguente:
  
### <a name="create-default-associations-file"></a>Creare file di associazioni predefinito

1. Aprire una console di amministrazione PowerShell.
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
La procedura seguente prova e creare il file di associazioni predefinita nella cartella SYSVOL del controller di dominio.
  
### <a name="add-or-edit-the-default-associations-file"></a>Aggiungere o modificare le associazioni file predefinito

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. Modificare le voci seguenti (con estensione htm o HTML, http, https) e rimuovere altre voci se non sono necessarie.
    
  - **Microsoft Edge**
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. Aprire Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo.
    
1. Passare a **Configurazione utente\Modelli amministrativi\Componenti di Components\File risorse**
    
2. Fare doppio clic su **imposta un file di configurazione di associazioni predefinito**, impostato su **attivato**e immettere il percorso di AppAssoc.xml (ad esempio %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)
    
4. Applicare criteri risultante tramite il collegamento al dominio appropriato.
    
Gli utenti saranno in grado di modificare il browser dopo che questo criterio è impostato.
  
## <a name="windows-7"></a>Windows 7

1. Configurare il computer locale che verrà utilizzato per impostare l'oggetto Criteri di gruppo.
    
1. Aprire **Programmi predefiniti di controllo Panel\Programs\Default Programs\Set** e Internet Explorer come predefinito. 
    
2. Aprire Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo.
    
1. Passare a ** \<Computer/utente\> Configuration\Policies\Preferences\Windows impostazioni**.
    
2. Pulsante destro del mouse su **Registry\New** e selezionare **Creazione guidata del Registro di sistema**.
    
3. Dalla finestra del Browser del Registro di sistema, selezionare **Computer locale** e fare clic su **Avanti**.
    
4. Accedere a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selezionare il valore ProgId. Verificare che il valore è simile a quello illustrato di seguito: 
    
    ![Seleziona un valore ProgID nella stringa di modifica](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. Accedere a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selezionare il valore ProgId. Verificare che il valore è simile a quella riportata di seguito: 
    
    ![Selezionare ProgId per HTTPS nella stringa di modifica](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. Applicare criteri risultante tramite il collegamento al dominio appropriato.
    
Gli utenti saranno in grado di modificare il browser dopo che questo criterio è impostato.