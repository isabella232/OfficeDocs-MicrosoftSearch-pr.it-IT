---
title: Connettore condivisione file
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurare il connettore di condivisione file per Microsoft Search
ms.openlocfilehash: bf9fb730abd4ca6e42b681893525bbe3dd8a1419
ms.sourcegitcommit: 249f41723dd6fda1e93ee1a8f3f7571ef066454b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750898"
---
# <a name="file-share-connector"></a>Connettore condivisione file

Con il connettore grafico condivisione file, gli utenti dell'organizzazione possono eseguire ricerche in condivisioni file di Windows locali.

Questo articolo è per gli amministratori di Microsoft 365 o per tutti gli utenti che configurano, eseguono e monitora un connettore di condivisione file. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.

## <a name="install-graph-connector-agent"></a>Installare l'agente del connettore grafico

Per indicizzare le condivisioni di file di Windows, è necessario installare e registrare il software dell' [agente del connettore grafico](on-prem-agent.md) .

## <a name="content-requirements"></a>Requisiti per il contenuto

### <a name="file-types"></a>Tipi di file

È possibile indicizzare e cercare il contenuto dei formati seguenti: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, xlb, xlc, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS e ZIP. Solo il contenuto testuale di questi formati è indicizzato. Tutto il contenuto multimediale viene ignorato. Per tutti i file che non appartengono a questo formato, solo i metadati vengono indicizzati.

### <a name="file-size-limits"></a>Limiti di dimensione dei file

La dimensione massima del file supportato è 100 MB. I file che superano i 100 MB non vengono indicizzati. Il limite massimo di dimensioni successive all'elaborazione è pari a 4 MB. L'elaborazione si interrompe quando la dimensione di un file raggiunge i 4 MB. Pertanto, alcune frasi presenti nel file potrebbero non funzionare per la ricerca.

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati

Nella pagina **Connetti a origine dati** selezionare **condivisione file** e specificare il nome, l'ID di connessione e la descrizione. Nella pagina successiva, specificare il percorso della condivisione file e selezionare l'agente del connettore grafico precedentemente installato. Immettere le credenziali per un account utente di [Microsoft Windows](https://microsoft.com/windows) con accesso in lettura a tutti i file nella condivisione file.

## <a name="preserve-last-access-time"></a>Mantieni l'ora dell'ultimo accesso

Quando il connettore tenta di eseguire la ricerca per indicizzazione di un file, viene aggiornato il campo "tempo di accesso ultimo" nei metadati. Se si dipendono da tale campo per qualsiasi soluzione di archiviazione e backup e non si desidera aggiornarlo quando il connettore lo accede, è possibile configurare questa opzione nella pagina **Impostazioni avanzate** .

## <a name="manage-search-permissions"></a>Gestire le autorizzazioni di ricerca

È possibile limitare le autorizzazioni per la ricerca di qualsiasi file in base agli elenchi di controllo di accesso condiviso o ai nuovi accessi di controllo di accesso NTFS. Se si desidera utilizzare gli elenchi di controllo di accesso di condivisione, selezionare l'opzione appropriata nella pagina **Impostazioni avanzate** . Se si desidera utilizzare gli elenchi di controllo di accesso NTFS, selezionare l'opzione appropriata nella pagina **Gestisci autorizzazioni di ricerca** .

## <a name="assign-property-labels"></a>Assegnare etichette delle proprietà

È possibile assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni. Anche se questo passaggio non è obbligatorio, l'utilizzo di alcune etichette di proprietà migliorerà la pertinenza della ricerca e assicurerà risultati di ricerca più accurati per gli utenti finali.

## <a name="manage-schema"></a>Gestione dello schema

Nella schermata **Gestisci schema** è possibile modificare gli attributi dello schema (**Queryable**, **Searchable**, **Retrievable** e **per affinamento ricerca**) associati alle proprietà, aggiungere alias facoltativi e scegliere la proprietà **Content** .

## <a name="set-the-refresh-schedule"></a>Impostare la pianificazione di aggiornamento

L'intervallo di pianificazione di aggiornamento predefinito consigliato è 15 minuti, ma è possibile modificarlo in base alle preferenze.

## <a name="result-layout"></a>Layout dei risultati

È consigliabile utilizzare il layout di risultati predefinito per visualizzare i risultati del connettore FileShare perché contiene icone e controlli adeguati che consentono di passare al percorso del file. Se si crea un nuovo layout dei risultati, il valore predefinito verrà ignorato.
