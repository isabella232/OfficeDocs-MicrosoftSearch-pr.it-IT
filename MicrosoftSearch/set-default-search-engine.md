---
title: Motore di ricerca set predefinito
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Informazioni su come impostare Bing come motore di ricerca predefinito dell'azienda tramite Microsoft Search.
ms.openlocfilehash: 1102c4c58b1e46e450276430a1e79b34964b4ad4
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378903"
---
# <a name="set-default-search-engine"></a><span data-ttu-id="a0fb2-103">Motore di ricerca set predefinito</span><span class="sxs-lookup"><span data-stu-id="a0fb2-103">Set default search engine</span></span>

<span data-ttu-id="a0fb2-104">Configurazione il browser predefinito, motore di ricerca predefinito e home page predefinita consente agli utenti individuare funzionalità Microsoft Search, incoraggiare altri dati di utilizzo e offrire un'esperienza più uniforme.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="a0fb2-105">Per impostare il motore di ricerca predefinito per l'organizzazione, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-105">To set the default search engine for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="a0fb2-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="a0fb2-106">Internet Explorer</span></span>

### <a name="internet-explorer-11"></a><span data-ttu-id="a0fb2-107">Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="a0fb2-107">Internet Explorer 11</span></span>

<span data-ttu-id="a0fb2-108">Gli utenti saranno in grado di modificare il provider di ricerca dopo che questo criterio è impostato.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-108">Users will be able to change the search provider after this policy is set.</span></span>
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="a0fb2-109">1. configurare il computer locale che verrà utilizzato per impostare l'oggetto Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="a0fb2-109">1. Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="a0fb2-110">Incollare il testo seguente in un registro di sistema (\*con estensione reg) file.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-110">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="a0fb2-111">Windows Registry Editor Version 5.00</span><span class="sxs-lookup"><span data-stu-id="a0fb2-111">Windows Registry Editor Version 5.00</span></span>
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"SuggestionsURL_JSON"="https://business.ing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA"
"ShowSearchSuggestions"=dword:00000001
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
<span data-ttu-id="a0fb2-p101">Fare doppio clic sul file creato ed eseguire la procedura per importare il file. Eseguire correttamente l'importazione deve risultare nella finestra di dialogo seguente:</span><span class="sxs-lookup"><span data-stu-id="a0fb2-p101">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![Messaggio importazione completata Editor del Registro di sistema](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="a0fb2-115">2. aprire la Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo</span><span class="sxs-lookup"><span data-stu-id="a0fb2-115">2. Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="a0fb2-116">Passare a **impostazioni utente Configuration\Policies\Preferences\Windows**.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-116">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="a0fb2-p102">Pulsante destro del mouse su **Registry\New** e selezionare **Creazione guidata del Registro di sistema**. Dalla finestra del Browser del Registro di sistema, selezionare **Computer locale** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-p102">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
3. <span data-ttu-id="a0fb2-119">Passare a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-119">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
    
