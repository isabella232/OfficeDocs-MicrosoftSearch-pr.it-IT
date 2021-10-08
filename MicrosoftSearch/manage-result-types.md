---
title: Gestire i tipi di risultati
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Gestire i tipi di risultati nella pagina dei risultati di ricerca
ms.openlocfilehash: eb0c00cbc05f899a31cd961d89147ac63c97e82c
ms.sourcegitcommit: 02d4f91210d992da080fd39d5b60f8cf30d8f0b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2021
ms.locfileid: "60238422"
---
# <a name="manage-result-types"></a>Gestire i tipi di risultati

È possibile definire la modalità di visualizzazione dei risultati della ricerca nella pagina dei risultati di ricerca [progettando il layout utilizzando](customize-results-layout.md) i tipi di risultati. Il layout dei risultati consente di visualizzare informazioni utili direttamente nei risultati della ricerca in modo che gli utenti possano trovare rapidamente le informazioni necessarie.

I tipi di contenuto incorporati, ad esempio file e utenti, dispongono di un layout standard che non può essere modificato. I tipi di risultati vengono utilizzati [per Graph connettori.](connectors-overview.md) Quando si configura un connettore con mapping di proprietà, Microsoft Search verrà utilizzato un layout dei risultati di ricerca predefinito per i risultati della ricerca del connettore. Il titolo *dell'etichetta* è il più importante; dovresti sempre avere una proprietà assegnata a questa etichetta per usare il layout dei risultati predefinito. Tuttavia, la creazione di un tipo di risultato personalizzato per il contenuto del connettore può rendere tali risultati più di impatto per gli utenti.

Quando si utilizzano verticali e contenuto connettore, è necessario creare un tipo di risultato o eseguire i mapping per un layout predefinito. In caso contrario, il verticale non visualizza alcun risultato della ricerca.

## <a name="understanding-result-types"></a>Informazioni sui tipi di risultati

Creare un layout [dei risultati di](customize-results-layout.md) ricerca personalizzato ed eseguire l'override del layout dei risultati di ricerca predefinito creando un tipo di risultato. Un tipo di risultati di ricerca è una regola che determina la visualizzazione di diversi tipi di risultati di ricerca. È costituito dai seguenti parametri:

- **Una o più condizioni**   per confrontare ogni risultato della ricerca. Esempi di condizioni sono l'origine contenuto e il titolo.
- Layout **dei risultati da** utilizzare per i risultati della ricerca che   soddisfano le condizioni. Il layout risultante controlla la modalità di visualizzazione dei risultati che soddisfano le condizioni nella pagina dei risultati di ricerca.

È possibile utilizzare più tipi di risultati per il contenuto visualizzato in verticale. Questo può essere importante quando si combinano più origini di contenuto in un'unica verticale. Può essere usato anche per un layout più di impatto anche quando è presente un solo tipo di contenuto. Ad esempio, in un verticale che visualizza i dettagli dell'evento imprevisto, è possibile personalizzare gli incidenti di "gravità elevata" in modo da avere colori più prominenti rispetto agli incidenti di "bassa gravità". A tale scopo, è possibile definire le condizioni nella proprietà "gravità" nella **sezione** Regole.

## <a name="create-or-update-result-types"></a>Creare o aggiornare tipi di risultati

L'esperienza di gestione dei tipi di risultati è guidata da una procedura guidata, che consente di definire il nome, l'origine di contenuto, le regole e il layout. I tipi di risultati possono essere personalizzati sia a livello di organizzazione che SharePoint sito.

### <a name="manage-organization-level-result-types"></a>Gestire i tipi di risultati a livello di organizzazione

1. In  [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/)passare alla pagina [**Tipi di risultati**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) nella sezione **Personalizzazione.**
2. Per creare un nuovo tipo di risultato, fare clic **su Aggiungi** o selezionarne uno esistente per modificarlo.
3. Dopo aver configurato il tipo di risultati, è possibile esaminarlo e salvarlo.

### <a name="manage-site-level-result-types"></a>Gestire i tipi di risultati a livello di sito

1. Nel sito di Sharepoint in cui si desidera gestire i tipi di risultati, aprire il pannello delle impostazioni facendo clic sull'ingranaggio.
2. Selezionare **Informazioni sito** e quindi Selezionare Visualizza tutte le impostazioni del **sito.**  
3. Cercare la sezione Microsoft Search e quindi selezionare **Configura impostazioni di ricerca**.
4. Nel riquadro di spostamento passare a Esperienza personalizzata e selezionare il **tipo di risultato**.
5. Per aggiungere un tipo di risultato, fare clic su **Aggiungi.** In caso contrario, per modificare un tipo di risultato, selezionare il tipo di risultato nell'elenco.
6. Dopo aver modificato un tipo di risultato, è possibile esaminare e salvare il tipo di risultato.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Ecco un elenco dei problemi comuni che potrebbero essere visualizzati e delle azioni per risolverli.

|Problema  |Azione  |
|---------|---------|
| Il layout dei risultati non è visualizzato nella pagina di ricerca, anche se ne è stato creato uno. | Potrebbe verificarsi un ritardo di alcuni minuti perché queste impostazioni vengono memorizzate nella cache. Attendere alcuni minuti e riprovare.        |
| Non viene visualizzata alcuna origine di contenuto nella pagina del tipo di risultato. | Assicurarsi di aver configurato i connettori e i dati indicizzati.   |
