---
title: Impostare il browser predefinito
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Informazioni su come configurare un browser predefinito per la propria azienda con Microsoft Search.
ms.openlocfilehash: 13a0a878b3288abeb7b07defdab839a158adc2ac
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378915"
---
# <a name="set-default-browser"></a><span data-ttu-id="28775-103">Impostare il browser predefinito</span><span class="sxs-lookup"><span data-stu-id="28775-103">Set default browser</span></span>

<span data-ttu-id="28775-104">Configurazione il browser predefinito, motore di ricerca predefinito e home page predefinita consente agli utenti individuare funzionalità Microsoft Search, incoraggiare altri dati di utilizzo e offrire un'esperienza più uniforme.</span><span class="sxs-lookup"><span data-stu-id="28775-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="28775-105">Per impostare il browser predefinito per l'organizzazione, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="28775-105">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="28775-106">Windows 8 e versioni superiori</span><span class="sxs-lookup"><span data-stu-id="28775-106">Windows 8 and above</span></span>

<span data-ttu-id="28775-107">Per configurare Internet Explorer o Microsoft Edge come browser predefinito, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="28775-107">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="28775-108">Creare file di associazioni predefinito</span><span class="sxs-lookup"><span data-stu-id="28775-108">Create default associations file</span></span>

1. <span data-ttu-id="28775-109">Aprire una console di amministrazione PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28775-109">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="28775-110">La procedura seguente prova e creare il file di associazioni predefinita nella cartella SYSVOL del controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="28775-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="28775-111">Aggiungere o modificare le associazioni file predefinito</span><span class="sxs-lookup"><span data-stu-id="28775-111">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="28775-112">Modificare le voci seguenti (con estensione htm o HTML, http, https) e rimuovere altre voci se non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="28775-112">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="28775-113">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="28775-113">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="28775-114">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="28775-114">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="28775-115">Aprire Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="28775-115">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="28775-116">Passare a **Configurazione utente\Modelli amministrativi\Componenti di Components\File risorse**</span><span class="sxs-lookup"><span data-stu-id="28775-116">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="28775-117">Fare doppio clic su **imposta un file di configurazione di associazioni predefinito**, impostato su **attivato**e immettere il percorso di AppAssoc.xml (ad esempio %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span><span class="sxs-lookup"><span data-stu-id="28775-117">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="28775-118">Applicare criteri risultante tramite il collegamento al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="28775-118">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="28775-119">Gli utenti saranno in grado di modificare il browser dopo che questo criterio è impostato.</span><span class="sxs-lookup"><span data-stu-id="28775-119">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="28775-120">Windows 7</span><span class="sxs-lookup"><span data-stu-id="28775-120">Windows 7</span></span>

1. <span data-ttu-id="28775-121">Configurare il computer locale che verrà utilizzato per impostare l'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="28775-121">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="28775-122">Aprire **Programmi predefiniti di controllo Panel\Programs\Default Programs\Set** e Internet Explorer come predefinito.</span><span class="sxs-lookup"><span data-stu-id="28775-122">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="28775-123">Aprire Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="28775-123">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="28775-124">Passare a \*\* \<Computer/utente\> Configuration\Policies\Preferences\Windows impostazioni\*\*.</span><span class="sxs-lookup"><span data-stu-id="28775-124">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="28775-125">Pulsante destro del mouse su **Registry\New** e selezionare **Creazione guidata del Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="28775-125">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="28775-126">Dalla finestra del Browser del Registro di sistema, selezionare **Computer locale** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="28775-126">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="28775-p101">Accedere a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selezionare il valore ProgId. Verificare che il valore è simile a quello illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="28775-p101">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Seleziona un valore ProgID nella stringa di modifica](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="28775-p102">Accedere a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selezionare il valore ProgId. Verificare che il valore è simile a quella riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="28775-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Selezionare ProgId per HTTPS nella stringa di modifica](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="28775-133">Applicare criteri risultante tramite il collegamento al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="28775-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="28775-134">Gli utenti saranno in grado di modificare il browser dopo che questo criterio è impostato.</span><span class="sxs-lookup"><span data-stu-id="28775-134">Users will be able to change the browser after this policy is set.</span></span>