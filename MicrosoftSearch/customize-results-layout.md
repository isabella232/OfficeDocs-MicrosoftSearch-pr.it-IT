---
title: Personalizzare il layout dei risultati della ricerca
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Utilizzo di schede adattive, creazione di un layout per visualizzare i risultati di ricerca personalizzati
ms.openlocfilehash: 2ca53f2e2dc207acdf48542f39ee4f448bdeb90e
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949849"
---
# <a name="create-a-layout-to-customize-search-results"></a>Creare un layout per la personalizzazione dei risultati di ricerca

È possibile progettare il layout dei risultati per un verticale personalizzato utilizzando lo strumento di progettazione del layout di ricerca. È possibile iniziare a progettare il layout scegliendo i modelli offerti nello strumento di progettazione del layout e utilizzandoli se sono adatti ai propri requisiti. In alternativa, è possibile scegliere di modificare questi modelli in vari modi per soddisfare le proprie esigenze. Ad esempio, aggiungere/rimuovere immagini, aggiungere/rimuovere testo, modificare il testo. Se nessuno dei modelli soddisfa il proprio requisito, è possibile scegliere di iniziare a progettare il layout utilizzando un modello vuoto.  

 

Una volta che il layout è pronto, è possibile utilizzare la [lingua del modello di schede Adaptive](https://docs.microsoft.com/adaptive-cards/templating/language) per creare JSON result layout di Thea che viene utilizzato per definire un tipo di risultati. È possibile mappare le proprietà dei risultati al layout utilizzando il passaggio di mapping nello strumento di progettazione del layout.  

## <a name="create-a-layout-on-your-own"></a>Creare un layout personalizzato
La creazione di un layout personalizzato richiede la conoscenza delle [schede adattative](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) e del relativo [schema](https://adaptivecards.io/explorer/). Il layout dei risultati di ricerca utilizza un sottoinsieme degli elementi offerti dalle schede adattive ed è possibile utilizzare lo strumento di progettazione del layout per ottenere informazioni sul set di elementi supportato.  

Durante la creazione di un layout personalizzato, creare il layout della scheda adattabile utilizzando i dati dell'utente e quindi finalizzare il layout.
Sono disponibili due passaggi principali per la creazione di un layout personalizzato
- Progettazione del layout
- Separazione dei dati dal modello

#### <a name="designing-the-layout"></a>Progettazione del layout

In questo esempio viene mostrato un layout con un'intestazione, un collegamento e un testo descrittivo.

![Esempio di un layout con un'intestazione, un collegamento e una descrizione.](media/Verts-ExampleLayout.png)

Ed ecco il file JSON associato al layout:


```json
{ 
    "type": "AdaptiveCard", 
    "version": "1.0", 
     "body": [ 
{ 

            "type": "ColumnSet", 
             "columns": [ 
                 { 
                     "type": "Column", 
                     "width": 8, 
                     "items": [ 
                         { 
                             "type": "TextBlock", 
                             "text": "Contoso Marketing Analysis - Q3 FY18", 
                             "color": "Accent", 
                             "size": "Medium", 
                             "spacing": "None", 
                             "$when": "{title != \"\"}", 
                             "weight": "Bolder" 
                        }, 
                        { 
                        "type": "TextBlock",  
                        "text": "https://contoso.com/hr/link", 
                        "spacing": "None",  
                        "color": "Dark", 
                        "weight": "Bolder" 

                        }, 

                        {  
                        "type": "TextBlock", 
                        "text": "Marketing team at Contoso.., and looking at the Contoso Marketing documents on the team site. This contains the data from FY20 and will taken over to FY21...Marketing Planning is ongoing for FY20..",  
                        "wrap": true, 
                        "maxLines": 2, 
                        "spacing": "Medium" 
                        } 
                        ], 

                    "horizontalAlignment": "Center", 
                    "spacing": "None" 

                } 

            ] 

        } 
        ], 

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json" 
}
```

#### <a name="separating-the-data-from-the-layout"></a>Separazione dei dati dal layout

È possibile separare i dati dal layout e associarli. 

Ecco il layout JSON dopo l'associazione dei dati:


```json
{ 

    "type": "AdaptiveCard", 
    "version": "1.0", 
    "body": [ 
    { 
    "type": "ColumnSet", 
"columns": [ 

                { 
                "type": "Column", 
                "width": 8, 
                "items": [ 
                { 
                "type": "TextBlock", 
                "text": "[{title}]({titleUrl})", 
                "color": "Accent", 
                "size": "Medium",
                "spacing": "None", 
                "weight": "Bolder" 

                 }, 
                 { 
                 "type": "TextBlock", 
                 "text": "{link}",
                 "spacing": "None", 
                 "color": "Dark",
                 "weight": "Bolder" 
                 }, 
                 { 
                 "type": "TextBlock",
                 "text": "{description}",
                 "wrap": true,
                 "maxLines": 2, 
                 "spacing": "Medium" 
                 } 
                 ], 
                 "horizontalAlignment": "Center", 
                 "spacing": "None" 
                 } 
                 ] 

        } 

    ], 

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json" 
}
```

Dati di esempio: specificare i dati di esempio nell' **editor di dati di esempio** per visualizzare la scheda con associazione a dati in "modalità anteprima".

```json
{ 

    "title": "Contoso Marketing Analysis - Q3 FY18", 
    "titleUrl": "https://contoso.com/hr/link", 
    "link": "https://contoso.com/hr/link", 
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?" 

} 
```

## <a name="map-the-layout-to-the-result-properties"></a>Mappare il layout alle proprietà dei risultati

È necessario eseguire il mapping di ogni campo del layout a una proprietà dei risultati o a una proprietà del connettore per generare il JSON del layout dei risultati.

![Verts-SearchLayoutDesigner. png](media/Verts-SearchLayoutDesigner.png)

Selezionare un campo nel layout per evidenziare le variabili che devono essere mappate. È possibile utilizzare più variabili per un singolo campo e tutti i campi devono essere mappati alle proprietà dei risultati.

## <a name="things-to-consider"></a>Considerazioni da prendere in considerazione...

Prima di iniziare, è necessario eseguire alcune operazioni e alcune operazioni che è necessario evitare per garantire la corretta esecuzione dei layout.

### <a name="do"></a>Non

- Modificare un modello per fornire il collegamento del logo nel layout se si utilizzano collegamenti statici per i loghi e non le proprietà dei risultati.   
- Convalidare il layout dei risultati per gli scenari in cui non viene restituito alcun dato per una proprietà dei risultati utilizzata nel JSON risultante. Utilizzare `$when` la condizione per nascondere un elemento se la proprietà non contiene dati.  
- Verificare che i tipi di dati della `$when` condizione e della proprietà Result corrispondano. Ad esempio, non confrontare `Number` con `Text` in `$when` condizione.  
- Si pensi ai requisiti del tema quando si progetta un layout dei risultati.  
- Verificare che l' `Textblock`  elemento sia in grado di gestire il contenuto dinamico. È possibile utilizzare le `wrap` proprietà `maxLines` and element per questo scopo. 
- Formattare correttamente la data in cui `{DATE()}` viene utilizzato in Markdown.  

### <a name="dont"></a>Non

- Non definire i tipi di dati non validi per i valori di binding. Per ulteriori informazioni sui tipi di dati, vedere [gestire lo schema di ricerca](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema ).
- Evitare di ritagliare il risultato nella pagina dei risultati attenendosi all'altezza massima del JSON del layout dei risultati. Se si supera l'altezza massima del layout dei risultati, il risultato verrà ritagliato nella pagina dei risultati.
- Non utilizzare `px` i valori nelle proprietà di un elemento.


## <a name="resources"></a>Risorse
[Personalizzare la pagina dei risultati di ricerca](customize-search-page.md)

[Schede adattative](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[Lingua modello per schede adattative](https://docs.microsoft.com/adaptive-cards/templating/language)

[Schema della scheda Adaptive](https://adaptivecards.io/explorer/)
