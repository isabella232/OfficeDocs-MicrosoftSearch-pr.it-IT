---
title: Connettore Graph condivisione file per Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurare il connettore di Graph file per Microsoft Search
ms.openlocfilehash: 387a04c435045d620f8e35aa9fbdd37e23da32a61489d0102dc7bda09920e980
ms.sourcegitcommit: 07d04a81d30b04d1f7e3c556bd711dc7efd710d9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2021
ms.locfileid: "57823016"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a>Connettore di Graph file

Il connettore Graph condivisione file consente agli utenti dell'organizzazione di cercare condivisioni Windows file locali.

> [!NOTE]
> Leggere [**l'articolo Setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup process.

## <a name="before-you-get-started"></a>Prima di iniziare

### <a name="install-the-graph-connector-agent"></a>Installare l'agente Graph connettore

Per indicizzare le Windows file condivisioni file, è necessario installare e registrare l'agente Graph connettore. Per [ulteriori informazioni, vedere Install the Graph connector agent.](graph-connector-agent.md)  

### <a name="content-requirements"></a>Requisiti del contenuto

### <a name="file-types"></a>Tipi di file

È possibile indicizzare e cercare il contenuto dei formati seguenti: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS e ZIP. Viene indicizzato solo il contenuto testuale di questi formati. Tutto il contenuto multimediale viene ignorato. Per qualsiasi file che non appartiene a questo formato, i metadati vengono indicizzati.

### <a name="file-size-limits"></a>Limiti di dimensione dei file

La dimensione massima supportata per il file è 100 MB. I file che superano i 100 MB non vengono indicizzati. Il limite massimo di dimensioni post-elaborazione è 4 MB. L'elaborazione si interrompe quando le dimensioni di un file raggiungono i 4 MB. Di conseguenza, alcune frasi presenti nel file potrebbero non funzionare per la ricerca.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nella interfaccia di amministrazione di Microsoft 365

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Passaggio 2: assegnare un nome alla connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: Configurare le impostazioni di connessione

Nella pagina **Connessione'origine** dati selezionare **Condivisione file** e specificare il nome, l'ID di connessione e la descrizione. Nella pagina successiva specificare il percorso della condivisione file e selezionare l'agente connettore Graph installato in precedenza. Immettere le credenziali per un account [utente di Microsoft Windows](https://microsoft.com/windows) con accesso in lettura a tutti i file nella condivisione file.

### <a name="preserve-last-access-time"></a>Mantenere l'ora dell'ultimo accesso

Quando il connettore tenta di eseguire la ricerca per indicizzazione di un file, il campo "Ora ultimo accesso" nei relativi metadati viene aggiornato. Se si dipende da tale campo per qualsiasi soluzione di archiviazione e backup e non si desidera aggiornarlo quando il connettore vi accede, è possibile configurare questa opzione nella **pagina Impostazioni** avanzate.

## <a name="step-4-limits-for-file-indexing"></a>Passaggio 4: Limiti per l'indicizzazione dei file

Durante la configurazione di una connessione condivisione file, l'amministratore potrebbe limitare l'indicizzazione di file e cartelle. Esistono diversi modi per farlo:

#### <a name="based-on-file-types"></a>In base ai tipi di file

Solo il contenuto testuale di questi formati è indicizzato: DOC, DOCM, DOCX, DOT, DOTX, EML, HTML, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLSX, XLT, XLXM, XML, XPS. Per i file multimediali e i file che non appartengono a questo formato, gli unici metadati vengono indicizzati.

#### <a name="based-on-last-modified-date-or-number-of-days-since-last-modification"></a>In base alla data dell'ultima modifica o al numero di giorni dall'ultima modifica

#### <a name="full-network-path-of-filefolder-or-regular-expression-to-limit-indexing"></a>Percorso di rete completo di file/cartella o espressione regolare per limitare l'indicizzazione 

Nel percorso di rete utilizzare il carattere di escape ( \\ ) prima di caratteri speciali come \\ . Esempio: per il percorso \\ \\ CONTOSO FILE \\ \\ SHAREDFOLDER, il modo corretto per l'input è \\ \\ \\ \\ CONTOSO \\ \\ FILE \\ \\ SHAREDFOLDER

Le regole per la scrittura di espressioni regolari sono disponibili [qui](https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference)

L'amministratore potrebbe anche avere la possibilità di concedere un'eccezione alla regola limite. La priorità della regola di eccezione sostituisce le regole limite. In modo analogo, l'eccezione può essere definita fornendo il percorso cartella/file per gli elementi che si desidera includere nell'indicizzazione.

![Limiti ed eccezioni](media/file-connector/ExclusionRule.png)

## <a name="step-5-manage-search-permissions"></a>Passaggio 5: Gestire le autorizzazioni di ricerca

È possibile limitare l'autorizzazione alla ricerca di qualsiasi file basato sugli elenchi di controllo di accesso condivisi o sugli elenchi di controllo di accesso NTFS (New Technology File System), selezionando l'opzione desiderata nella pagina Gestisci autorizzazioni **di** ricerca. Gli account utente e i gruppi forniti in questi elenchi di controllo di accesso devono essere gestiti da Active Directory (AD). Se si utilizza qualsiasi altro sistema per la gestione degli account utente, è possibile selezionare l'opzione "tutti", che consente agli utenti di cercare tutti i file senza restrizioni di accesso. Tuttavia, quando gli utenti tentano di aprire il file, vengono applicati i controlli di accesso impostati nell'origine.

Tieni presente che le finestre per impostazione predefinita forniscono l'autorizzazione "Lettura" a "Tutti" in Condividi ACL quando una cartella viene condivisa in rete. Per estensione, se si sceglie Condividi ACL in **Gestisci** autorizzazioni di ricerca, gli utenti saranno in grado di cercare tutti i file. Se si desidera limitare l'accesso, rimuovere l'accesso "Lettura" per "Tutti" nelle condivisioni file e fornire l'accesso solo agli utenti e ai gruppi desiderati. Il connettore legge quindi queste restrizioni di accesso e le applica alla ricerca.

È possibile scegliere Condividi ACL solo se il percorso di condivisione specificato segue il formato di percorso UNC. Puoi creare un percorso in formato UNC andando a "Condivisione avanzata" in "Condivisione".

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-6-assign-property-labels"></a>Passaggio 6: Assegnare etichette di proprietà

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a>Passaggio 7: Gestire lo schema

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a>Passaggio 8: Scegliere le impostazioni di aggiornamento

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-9-review-connection"></a>Passaggio 9: esaminare la connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
