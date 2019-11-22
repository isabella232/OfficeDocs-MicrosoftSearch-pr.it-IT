---
title: Personalizzare il layout dei risultati della ricerca
ms.author: anfowler
author: jeffkizn
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
ms.openlocfilehash: 6d1409eaf070275a4c6dbc713b1ec7914e09e541
ms.sourcegitcommit: b28d7f4dfc71ecd7edc28c964a3da2180e1f4c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793551"
---
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="02b6f-103">Creare un layout per la personalizzazione dei risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="02b6f-103">Create a layout to customize search results</span></span>

<span data-ttu-id="02b6f-104">È possibile progettare il layout dei risultati per un verticale personalizzato utilizzando lo strumento di progettazione del layout di ricerca.</span><span class="sxs-lookup"><span data-stu-id="02b6f-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="02b6f-105">È possibile iniziare a progettare il layout scegliendo i modelli offerti nello strumento di progettazione del layout e utilizzandoli se sono adatti ai propri requisiti.</span><span class="sxs-lookup"><span data-stu-id="02b6f-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="02b6f-106">In alternativa, è possibile scegliere di modificare questi modelli in vari modi per soddisfare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="02b6f-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="02b6f-107">Ad esempio, aggiungere/rimuovere immagini, aggiungere/rimuovere testo e modificare il testo.</span><span class="sxs-lookup"><span data-stu-id="02b6f-107">For example, add/remove images, add/remove text, and modify text.</span></span> <span data-ttu-id="02b6f-108">Se nessuno dei modelli soddisfa i requisiti, è possibile scegliere di iniziare a progettare il layout utilizzando un modello vuoto.</span><span class="sxs-lookup"><span data-stu-id="02b6f-108">If none of the templates meet your requirements, you can choose to start designing your layout using a blank template.</span></span>  

 

