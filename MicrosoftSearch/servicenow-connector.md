---
title: Connettore ServiceNow per Microsoft Search
ms.author: mnirkhe
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore ServiceNow per Microsoft Search
ms.openlocfilehash: 357722f83e7f276615d231c8d3e56016bc17ba6e
ms.sourcegitcommit: be0c64845477127d73ee24dc727e4583ced3d0e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48206960"
---
# <a name="servicenow-connector"></a>Connettore ServiceNow

Con il connettore ServiceNow, l'organizzazione può indicizzare gli articoli della Knowledge base che sono visibili a tutti gli utenti all'interno dell'organizzazione. Dopo aver configurato il connettore e l'indicizzazione del contenuto da ServiceNow, gli utenti finali possono cercare tali articoli da qualsiasi client di ricerca di Microsoft.  

Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitorano un connettore di ServiceNow. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati

Per connettersi ai dati di ServiceNow, è necessario l'URL dell' **istanza di ServiceNow**dell'organizzazione, le credenziali per questo account e l'ID client e il segreto client per l'autenticazione OAuth.  

L'URL dell' **istanza di ServiceNow** dell'organizzazione è in genere simile a **https:// &lt; Your-Organization-Domain>. Service-Now.com**. Insieme a questo URL, è necessario un account per la configurazione della connessione a ServiceNow, nonché per consentire a Microsoft Search di aggiornare periodicamente gli articoli da ServiceNow in base alla pianificazione di aggiornamento.

Per eseguire l'autenticazione e la sincronizzazione del contenuto da ServiceNow, scegliere uno dei due metodi supportati:

 - Autenticazione di base
 - OAuth (scelta consigliata)

> [!Note]
> Per utilizzare OAuth per l'autenticazione, un amministratore di ServiceNow deve eseguire il provisioning di un endpoint nell'istanza di ServiceNow, in modo che l'app di ricerca di Microsoft possa accedere all'istanza. Per ulteriori informazioni, vedere [creare un endpoint per i client per accedere all'istanza](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) nella documentazione di ServiceNow.

Nella tabella seguente vengono fornite indicazioni su come compilare il modulo di creazione dell'endpoint:

Campo | Descrizione | Valore consigliato
--- | --- | ---
Nome | Questo valore univoco identifica l'applicazione per la quale è necessario l'accesso OAuth. | Microsoft Search
ID client | ID univoco di sola lettura e generato automaticamente per l'applicazione. L'istanza utilizza l'ID client quando richiede un token di accesso. | ND
Segreto client | Con questa stringa segreta condivisa, l'istanza di ServiceNow e Microsoft Search autorizzano le comunicazioni tra loro. | Seguire le procedure consigliate per la sicurezza trattando questa come una password.
URL di Reindirizzamento | Un URL di callback obbligatorio a cui il server di autorizzazione reindirizza. | https://gcs.office.com/v1.0/admin/oauth/callback
URL logo | URL che contiene l'immagine per il logo dell'applicazione. | ND
Attivazione | Selezionare la casella di controllo per rendere attivo il registro di sistema dell'applicazione. | Impostata su attivo
Aggiornare la durata del token | Il numero di secondi in cui un token di aggiornamento è valido. Per impostazione predefinita, i token di aggiornamento scadono in 100 giorni (8640000 secondi). | 31.536.000 (1 anno)
Durata del token di accesso | Il numero di secondi in cui un token di accesso è valido. | 43.200 (12 ore)

## <a name="set-a-sync-filter"></a>Impostare un filtro di sincronizzazione

Con un filtro di sincronizzazione, è possibile specificare le condizioni per la sincronizzazione degli articoli. È come una clausola **where** in un'istruzione **SQL SELECT** . Ad esempio, è possibile scegliere di indicizzare solo gli articoli pubblicati e attivi. La pagina di configurazione di SyncNow descrive come acquisire e impostare un filtro di sincronizzazione.

## <a name="manage-the-search-schema"></a>Gestire lo schema di ricerca

Dopo la connessione completata, configurare il mapping dello schema di ricerca. È possibile scegliere quali proprietà rendere **querybili** **, reperibili e** **recuperabili**.

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca

Il connettore ServiceNow supporta solo le autorizzazioni di ricerca visibili a **tutti**. I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione.

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento

Il connettore ServiceNow supporta le pianificazioni di aggiornamento per le ricerche per indicizzazione complete e incrementali. È consigliabile impostare entrambi.

Una pianificazione di ricerca per indicizzazione completa trova gli articoli eliminati precedentemente sincronizzati con l'indice Microsoft Search e tutti gli articoli che sono stati spostati dal filtro di sincronizzazione. Quando si esegue la connessione a ServiceNow, viene eseguita una ricerca per indicizzazione completa per sincronizzare tutti gli articoli della Knowledge base. Per sincronizzare nuovi elementi e rendere gli aggiornamenti, è necessario pianificare ricerche per indicizzazione incrementali.

Il valore predefinito consigliato è un giorno per una ricerca per indicizzazione completa e quattro ore per una ricerca per indicizzazione incrementale.
