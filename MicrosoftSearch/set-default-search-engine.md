---
title: Impostare il motore di ricerca predefinito
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Informazioni su come impostare Bing come motore di ricerca predefinito dell'azienda tramite Microsoft Search.
ms.openlocfilehash: a0798da94f4433bb754c71b9e0d00e09ba5a543b
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612530"
---
# <a name="set-default-search-engine"></a>Impostare il motore di ricerca predefinito

Configurazione il browser predefinito, motore di ricerca predefinito e home page predefinita consente agli utenti individuare funzionalità Microsoft Search, incoraggiare altri dati di utilizzo e offrire un'esperienza più uniforme.
  
Per impostare il motore di ricerca predefinito per l'organizzazione, attenersi alla procedura seguente.
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-11"></a>Internet Explorer 11

Gli utenti saranno in grado di modificare il provider di ricerca dopo che questo criterio è impostato.
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>1. configurare il computer locale che verrà utilizzato per impostare l'oggetto Criteri di gruppo

Incollare il testo seguente in un registro di sistema (\*con estensione reg) file.
  
Windows Registry Editor Version 5.00
  
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
  
Fare doppio clic sul file creato ed eseguire la procedura per importare il file. Eseguire correttamente l'importazione deve risultare nella finestra di dialogo seguente:
  
![Messaggio importazione completata Editor del Registro di sistema](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>2. aprire la Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo

1. Passare a **impostazioni utente Configuration\Policies\Preferences\Windows**.
    
2. Pulsante destro del mouse su **Registry\New** e selezionare **Creazione guidata del Registro di sistema**. Dalla finestra del Browser del Registro di sistema, selezionare **Computer locale** e fare clic su **Avanti**.
    
3. Passare a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.
    
4. Da questa chiave, assicurarsi di selezionare DefaultScope.
    
    ![Browser del Registro di sistema con DefaultScope selezionata](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. Verificare tutte le chiavi sub contenente il GUID di Microsoft Search Bing e ogni valore nella chiave, ad eccezione di qualsiasi percorso ai profili utente. Scorrere verso il basso per selezionare altri elementi.
    
    ![Browser del Registro di sistema con altri valori selezionati](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. Fare clic su Fine per completare questa configurazione.
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>3. configurare le preferenze dell'utente per semplificare l'eliminazione di un messaggio di avviso che all'utente che venga visualizzato quando viene applicato DefaultScope ricerca

È per impostazione predefinita un avviso che informa gli utenti di un programma tenta di modificare le relative impostazioni.
  
1. Nell'oggetto Criteri di gruppo stesso, fare clic con il pulsante destro su **Registry\New** e selezionare **Creazione guidata del Registro di sistema**.
    
2. Passare a **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User preferenze**.
    
3. Selezionare la chiave **Delle preferenze utente** .
    
4. Fare clic su **Fine**.
    
5. Fare clic sull'oggetto appena creato. Nel riquadro di destra fare doppio clic sull'oggetto preferenze utente, modificare l' **azione** **Elimina**e salvare.
    
Applicare criteri risultante tramite il collegamento al dominio appropriato.
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1703-or-later"></a>Windows 10 1703 o versioni successive

Gli utenti saranno in grado di modificare il provider di ricerca dopo che questo criterio è impostato.
  
Per i file ADMX più recenti per diverse versioni di Windows, vedere [come creare e gestire l'archivio centrale per i modelli amministrativi di criteri di gruppo in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).
  
Se l'impostazione descritta in questa sezione non viene trovato all'interno di GPMC, scaricare ADMX appropriato e copiarli nell'archivio centrale. Per ulteriori informazioni, vedere [File ADMX utilizzando oggetti Criteri di gruppo di modifica](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Archivio centrale sul controller è una cartella con la convenzione di denominazione seguente:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Ogni dominio che gestisce il controller di utilizzare una cartella separata. Può utilizzare il comando seguente per copiare il file ADMX al prompt dei comandi:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Aprire la Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo.
    
2. Passare a ** &lt;configurazione Computer/utente&gt;\Administrative Templates\Windows Components\Microsoft Edge**.
    
1. Fare doppio clic su **Imposta motore di ricerca predefinito**, impostato su **attivato**e immettere`https://www.bing.com/sa/osd/bfb.xml`
    
3. Applicare criteri risultante tramite il collegamento al dominio appropriato.
    
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 o versione successiva

Gli utenti saranno in grado di modificare il provider di ricerca dopo che questo criterio è impostato.
  
Chrome dotato di un proprio set di criteri di gruppo che possono essere scaricati nel formato di file ADMX da [Google Chrome Enterprise Guida](https://support.google.com/chrome/a/answer/187202). Se del sistema operativo Windows Vista/Server 2008 o versione successiva vengono utilizzati per la gestione dell'oggetto Criteri di gruppo per il dominio, il file ADMX fornito in questo pacchetto si occupa di impostazioni di Chrome in Windows XP SP2 o versione successiva.
  
Copiare il file di modello in un archivio centrale dei file ADMX sui controller di dominio. Per ulteriori informazioni, vedere [File ADMX utilizzando oggetti Criteri di gruppo di modifica](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Archivio centrale sul controller è una cartella con la convenzione di denominazione seguente:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Ogni dominio che gestisce il controller di utilizzare una cartella separata. Può utilizzare il comando seguente per copiare il file ADMX al prompt dei comandi:
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Aprire la Console Gestione criteri di gruppo (GPMC) e passare alla modifica di un criterio esistente o crearne uno nuovo.
    
2. Verificare che le cartelle seguenti vengono visualizzati nella sezione Modelli amministrativi di entrambe configurazione utente/Computer: Google Chrome e Google Chrome - impostazioni predefinite.
    
  - Le impostazioni della prima sezione risolti e administrators locale non è possibile modificarli nel browser.
    
  - Le impostazioni di quest'ultima sezione dei criteri possono essere modificate da utenti nelle impostazioni del browser.
    
3. Passare a ** \<Computer/utente\> Configurazione utente\Modelli Templates\Google Chrome\Default provider di ricerca**
    
4. Fare doppio clic su **Abilita il provider di ricerca predefinito**e impostarla su **attivato**.
    
5. Fare doppio clic **sull'icona di ricerca del provider predefinito**, impostato su **attivato**e immettere`https://www.bing.com/sa/simg/bb.ico`
    
6. Fare doppio clic su **URL immediato del provider di ricerca predefinito**e immettere`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
7. Fare doppio clic sul **nome del provider di ricerca predefinito**, impostato su attivato e immettere 'Microsoft Search in Bing'
    
8. Fare doppio clic su **URL di ricerca del provider di ricerca predefinito**, impostato su **attivato**e immettere`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
9. Fare doppio clic su **provider di ricerca predefinito suggerire URL**, impostato su **attivato**e immettere`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`
    
10. Applicare criteri risultante tramite il collegamento al dominio appropriato.
    
L'impostazione motore di ricerca predefinito verrà aggiunto la funzionalità di suggerimenti di ricerca Microsoft Search nella barra degli indirizzi del browser. Attualmente, supporta solo i segnalibri. Gli utenti vedranno i suggerimenti due segnalibro principali sopra suggerimenti web pubblici durante la digitazione nella barra degli indirizzi.