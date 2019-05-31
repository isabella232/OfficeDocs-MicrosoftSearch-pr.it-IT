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
ROBOTS: NOINDEX
description: Informazioni su come configurare un browser predefinito per la società con Microsoft Search.
ms.openlocfilehash: daff7f66bd38bdd56179e44c36092a2c4fd42b42
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591162"
---
# <a name="set-default-browser"></a><span data-ttu-id="ac514-103">Impostare il browser predefinito</span><span class="sxs-lookup"><span data-stu-id="ac514-103">Set default browser</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac514-104">Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="ac514-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="ac514-105">Stiamo trasferendo il portale nell’interfaccia di amministrazione di Microsoft 365, e lo stesso sarà poi rimosso.</span><span class="sxs-lookup"><span data-stu-id="ac514-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="ac514-106">Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac514-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="ac514-107">[Panoramica di Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="ac514-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="ac514-108">La configurazione del browser predefinito, del motore di ricerca predefinito e della home page predefinita consente agli utenti di scoprire le funzionalità di Microsoft Search, incoraggiarli a un utilizzo maggiore e fornire loro un'esperienza ottimale.</span><span class="sxs-lookup"><span data-stu-id="ac514-108">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="ac514-109">Per impostare il browser predefinito per l'organizzazione, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="ac514-109">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="ac514-110">Windows 8 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="ac514-110">Windows 8 and above</span></span>

<span data-ttu-id="ac514-111">Per impostare Internet Explorer o Microsoft Edge come browser predefinito, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="ac514-111">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="ac514-112">Creare il file delle associazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="ac514-112">Create default associations file</span></span>

1. <span data-ttu-id="ac514-113">Aprire una console di amministrazione di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac514-113">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="ac514-114">Questa procedura prova a creare il file delle associazioni predefinite nella cartella SYSVOL del controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="ac514-114">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="ac514-115">Aggiungere o modificare il file delle associazione predefinite</span><span class="sxs-lookup"><span data-stu-id="ac514-115">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="ac514-116">Modificare le voci seguenti (con estensione htm, html, http, https) e rimuovere altre voci se non sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="ac514-116">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="ac514-117">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="ac514-117">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="ac514-118">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="ac514-118">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="ac514-119">Aprire Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="ac514-119">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="ac514-120">Passare a **Configurazione computer\Modelli amministrativi\Componenti di Windows\Esplora file**</span><span class="sxs-lookup"><span data-stu-id="ac514-120">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="ac514-121">Fare doppio clic su **Imposta file di configurazione delle associazioni predefinite**, impostarlo su **Abilitato** e immettere il percorso del file AppAssoc.xml (ad esempio %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span><span class="sxs-lookup"><span data-stu-id="ac514-121">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="ac514-122">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="ac514-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="ac514-123">Gli utenti potranno modificare il browser dopo aver impostato il criterio.</span><span class="sxs-lookup"><span data-stu-id="ac514-123">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="ac514-124">Windows 7</span><span class="sxs-lookup"><span data-stu-id="ac514-124">Windows 7</span></span>

1. <span data-ttu-id="ac514-125">Configurare il computer locale che verrà usato per impostare l'oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="ac514-125">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="ac514-126">Aprire **Pannello di controllo\Programmi\Programmi predefiniti\Imposta programmi predefiniti** e impostare Internet Explorer come predefinito.</span><span class="sxs-lookup"><span data-stu-id="ac514-126">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="ac514-127">Aprire Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="ac514-127">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="ac514-128">Passare a **\<Computer/Utente\> Configurazione\Criteri\Preferenze\Impostazioni di Windows**.</span><span class="sxs-lookup"><span data-stu-id="ac514-128">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="ac514-129">Fare clic con il pulsante destro del mouse su **Registro\Nuovo** e selezionare **Creazione guidata Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="ac514-129">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="ac514-130">Nella finestra Visualizzatore Registro di sistema selezionare **Computer locale** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ac514-130">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="ac514-p102">Passare a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selezionare il valore ProgId. Assicurarsi che il valore sia simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ac514-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Selezionare il valore ProgID in Modifica stringa](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="ac514-p103">Passare a **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selezionare il valore ProgId. Assicurarsi che il valore sia simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ac514-p103">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Selezionare il valore ProgID per HTTPS in Modifica stringa](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="ac514-137">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="ac514-137">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="ac514-138">Gli utenti potranno modificare il browser dopo aver impostato il criterio.</span><span class="sxs-lookup"><span data-stu-id="ac514-138">Users will be able to change the browser after this policy is set.</span></span>