---
title: Gestire i layout dei risultati della ricerca
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Utilizzo di schede adattive, creazione di un layout per visualizzare i risultati di ricerca personalizzati
ms.openlocfilehash: 425e5404c14d500f6ecd84ad449dafb05bbfd31b
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927181"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="02b8b-103">Creare un layout per la personalizzazione dei risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="02b8b-103">Create a layout to customize search results</span></span>

<span data-ttu-id="02b8b-104">È possibile progettare il layout dei risultati per un verticale personalizzato utilizzando lo strumento di progettazione del layout di ricerca.</span><span class="sxs-lookup"><span data-stu-id="02b8b-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="02b8b-105">È possibile iniziare a progettare il layout scegliendo i modelli offerti nello strumento di progettazione del layout e utilizzandoli se sono adatti ai propri requisiti.</span><span class="sxs-lookup"><span data-stu-id="02b8b-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="02b8b-106">In alternativa, è possibile scegliere di modificare questi modelli in vari modi per soddisfare le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="02b8b-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="02b8b-107">Ad esempio, aggiungere/rimuovere immagini, aggiungere/rimuovere testo e modificare il testo.</span><span class="sxs-lookup"><span data-stu-id="02b8b-107">For example, add/remove images, add/remove text, and modify text.</span></span> <span data-ttu-id="02b8b-108">Se nessuno dei modelli soddisfa i requisiti, è possibile scegliere di iniziare a progettare il layout utilizzando un modello vuoto.</span><span class="sxs-lookup"><span data-stu-id="02b8b-108">If none of the templates meet your requirements, you can choose to start designing your layout using a blank template.</span></span>  