<span data-ttu-id="02b6f-109">Dopo che il layout è pronto, utilizzare la [lingua del modello schede adattive](https://docs.microsoft.com/adaptive-cards/templating/language) per creare un JSON di layout dei risultati utilizzato per definire un tipo di risultati.</span><span class="sxs-lookup"><span data-stu-id="02b6f-109">After the layout is ready, use the [Adaptive Cards Template language](https://docs.microsoft.com/adaptive-cards/templating/language) to create a result layout JSON that's used to define a result type.</span></span> <span data-ttu-id="02b6f-110">È possibile mappare le proprietà dei risultati al layout utilizzando il passaggio di mapping nello strumento di progettazione del layout.</span><span class="sxs-lookup"><span data-stu-id="02b6f-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="02b6f-111">Creare un layout personalizzato</span><span class="sxs-lookup"><span data-stu-id="02b6f-111">Create a layout on your own</span></span>
<span data-ttu-id="02b6f-112">La creazione di un layout personalizzato richiede la conoscenza delle [schede adattative](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) e del relativo [schema](https://adaptivecards.io/explorer/).</span><span class="sxs-lookup"><span data-stu-id="02b6f-112">Creating a layout on your own requires knowledge of [adaptive cards](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="02b6f-113">Il layout dei risultati di ricerca utilizza un sottoinsieme degli elementi offerti dalle schede adattive ed è possibile utilizzare lo strumento di progettazione del layout per ottenere informazioni sul set di elementi supportato.</span><span class="sxs-lookup"><span data-stu-id="02b6f-113">Search result layout uses a subset of the elements offered by adaptive cards, and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="02b6f-114">Durante la creazione di un layout personalizzato, creare il layout della scheda adattabile utilizzando i dati del connettore e quindi finalizzare il layout.</span><span class="sxs-lookup"><span data-stu-id="02b6f-114">While creating your own layout, create the adaptive card layout using data from your connector, and then finalize the layout.</span></span>
<span data-ttu-id="02b6f-115">Per creare un layout personalizzato, sono disponibili due passaggi principali:</span><span class="sxs-lookup"><span data-stu-id="02b6f-115">There are two main steps in creating your own layout:</span></span>
- <span data-ttu-id="02b6f-116">Progettare il layout.</span><span class="sxs-lookup"><span data-stu-id="02b6f-116">Design the layout.</span></span>
- <span data-ttu-id="02b6f-117">Separare i dati dal modello.</span><span class="sxs-lookup"><span data-stu-id="02b6f-117">Separate the data from the template.</span></span>

#### <a name="design-the-layout"></a><span data-ttu-id="02b6f-118">Progettare il layout</span><span class="sxs-lookup"><span data-stu-id="02b6f-118">Design the layout</span></span>

<span data-ttu-id="02b6f-119">In questo esempio viene mostrato un layout con un'intestazione, un collegamento e un testo descrittivo.</span><span class="sxs-lookup"><span data-stu-id="02b6f-119">In this example, we show a layout with a header, link, and descriptive text.</span></span>

![Esempio di un layout con un'intestazione, un collegamento e una descrizione.](media/Verts-ExampleLayout.png)

<span data-ttu-id="02b6f-121">Ed ecco il file JSON associato al layout:</span><span class="sxs-lookup"><span data-stu-id="02b6f-121">And here's the layout's associated JSON file:</span></span>


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

#### <a name="separate-the-data-from-the-layout"></a><span data-ttu-id="02b6f-122">Separare i dati dal layout</span><span class="sxs-lookup"><span data-stu-id="02b6f-122">Separate the data from the layout</span></span>

<span data-ttu-id="02b6f-123">È possibile separare i dati dal layout e associarli.</span><span class="sxs-lookup"><span data-stu-id="02b6f-123">You can separate the data from the layout and bind the data.</span></span> 

<span data-ttu-id="02b6f-124">Ecco il layout JSON dopo l'associazione dei dati:</span><span class="sxs-lookup"><span data-stu-id="02b6f-124">Here's Layout JSON after binding the data:</span></span>


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

<span data-ttu-id="02b6f-125">Dati di esempio: specificare i dati di esempio nell' **editor di dati di esempio** per visualizzare la scheda con associazione a dati in **modalità anteprima**.</span><span class="sxs-lookup"><span data-stu-id="02b6f-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in **Preview Mode**.</span></span>

```json
{ 

    "title": "Contoso Marketing Analysis - Q3 FY18", 
    "titleUrl": "https://contoso.com/hr/link", 
    "link": "https://contoso.com/hr/link", 
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?" 

} 
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="02b6f-126">Mappare il layout alle proprietà dei risultati</span><span class="sxs-lookup"><span data-stu-id="02b6f-126">Map the layout to the result properties</span></span>

<span data-ttu-id="02b6f-127">È necessario eseguire il mapping di ogni campo del layout a una proprietà dei risultati o a una proprietà del connettore per generare il JSON del layout dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b6f-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

![Acquisizione dello schermo di un layout di esempio nella pagina progettazione layout di ricerca con un campo selezionato e il riquadro delle proprietà aperto.](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="02b6f-129">Selezionare un campo nel layout per evidenziare le variabili che devono essere mappate.</span><span class="sxs-lookup"><span data-stu-id="02b6f-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="02b6f-130">È possibile utilizzare più variabili per un singolo campo e tutti i campi devono essere mappati alle proprietà dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b6f-130">You can use multiple variables for a single field, and all fields must be mapped to the result properties.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="02b6f-131">Considerazioni da prendere in considerazione...</span><span class="sxs-lookup"><span data-stu-id="02b6f-131">Things to consider...</span></span>

<span data-ttu-id="02b6f-132">Prima di iniziare, è necessario eseguire alcune operazioni e alcune operazioni che è necessario evitare per garantire la corretta esecuzione dei layout.</span><span class="sxs-lookup"><span data-stu-id="02b6f-132">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="02b6f-133">Non</span><span class="sxs-lookup"><span data-stu-id="02b6f-133">Do</span></span>

- <span data-ttu-id="02b6f-134">Modificare un modello per fornire il collegamento del logo nel layout se si utilizzano collegamenti statici per i loghi e non le proprietà dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b6f-134">Edit a template to provide the logo link in the layout if you're using static links for logos and not result properties.</span></span>   
- <span data-ttu-id="02b6f-135">Convalidare il layout dei risultati per gli scenari in cui non viene restituito alcun dato per una proprietà dei risultati utilizzata nel JSON risultante.</span><span class="sxs-lookup"><span data-stu-id="02b6f-135">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="02b6f-136">Utilizzare la `$when` condizione per nascondere un elemento se la proprietà non contiene dati.</span><span class="sxs-lookup"><span data-stu-id="02b6f-136">Use the `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="02b6f-137">Verificare che i tipi di dati della `$when` condizione e della proprietà Result corrispondano.</span><span class="sxs-lookup"><span data-stu-id="02b6f-137">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="02b6f-138">Ad esempio, non confrontare `Number` con `Text` la `$when` condizione.</span><span class="sxs-lookup"><span data-stu-id="02b6f-138">For example, don't compare `Number` with `Text` in the `$when` condition.</span></span>  
- <span data-ttu-id="02b6f-139">Si pensi ai requisiti del tema quando si progetta un layout dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b6f-139">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="02b6f-140">Verificare che l'elemento `Textblock`  sia in grado di gestire il contenuto dinamico.</span><span class="sxs-lookup"><span data-stu-id="02b6f-140">Make sure that the `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="02b6f-141">È possibile utilizzare le `wrap` proprietà `maxLines` and element per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="02b6f-141">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span> 
- <span data-ttu-id="02b6f-142">Formattare correttamente la data in cui `{DATE()}` viene utilizzato in Markdown.</span><span class="sxs-lookup"><span data-stu-id="02b6f-142">Properly format the date when using `{DATE()}` in Markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="02b6f-143">Non</span><span class="sxs-lookup"><span data-stu-id="02b6f-143">Don't</span></span>

- <span data-ttu-id="02b6f-144">Non definire i tipi di dati non validi per i valori di binding.</span><span class="sxs-lookup"><span data-stu-id="02b6f-144">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="02b6f-145">Per ulteriori informazioni sui tipi di dati, vedere [gestire lo schema di ricerca](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).</span><span class="sxs-lookup"><span data-stu-id="02b6f-145">For more information about data types, see [Manage the Search schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).</span></span>
- <span data-ttu-id="02b6f-146">Evitare di ritagliare il risultato nella pagina dei risultati attenendosi all'altezza massima del JSON del layout dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b6f-146">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="02b6f-147">Se si supera l'altezza massima del layout dei risultati, il risultato verrà ritagliato nella pagina dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b6f-147">If you exceed the maximum height of the result layout, the result will be cropped on the result page.</span></span>
- <span data-ttu-id="02b6f-148">Non utilizzare `px` i valori nelle proprietà degli elementi.</span><span class="sxs-lookup"><span data-stu-id="02b6f-148">Don't use `px` values in element properties.</span></span>


## <a name="resources"></a><span data-ttu-id="02b6f-149">Risorse</span><span class="sxs-lookup"><span data-stu-id="02b6f-149">Resources</span></span>
[<span data-ttu-id="02b6f-150">Personalizzare la pagina dei risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="02b6f-150">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="02b6f-151">Schede adattative</span><span class="sxs-lookup"><span data-stu-id="02b6f-151">Adaptive cards</span></span>](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="02b6f-152">Lingua modello per schede adattative</span><span class="sxs-lookup"><span data-stu-id="02b6f-152">Adaptive Cards Template language</span></span>](https://docs.microsoft.com/adaptive-cards/templating/language)

[<span data-ttu-id="02b6f-153">Schema della scheda Adaptive</span><span class="sxs-lookup"><span data-stu-id="02b6f-153">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)
