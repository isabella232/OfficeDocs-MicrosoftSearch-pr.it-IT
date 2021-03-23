---
title: Gestione della casella di ricerca nei siti di SharePoint
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Come personalizzare l'esperienza della casella di ricerca nei siti di SharePoint
ms.openlocfilehash: c58e7cf0a47d22fa9c6fd3abd93cc97087625690
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031360"
---
# <a name="search-box-settings-on-sharepoint-sites"></a><span data-ttu-id="cfd39-103">Impostazioni della casella di ricerca nei siti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="cfd39-103">Search box settings on SharePoint sites</span></span>

<span data-ttu-id="cfd39-104">Uno dei diversi modi in cui Microsoft Search può essere personalizzato nei siti di SharePoint è personalizzare il funzionamento della casella di ricerca nella barra di spostamento della famiglia di prodotti nei siti di SharePoint in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="cfd39-104">One of the several ways Microsoft Search can be customized on SharePoint sites is to tailor how the search box in the suite navigation bar works in SharePoint sites to best fit your needs.</span></span>

<span data-ttu-id="cfd39-105">Per altre opzioni di personalizzazione, vedere Modifica della pagina dei risultati di Microsoft Search per aggiungere [verticali,](customize-search-page.md)tipi di risultati e layout personalizzati e [Creazione di una pagina dei risultati di ricerca personalizzata.](create-search-results-pages.md)</span><span class="sxs-lookup"><span data-stu-id="cfd39-105">For other customization options, see [Changing the Microsoft Search results page to add custom verticals, result types and layouts](customize-search-page.md), and [Creating a custom search results page](create-search-results-pages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cfd39-106">La casella di ricerca della barra di spostamento della famiglia di prodotti non è disponibile per tutti i clienti in questo momento, ma queste opzioni possono comunque essere impostate ora e diventeranno effettive quando saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="cfd39-106">The suite navigation bar search box is not available for all customers at this time, but these options can still be set now and they will take effect when it becomes available.</span></span>

<span data-ttu-id="cfd39-107">Per le attività elencate di seguito, si utilizzerà PowerShell con le estensioni di PowerShell PnP di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cfd39-107">For the tasks listed below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="cfd39-108">Puoi installare e altre informazioni su come iniziare [qui](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="cfd39-108">You can install and learn more about how to get started [here](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="cfd39-109">Per accedere al sito o alla raccolta siti, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="cfd39-109">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a><span data-ttu-id="cfd39-110">Modifica dell'ambito della ricerca</span><span class="sxs-lookup"><span data-stu-id="cfd39-110">Changing the scope of search</span></span>

<span data-ttu-id="cfd39-111">Quando si crea un nuovo sito in SharePoint Online oggi e si digita nella casella di ricerca, viene visualizzata la pagina dei risultati di Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="cfd39-111">When you create a new site in SharePoint Online today, and type into the search box, you are taken to the Microsoft Search results page.</span></span> <span data-ttu-id="cfd39-112">Questa pagina mostra i risultati del sito corrente per impostazione predefinita e consente di espandere l'ambito della ricerca fino all'hub a cui è associato il sito corrente (se presente) o all'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cfd39-112">This page shows results from your current site by default and allows you to expand the scope of your search to the hub that the current site is associated with (if there is one), or to the whole organization.</span></span>

<span data-ttu-id="cfd39-113">L'ambito utilizzato dalla casella di ricerca, per impostazione predefinita, dipende dal tipo di sito.</span><span class="sxs-lookup"><span data-stu-id="cfd39-113">The scope the search box uses, by default, depends on type of site.</span></span>

* <span data-ttu-id="cfd39-114">La ricerca nei siti regolari viene esequista nel sito corrente.</span><span class="sxs-lookup"><span data-stu-id="cfd39-114">Regular sites search over the current site.</span></span>
* <span data-ttu-id="cfd39-115">I siti hub esere ricercano in tutti i siti nell'hub.</span><span class="sxs-lookup"><span data-stu-id="cfd39-115">Hub sites search over all sites in the hub.</span></span>
* <span data-ttu-id="cfd39-116">I siti principali esere ricercano tutto il contenuto.</span><span class="sxs-lookup"><span data-stu-id="cfd39-116">Home sites search over all content.</span></span>

<span data-ttu-id="cfd39-117">In alcuni casi, è possibile modificare queste impostazioni predefinite per eseguire sempre la ricerca nell'intera organizzazione o nell'hub a cui è associato un sito, senza bisogno di un ulteriore clic.</span><span class="sxs-lookup"><span data-stu-id="cfd39-117">In some cases, you may want to change these defaults to always search over the whole organization, or across the hub a site is associated with, without needing an additional click.</span></span>

<span data-ttu-id="cfd39-118">In quanto proprietario del sito, è possibile modificare queste impostazioni predefinite utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cfd39-118">As a site owner, you can change these defaults using the following command:</span></span>

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

<span data-ttu-id="cfd39-119">Dopo aver eseguito questo comando, il sito che in precedenza mostrava i risultati del sito corrente per impostazione predefinita inizierà a mostrare i risultati dell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cfd39-119">After running this command, the site that was previously showing results from the current site by default will start to show results from the whole organization.</span></span>

<span data-ttu-id="cfd39-120">Per tornare all'impostazione predefinita, eseguire di nuovo il comando con il valore "DefaultScope".</span><span class="sxs-lookup"><span data-stu-id="cfd39-120">To go back to the default setting, run the command again with the value “DefaultScope".</span></span> <span data-ttu-id="cfd39-121">Per eseguire una ricerca nell'hub, usa "Hub" come valore SearchScope.</span><span class="sxs-lookup"><span data-stu-id="cfd39-121">To search across the Hub, use “Hub” as the SearchScope value.</span></span>

<span data-ttu-id="cfd39-122">Questa impostazione si applica a livello di singolo sito.</span><span class="sxs-lookup"><span data-stu-id="cfd39-122">This setting applies at the individual site level.</span></span> <span data-ttu-id="cfd39-123">Non esiste un'impostazione equivalente per le raccolte siti.</span><span class="sxs-lookup"><span data-stu-id="cfd39-123">There is no equivalent setting for site collections.</span></span>

## <a name="show-or-hide-the-search-box"></a><span data-ttu-id="cfd39-124">Mostrare o nascondere la casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="cfd39-124">Show or hide the search box</span></span>

<span data-ttu-id="cfd39-125">È possibile scegliere di nascondere la casella di ricerca della barra di spostamento della famiglia di prodotti se si desidera impedire agli utenti di eseguire ricerche o di utilizzare un'implementazione personalizzata della casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cfd39-125">You can choose to hide the suite navigation bar search box if you want to prevent your users from searching or to use a custom search box implementation.</span></span>

<span data-ttu-id="cfd39-126">Per modificare questa impostazione per un determinato sito, utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="cfd39-126">To change this setting for a given site use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="cfd39-127">In alternativa, se si desidera impostarlo per tutti i siti di una raccolta siti, è possibile utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="cfd39-127">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="cfd39-128">Dopo aver eseguito questi comandi, la casella di ricerca non verrà più visualizzata nella barra di spostamento nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="cfd39-128">After running these commands, the search box will no longer show up in the navigation bar on top of your page.</span></span> <span data-ttu-id="cfd39-129">Per tornare a visualizzare la casella di ricerca, eseguire di nuovo i comandi con il valore fornito al parametro "SearchBoxInNavBar" su "Inherit".</span><span class="sxs-lookup"><span data-stu-id="cfd39-129">To go back to showing the search box, run the commands again with the value provided to "SearchBoxInNavBar" parameter to “Inherit”.</span></span>

<span data-ttu-id="cfd39-130">Esistono diversi punti da considerare:</span><span class="sxs-lookup"><span data-stu-id="cfd39-130">There are several points to consider:</span></span>

* <span data-ttu-id="cfd39-131">Questa impostazione si applica solo alla casella di ricerca nella barra di spostamento della famiglia di prodotti.</span><span class="sxs-lookup"><span data-stu-id="cfd39-131">This setting only applies to the search box in the suite navigation bar.</span></span> <span data-ttu-id="cfd39-132">Non si applica alle caselle di ricerca presenti nella pagina o alle caselle di ricerca nelle pagine classiche.</span><span class="sxs-lookup"><span data-stu-id="cfd39-132">It does not apply to search boxes that are in the page, or to search boxes on classic pages.</span></span>

* <span data-ttu-id="cfd39-133">Dopo aver disabilitato la casella di ricerca nella barra di spostamento, se si desidera utilizzare la funzionalità di ricerca nel sito, sarà necessario fornirla manualmente utilizzando una web part personalizzata o un'estensione di SharePoint Framework.</span><span class="sxs-lookup"><span data-stu-id="cfd39-133">Once you’ve disabled the search box in the navigation bar, if you want search functionality in your site, you will have to provide it yourself using a custom web part or a SharePoint Framework extension.</span></span>

* <span data-ttu-id="cfd39-134">Questa soluzione rimuoverà la casella di ricerca anche dagli elenchi e dalle raccolte per il sito.</span><span class="sxs-lookup"><span data-stu-id="cfd39-134">This solution will remove the search box from lists and libraries for your site as well.</span></span> <span data-ttu-id="cfd39-135">La soluzione di ricerca personalizzata dovrà prendere in considerazione le ricerche contestuali per elenchi e raccolte di SharePoint, oltre alla ricerca a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="cfd39-135">Your custom search solution will need to consider contextual searches for SharePoint lists and libraries, in addition to site-wide search.</span></span>

* <span data-ttu-id="cfd39-136">Se si applica l'impostazione al sito radice del dominio, anche la pagina iniziale di SharePoint smetterà di visualizzare la casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cfd39-136">If you apply the setting to the root site of your domain, the SharePoint start page will also stop showing the search box.</span></span>

## <a name="changing-the-hint-displayed-in-the-search-box"></a><span data-ttu-id="cfd39-137">Modifica del suggerimento visualizzato nella casella di ricerca</span><span class="sxs-lookup"><span data-stu-id="cfd39-137">Changing the hint displayed in the search box</span></span>

<span data-ttu-id="cfd39-138">È possibile modificare il suggerimento visualizzato nella casella di ricerca per un determinato sito o raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="cfd39-138">You can change the hint the search box shows for a given site or site collection.</span></span> <span data-ttu-id="cfd39-139">Questo è il testo visualizzato nella casella di ricerca prima che inizino a digitarlo.</span><span class="sxs-lookup"><span data-stu-id="cfd39-139">This is the text that appears in the search box before they start typing into it.</span></span> <span data-ttu-id="cfd39-140">Ciò può aiutare gli utenti a capire cosa aspettarsi dalla ricerca se è stata configurata una pagina dei risultati personalizzata o se è stato modificato il comportamento della ricerca in altri modi.</span><span class="sxs-lookup"><span data-stu-id="cfd39-140">This may help guide your users about what to expect from search if you’ve configured a custom results page or changed behavior of search in other ways.</span></span>

> [!NOTE]
> <span data-ttu-id="cfd39-141">Per poter apportare questa modifica, è necessario consentire l'esecuzione di script personalizzati nel sito in questione come amministratore tenant, operazione non consentita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cfd39-141">To be able to make this change, you need to allow running custom scripts on the site in question as a tenant administrator, which is disallowed by default.</span></span> <span data-ttu-id="cfd39-142">Per informazioni https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script dettagliate, vedere .</span><span class="sxs-lookup"><span data-stu-id="cfd39-142">Please see https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script for details.</span></span> <span data-ttu-id="cfd39-143">È possibile consentire l'esecuzione di script personalizzati, apportare la modifica e quindi ripristinare la disattivazione degli script per il sito, se necessario.</span><span class="sxs-lookup"><span data-stu-id="cfd39-143">You can allow running custom scripts, make the change, and then revert to disallowing scripts for the site if necessary.</span></span>

<span data-ttu-id="cfd39-144">Per modificare questa impostazione per un determinato sito, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cfd39-144">To change this setting for a given site run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="cfd39-145">In alternativa, se si desidera impostarlo per tutti i siti di una raccolta siti, è possibile utilizzare questo comando:</span><span class="sxs-lookup"><span data-stu-id="cfd39-145">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="cfd39-146">Per tornare al testo segnaposto predefinito, impostare il valore su vuoto ("").</span><span class="sxs-lookup"><span data-stu-id="cfd39-146">To go back to the default placeholder text, set the value to be blank ("").</span></span>