<span data-ttu-id="02b8b-109">Dopo che il layout è pronto, utilizzare la [lingua del modello schede adattive](https://docs.microsoft.com/adaptive-cards/templating/language) per creare un JSON di layout dei risultati utilizzato per definire un tipo di risultati.</span><span class="sxs-lookup"><span data-stu-id="02b8b-109">After the layout is ready, use the [Adaptive Cards Template language](https://docs.microsoft.com/adaptive-cards/templating/language) to create a result layout JSON that's used to define a result type.</span></span> <span data-ttu-id="02b8b-110">È possibile mappare le proprietà dei risultati al layout utilizzando il passaggio di mapping nello strumento di progettazione del layout.</span><span class="sxs-lookup"><span data-stu-id="02b8b-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="02b8b-111">Creare un layout personalizzato</span><span class="sxs-lookup"><span data-stu-id="02b8b-111">Create a layout on your own</span></span>

<span data-ttu-id="02b8b-112">La creazione di un layout personalizzato richiede la conoscenza delle [schede adattative](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) e del relativo [schema](https://adaptivecards.io/explorer/).</span><span class="sxs-lookup"><span data-stu-id="02b8b-112">Creating a layout on your own requires knowledge of [adaptive cards](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="02b8b-113">Il layout dei risultati di ricerca utilizza un sottoinsieme degli elementi offerti dalle schede adattive ed è possibile utilizzare lo strumento di progettazione del layout per ottenere informazioni sul set di elementi supportato.</span><span class="sxs-lookup"><span data-stu-id="02b8b-113">Search result layout uses a subset of the elements offered by adaptive cards, and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="02b8b-114">Durante la creazione di un layout personalizzato, creare il layout della scheda adattabile utilizzando i dati del connettore e quindi finalizzare il layout.</span><span class="sxs-lookup"><span data-stu-id="02b8b-114">While creating your own layout, create the adaptive card layout using data from your connector, and then finalize the layout.</span></span>
<span data-ttu-id="02b8b-115">Per creare un layout personalizzato, sono disponibili due passaggi principali:</span><span class="sxs-lookup"><span data-stu-id="02b8b-115">There are two main steps in creating your own layout:</span></span>

- <span data-ttu-id="02b8b-116">Progettare il layout.</span><span class="sxs-lookup"><span data-stu-id="02b8b-116">Design the layout.</span></span>
- <span data-ttu-id="02b8b-117">Separare i dati dal modello.</span><span class="sxs-lookup"><span data-stu-id="02b8b-117">Separate the data from the template.</span></span>

### <a name="design-the-layout"></a><span data-ttu-id="02b8b-118">Progettare il layout</span><span class="sxs-lookup"><span data-stu-id="02b8b-118">Design the layout</span></span>

<span data-ttu-id="02b8b-119">In questo esempio viene mostrato un layout con un'intestazione, un collegamento e un testo descrittivo.</span><span class="sxs-lookup"><span data-stu-id="02b8b-119">In this example, we show a layout with a header, link, and descriptive text.</span></span>

![Esempio di un layout con un'intestazione, un collegamento e una descrizione.](media/Verts-ExampleLayout.png)

<span data-ttu-id="02b8b-121">Ed ecco il file JSON associato al layout:</span><span class="sxs-lookup"><span data-stu-id="02b8b-121">And here's the layout's associated JSON file:</span></span>

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

### <a name="separate-the-data-from-the-layout"></a><span data-ttu-id="02b8b-122">Separare i dati dal layout</span><span class="sxs-lookup"><span data-stu-id="02b8b-122">Separate the data from the layout</span></span>

<span data-ttu-id="02b8b-123">È possibile separare i dati dal layout e associarli.</span><span class="sxs-lookup"><span data-stu-id="02b8b-123">You can separate the data from the layout and bind the data.</span></span>

<span data-ttu-id="02b8b-124">Ecco il layout JSON dopo l'associazione dei dati:</span><span class="sxs-lookup"><span data-stu-id="02b8b-124">Here's Layout JSON after binding the data:</span></span>

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

<span data-ttu-id="02b8b-125">Dati di esempio: specificare i dati di esempio nell' **editor di dati di esempio** per visualizzare la scheda con associazione a dati in **modalità anteprima**.</span><span class="sxs-lookup"><span data-stu-id="02b8b-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in **Preview Mode**.</span></span>

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="02b8b-126">Mappare il layout alle proprietà dei risultati</span><span class="sxs-lookup"><span data-stu-id="02b8b-126">Map the layout to the result properties</span></span>

<span data-ttu-id="02b8b-127">È necessario eseguire il mapping di ogni campo del layout a una proprietà dei risultati o a una proprietà del connettore per generare il JSON del layout dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b8b-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

![Acquisizione dello schermo di un layout di esempio nella pagina progettazione layout di ricerca con un campo selezionato e il riquadro delle proprietà aperto.](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="02b8b-129">Selezionare un campo nel layout per evidenziare le variabili che devono essere mappate.</span><span class="sxs-lookup"><span data-stu-id="02b8b-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="02b8b-130">È possibile utilizzare più variabili per un singolo campo e tutti i campi devono essere mappati alle proprietà dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b8b-130">You can use multiple variables for a single field, and all fields must be mapped to the result properties.</span></span>

### <a name="show-snippet-on-search-result"></a><span data-ttu-id="02b8b-131">Mostra frammento nei risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="02b8b-131">Show snippet on search result</span></span>  

<span data-ttu-id="02b8b-132">I frammenti dinamici generati nella proprietà **Content** del risultato del connettore possono essere visualizzati nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="02b8b-132">Dynamic snippets generated on the **content** property of the connector result can be shown on the search result.</span></span> <span data-ttu-id="02b8b-133">**ResultSnippet** è la proprietà di sistema che funge da Proprietà segnaposto per i frammenti generati per ogni risultato del connettore.</span><span class="sxs-lookup"><span data-stu-id="02b8b-133">**ResultSnippet** is the system property that acts as a placeholder property for the snippets generated for each Connector result.</span></span> <span data-ttu-id="02b8b-134">Per visualizzare i frammenti nel layout dei risultati, è necessario che la proprietà di sistema **ResultSnippet** sia mappata a un campo appropriato, ad esempio descrizione, nel layout dei risultati di ricerca.</span><span class="sxs-lookup"><span data-stu-id="02b8b-134">To show the snippets on the result layout, the **ResultSnippet** system property must be mapped to an appropriate field, for example Description, in the search result layout.</span></span> <span data-ttu-id="02b8b-135">I frammenti generati in ogni risultato evidenziano anche le corrispondenze nel frammento con il termine di query immesso dall'utente.</span><span class="sxs-lookup"><span data-stu-id="02b8b-135">Snippets generated on each result also highlight the matches in the Snippet with the query term entered by the user.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="02b8b-136">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="02b8b-136">Things to consider</span></span>

<span data-ttu-id="02b8b-137">Prima di iniziare, è necessario eseguire alcune operazioni e alcune operazioni che è necessario evitare per garantire la corretta esecuzione dei layout.</span><span class="sxs-lookup"><span data-stu-id="02b8b-137">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="02b8b-138">Operazione da eseguire</span><span class="sxs-lookup"><span data-stu-id="02b8b-138">Do</span></span>

- <span data-ttu-id="02b8b-139">Modificare un modello per fornire il collegamento del logo nel layout se si utilizzano collegamenti statici per i loghi e non le proprietà dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b8b-139">Edit a template to provide the logo link in the layout if you're using static links for logos and not result properties.</span></span>
- <span data-ttu-id="02b8b-140">Convalidare il layout dei risultati per gli scenari in cui non viene restituito alcun dato per una proprietà dei risultati utilizzata nel JSON risultante.</span><span class="sxs-lookup"><span data-stu-id="02b8b-140">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="02b8b-141">Utilizzare la `$when` condizione per nascondere un elemento se la proprietà non contiene dati.</span><span class="sxs-lookup"><span data-stu-id="02b8b-141">Use the `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="02b8b-142">Verificare che i tipi di dati della `$when` condizione e della proprietà Result corrispondano.</span><span class="sxs-lookup"><span data-stu-id="02b8b-142">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="02b8b-143">Ad esempio, non confrontare `Number` con `Text` la `$when` condizione.</span><span class="sxs-lookup"><span data-stu-id="02b8b-143">For example, don't compare `Number` with `Text` in the `$when` condition.</span></span>  
- <span data-ttu-id="02b8b-144">Si pensi ai requisiti del tema quando si progetta un layout dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b8b-144">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="02b8b-145">Verificare che l'elemento sia in `Textblock`   grado di gestire il contenuto dinamico.</span><span class="sxs-lookup"><span data-stu-id="02b8b-145">Make sure that the `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="02b8b-146">È possibile utilizzare le `wrap` `maxLines` Proprietà and element per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="02b8b-146">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span>
- <span data-ttu-id="02b8b-147">Formattare correttamente la data in cui viene utilizzato `{DATE()}` in Markdown.</span><span class="sxs-lookup"><span data-stu-id="02b8b-147">Properly format the date when using `{DATE()}` in Markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="02b8b-148">Non</span><span class="sxs-lookup"><span data-stu-id="02b8b-148">Don't</span></span>

- <span data-ttu-id="02b8b-149">Non definire i tipi di dati non validi per i valori di binding.</span><span class="sxs-lookup"><span data-stu-id="02b8b-149">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="02b8b-150">Per ulteriori informazioni sui tipi di dati, vedere [gestire lo schema di ricerca](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).</span><span class="sxs-lookup"><span data-stu-id="02b8b-150">For more information about data types, see [Manage the Search schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).</span></span>
- <span data-ttu-id="02b8b-151">Evitare di ritagliare il risultato nella pagina dei risultati attenendosi all'altezza massima del JSON del layout dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b8b-151">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="02b8b-152">Se si supera l'altezza massima del layout dei risultati, il risultato verrà ritagliato nella pagina dei risultati.</span><span class="sxs-lookup"><span data-stu-id="02b8b-152">If you exceed the maximum height of the result layout, the result will be cropped on the result page.</span></span>
- <span data-ttu-id="02b8b-153">Non utilizzare `px` i valori nelle proprietà degli elementi.</span><span class="sxs-lookup"><span data-stu-id="02b8b-153">Don't use `px` values in element properties.</span></span>
- <span data-ttu-id="02b8b-154">Non utilizzare Markdown con la proprietà **ResultSnippet** nel layout dei risultati per evidenziare la corrispondenza delle query nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="02b8b-154">Don't use markdown with the **ResultSnippet** property in the result layout to highlight query match in the search result.</span></span>

## <a name="resources"></a><span data-ttu-id="02b8b-155">Risorse</span><span class="sxs-lookup"><span data-stu-id="02b8b-155">Resources</span></span>

[<span data-ttu-id="02b8b-156">Personalizzare la pagina dei risultati di ricerca</span><span class="sxs-lookup"><span data-stu-id="02b8b-156">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="02b8b-157">Schede adattative</span><span class="sxs-lookup"><span data-stu-id="02b8b-157">Adaptive cards</span></span>](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="02b8b-158">Lingua modello per schede adattative</span><span class="sxs-lookup"><span data-stu-id="02b8b-158">Adaptive Cards Template language</span></span>](https://docs.microsoft.com/adaptive-cards/templating/language)

[<span data-ttu-id="02b8b-159">Schema della scheda Adaptive</span><span class="sxs-lookup"><span data-stu-id="02b8b-159">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)