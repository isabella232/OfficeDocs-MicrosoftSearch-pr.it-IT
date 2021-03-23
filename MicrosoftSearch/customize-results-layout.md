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
description: Usando schede adattive, crea un layout per visualizzare i risultati di ricerca personalizzati
ms.openlocfilehash: d29b1a45f11079f4b71f71a387cf43cbf2f48e7d
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031738"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="b2dff-103">Creare un layout per personalizzare i risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="b2dff-103">Create a layout to customize search results</span></span>

<span data-ttu-id="b2dff-104">Puoi progettare il layout dei risultati per un verticale personalizzato usando lo strumento di progettazione del layout di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b2dff-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="b2dff-105">Puoi iniziare a progettare il layout scegliendo i modelli disponibili nello strumento di progettazione del layout e usandoli se si adattano alle tue esigenze.</span><span class="sxs-lookup"><span data-stu-id="b2dff-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="b2dff-106">Oppure puoi scegliere di modificare questi modelli in vari modi per soddisfare le tue esigenze.</span><span class="sxs-lookup"><span data-stu-id="b2dff-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="b2dff-107">Ad esempio, aggiungere/rimuovere immagini, aggiungere/rimuovere testo e modificare il testo.</span><span class="sxs-lookup"><span data-stu-id="b2dff-107">For example, add/remove images, add/remove text, and modify text.</span></span> <span data-ttu-id="b2dff-108">Se nessuno dei modelli soddisfa i requisiti, puoi scegliere di iniziare a progettare il layout usando un modello vuoto.</span><span class="sxs-lookup"><span data-stu-id="b2dff-108">If none of the templates meet your requirements, you can choose to start designing your layout using a blank template.</span></span>  

<span data-ttu-id="b2dff-109">Una volta pronto il layout, usa il linguaggio [Adaptive Cards Template](/adaptive-cards/templating/language) per creare un JSON per il layout dei risultati usato per definire un tipo di risultato.</span><span class="sxs-lookup"><span data-stu-id="b2dff-109">After the layout is ready, use the [Adaptive Cards Template language](/adaptive-cards/templating/language) to create a result layout JSON that's used to define a result type.</span></span> <span data-ttu-id="b2dff-110">Puoi mappare le proprietà dei risultati al layout usando il passaggio Mapping nella finestra di progettazione del layout.</span><span class="sxs-lookup"><span data-stu-id="b2dff-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="b2dff-111">Creare un layout personalizzato</span><span class="sxs-lookup"><span data-stu-id="b2dff-111">Create a layout on your own</span></span>

