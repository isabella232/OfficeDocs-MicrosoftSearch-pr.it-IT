---
title: Connettore MediaWiki Graph per Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore MediaWiki Graph per Microsoft Search
ms.openlocfilehash: 9d9d7a1ef9aeaba079f8cccef1ec4a4836768e8d
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084984"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a>Connettore Grafico MediaWiki

Il connettore Grafico MediaWiki consente all'organizzazione di individuare e indicizzare i dati da un wiki creato utilizzando il software MediaWiki. Questo connettore indicizza il contenuto specificato in Microsoft Search e supporta ricerche per indicizzazione periodiche per mantenere aggiornato l'indice.

> [!NOTE]
> Leggere [**l'articolo setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup process.

Questo articolo è per tutti gli utenti che configurano, eseguiti e monitorano un connettore ServiceNow Graph. Integra il processo di configurazione generale e mostra le istruzioni che si applicano solo al connettore MediaWiki Graph. In questo articolo sono inoltre incluse informazioni [sulle limitazioni.](#limitations)

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nell'interfaccia di amministrazione di Microsoft 365

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Passaggio 2: Assegnare un nome alla connessione

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: Configurare le impostazioni di connessione

Immetti **l'URL wiki** e scegli **il tipo di** autenticazione dal menu a discesa delle opzioni. Le opzioni sono **None,** **Basic** e **OAuth 2.0 AAD.**

Se si sceglie **Di base** come tipo di autenticazione, sarà necessario specificare il nome **utente** e la **password** per il wiki.

Se si sceglie **OAuth 2.0 AAD** come tipo di autenticazione, sarà necessario fornire l'ID **risorsa** dell'installazione wiki. Dovrai anche fornire **l'ID client** e il **segreto client** generati nella pagina di registrazione dell'applicazione AAD.

## <a name="step-4-manage-search-permissions"></a>Passaggio 4: Gestire le autorizzazioni di ricerca

Il connettore MediaWiki supporta solo le autorizzazioni di ricerca visibili a **Tutti.** I dati indicizzati vengono visualizzati nei risultati della ricerca ed è visibile a tutti gli utenti dell'organizzazione.

## <a name="step-5-assign-property-labels"></a>Passaggio 5: Assegnare etichette di proprietà

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>Passaggio 6: Gestire lo schema

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>Passaggio 7: Scegliere le impostazioni di aggiornamento

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>Passaggio 8: esaminare la connessione

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>Limitazioni

Il connettore MediaWiki presenta queste limitazioni nella versione di anteprima:

* Supporta solo wiki basati sul cloud.
* Supporta solo Basic o OAuth 2.0 con l'autenticazione di Azure Active Directory o Azure.
* Non supporta la selezione dello spazio dei nomi per l'indicizzazione. Indicizza solo gli spazi dei nomi Main, Category e File.
* Non supporta gli elenchi di controllo di accesso (ACL). Pertanto, le pagine indicizzate sono visibili a tutti gli utenti dell'organizzazione.
