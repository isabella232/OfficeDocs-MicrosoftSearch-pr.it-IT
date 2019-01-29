---
title: Impostare la pagina iniziale predefinita
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
description: Informazioni su come impostare Bing come la home page predefinita per la propria azienda con Microsoft Search.
ms.openlocfilehash: db0611ebd7f4a8344664825bbb42025f3bb36486
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612490"
---
# <a name="set-default-homepage"></a><span data-ttu-id="e0a39-103">Impostare la pagina iniziale predefinita</span><span class="sxs-lookup"><span data-stu-id="e0a39-103">Set default homepage</span></span>

<span data-ttu-id="e0a39-104">Configurazione il browser predefinito, motore di ricerca predefinito e home page predefinita consente agli utenti individuare funzionalità Microsoft Search, incoraggiare altri dati di utilizzo e offrire un'esperienza più uniforme.</span><span class="sxs-lookup"><span data-stu-id="e0a39-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="e0a39-105">Per impostare la home page predefinita per l'organizzazione, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e0a39-105">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="e0a39-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="e0a39-106">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="e0a39-107">Internet Explorer 5.0 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="e0a39-107">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="e0a39-108">Aprire la Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="e0a39-108">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="e0a39-109">Passare alle **impostazioni di Windows\Manutenzione pannello Configuration\Preferences\Control dell'utente**.</span><span class="sxs-lookup"><span data-stu-id="e0a39-109">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="e0a39-110">Fare clic su **Impostazioni di Internet** e selezionare **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="e0a39-110">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e0a39-111">È necessario selezionare l'opzione di Internet Explorer 10 per applicare le impostazioni di Internet Explorer 11 come applicano le stesse impostazioni di Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="e0a39-111">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="e0a39-p101">Non sono configurate impostazioni che sono sottolineate in rosso al computer di destinazione, mentre sottolineato verde vengono configurate in computer di destinazione. Per cambiare il carattere di sottolineatura, utilizzare i tasti funzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0a39-p101">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="e0a39-114">F5 - Abilita tutte le impostazioni nella scheda corrente</span><span class="sxs-lookup"><span data-stu-id="e0a39-114">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="e0a39-115">F6 - Abilita l'impostazione corrente selezionata</span><span class="sxs-lookup"><span data-stu-id="e0a39-115">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="e0a39-116">F7 - disattiva l'impostazione corrente selezionata</span><span class="sxs-lookup"><span data-stu-id="e0a39-116">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="e0a39-117">F8 - disabilitare tutte le impostazioni nella scheda corrente</span><span class="sxs-lookup"><span data-stu-id="e0a39-117">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="e0a39-p102">Premere **F8** per disabilitare tutte le impostazioni prima di configurare qualsiasi operazione. La schermata dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e0a39-p102">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Finestra di dialogo Proprietà Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="e0a39-121">Premere **F6** l'impostazione della Home page, quindi immettere`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="e0a39-121">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="e0a39-122">Applicare criteri risultante tramite il collegamento al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="e0a39-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e0a39-123">Gli utenti possono comunque modificare la home page dopo che questo criterio è impostato.</span><span class="sxs-lookup"><span data-stu-id="e0a39-123">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="e0a39-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e0a39-124">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="e0a39-125">Windows 10, 1511 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="e0a39-125">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="e0a39-126">Aprire la Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="e0a39-126">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="e0a39-127">Passare a **amministrazione amministrativi\Componenti Components\Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="e0a39-127">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="e0a39-128">Fare doppio clic su **pagine configurazione iniziali**, impostato su **attivato**e immettere`https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="e0a39-128">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="e0a39-129">Applicare criteri risultante tramite il collegamento al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="e0a39-129">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="e0a39-130">Gli utenti saranno in grado di modificare il provider di ricerca dopo che questo criterio è impostato.</span><span class="sxs-lookup"><span data-stu-id="e0a39-130">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="e0a39-131">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="e0a39-131">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="e0a39-132">Windows XP SP2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="e0a39-132">Windows XP SP2 or later</span></span>

<span data-ttu-id="e0a39-133">Articolo del supporto tecnico di Windows sulla gestione dei file ADMX e i file ADMX più recenti per diverse versioni di Windows sono disponibili [nel supporto tecnico clienti Microsoft](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="e0a39-133">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="e0a39-134">È inoltre necessario il file criteri più recente di Google, che è possibile trovare nella [Guida di Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="e0a39-134">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="e0a39-p103">Se le impostazioni descritte in questa sezione non viene trovate all'interno di GPMC, scaricare ADMX appropriato e copiarli nell' [archivio centrale](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Archivio centrale sul controller è una cartella con la convenzione di denominazione seguente:</span><span class="sxs-lookup"><span data-stu-id="e0a39-p103">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="e0a39-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="e0a39-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="e0a39-p104">Ogni dominio i punti di manipolazione di controller devono ottenere una cartella separata. Può utilizzare il comando seguente per copiare il file ADMX al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="e0a39-p104">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="e0a39-140">Aprire la Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="e0a39-140">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="e0a39-141">Verificare che le cartelle seguenti vengono visualizzati nella sezione **Modelli amministrativi** di entrambe *Configurazione utente/Computer*: Google Chrome e Google Chrome - impostazioni predefinite (gli utenti possono ignorare).</span><span class="sxs-lookup"><span data-stu-id="e0a39-141">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="e0a39-142">Le impostazioni della prima sezione risolti e l'amministratore locale non è possibile modificarli.</span><span class="sxs-lookup"><span data-stu-id="e0a39-142">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="e0a39-p105">Le impostazioni di quest'ultima sezione dei criteri possono essere modificate da utenti nelle impostazioni del browser. È necessario stabilire se gli utenti possono ignorare l'impostazione predefinita. Nei passaggi seguenti, modificare l'impostazione nella cartella che corrisponde ai criteri dell'organizzazione e alle esigenze. La procedura seguente utilizza Google Chrome - impostazioni predefinite come predefinito.</span><span class="sxs-lookup"><span data-stu-id="e0a39-p105">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="e0a39-147">Passare a \*\* &lt;configurazione Computer/utente&gt;\Administrative Templates\Google Chrome - pagina predefinita Settings\Home\*\*.</span><span class="sxs-lookup"><span data-stu-id="e0a39-147">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="e0a39-148">Fare doppio clic su **Usa nuova scheda pagina come home page**e impostarla su **attivato**.</span><span class="sxs-lookup"><span data-stu-id="e0a39-148">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="e0a39-149">Passare a \*\* &lt;configurazione Computer/utente&gt;\Administrative Templates\Google Chrome - predefinito Settings\New scheda pagina\*\*.</span><span class="sxs-lookup"><span data-stu-id="e0a39-149">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="e0a39-150">Fare doppio clic su **Configura l'URL della pagina nuova scheda**, impostato su **attivato**e immettere`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="e0a39-150">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="e0a39-151">Applicare criteri risultante tramite il collegamento al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="e0a39-151">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="e0a39-152">Gli utenti saranno in grado di modificare la home page dopo che questo criterio è impostato.</span><span class="sxs-lookup"><span data-stu-id="e0a39-152">Users will be able to change the home page after this policy is set.</span></span>