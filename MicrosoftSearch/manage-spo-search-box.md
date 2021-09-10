---
title: Gestione della casella di ricerca nei SharePoint siti
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Come personalizzare l'esperienza della casella di ricerca SharePoint siti
ms.openlocfilehash: b5d58dd5a241ccf2ada556c44ec0ea5479ea2e2b
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973787"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>Impostazioni della casella di ricerca SharePoint siti

Uno dei diversi modi Microsoft Search personalizzare i siti di SharePoint è quello di personalizzare il funzionamento della casella di ricerca nella barra di spostamento della famiglia di SharePoint in base alle proprie esigenze.

Per altre opzioni di personalizzazione, [vedere Changing the Microsoft Search results page to add custom verticals, result types and layouts](customize-search-page.md)e [Creating a custom search results page](create-search-results-pages.md).

> [!NOTE]
> La casella di ricerca della barra di spostamento della famiglia di prodotti non è disponibile per tutti i clienti in questo momento, ma queste opzioni possono comunque essere impostate ora e diventeranno effettive quando saranno disponibili.

Per le attività elencate di seguito, si userà PowerShell con SharePoint powershell PnP. Puoi installare e altre informazioni su come iniziare [qui](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Per accedere al sito o alla raccolta siti, utilizzare questo comando:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>Modifica dell'ambito della ricerca

Quando si crea un nuovo sito in SharePoint Online oggi e si digita nella casella di ricerca, viene visualizzata la pagina dei Microsoft Search risultati. Questa pagina mostra i risultati del sito corrente per impostazione predefinita e consente di espandere l'ambito della ricerca all'hub a cui è associato il sito corrente (se presente) o all'intera organizzazione.

L'ambito utilizzato dalla casella di ricerca, per impostazione predefinita, dipende dal tipo di sito.

* La ricerca nei siti regolari viene esequista nel sito corrente.
* I siti hub esere ricercano in tutti i siti nell'hub.
* I siti principali esere ricercano tutto il contenuto.

In alcuni casi, è possibile modificare queste impostazioni predefinite per eseguire sempre la ricerca nell'intera organizzazione o nell'hub a cui è associato un sito, senza bisogno di un ulteriore clic.

In quanto proprietario del sito, è possibile modificare queste impostazioni predefinite utilizzando il comando seguente:

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

Dopo aver eseguito questo comando, il sito che in precedenza mostrava i risultati del sito corrente per impostazione predefinita inizierà a mostrare i risultati dell'intera organizzazione.

Per tornare all'impostazione predefinita, eseguire di nuovo il comando con il valore "DefaultScope". Per eseguire una ricerca nell'hub, usa "Hub" come valore SearchScope.

Questa impostazione si applica a livello di singolo sito. Non esiste un'impostazione equivalente per le raccolte siti.

## <a name="show-or-hide-the-search-box"></a>Mostrare o nascondere la casella di ricerca

È possibile scegliere di nascondere la casella di ricerca della barra di spostamento della famiglia di prodotti se si desidera impedire agli utenti di eseguire ricerche o di utilizzare un'implementazione personalizzata della casella di ricerca.

Per modificare questa impostazione per un determinato sito, utilizzare questo comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

In alternativa, se si desidera impostarlo per tutti i siti di una raccolta siti, è possibile utilizzare questo comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Dopo aver eseguito questi comandi, la casella di ricerca non verrà più visualizzata nella barra di spostamento nella parte superiore della pagina. Per tornare a visualizzare la casella di ricerca, eseguire di nuovo i comandi con il valore fornito al parametro "SearchBoxInNavBar" su "Inherit".

Esistono diversi punti da considerare:

* Questa impostazione si applica solo alla casella di ricerca nella barra di spostamento della famiglia di prodotti. Non si applica alle caselle di ricerca presenti nella pagina o alle caselle di ricerca nelle pagine classiche.

* Dopo aver disabilitato la casella di ricerca nella barra di spostamento, se si desidera utilizzare la funzionalità di ricerca nel sito, sarà necessario fornirla manualmente utilizzando una web part personalizzata o un'estensione SharePoint Framework ricerca.

* Questa soluzione rimuoverà la casella di ricerca anche dagli elenchi e dalle raccolte per il sito. La soluzione di ricerca personalizzata dovrà prendere in considerazione le ricerche contestuali per SharePoint elenchi e raccolte, oltre alla ricerca a livello di sito.

* Se si applica l'impostazione al sito radice del dominio, anche la pagina iniziale SharePoint verrà interrotta la visualizzazione della casella di ricerca.

## <a name="changing-the-hint-displayed-in-the-search-box"></a>Modifica del suggerimento visualizzato nella casella di ricerca

È possibile modificare il suggerimento visualizzato nella casella di ricerca per un determinato sito o raccolta siti. Questo è il testo visualizzato nella casella di ricerca prima che inizino a digitarlo. Ciò può aiutare gli utenti a capire cosa aspettarsi dalla ricerca se è stata configurata una pagina dei risultati personalizzata o se è stato modificato il comportamento della ricerca in altri modi.

> [!NOTE]
> Per poter apportare questa modifica, è necessario consentire l'esecuzione di script personalizzati nel sito in questione come amministratore tenant, operazione non consentita per impostazione predefinita. Per informazioni https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script dettagliate, vedere . È possibile consentire l'esecuzione di script personalizzati, apportare la modifica e quindi ripristinare la disattivazione degli script per il sito, se necessario.

Per modificare questa impostazione per un determinato sito, eseguire il comando seguente:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

In alternativa, se si desidera impostarlo per tutti i siti di una raccolta siti, è possibile utilizzare questo comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

Per tornare al testo segnaposto predefinito, impostare il valore su vuoto ("").