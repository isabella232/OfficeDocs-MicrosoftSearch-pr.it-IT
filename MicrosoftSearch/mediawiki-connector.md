---
title: Connettore MediaWiki per Microsoft Search
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore MediaWiki per Microsoft Search
ms.openlocfilehash: 281d270a47051e20cb1cfd44540bd51371557c13
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949889"
---
# <a name="mediawiki-connector"></a>Connettore MediaWiki

Con il connettore MediaWiki, l'organizzazione può individuare e indicizzare i dati da un wiki creato usando il software MediaWiki. Questo connettore indicizza il contenuto specificato in Microsoft Search e supporta le ricerche per indicizzazione periodiche per mantenere l'indice aggiornato.

Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitorano un connettore MediaWiki. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati
Immettere l'URL MediaWiki e le credenziali per l'autenticazione della connessione. Sono necessarie le informazioni seguenti: **ID tenant**, ID **risorsa**, **ID client**e **segreto client**.

## <a name="manage-the-search-schema"></a>Gestire lo schema di ricerca
Dopo la connessione completata, configurare il mapping dello schema di ricerca. È possibile scegliere quali proprietà rendere **querybili** **, reperibili e** **recuperabili**.

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca
Il connettore MediaWiki supporta solo le autorizzazioni di ricerca visibili a **tutti**. I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione.

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento 
Questa pianificazione consente di aggiornare i dati indicizzati, in modo che le modifiche apportate al wiki siano riflesse in Microsoft Search. Tutte le nuove pagine, le pagine eliminate, il contenuto della pagina o le modifiche dei metadati vengono visualizzati nei risultati della ricerca dopo l'intervallo di aggiornamento specificato. Il tempo di ricerca per indicizzazione dipende dalle dimensioni del wiki. Attualmente il connettore esegue la ricerca per indicizzazione a circa 50 pagine al minuto.

## <a name="limitations"></a>Limitazioni 
Il connettore MediaWiki ha queste limitazioni nella versione di anteprima:
* Supporta solo wiki basati su cloud.
* Supporta solo Basic o OAuth 2,0 con Azure Active Directory o l'autenticazione di Azure.
* Non supporta la selezione dello spazio dei nomi per l'indicizzazione. Indicizza solo gli spazi dei nomi **principale**, di **categoria**e di **file** .
* Non supporta gli elenchi di controllo di accesso (ACL, Access Control List). Di conseguenza, le pagine indicizzate sono visibili a tutti gli utenti dell'organizzazione.
