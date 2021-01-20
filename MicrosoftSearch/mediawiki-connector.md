---
title: Connettore MediaWiki per Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore MediaWiki per Microsoft Search
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905954"
---
# <a name="mediawiki-connector"></a>Connettore MediaWiki

Con il connettore MediaWiki, l'organizzazione può individuare e indicizzare i dati da un wiki creato usando il software MediaWiki. Questo connettore indicizza il contenuto specificato in Microsoft Search e supporta le ricerche per indicizzazione periodiche per mantenere l'indice aggiornato.

Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitorano un connettore grafico MediaWiki. Integra le istruzioni generali fornite nell'articolo [configurazione del connettore grafico](configure-connector.md) . Se non è stato ancora fatto, leggere l'articolo configurazione del connettore grafico completo per comprendere il processo di installazione generale.

Ogni passaggio del processo di installazione è elencato di seguito insieme a una nota che indica che è necessario seguire le istruzioni generali per l'installazione o altre istruzioni che si applicano solo ai connettori del grafico MediaWiki. Questo articolo include anche informazioni sulle [limitazioni](#limitations) per i connettori del grafico MediaWiki. 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: aggiungere un connettore grafico nell'interfaccia di amministrazione di Microsoft 365.
Seguire le istruzioni generali per l'installazione.

## <a name="step-2-name-the-connection"></a>Passaggio 2: denominare la connessione.
Seguire le istruzioni generali per l'installazione.
 
## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: configurare le impostazioni di connessione.
Immettere l' **URL del wiki** e scegliere il **tipo di autenticazione** dal menu a discesa delle opzioni. Le opzioni sono **None**, **Basic** e **OAuth 2,0 AAD**.

Se si sceglie **Basic** come tipo di autenticazione, sarà necessario specificare il **nome utente** e la **password** per il wiki.

Se si sceglie **OAuth 2,0 AAD** come tipo di autenticazione, sarà necessario fornire l'ID della **risorsa** per l'installazione wiki. Sarà inoltre necessario fornire l' **ID client** e il **segreto client** generati nella pagina di registrazione dell'applicazione AAD. 

## <a name="step-4-manage-search-permissions"></a>Passaggio 4: gestire le autorizzazioni di ricerca
Il connettore MediaWiki supporta solo le autorizzazioni di ricerca visibili a **tutti**. I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione.

## <a name="step-5-assign-property-labels"></a>Passaggio 5: assegnare etichette delle proprietà
Seguire le istruzioni generali per l'installazione.

## <a name="step-6-manage-schema"></a>Passaggio 6: gestire lo schema
Seguire le istruzioni generali per l'installazione.

## <a name="step-7-choose-refresh-settings"></a>Passaggio 7: scegliere Aggiorna impostazioni
Seguire le istruzioni generali per l'installazione.

## <a name="step-8-review-connection"></a>Passaggio 8: verifica della connessione
Seguire le istruzioni generali per l'installazione.

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Limitazioni
Il connettore MediaWiki ha queste limitazioni nella versione di anteprima:

* Supporta solo wiki basati su cloud.
* Supporta solo Basic o OAuth 2,0 con Azure Active Directory o l'autenticazione di Azure.
* Non supporta la selezione dello spazio dei nomi per l'indicizzazione. Indicizza solo gli spazi dei nomi principale, di categoria e di file.
* Non supporta gli elenchi di controllo di accesso (ACL, Access Control List). Di conseguenza, le pagine indicizzate sono visibili a tutti gli utenti dell'organizzazione.
