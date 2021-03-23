---
title: Impostare la home page predefinita
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
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
description: Informazioni su come impostare Bing come home page predefinita per la società con Microsoft Search.
ms.openlocfilehash: 0d8fac0302e672c603853185ff0810bf6d42371c
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031675"
---
# <a name="make-bingcom-the-default-home-page"></a><span data-ttu-id="ff4f8-103">Impostare Bing.com come home page predefinita</span><span class="sxs-lookup"><span data-stu-id="ff4f8-103">Make Bing.com the default home page</span></span>

<span data-ttu-id="ff4f8-104">Questo articolo spiega come impostare Bing.com come home page predefinita per i browser Microsoft Edge, Google Chrome e Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-104">This article explains how to set Bing.com as the default home page for Microsoft Edge, Google Chrome, and Internet Explorer browsers.</span></span> 
  
 
## <a name="microsoft-edge-on-windows-10-version-1511-or-later"></a><span data-ttu-id="ff4f8-105">Microsoft Edge in Windows 10 versione 1511 o successiva</span><span class="sxs-lookup"><span data-stu-id="ff4f8-105">Microsoft Edge on Windows 10, Version 1511 or later</span></span>

<span data-ttu-id="ff4f8-106">Gli utenti non potranno modificare la home page dopo aver impostato questo criterio.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-106">Users won't be able to change this once this policy is set.</span></span> 

1. <span data-ttu-id="ff4f8-107">Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-107">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span> 
1. <span data-ttu-id="ff4f8-108">Passare a **Modelli amministrativi\Componenti di Windows\Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-108">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**.</span></span>    
1. <span data-ttu-id="ff4f8-109">Fare doppio clic su **Configura pagine iniziali**, impostarlo su **Abilitato** e immettere `https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="ff4f8-109">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
1.  <span data-ttu-id="ff4f8-110">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-110">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

  
## <a name="google-chrome-on-windows-xp-sp2-or-later"></a><span data-ttu-id="ff4f8-111">Google Chrome in Windows XP SP2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="ff4f8-111">Google Chrome on Windows XP SP2 or later</span></span>


<span data-ttu-id="ff4f8-112">L'articolo del supporto di Windows sulla gestione dei file ADMX e i file ADMX più recenti per le diverse versioni di Windows sono disponibili nel sito del [Supporto tecnico Microsoft](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="ff4f8-112">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="ff4f8-113">È necessario anche il file di criteri Google più recente, disponibile nella [Guida di Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="ff4f8-113">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="ff4f8-p101">Se le impostazioni descritte in questa sezione non sono disponibili all'interno di GPMC, scaricare il file ADMX appropriato e copiarlo nell'[archivio centrale](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). L'archivio centrale nel controller è una cartella conforme alla convenzione di denominazione seguente:</span><span class="sxs-lookup"><span data-stu-id="ff4f8-p101">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="ff4f8-116">**%systemroot%\sysvol\\<dominio\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="ff4f8-116">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="ff4f8-p102">Ogni dominio gestito dal controller deve ottenere una cartella separata. Per copiare il file ADMX dal prompt dei comandi, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ff4f8-p102">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="ff4f8-119">Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-119">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
1. <span data-ttu-id="ff4f8-120">Verificare che le cartelle seguenti vengono visualizzate nella sezione **Modelli amministrativi** di *Configurazione utente/computer*: Google Chrome e Google Chrome - Impostazioni predefinite (gli utenti possono eseguire l'override).</span><span class="sxs-lookup"><span data-stu-id="ff4f8-120">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
   - <span data-ttu-id="ff4f8-121">Le impostazioni della prima sezione sono fisse e gli amministratori locali non possono modificarle.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-121">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
   - <span data-ttu-id="ff4f8-p103">Le impostazioni dell'ultima sezione dei criteri possono essere modificate dagli utenti nelle impostazioni del browser. È necessario decidere se gli utenti possono eseguire l'override dell'impostazione predefinita. Nella procedura seguente modificare l'impostazione nella cartella corrispondente ai criteri e alle esigenze dell'organizzazione. Nella procedura seguente si usa Google Chrome - Impostazioni predefinite come valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-p103">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>

1. <span data-ttu-id="ff4f8-126">Passare a **&lt;Configurazione computer/utente&gt;\Modelli amministrativi\Google Chrome - Impostazioni predefinite\Home page**.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-126">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span> 
1. <span data-ttu-id="ff4f8-127">Fare doppio clic su **Usa la pagina Nuova scheda come Pagina iniziale** e impostarlo su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-127">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span> 
1. <span data-ttu-id="ff4f8-128">Passare a **&lt;Configurazione computer/utente&gt;\Modelli amministrativi\Google Chrome - Impostazioni predefinite\Pagina Nuova scheda**.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-128">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span> 
1. <span data-ttu-id="ff4f8-129">Fare doppio clic su **Configura l'URL della pagina iniziale**, impostarlo su **Abilitato** e immettere `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="ff4f8-129">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span> 
1. <span data-ttu-id="ff4f8-130">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-130">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

## <a name="internet-explorer-50-or-later"></a><span data-ttu-id="ff4f8-131">Internet Explorer 5.0 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="ff4f8-131">Internet Explorer 5.0 or later</span></span>
<span data-ttu-id="ff4f8-132">Gli utenti possono comunque modificare la home page dopo aver impostato questo criterio.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-132">Users can still change the home page after this policy is set.</span></span> 

1. <span data-ttu-id="ff4f8-133">Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-133">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="ff4f8-134">Passare a **Configurazione utente\Preferenze\Impostazioni del Pannello di controllo\Impostazioni Internet**.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-134">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="ff4f8-135">Fare clic con il pulsante destro del mouse su **Impostazioni Internet** e selezionare **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-135">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff4f8-136">È necessario selezionare l'opzione Internet Explorer 10 per applicare le impostazioni di Internet Explorer 11 perché le stesse impostazioni valgono anche per Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-136">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="ff4f8-p104">Le impostazioni sottolineate in rosso non vengono configurate nel computer di destinazione, mentre quelle sottolineate in verde vengono configurate. Per modificare il tipo di sottolineatura, usare i tasti funzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff4f8-p104">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="ff4f8-139">F5 - Abilita tutte le impostazioni nella scheda corrente</span><span class="sxs-lookup"><span data-stu-id="ff4f8-139">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="ff4f8-140">F6 - Abilita l'impostazione attualmente selezionata</span><span class="sxs-lookup"><span data-stu-id="ff4f8-140">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="ff4f8-141">F7 - Disabilita l'impostazione attualmente selezionata</span><span class="sxs-lookup"><span data-stu-id="ff4f8-141">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="ff4f8-142">F8 - Disabilita tutte le impostazioni nella scheda corrente</span><span class="sxs-lookup"><span data-stu-id="ff4f8-142">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="ff4f8-p105">Premere **F8** per disabilitare tutte le impostazioni prima di configurare qualsiasi valore. La schermata sarà simile a quella seguente:</span><span class="sxs-lookup"><span data-stu-id="ff4f8-p105">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Finestra di dialogo delle proprietà di Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="ff4f8-146">Premere **F6** nell'impostazione della home page e immettere `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="ff4f8-146">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="ff4f8-147">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="ff4f8-147">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>