<span data-ttu-id="b2dff-112">La creazione di un layout personalizzato richiede la conoscenza delle schede [adattive](/adaptive-cards/authoring-cards/getting-started) e del relativo [schema.](https://adaptivecards.io/explorer/)</span><span class="sxs-lookup"><span data-stu-id="b2dff-112">Creating a layout on your own requires knowledge of [adaptive cards](/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="b2dff-113">Il layout dei risultati della ricerca usa un sottoinsieme degli elementi offerti dalle schede adattive ed è possibile usare lo strumento di progettazione del layout per informazioni sul set di elementi supportato.</span><span class="sxs-lookup"><span data-stu-id="b2dff-113">Search result layout uses a subset of the elements offered by adaptive cards, and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="b2dff-114">Durante la creazione di un layout personalizzato, crea il layout della scheda adattiva usando i dati del connettore e quindi finalizza il layout.</span><span class="sxs-lookup"><span data-stu-id="b2dff-114">While creating your own layout, create the adaptive card layout using data from your connector, and then finalize the layout.</span></span>
<span data-ttu-id="b2dff-115">Esistono due passaggi principali per creare un layout personalizzato:</span><span class="sxs-lookup"><span data-stu-id="b2dff-115">There are two main steps in creating your own layout:</span></span>

- <span data-ttu-id="b2dff-116">Progettare il layout.</span><span class="sxs-lookup"><span data-stu-id="b2dff-116">Design the layout.</span></span>
- <span data-ttu-id="b2dff-117">Separare i dati dal modello.</span><span class="sxs-lookup"><span data-stu-id="b2dff-117">Separate the data from the template.</span></span>

### <a name="design-the-layout"></a><span data-ttu-id="b2dff-118">Progettare il layout</span><span class="sxs-lookup"><span data-stu-id="b2dff-118">Design the layout</span></span>

<span data-ttu-id="b2dff-119">In questo esempio viene visualizzato un layout con un'intestazione, un collegamento e un testo descrittivo.</span><span class="sxs-lookup"><span data-stu-id="b2dff-119">In this example, we show a layout with a header, link, and descriptive text.</span></span>

![Esempio di layout con un'intestazione, un collegamento e una descrizione.](media/Verts-ExampleLayout.png)

<span data-ttu-id="b2dff-121">Ed ecco il file JSON associato al layout:</span><span class="sxs-lookup"><span data-stu-id="b2dff-121">And here's the layout's associated JSON file:</span></span>

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

### <a name="separate-the-data-from-the-layout"></a><span data-ttu-id="b2dff-122">Separare i dati dal layout</span><span class="sxs-lookup"><span data-stu-id="b2dff-122">Separate the data from the layout</span></span>

<span data-ttu-id="b2dff-123">Puoi separare i dati dal layout e associare i dati.</span><span class="sxs-lookup"><span data-stu-id="b2dff-123">You can separate the data from the layout and bind the data.</span></span>

<span data-ttu-id="b2dff-124">Ecco LAYOUT JSON dopo il binding dei dati:</span><span class="sxs-lookup"><span data-stu-id="b2dff-124">Here's Layout JSON after binding the data:</span></span>

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

<span data-ttu-id="b2dff-125">Dati di esempio: specificare dati di esempio **nell'Editor** dati di esempio per visualizzare la scheda associata a dati in **modalità anteprima.**</span><span class="sxs-lookup"><span data-stu-id="b2dff-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in **Preview Mode**.</span></span>

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="b2dff-126">Mappare il layout alle proprietà dei risultati</span><span class="sxs-lookup"><span data-stu-id="b2dff-126">Map the layout to the result properties</span></span>

<span data-ttu-id="b2dff-127">È necessario eseguire il mapping di ogni campo del layout a una proprietà dei risultati o a una proprietà del connettore per generare il formato JSON del layout dei risultati.</span><span class="sxs-lookup"><span data-stu-id="b2dff-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

![Acquisizione dello schermo di un layout di esempio nella pagina Progettazione layout di ricerca con un campo selezionato e il riquadro delle proprietà aperto.](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="b2dff-129">Selezionare un campo nel layout per evidenziare le variabili da mappare.</span><span class="sxs-lookup"><span data-stu-id="b2dff-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="b2dff-130">È possibile utilizzare più variabili per un singolo campo e tutti i campi devono essere mappati alle proprietà dei risultati.</span><span class="sxs-lookup"><span data-stu-id="b2dff-130">You can use multiple variables for a single field, and all fields must be mapped to the result properties.</span></span>

### <a name="show-snippet-on-search-result"></a><span data-ttu-id="b2dff-131">Mostra frammento di codice nel risultato della ricerca</span><span class="sxs-lookup"><span data-stu-id="b2dff-131">Show snippet on search result</span></span>  

<span data-ttu-id="b2dff-132">I frammenti di codice dinamici generati **sulla proprietà del** contenuto del risultato del connettore possono essere visualizzati nel risultato della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b2dff-132">Dynamic snippets generated on the **content** property of the connector result can be shown on the search result.</span></span> <span data-ttu-id="b2dff-133">**ResultSnippet** è la proprietà di sistema che funge da proprietà segnaposto per i frammenti di codice generati per ogni risultato del connettore.</span><span class="sxs-lookup"><span data-stu-id="b2dff-133">**ResultSnippet** is the system property that acts as a placeholder property for the snippets generated for each Connector result.</span></span> <span data-ttu-id="b2dff-134">Per visualizzare i frammenti di codice nel layout dei risultati, la proprietà di sistema **ResultSnippet** deve essere mappata a un campo appropriato, ad esempio Description, nel layout dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b2dff-134">To show the snippets on the result layout, the **ResultSnippet** system property must be mapped to an appropriate field, for example Description, in the search result layout.</span></span> <span data-ttu-id="b2dff-135">I frammenti di codice generati su ogni risultato evidenziano anche le corrispondenze nel frammento di codice con il termine di query immesso dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b2dff-135">Snippets generated on each result also highlight the matches in the Snippet with the query term entered by the user.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="b2dff-136">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b2dff-136">Things to consider</span></span>

<span data-ttu-id="b2dff-137">Prima di iniziare, è consigliabile eseguire alcune operazioni e alcune operazioni da evitare per garantire la corretta esecuzione dei layout.</span><span class="sxs-lookup"><span data-stu-id="b2dff-137">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="b2dff-138">Operazione da eseguire</span><span class="sxs-lookup"><span data-stu-id="b2dff-138">Do</span></span>

- <span data-ttu-id="b2dff-139">Modificare un modello per fornire il collegamento al logo nel layout se si usano collegamenti statici per i logo e non le proprietà dei risultati.</span><span class="sxs-lookup"><span data-stu-id="b2dff-139">Edit a template to provide the logo link in the layout if you're using static links for logos and not result properties.</span></span>
- <span data-ttu-id="b2dff-140">Convalidare il layout dei risultati per gli scenari in cui non vengono restituiti dati per una proprietà dei risultati usata nel risultato JSON.</span><span class="sxs-lookup"><span data-stu-id="b2dff-140">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="b2dff-141">Utilizzare la `$when` condizione per nascondere un elemento se la proprietà non contiene dati.</span><span class="sxs-lookup"><span data-stu-id="b2dff-141">Use the `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="b2dff-142">Verificare che i tipi di dati della `$when` condizione e della proprietà del risultato corrispondano.</span><span class="sxs-lookup"><span data-stu-id="b2dff-142">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="b2dff-143">Ad esempio, non confrontare `Number` con `Text` nella `$when` condizione.</span><span class="sxs-lookup"><span data-stu-id="b2dff-143">For example, don't compare `Number` with `Text` in the `$when` condition.</span></span>  
- <span data-ttu-id="b2dff-144">Quando progetti un layout dei risultati, pensa ai requisiti del tema.</span><span class="sxs-lookup"><span data-stu-id="b2dff-144">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="b2dff-145">Assicurati che `Textblock`   l'elemento sia in grado di gestire il contenuto dinamico.</span><span class="sxs-lookup"><span data-stu-id="b2dff-145">Make sure that the `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="b2dff-146">A tale scopo, `wrap` è possibile utilizzare le proprietà `maxLines` dell'elemento e .</span><span class="sxs-lookup"><span data-stu-id="b2dff-146">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span>
- <span data-ttu-id="b2dff-147">Formattare correttamente la data quando viene utilizzato `{DATE()}` in Markdown.</span><span class="sxs-lookup"><span data-stu-id="b2dff-147">Properly format the date when using `{DATE()}` in Markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="b2dff-148">Non</span><span class="sxs-lookup"><span data-stu-id="b2dff-148">Don't</span></span>

- <span data-ttu-id="b2dff-149">Non definire tipi di dati non validi quando si associano valori.</span><span class="sxs-lookup"><span data-stu-id="b2dff-149">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="b2dff-150">Per ulteriori informazioni sui tipi di dati, vedere [Manage the Search schema](/sharepoint/search/manage-the-search-schema).</span><span class="sxs-lookup"><span data-stu-id="b2dff-150">For more information about data types, see [Manage the Search schema](/sharepoint/search/manage-the-search-schema).</span></span>
- <span data-ttu-id="b2dff-151">Evitare di ritagliare il risultato nella pagina dei risultati seguendo l'altezza massima del formato JSON del layout dei risultati.</span><span class="sxs-lookup"><span data-stu-id="b2dff-151">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="b2dff-152">Se si supera l'altezza massima del layout dei risultati, il risultato verrà ritagliato nella pagina dei risultati.</span><span class="sxs-lookup"><span data-stu-id="b2dff-152">If you exceed the maximum height of the result layout, the result will be cropped on the result page.</span></span>
- <span data-ttu-id="b2dff-153">Non usare valori `px` nelle proprietà degli elementi.</span><span class="sxs-lookup"><span data-stu-id="b2dff-153">Don't use `px` values in element properties.</span></span>
- <span data-ttu-id="b2dff-154">Non utilizzare markdown con la **proprietà ResultSnippet** nel layout dei risultati per evidenziare la corrispondenza della query nel risultato della ricerca.</span><span class="sxs-lookup"><span data-stu-id="b2dff-154">Don't use markdown with the **ResultSnippet** property in the result layout to highlight query match in the search result.</span></span>

## <a name="resources"></a><span data-ttu-id="b2dff-155">Risorse</span><span class="sxs-lookup"><span data-stu-id="b2dff-155">Resources</span></span>

[<span data-ttu-id="b2dff-156">Personalizzare la pagina dei risultati della ricerca</span><span class="sxs-lookup"><span data-stu-id="b2dff-156">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="b2dff-157">Schede adattive</span><span class="sxs-lookup"><span data-stu-id="b2dff-157">Adaptive cards</span></span>](/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="b2dff-158">Linguaggio del modello di schede adattive</span><span class="sxs-lookup"><span data-stu-id="b2dff-158">Adaptive Cards Template language</span></span>](/adaptive-cards/templating/language)

[<span data-ttu-id="b2dff-159">Schema scheda adattiva</span><span class="sxs-lookup"><span data-stu-id="b2dff-159">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)