4. <span data-ttu-id="a0fb2-120">Da questa chiave, assicurarsi di selezionare DefaultScope.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-120">From this key, make sure to select DefaultScope.</span></span>
    
    ![Browser del Registro di sistema con DefaultScope selezionata](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. <span data-ttu-id="a0fb2-p103">Verificare tutte le chiavi sub contenente il GUID di Microsoft Search Bing e ogni valore nella chiave, ad eccezione di qualsiasi percorso ai profili utente. Scorrere verso il basso per selezionare altri elementi.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-p103">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
    
    ![Browser del Registro di sistema con altri valori selezionati](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. <span data-ttu-id="a0fb2-125">Fare clic su Fine per completare questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-125">Click Finish to complete this configuration.</span></span>
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="a0fb2-126">3. configurare le preferenze dell'utente per semplificare l'eliminazione di un messaggio di avviso che all'utente che venga visualizzato quando viene applicato DefaultScope ricerca</span><span class="sxs-lookup"><span data-stu-id="a0fb2-126">3. Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="a0fb2-127">È per impostazione predefinita un avviso che informa gli utenti di un programma tenta di modificare le relative impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-127">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="a0fb2-128">Nell'oggetto Criteri di gruppo stesso, fare clic con il pulsante destro su **Registry\New** e selezionare **Creazione guidata del Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-128">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
    
2. <span data-ttu-id="a0fb2-129">Passare a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User preferenze**.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-129">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
    
3. <span data-ttu-id="a0fb2-130">Selezionare la chiave **Delle preferenze utente** .</span><span class="sxs-lookup"><span data-stu-id="a0fb2-130">Select the **User Preference** key.</span></span>
    
4. <span data-ttu-id="a0fb2-131">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-131">Click **Finish**.</span></span>
    
5. <span data-ttu-id="a0fb2-p104">Fare clic sull'oggetto appena creato. Nel riquadro di destra fare doppio clic sull'oggetto preferenze utente, modificare l' **azione** **Elimina**e salvare.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-p104">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
    
<span data-ttu-id="a0fb2-134">Applicare criteri risultante tramite il collegamento al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-134">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
  
## <a name="microsoft-edge"></a><span data-ttu-id="a0fb2-135">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a0fb2-135">Microsoft Edge</span></span>

### <a name="windows-10-version-1703-or-later"></a><span data-ttu-id="a0fb2-136">Windows 10 1703 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="a0fb2-136">Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="a0fb2-137">Gli utenti saranno in grado di modificare il provider di ricerca dopo che questo criterio è impostato.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-137">Users will be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="a0fb2-138">Per i file ADMX più recenti per diverse versioni di Windows, vedere [come creare e gestire l'archivio centrale per i modelli amministrativi di criteri di gruppo in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="a0fb2-138">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="a0fb2-p105">Se l'impostazione descritta in questa sezione non viene trovato all'interno di GPMC, scaricare ADMX appropriato e copiarli nell'archivio centrale. Per ulteriori informazioni, vedere [File ADMX utilizzando oggetti Criteri di gruppo di modifica](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Archivio centrale sul controller è una cartella con la convenzione di denominazione seguente:</span><span class="sxs-lookup"><span data-stu-id="a0fb2-p105">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="a0fb2-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="a0fb2-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="a0fb2-p106">Ogni dominio che gestisce il controller di utilizzare una cartella separata. Può utilizzare il comando seguente per copiare il file ADMX al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="a0fb2-p106">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="a0fb2-145">Aprire la Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-145">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="a0fb2-146">Passare a \*\* &lt;configurazione Computer/utente&gt;\Administrative Templates\Windows Components\Microsoft Edge\*\*.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-146">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
    
1. <span data-ttu-id="a0fb2-147">Fare doppio clic su **Imposta motore di ricerca predefinito**, impostato su **attivato**e immettere`https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="a0fb2-147">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
    
3. <span data-ttu-id="a0fb2-148">Applicare criteri risultante tramite il collegamento al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-148">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
## <a name="google-chrome"></a><span data-ttu-id="a0fb2-149">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="a0fb2-149">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="a0fb2-150">Windows XP SP2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="a0fb2-150">Windows XP SP2 or later</span></span>

<span data-ttu-id="a0fb2-151">Gli utenti saranno in grado di modificare il provider di ricerca dopo che questo criterio è impostato.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-151">Users won't be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="a0fb2-p107">Chrome dotato di un proprio set di criteri di gruppo che possono essere scaricati nel formato di file ADMX da [Google Chrome Enterprise Guida](https://support.google.com/chrome/a/answer/187202). Se del sistema operativo Windows Vista/Server 2008 o versione successiva vengono utilizzati per la gestione dell'oggetto Criteri di gruppo per il dominio, il file ADMX fornito in questo pacchetto si occupa di impostazioni di Chrome in Windows XP SP2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-p107">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). If operating systems Windows Vista/Server 2008 or later are used to manage GPO's for the domain, the ADMX file provided in this package takes care of Chrome settings on Windows XP SP2 or later.</span></span>
  
<span data-ttu-id="a0fb2-p108">Copiare il file di modello in un archivio centrale dei file ADMX sui controller di dominio. Per ulteriori informazioni, vedere [File ADMX utilizzando oggetti Criteri di gruppo di modifica](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Archivio centrale sul controller è una cartella con la convenzione di denominazione seguente:</span><span class="sxs-lookup"><span data-stu-id="a0fb2-p108">Copy the template file to a central store for ADMX files on the domain controller. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="a0fb2-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="a0fb2-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="a0fb2-p109">Ogni dominio che gestisce il controller di utilizzare una cartella separata. Può utilizzare il comando seguente per copiare il file ADMX al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="a0fb2-p109">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="a0fb2-160">Aprire la Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-160">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="a0fb2-161">Verificare che le cartelle seguenti vengono visualizzati nella sezione Modelli amministrativi di entrambe configurazione utente/Computer: Google Chrome e Google Chrome - impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-161">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>
    
  - <span data-ttu-id="a0fb2-162">Le impostazioni della prima sezione risolti e administrators locale non è possibile modificarli nel browser.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-162">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    
  - <span data-ttu-id="a0fb2-163">Le impostazioni di quest'ultima sezione dei criteri possono essere modificate da utenti nelle impostazioni del browser.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-163">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>
    
3. <span data-ttu-id="a0fb2-164">Passare a \*\* \<Computer/utente\> Configurazione utente\Modelli Templates\Google Chrome\Default provider di ricerca\*\*</span><span class="sxs-lookup"><span data-stu-id="a0fb2-164">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
    
4. <span data-ttu-id="a0fb2-165">Fare doppio clic su **Abilita il provider di ricerca predefinito**e impostarla su **attivato**.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-165">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="a0fb2-166">Fare doppio clic **sull'icona di ricerca del provider predefinito**, impostato su **attivato**e immettere`https://www.bing.com/sa/simg/bb.ico`</span><span class="sxs-lookup"><span data-stu-id="a0fb2-166">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
    
6. <span data-ttu-id="a0fb2-167">Fare doppio clic su **URL immediato del provider di ricerca predefinito**e immettere`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="a0fb2-167">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
7. <span data-ttu-id="a0fb2-168">Fare doppio clic sul **nome del provider di ricerca predefinito**, impostato su attivato e immettere 'Microsoft Search in Bing'</span><span class="sxs-lookup"><span data-stu-id="a0fb2-168">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
    
8. <span data-ttu-id="a0fb2-169">Fare doppio clic su **URL di ricerca del provider di ricerca predefinito**, impostato su **attivato**e immettere`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="a0fb2-169">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
9. <span data-ttu-id="a0fb2-170">Fare doppio clic su **provider di ricerca predefinito suggerire URL**, impostato su **attivato**e immettere`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span><span class="sxs-lookup"><span data-stu-id="a0fb2-170">Double-click **Default search provider suggest URL**, set it to **Enabled**, and enter `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span></span>
    
10. <span data-ttu-id="a0fb2-171">Applicare criteri risultante tramite il collegamento al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-171">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="a0fb2-p110">L'impostazione motore di ricerca predefinito verrà aggiunto la funzionalità di suggerimenti di ricerca Microsoft Search nella barra degli indirizzi del browser. Attualmente, supporta solo i segnalibri. Gli utenti vedranno i suggerimenti due segnalibro principali sopra suggerimenti web pubblici durante la digitazione nella barra degli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="a0fb2-p110">Setting the default search engine will add the Microsoft Search search suggestions feature in the browser address bar. Currently, this supports bookmarks only. Users will see the top two bookmark suggestions above public web suggestions as they type in the address bar.</span></span>