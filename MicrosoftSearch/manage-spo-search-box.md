---
title: Gestione della casella di ricerca in siti di SharePoint
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
ms.openlocfilehash: 6ebd084aadb38acb5475b7e43d7c4092ffc09eb8
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700965"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>Impostazioni della casella di ricerca nei siti di SharePoint

Uno dei diversi modi in cui Microsoft Search può essere personalizzato sui siti di SharePoint è adattare la modalità di utilizzo della casella di ricerca nella barra di spostamento della famiglia in siti di SharePoint per soddisfare al meglio le proprie esigenze.

Per altre opzioni di personalizzazione, vedere [modifica della pagina dei risultati di ricerca di Microsoft per aggiungere verticali, tipi di risultati e layout personalizzati](customize-search-page.md)e [creazione di una pagina dei risultati di ricerca personalizzata](create-search-results-pages.md).

> [!NOTE]
> La casella di ricerca della barra di spostamento Suite non è disponibile per tutti i clienti in questo momento, ma queste opzioni possono ancora essere impostate e diventeranno effettive quando saranno disponibili.

Per le attività elencate di seguito, si utilizzerà PowerShell con le estensioni di PowerShell di SharePoint PnP. È possibile installare e scoprire altre informazioni su come [iniziare.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps) Si eseguirà l'accesso al sito o alla raccolta siti utilizzando il comando seguente:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>Modifica dell'ambito della ricerca

Quando si crea un nuovo sito in SharePoint Online oggi e si digita la casella di ricerca, si viene reindirizzati alla pagina dei risultati di ricerca di Microsoft. Questa pagina Visualizza i risultati del sito corrente per impostazione predefinita e consente di espandere l'ambito della ricerca all'hub a cui è associato il sito corrente (se presente) o all'intera organizzazione.

Per impostazione predefinita, l'ambito utilizzato per la casella di ricerca dipende dal tipo di sito.

* Ricerca di siti regolari nel sito corrente.
* I siti hub vengono ricercati in tutti i siti dell'hub.
* Home sites Cerca su tutto il contenuto.

In alcuni casi, è possibile modificare queste impostazioni predefinite per eseguire sempre una ricerca nell'intera organizzazione o nell'hub a cui è associato un sito, senza che sia necessario un ulteriore clic.

Come proprietario di un sito, è possibile modificare queste impostazioni predefinite utilizzando il seguente comando:

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

Dopo l'esecuzione di questo comando, il sito che in precedenza stava mostrando i risultati del sito corrente per impostazione predefinita inizierà a mostrare i risultati dell'intera organizzazione.

Per tornare all'impostazione predefinita, eseguire di nuovo il comando con il valore "DefaultScope". Per eseguire una ricerca nell'hub, utilizzare "hub" come valore SearchScope.

Questa impostazione si applica a livello di singolo sito. Non esistono impostazioni equivalenti per le raccolte siti.

## <a name="show-or-hide-the-search-box"></a>Mostrare o nascondere la casella di ricerca

Se si desidera impedire agli utenti di eseguire la ricerca o l'utilizzo di un'implementazione di una casella di ricerca personalizzata, è possibile scegliere di nascondere la casella di ricerca della barra di spostamento del gruppo.

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

Dopo aver eseguito questi comandi, la casella di ricerca non verrà più visualizzata nella barra di spostamento nella parte superiore della pagina. Per tornare a visualizzare la casella di ricerca, eseguire di nuovo i comandi con il valore fornito al parametro "SearchBoxInNavBar" su "inherit".

Sono disponibili diversi punti da prendere in considerazione:

* Questa impostazione si applica solo alla casella di ricerca nella barra di spostamento della famiglia di prodotti. Non si applica alle caselle di ricerca presenti nella pagina o alle caselle di ricerca nelle pagine classiche.

* Dopo aver disabilitato la casella di ricerca nella barra di spostamento, se si desidera che la funzionalità di ricerca venga eseguita nel sito, sarà necessario fornirla personalmente utilizzando una Web part personalizzata o un'estensione di SharePoint Framework.

* Questa soluzione rimuoverà anche la casella di ricerca da elenchi e raccolte per il sito. La soluzione di ricerca personalizzata dovrà prendere in considerazione le ricerche contestuali per gli elenchi e le raccolte di SharePoint, oltre alla ricerca a livello di sito.

* Se si applica l'impostazione al sito radice del dominio, la pagina iniziale di SharePoint interrompe anche la visualizzazione della casella di ricerca.

## <a name="changing-the-hint-displayed-in-the-search-box"></a>Modifica del suggerimento visualizzato nella casella di ricerca

È possibile modificare il suggerimento visualizzato nella casella di ricerca per un determinato sito o una raccolta siti. Questo è il testo che viene visualizzato nella casella di ricerca prima di iniziare a digitarlo. In questo modo gli utenti possono essere utili per sapere cosa aspettarsi dalla ricerca se è stata configurata una pagina dei risultati personalizzata o è stato modificato il comportamento della ricerca in altri modi.

> [!NOTE]
> Per poter apportare questa modifica, è necessario consentire l'esecuzione di script personalizzati nel sito in questione come amministratore tenant, che non è consentito per impostazione predefinita. https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-scriptPer ulteriori informazioni, vedere. È possibile consentire l'esecuzione di script personalizzati, apportare le modifiche e quindi ripristinare gli script non consentiti per il sito, se necessario.

Per modificare questa impostazione per un determinato sito, eseguire il comando riportato di seguito:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

In alternativa, se si desidera impostarlo per tutti i siti di una raccolta siti, è possibile utilizzare questo comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

Per tornare al testo segnaposto predefinito, impostare il valore su vuoto ("").
