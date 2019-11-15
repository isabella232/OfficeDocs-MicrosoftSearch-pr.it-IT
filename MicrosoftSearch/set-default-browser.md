---
title: Impostare il browser predefinito
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Impostare il browser predefinito su Microsoft Edge o Internet Explorer per gli utenti di Microsoft Search.
ms.openlocfilehash: b99127411d070b37fe34a4f8468449f2354cb6be
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626937"
---
# <a name="make-microsoft-edge-the-default-browser"></a><span data-ttu-id="e7589-103">Impostare Microsoft Edge come browser predefinito</span><span class="sxs-lookup"><span data-stu-id="e7589-103">Make Microsoft Edge the default browser</span></span>
  
<span data-ttu-id="e7589-104">Per offrire agli utenti l'esperienza migliore con la ricerca Microsoft, è possibile impostare Microsoft Edge come browser predefinito.</span><span class="sxs-lookup"><span data-stu-id="e7589-104">To give your users the best experience with Microsoft Search, you can make Microsoft Edge the default browser.</span></span> <span data-ttu-id="e7589-105">Questa opzione consentirà di impostare Microsoft Edge come browser predefinito solo per gli utenti dell'organizzazione, mentre i singoli utenti potranno comunque selezionare un browser diverso.</span><span class="sxs-lookup"><span data-stu-id="e7589-105">This will only set Microsoft Edge as the default browser for users in your org, individual users can still select a different browser.</span></span>
  
  
## <a name="windows-8-and-later"></a><span data-ttu-id="e7589-106">Windows 8 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="e7589-106">Windows 8 and later</span></span>

<span data-ttu-id="e7589-107">Queste istruzioni spiegano come impostare Microsoft Edge o Internet Explorer come browser predefinito per computer che eseguono Windows 8 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="e7589-107">These instructions show you how to make Microsoft Edge or Internet Explorer as the default browser for computers running Windows 8 or later.</span></span> <span data-ttu-id="e7589-108">Gli utenti potranno modificare il browser dopo aver impostato questi criteri.</span><span class="sxs-lookup"><span data-stu-id="e7589-108">Users will be able to change the browser after this policy is set.</span></span>
  
### <a name="step-1-create-the-default-associations-file"></a><span data-ttu-id="e7589-109">PASSAGGIO 1: Creare il file delle associazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="e7589-109">STEP 1: Create the default associations file</span></span>
<span data-ttu-id="e7589-110">Creare il file delle associazioni predefinite nella cartella SYSVOL del controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="e7589-110">Create the default associations file in the SYSVOL folder of the domain controller.</span></span>

1. <span data-ttu-id="e7589-111">Aprire una console di amministrazione di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7589-111">Open an administrative PowerShell console.</span></span>
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a><span data-ttu-id="e7589-112">PASSAGGIO 2:</span><span class="sxs-lookup"><span data-stu-id="e7589-112">STEP 2.</span></span> <span data-ttu-id="e7589-113">Aggiungere o modificare il file delle associazione predefinite</span><span class="sxs-lookup"><span data-stu-id="e7589-113">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. <span data-ttu-id="e7589-114">Modificare le voci seguenti (con estensione htm, html, http, https) e rimuovere altre voci se non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="e7589-114">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
  - <span data-ttu-id="e7589-115">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="e7589-115">**Microsoft Edge**</span></span>
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="e7589-116">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="e7589-116">**Internet Explorer**</span></span>
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a><span data-ttu-id="e7589-117">Passaggio 3:</span><span class="sxs-lookup"><span data-stu-id="e7589-117">Step 3.</span></span> <span data-ttu-id="e7589-118">Modificare i Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="e7589-118">Edit the Group Policy</span></span>

1. <span data-ttu-id="e7589-119">Aprire **Console Gestione Criteri di gruppo** (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="e7589-119">Open **Group Policy Management Console** (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
1. <span data-ttu-id="e7589-120">Passare a **Configurazione computer\Modelli amministrativi\Componenti di Windows\Esplora file**.</span><span class="sxs-lookup"><span data-stu-id="e7589-120">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**.</span></span>
1. <span data-ttu-id="e7589-121">Fare doppio clic su **Imposta file di configurazione delle associazioni predefinite**, impostarlo su **Abilitato** e immettere il percorso del file AppAssoc.xml (ad esempio %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml). Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="e7589-121">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

  
## <a name="windows-7"></a><span data-ttu-id="e7589-122">Windows 7</span><span class="sxs-lookup"><span data-stu-id="e7589-122">Windows 7</span></span>

1. <span data-ttu-id="e7589-123">Configurare il computer locale che verrà usato per impostare l'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="e7589-123">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="e7589-124">Aprire **Pannello di controllo\Programmi\Programmi predefiniti\Imposta programmi predefiniti** e impostare Internet Explorer come predefinito.</span><span class="sxs-lookup"><span data-stu-id="e7589-124">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="e7589-125">Aprire Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="e7589-125">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="e7589-126">Passare a **\<Computer/Utente\> Configurazione\Criteri\Preferenze\Impostazioni di Windows**.</span><span class="sxs-lookup"><span data-stu-id="e7589-126">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="e7589-127">Fare clic con il pulsante destro del mouse su **Registro\Nuovo** e selezionare **Creazione guidata Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="e7589-127">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="e7589-128">Nella finestra Visualizzatore Registro di sistema selezionare **Computer locale** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e7589-128">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="e7589-p105">Passare a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selezionare il valore ProgId. Assicurarsi che il valore sia simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e7589-p105">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Selezionare il valore ProgID in Modifica stringa](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="e7589-p106">Passare a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selezionare il valore ProgId. Assicurarsi che il valore sia simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e7589-p106">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Selezionare il valore ProgID per HTTPS in Modifica stringa](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="e7589-135">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="e7589-135">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
