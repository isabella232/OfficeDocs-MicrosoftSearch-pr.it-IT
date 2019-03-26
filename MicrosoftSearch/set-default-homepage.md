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
description: Informazioni su come impostare Bing come home page predefinita per la società con Microsoft Search.
ms.openlocfilehash: db0611ebd7f4a8344664825bbb42025f3bb36486
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612490"
---
# <a name="set-default-homepage"></a>Impostare la home page predefinita

La configurazione del browser predefinito, del motore di ricerca predefinito e della home page predefinita consente agli utenti di scoprire le funzionalità di Microsoft Search, incoraggiarli a un utilizzo maggiore e fornire loro un'esperienza ottimale.
  
Per impostare la home page predefinita per l'organizzazione, eseguire la procedura seguente.
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-50-or-later"></a>Internet Explorer 5.0 o versioni successive

1. Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.
    
2. Passare a **Configurazione utente\Preferenze\Impostazioni del Pannello di controllo\Impostazioni Internet**.
    
3. Fare clic con il pulsante destro del mouse su **Impostazioni Internet** e selezionare **Internet Explorer 10**.
    
    > [!NOTE]
    > È necessario selezionare l'opzione Internet Explorer 10 per applicare le impostazioni di Internet Explorer 11 perché le stesse impostazioni valgono anche per Internet Explorer 11. 
  
4. Le impostazioni sottolineate in rosso non vengono configurate nel computer di destinazione, mentre quelle sottolineate in verde vengono configurate. Per modificare il tipo di sottolineatura, usare i tasti funzione seguenti:
    
    F5 - Abilita tutte le impostazioni nella scheda corrente
    
    F6 - Abilita l'impostazione attualmente selezionata
    
    F7 - Disabilita l'impostazione attualmente selezionata
    
    F8 - Disabilita tutte le impostazioni nella scheda corrente
    
5. Premere **F8** per disabilitare tutte le impostazioni prima di configurare qualsiasi valore. La schermata sarà simile a quella seguente: 
    
    ![Finestra di dialogo delle proprietà di Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. Premere **F6** nell'impostazione della home page e immettere `https://www.bing.com/business?form=BFBSPR`
    
7. Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.
    
> [!NOTE]
> Gli utenti possono comunque modificare la home page dopo aver impostato questo criterio. 
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1511-or-later"></a>Windows 10 versione 1511 o successiva

1. Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.
    
2. Passare a **Modelli amministrativi\Componenti di Windows\Microsoft Edge**
    
1. Fare doppio clic su **Configura pagine iniziali**, impostarlo su **Abilitato** e immettere `https://www.bing.com/business`
    
3. Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.
    
> [!CAUTION]
> Gli utenti non potranno modificare il provider di ricerca dopo aver impostato il criterio. 
  
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 o versioni successive

L'articolo del supporto di Windows sulla gestione dei file ADMX e i file ADMX più recenti per le diverse versioni di Windows sono disponibili nel sito del [Supporto tecnico Microsoft](https://support.microsoft.com/it-IT/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).

È necessario anche il file di criteri Google più recente, disponibile nella [Guida di Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).
  
Se le impostazioni descritte in questa sezione non sono disponibili all'interno di GPMC, scaricare il file ADMX appropriato e copiarlo nell'[archivio centrale](https://docs.microsoft.com/it-IT/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). L'archivio centrale nel controller è una cartella conforme alla convenzione di denominazione seguente:
  
 **%systemroot%\sysvol\\<dominio\>\policies\PolicyDefinitions**
  
Ogni dominio gestito dal controller deve ottenere una cartella separata. Per copiare il file ADMX dal prompt dei comandi, usare il comando seguente:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Aprire la Console Gestione criteri di gruppo (gpmc.msc) e passare alla modifica di un criterio esistente o crearne uno nuovo.
    
2. Verificare che le cartelle seguenti vengono visualizzate nella sezione **Modelli amministrativi** di *Configurazione utente/computer*: Google Chrome e Google Chrome - Impostazioni predefinite (gli utenti possono eseguire l'override).
    
   - Le impostazioni della prima sezione sono fisse e gli amministratori locali non possono modificarle.
    
   - Le impostazioni dell'ultima sezione dei criteri possono essere modificate dagli utenti nelle impostazioni del browser. È necessario decidere se gli utenti possono eseguire l'override dell'impostazione predefinita. Nella procedura seguente modificare l'impostazione nella cartella corrispondente ai criteri e alle esigenze dell'organizzazione. Nella procedura seguente si usa Google Chrome - Impostazioni predefinite come valore predefinito.
    
3. Passare a **&lt;Configurazione computer/utente&gt;\Modelli amministrativi\Google Chrome - Impostazioni predefinite\Home page**.
    
4. Fare doppio clic su **Usa la pagina Nuova scheda come Pagina iniziale** e impostarlo su **Abilitato**.
    
5. Passare a **&lt;Configurazione computer/utente&gt;\Modelli amministrativi\Google Chrome - Impostazioni predefinite\Pagina Nuova scheda**.
    
6. Fare doppio clic su **Configura l'URL della pagina iniziale**, impostarlo su **Abilitato** e immettere `https://www.bing.com/business?form=BFBSPR`
    
7. Applicare l'oggetto Criteri di gruppo risultante collegandolo al dominio appropriato.
    
Gli utenti potranno modificare la home page dopo aver impostato il criterio.