---
title: Impostare il motore di ricerca predefinito
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
ROBOTS: NOINDEX
description: Informazioni su come impostare Bing come motore di ricerca predefinito dell'organizzazione con Microsoft Search.
ms.openlocfilehash: cc03e3aa280ea621702ce99c2cc8eb530b310251
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639839"
---
# <a name="make-bing-the-default-search-engine"></a><span data-ttu-id="15eae-103">Impostare Bing come motore di ricerca predefinito</span><span class="sxs-lookup"><span data-stu-id="15eae-103">Make Bing the default search engine</span></span>
  
<span data-ttu-id="15eae-104">Questo articolo spiega come impostare Bing come motore di ricerca predefinito per Microsoft Edge, Google Chrome e Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="15eae-104">This article explains how to make Bing the default search engine for Microsoft Edge, Google Chrome, and Internet Explorer.</span></span> 
  
## <a name="microsoft-edge-on-windows-10-version-1703-or-later"></a><span data-ttu-id="15eae-105">Microsoft Edge in Windows 10 versione 1703 o successiva</span><span class="sxs-lookup"><span data-stu-id="15eae-105">Microsoft Edge on Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="15eae-106">Anche se si imposta Bing come motore di ricerca predefinito, Microsoft Edge consente agli utenti di modificare le impostazioni per usare un altro motore di ricerca.</span><span class="sxs-lookup"><span data-stu-id="15eae-106">Although you'll set Bing as the default search engine, Microsoft Edge allows users to change their settings to use a different search engine.</span></span>
  
