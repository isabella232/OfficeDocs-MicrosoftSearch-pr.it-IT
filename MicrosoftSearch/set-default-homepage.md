---
title: Impostare la home page predefinita
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
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
ROBOTS: NOINDEX
description: Informazioni su come impostare Bing come home page predefinita per la società con Microsoft Search.
ms.openlocfilehash: 0fc16bc7389b8cfffc2ad528b3b10c7ae1d498c3
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591180"
---
# <a name="set-default-homepage"></a><span data-ttu-id="34200-103">Impostare la pagina iniziale predefinita</span><span class="sxs-lookup"><span data-stu-id="34200-103">Set default homepage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34200-104">Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="34200-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="34200-105">Stiamo trasferendo il portale nell’interfaccia di amministrazione di Microsoft 365, e lo stesso sarà poi rimosso.</span><span class="sxs-lookup"><span data-stu-id="34200-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="34200-106">Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34200-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="34200-107">[Panoramica di Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="34200-107">Overview of Microsoft Search</span></span>

<span data-ttu-id="34200-108">La configurazione del browser predefinito, del motore di ricerca predefinito e della home page predefinita consente agli utenti di scoprire le funzionalità di Microsoft Search, incoraggiarli a un utilizzo maggiore e fornire loro un'esperienza ottimale.</span><span class="sxs-lookup"><span data-stu-id="34200-108">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="34200-109">Per impostare la home page predefinita per l'organizzazione, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="34200-109">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="34200-110">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="34200-110">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="34200-111">Internet Explorer 5.0 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="34200-111">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="34200-112">Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="34200-112">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="34200-113">Passare a **Configurazione utente\Preferenze\Impostazioni del Pannello di controllo\Impostazioni Internet**.</span><span class="sxs-lookup"><span data-stu-id="34200-113">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="34200-114">Fare clic con il pulsante destro del mouse su **Impostazioni Internet** e selezionare **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="34200-114">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="34200-115">È necessario selezionare l'opzione Internet Explorer 10 per applicare le impostazioni di Internet Explorer 11 perché le stesse impostazioni valgono anche per Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="34200-115">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="34200-p102">Le impostazioni sottolineate in rosso non vengono configurate nel computer di destinazione, mentre quelle sottolineate in verde vengono configurate. Per modificare il tipo di sottolineatura, usare i tasti funzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="34200-p102">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="34200-118">F5 - Abilita tutte le impostazioni nella scheda corrente</span><span class="sxs-lookup"><span data-stu-id="34200-118">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="34200-119">F6 - Abilita l'impostazione attualmente selezionata</span><span class="sxs-lookup"><span data-stu-id="34200-119">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="34200-120">F7 - Disabilita l'impostazione attualmente selezionata</span><span class="sxs-lookup"><span data-stu-id="34200-120">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="34200-121">F8 - Disabilita tutte le impostazioni nella scheda corrente</span><span class="sxs-lookup"><span data-stu-id="34200-121">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="34200-p103">Premere **F8** per disabilitare tutte le impostazioni prima di configurare qualsiasi valore. La schermata sarà simile a quella seguente:</span><span class="sxs-lookup"><span data-stu-id="34200-p103">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Finestra di dialogo delle proprietà di Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="34200-125">Premere **F6** nell'impostazione della home page e immettere `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="34200-125">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="34200-126">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="34200-126">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="34200-127">Gli utenti possono comunque modificare la home page dopo aver impostato questo criterio.</span><span class="sxs-lookup"><span data-stu-id="34200-127">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="34200-128">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="34200-128">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="34200-129">Windows 10 versione 1511 o successiva</span><span class="sxs-lookup"><span data-stu-id="34200-129">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="34200-130">Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="34200-130">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="34200-131">Passare a **Modelli amministrativi\Componenti di Windows\Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="34200-131">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="34200-132">Fare doppio clic su **Configura pagine iniziali**, impostarlo su **Abilitato** e immettere `https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="34200-132">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="34200-133">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="34200-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="34200-134">Gli utenti non potranno modificare il provider di ricerca dopo aver impostato il criterio.</span><span class="sxs-lookup"><span data-stu-id="34200-134">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="34200-135">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="34200-135">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="34200-136">Windows XP SP2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="34200-136">Windows XP SP2 or later</span></span>

<span data-ttu-id="34200-137">L'articolo del supporto di Windows sulla gestione dei file ADMX e i file ADMX più recenti per le diverse versioni di Windows sono disponibili nel sito del [Supporto tecnico Microsoft](https://support.microsoft.com/it-IT/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="34200-137">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="34200-138">È necessario anche il file di criteri Google più recente, disponibile nella [Guida di Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="34200-138">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="34200-p104">Se le impostazioni descritte in questa sezione non sono disponibili all'interno di GPMC, scaricare il file ADMX appropriato e copiarlo nell'[archivio centrale](https://docs.microsoft.com/it-IT/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). L'archivio centrale nel controller è una cartella conforme alla convenzione di denominazione seguente:</span><span class="sxs-lookup"><span data-stu-id="34200-p104">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="34200-141">**%systemroot%\sysvol\\<dominio\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="34200-141">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="34200-p105">Ogni dominio gestito dal controller deve ottenere una cartella separata. Per copiare il file ADMX dal prompt dei comandi, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="34200-p105">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="34200-144">Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="34200-144">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="34200-145">Verificare che le cartelle seguenti vengono visualizzate nella sezione **Modelli amministrativi** di *Configurazione utente/computer*: Google Chrome e Google Chrome - Impostazioni predefinite (gli utenti possono eseguire l'override).</span><span class="sxs-lookup"><span data-stu-id="34200-145">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="34200-146">Le impostazioni della prima sezione sono fisse e gli amministratori locali non possono modificarle.</span><span class="sxs-lookup"><span data-stu-id="34200-146">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="34200-p106">Le impostazioni dell'ultima sezione dei criteri possono essere modificate dagli utenti nelle impostazioni del browser. È necessario decidere se gli utenti possono eseguire l'override dell'impostazione predefinita. Nella procedura seguente modificare l'impostazione nella cartella corrispondente ai criteri e alle esigenze dell'organizzazione. Nella procedura seguente si usa Google Chrome - Impostazioni predefinite come valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="34200-p106">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="34200-151">Passare a **&lt;Configurazione computer/utente&gt;\Modelli amministrativi\Google Chrome - Impostazioni predefinite\Home page**.</span><span class="sxs-lookup"><span data-stu-id="34200-151">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="34200-152">Fare doppio clic su **Usa la pagina Nuova scheda come Pagina iniziale** e impostarlo su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="34200-152">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="34200-153">Passare a **&lt;Configurazione computer/utente&gt;\Modelli amministrativi\Google Chrome - Impostazioni predefinite\Pagina Nuova scheda**.</span><span class="sxs-lookup"><span data-stu-id="34200-153">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="34200-154">Fare doppio clic su **Configura l'URL della pagina iniziale**, impostarlo su **Abilitato** e immettere `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="34200-154">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="34200-155">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="34200-155">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="34200-156">Gli utenti potranno modificare la home page dopo aver impostato il criterio.</span><span class="sxs-lookup"><span data-stu-id="34200-156">Users will be able to change the home page after this policy is set.</span></span>