<span data-ttu-id="15eae-107">Per i file ADMX più recenti per varie versioni di Windows, vedere [Come creare e gestire l'archivio centrale per i modelli amministrativi di Criteri di gruppo in Windows](https://support.microsoft.com/it-IT/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="15eae-107">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="15eae-p101">Se l'impostazione descritta in questa sezione non è disponibile all'interno di GPMC, scaricare il file ADMX appropriato e copiarlo nell'archivio centrale. Per altre informazioni, vedere [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/it-IT/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29) (Modifica di oggetti Criteri di gruppo basati su dominio con i file ADMX). L'archivio centrale sul controller è una cartella con la convenzione di denominazione seguente:</span><span class="sxs-lookup"><span data-stu-id="15eae-p101">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="15eae-111">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="15eae-111">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="15eae-p102">Ogni dominio gestito dal controller deve ottenere una cartella separata. Per copiare il file ADMX dal prompt dei comandi, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="15eae-p102">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="15eae-114">Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="15eae-114">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="15eae-115">Passare a **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="15eae-115">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
    
1. <span data-ttu-id="15eae-116">Fare doppio clic su **Imposta motore di ricerca predefinito**, impostare su **Abilitato** e immettere `https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="15eae-116">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
    
3. <span data-ttu-id="15eae-117">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="15eae-117">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>


## <a name="google-chrome-on-windows-xp-sp2-or-later"></a><span data-ttu-id="15eae-118">Google Chrome in Windows XP SP2 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="15eae-118">Google Chrome on Windows XP SP2 or later</span></span>

<span data-ttu-id="15eae-119">Gli utenti non potranno modificare il motore di ricerca predefinito dopo aver impostato il criterio.</span><span class="sxs-lookup"><span data-stu-id="15eae-119">Users won't be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="15eae-p103">Chrome include un proprio set di impostazioni di criteri di gruppo, scaricabile sotto forma di file ADMX dalla [Guida di Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202). Se si usano i sistemi operativi Windows Vista/Server 2008 o versioni successive per gestire gli oggetti Criteri di gruppo per il dominio, il file ADMX fornito in questo pacchetto si occupa delle impostazioni di Chrome in Windows XP SP2 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="15eae-p103">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). If operating systems Windows Vista/Server 2008 or later are used to manage GPO's for the domain, the ADMX file provided in this package takes care of Chrome settings on Windows XP SP2 or later.</span></span>
  
<span data-ttu-id="15eae-p104">Copiare il file modello in un archivio centrale per i file ADMX nel controller di dominio. Per altre informazioni, vedere [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/it-IT/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29) (Modifica di oggetti Criteri di gruppo basati su dominio con i file ADMX). L'archivio centrale sul controller è una cartella con la convenzione di denominazione seguente:</span><span class="sxs-lookup"><span data-stu-id="15eae-p104">Copy the template file to a central store for ADMX files on the domain controller. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="15eae-125">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="15eae-125">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="15eae-p105">Ogni dominio gestito dal controller deve ottenere una cartella separata. Per copiare il file ADMX dal prompt dei comandi, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="15eae-p105">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="15eae-128">Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="15eae-128">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="15eae-129">Verificare che le cartelle seguenti vengono visualizzate nella sezione Modelli amministrativi di Configurazione utente/computer: Google Chrome e Google Chrome - Impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="15eae-129">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>
    
  - <span data-ttu-id="15eae-130">Le impostazioni della prima sezione sono fisse e gli amministratori non possono modificarle nel browser.</span><span class="sxs-lookup"><span data-stu-id="15eae-130">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    
  - <span data-ttu-id="15eae-131">Le impostazioni della seconda sezione di criteri possono essere modificate dagli utenti nelle impostazioni del browser.</span><span class="sxs-lookup"><span data-stu-id="15eae-131">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>
    
3. <span data-ttu-id="15eae-132">Passare a **\<Computer/Utente\> Configurazione\Modelli amministrativi\Google Chrome\Motore di ricerca predefinito**</span><span class="sxs-lookup"><span data-stu-id="15eae-132">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
    
4. <span data-ttu-id="15eae-133">Fare doppio clic su **Enable the default search provider** (Abilita il motore di ricerca predefinito) e impostarlo su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="15eae-133">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="15eae-134">Fare doppio clic sull'**icona del motore di ricerca predefinito**, impostarla su **Abilitato** e immettere `https://www.bing.com/sa/simg/bb.ico`</span><span class="sxs-lookup"><span data-stu-id="15eae-134">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
    
6. <span data-ttu-id="15eae-135">Fare doppio clic sull'**URL immediato del motore di ricerca predefinito** e immettere `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="15eae-135">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
7. <span data-ttu-id="15eae-136">Fare doppio clic sul **nome del motore di ricerca predefinito**, impostarlo su Abilitato e immettere "Microsoft Search in Bing"</span><span class="sxs-lookup"><span data-stu-id="15eae-136">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
    
8. <span data-ttu-id="15eae-137">Fare doppio clic sull'**URL del servizio di ricerca del motore predefinito**, impostarlo su **Abilitato** e immettere `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="15eae-137">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
9. <span data-ttu-id="15eae-138">Fare doppio clic sull'**URL di suggerimento del motore di ricerca predefinito**, impostarlo su **Abilitato** e immettere `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span><span class="sxs-lookup"><span data-stu-id="15eae-138">Double-click **Default search provider suggest URL**, set it to **Enabled**, and enter `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span></span>
    
10. <span data-ttu-id="15eae-139">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="15eae-139">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="15eae-p106">L'impostazione del motore di ricerca predefinito aggiunge la funzione dei suggerimenti per la ricerca di Microsoft Search nella barra degli indirizzi del browser. Attualmente, sono supportati solo i segnalibri. Gli utenti vedranno i primi due suggerimenti di segnalibri sopra i suggerimenti del Web pubblico mentre digitano nella barra degli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="15eae-p106">Setting the default search engine will add the Microsoft Search search suggestions feature in the browser address bar. Currently, this supports bookmarks only. Users will see the top two bookmark suggestions above public web suggestions as they type in the address bar.</span></span>

## <a name="internet-explorer-11-or-later"></a><span data-ttu-id="15eae-143">Internet Explorer 11 o versioni successive</span><span class="sxs-lookup"><span data-stu-id="15eae-143">Internet Explorer 11 or later versions</span></span>

<span data-ttu-id="15eae-144">Gli utenti potranno modificare il provider di ricerca dopo aver impostato il criterio.</span><span class="sxs-lookup"><span data-stu-id="15eae-144">Users will be able to change the search provider after this policy is set.</span></span>
  
### <a name="step-1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="15eae-145">Passaggio 1:</span><span class="sxs-lookup"><span data-stu-id="15eae-145">Step 1</span></span> <span data-ttu-id="15eae-146">Configurare il computer locale che verrà utilizzato per impostare l'oggetto Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="15eae-146">Configure the local machine that will be used to set the GPO.</span></span>

<span data-ttu-id="15eae-147">Incollare il testo seguente in un file reg(\*.reg).</span><span class="sxs-lookup"><span data-stu-id="15eae-147">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="15eae-148">Editor del Registro di sistema di Windows, versione 5.00</span><span class="sxs-lookup"><span data-stu-id="15eae-148">Windows Registry Editor Version 5.00</span></span>
  
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
  
<span data-ttu-id="15eae-p108">Fare doppio clic sul file creato e seguire la procedura per importare il file. Dopo la corretta importazione, dovrebbe essere visualizzato il seguente messaggio:</span><span class="sxs-lookup"><span data-stu-id="15eae-p108">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![Messaggio importazione completata dell'Editor del Registro di sistema](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
### <a name="step-2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="15eae-152">Passaggio 2:</span><span class="sxs-lookup"><span data-stu-id="15eae-152">Step 2</span></span> <span data-ttu-id="15eae-153">Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo</span><span class="sxs-lookup"><span data-stu-id="15eae-153">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>

1. <span data-ttu-id="15eae-154">Passare a **Configurazione utente\Criteri\Preferenze\Impostazioni Windows**.</span><span class="sxs-lookup"><span data-stu-id="15eae-154">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="15eae-p110">Fare clic con il pulsante destro del mouse su **Registro\Nuovo** e selezionare **Creazione guidata Registro di sistema**. Dalla finestra Visualizzatore Registro di sistema, selezionare **Computer locale** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="15eae-p110">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
3. <span data-ttu-id="15eae-157">Passare a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span><span class="sxs-lookup"><span data-stu-id="15eae-157">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
    
4. <span data-ttu-id="15eae-158">Da questa chiave, assicurarsi di selezionare DefaultScope.</span><span class="sxs-lookup"><span data-stu-id="15eae-158">From this key, make sure to select DefaultScope.</span></span>
    
    ![Visualizzatore Registro di sistema con DefaultScope selezionato](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. <span data-ttu-id="15eae-p111">Selezionare tutte le sottochiavi che contengono il GUID di Microsoft Search in Bing e ogni valore della chiave, ad eccezione dei percorsi per i profili utente. Scorrere verso il basso per selezionare altri elementi.</span><span class="sxs-lookup"><span data-stu-id="15eae-p111">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
    
    ![Visualizzatore Registro di sistema con valori aggiuntivi selezionati](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. <span data-ttu-id="15eae-163">Fare clic su Fine per completare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="15eae-163">Click Finish to complete this configuration.</span></span>
    
### <a name="step-3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="15eae-164">Passaggio 3:</span><span class="sxs-lookup"><span data-stu-id="15eae-164">Step 3</span></span> <span data-ttu-id="15eae-165">Impostare le Preferenze utente per eliminare un avviso che l'utente può ricevere quando viene applicata la ricerca di DefaultScope.</span><span class="sxs-lookup"><span data-stu-id="15eae-165">3. Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="15eae-166">Questo avviso viene inviato per impostazione predefinita e avverte gli utenti che un programma sta provando a modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="15eae-166">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="15eae-167">Nello stesso oggetto Criteri di gruppo, fare clic con il pulsante destro del mouse su **Registro\Nuovo** e selezionare **Creazione guidata Registro di sistema**.</span><span class="sxs-lookup"><span data-stu-id="15eae-167">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
    
2. <span data-ttu-id="15eae-168">Passare a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span><span class="sxs-lookup"><span data-stu-id="15eae-168">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
    
3. <span data-ttu-id="15eae-169">Selezionare la chiave **Preferenza utente**.</span><span class="sxs-lookup"><span data-stu-id="15eae-169">Select the **User Preference** key.</span></span>
    
4. <span data-ttu-id="15eae-170">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="15eae-170">Click **Finish**.</span></span>
    
5. <span data-ttu-id="15eae-p113">Fare clic sull'oggetto appena creato. Nel riquadro a destra, fare doppio clic sull'oggetto User Preferences, cambiare l'**azione** in **Delete and Save** (Elimina e salva).</span><span class="sxs-lookup"><span data-stu-id="15eae-p113">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
1. <span data-ttu-id="15eae-173">Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.</span><span class="sxs-lookup"><span data-stu-id="15eae-173">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>