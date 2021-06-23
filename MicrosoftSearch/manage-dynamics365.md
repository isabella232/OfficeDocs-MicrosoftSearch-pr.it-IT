---
title: Ricerca federativa dynamics 365 (anteprima)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Gestire la modalità di visualizzazione del contenuto di Dynamics 365 nei risultati della ricerca
ms.openlocfilehash: 5f642bcb026358e57258e5e736fc263616fc4b05
ms.sourcegitcommit: f07a2e578b6c9ed5a1a3b22266cca371782870a7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53067929"
---
# <a name="dynamics-365-federation-search-preview"></a><span data-ttu-id="056ee-103">Ricerca federativa dynamics 365 (anteprima)</span><span class="sxs-lookup"><span data-stu-id="056ee-103">Dynamics 365 federation search (preview)</span></span>

## <a name="microsoft-search-federation-and-connectors"></a><span data-ttu-id="056ee-104">Microsoft Search Federazione e connettori</span><span class="sxs-lookup"><span data-stu-id="056ee-104">Microsoft Search Federation and connectors</span></span>

<span data-ttu-id="056ee-105">Per rendere più Microsoft Search, stiamo introducendo la federazione Microsoft Search federazione.</span><span class="sxs-lookup"><span data-stu-id="056ee-105">To help make Microsoft Search more useful, we're introducing Microsoft Search Federation.</span></span> <span data-ttu-id="056ee-106">Con la ricerca federata, le organizzazioni possono rendere accessibili i dati in questi scenari in Microsoft Search:</span><span class="sxs-lookup"><span data-stu-id="056ee-106">With federated search, organizations can make data in these scenarios accessible in Microsoft Search:</span></span>

* <span data-ttu-id="056ee-107">Dati nei sistemi soggetti a rigorosi requisiti di conformità</span><span class="sxs-lookup"><span data-stu-id="056ee-107">Data in systems that are subject to strict compliance requirements</span></span>
* <span data-ttu-id="056ee-108">Dati che non possono uscire dai limiti del sistema</span><span class="sxs-lookup"><span data-stu-id="056ee-108">Data that can't leave system boundaries</span></span>
* <span data-ttu-id="056ee-109">Dati sensibili archiviati in locale che l'organizzazione non desidera indicizzare nel cloud</span><span class="sxs-lookup"><span data-stu-id="056ee-109">Sensitive data stored on-prem that your organization doesn’t want indexed on the cloud</span></span>

<span data-ttu-id="056ee-110">I dati a cui si accede tramite una connessione di ricerca federata non vengono indicizzati Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="056ee-110">Data accessed through a federated search connection isn't indexed in Microsoft Search.</span></span> <span data-ttu-id="056ee-111">Inoltre, utilizzando i connettori predefiniti di Microsoft, è facile configurare le connessioni di ricerca federate.</span><span class="sxs-lookup"><span data-stu-id="056ee-111">Also, using built-in connectors from Microsoft, it's easy to set up federated search connections.</span></span> <span data-ttu-id="056ee-112">Il connettore Dynamics 365 è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="056ee-112">Our Dynamics 365 connector is currently in preview.</span></span> <span data-ttu-id="056ee-113">Se vuoi partecipare all'anteprima, contattaci [all'indirizzo aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).</span><span class="sxs-lookup"><span data-stu-id="056ee-113">If you're interested in joining the preview, let us know at [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).</span></span>

## <a name="dynamics-365-federation-connector"></a><span data-ttu-id="056ee-114">Connettore di federazione dynamics 365</span><span class="sxs-lookup"><span data-stu-id="056ee-114">Dynamics 365 federation connector</span></span>

<span data-ttu-id="056ee-115">Microsoft Dynamics 365 è una linea di applicazioni aziendali intelligenti progettate per la pianificazione delle risorse aziendali e la gestione delle relazioni con i clienti.</span><span class="sxs-lookup"><span data-stu-id="056ee-115">Microsoft Dynamics 365 is a line of intelligent business applications designed for enterprise resource planning and customer relationship management.</span></span> <span data-ttu-id="056ee-116">Con la federazione di Dynamics 365, Microsoft Search offre un'esperienza di ricerca senza problemi, consentendo agli utenti di trovare facilmente i dati aziendali e dei clienti più rilevanti archiviati in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="056ee-116">With Dynamics 365 federation, Microsoft Search provides a seamless search experience, enabling users to easily find the most relevant customer and business data stored in Dynamics 365.</span></span> <span data-ttu-id="056ee-117">Il connettore di federazione di Dynamics 365 offre alcuni vantaggi principali:</span><span class="sxs-lookup"><span data-stu-id="056ee-117">The Dynamics 365 federation connector provides some key benefits:</span></span>

* <span data-ttu-id="056ee-118">**Facile da amministrare:** Processo semplificato per configurare e gestire la connessione di ricerca a un'istanza di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="056ee-118">**Easy to administer:** Streamlined process to configure and maintain the search connection to a Dynamics 365 instance.</span></span>
* <span data-ttu-id="056ee-119">**Facile da usare:** Gli utenti possono trovare facilmente e rapidamente le informazioni chiave archiviate in Dynamics 365, inclusi account, contatti, opportunità aperte e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="056ee-119">**Easy to use:** Users can easily and quickly find key information stored in Dynamics 365, including accounts, contacts, open opportunities, and more.</span></span>
* <span data-ttu-id="056ee-120">**Contenuto più ricco:** Per rendere più utili i risultati della ricerca di Dynamics 365, includono informazioni chiave come lead, contatti e dettagli dell'account.</span><span class="sxs-lookup"><span data-stu-id="056ee-120">**Richer content:** To make Dynamics 365 search results more useful, they include key information like leads, contacts, and account details.</span></span>
* <span data-ttu-id="056ee-121">**Protezione dei dati incorporata:** I risultati di Dynamics 365 verranno visualizzati solo per gli utenti che hanno accesso all'istanza connessa.</span><span class="sxs-lookup"><span data-stu-id="056ee-121">**Built-in data protection:** Dynamics 365 results will only appear for users that have access to the connected instance.</span></span>
* <span data-ttu-id="056ee-122">**Esperienza di ricerca unificata:** Per mantenere un'esperienza coerente, i risultati di Dynamics 365 sono coerenti in tutti i punti di ingresso della ricerca.</span><span class="sxs-lookup"><span data-stu-id="056ee-122">**Unified search experience:** To maintain a cohesive experience, Dynamics 365 results are consistent across all search entry points.</span></span> <span data-ttu-id="056ee-123">Ovunque si eserciti la ricerca, si otterrà gli stessi risultati con lo stesso aspetto.</span><span class="sxs-lookup"><span data-stu-id="056ee-123">Wherever you search, you'll get the same results with the same look and feel.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="056ee-124">Esperienza degli utenti</span><span class="sxs-lookup"><span data-stu-id="056ee-124">What users experience</span></span>

<span data-ttu-id="056ee-125">Le risposte di Dynamics 365 vengono visualizzate nei risultati della ricerca in tutti i Microsoft Search canvas, tra cui SharePoint Online, Bing e Office.</span><span class="sxs-lookup"><span data-stu-id="056ee-125">Dynamics 365 answers appear in search results across all Microsoft Search canvases, including SharePoint Online, Bing, and Office.</span></span>

:::image type="content" alt-text="Screenshot delle risposte di Dynamics 365 su SharePoint, Bing e Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

<span data-ttu-id="056ee-127">Dalla risposta, è facile vedere altri risultati di ricerca di Dynamics 365 usando il **collegamento Altri risultati di Dynamics 365.**</span><span class="sxs-lookup"><span data-stu-id="056ee-127">From the answer, it's easy to see more Dynamics 365 search results by using the **More Dynamics 365 results** link.</span></span> <span data-ttu-id="056ee-128">Porta gli utenti a una pagina dei risultati di Dynamics 365 dedicata con più risultati rilevanti per la query.</span><span class="sxs-lookup"><span data-stu-id="056ee-128">It takes users to a dedicated Dynamics 365 results page with more results relevant to their query.</span></span>

:::image type="content" alt-text="Screenshot of Dynamics 365 vertical and results on SharePoint, Bing, and Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

<span data-ttu-id="056ee-130">Se si fa clic o si tocca un risultato, viene aperto Dynamics 365 e vengono visualizzate le informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="056ee-130">Clicking or tapping any result opens Dynamics 365 and shows the detailed information.</span></span>

:::image type="content" alt-text="Screenshot della pagina dei dettagli in Dynamics 365" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

<span data-ttu-id="056ee-132">Indipendentemente da dove gli utenti avviano la ricerca, l'esperienza sarà coerente e consentirà loro di trovare rapidamente i risultati di Dynamics 365 più pertinenti.</span><span class="sxs-lookup"><span data-stu-id="056ee-132">No matter where your users start their search their experience will be consistent and enable them to quickly find the most relevant Dynamics 365 results.</span></span> <span data-ttu-id="056ee-133">Per una dimostrazione, vedere il video di Microsoft Build 2021.</span><span class="sxs-lookup"><span data-stu-id="056ee-133">Check out our Microsoft Build 2021 video for a demonstration.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4P83t]

## <a name="supported-query-patterns"></a><span data-ttu-id="056ee-134">Modelli di query supportati</span><span class="sxs-lookup"><span data-stu-id="056ee-134">Supported query patterns</span></span>

<span data-ttu-id="056ee-135">Le query in linguaggio naturale e nome prodotto sono supportate quando si usa Microsoft Search per trovare i risultati di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="056ee-135">Both natural language and product name queries are supported when using Microsoft Search to find Dynamics 365 results.</span></span> <span data-ttu-id="056ee-136">Inoltre, per le query di Dynamics 365 non viene distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="056ee-136">Also, Dynamics 365 queries aren't case sensitive.</span></span> <span data-ttu-id="056ee-137">Utilizzare modelli di linguaggio naturale per trovare contatti, account e opportunità, in base al nome o alla posizione del cliente, e altre query utilizzate di frequente.</span><span class="sxs-lookup"><span data-stu-id="056ee-137">Use natural language patterns to find contact, account, and opportunities--by customer name or location--and other frequently used queries.</span></span> <span data-ttu-id="056ee-138">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="056ee-138">Here are a few examples:</span></span>

* <span data-ttu-id="056ee-139">Who è il contatto per Contoso</span><span class="sxs-lookup"><span data-stu-id="056ee-139">Who is the contact for Contoso</span></span>
* <span data-ttu-id="056ee-140">Opportunità aperte per Contoso</span><span class="sxs-lookup"><span data-stu-id="056ee-140">Open opportunities for Contoso</span></span>
* <span data-ttu-id="056ee-141">Quali sono le opportunità aperte a Seattle</span><span class="sxs-lookup"><span data-stu-id="056ee-141">What are open opportunities in Seattle</span></span>
* <span data-ttu-id="056ee-142">Quali sono gli account a Seattle</span><span class="sxs-lookup"><span data-stu-id="056ee-142">What are the accounts in Seattle</span></span>
* <span data-ttu-id="056ee-143">Quali sono i contatti di Seattle</span><span class="sxs-lookup"><span data-stu-id="056ee-143">What are the contacts in Seattle</span></span>
* <span data-ttu-id="056ee-144">Quali sono i lead che chiudono questo mese</span><span class="sxs-lookup"><span data-stu-id="056ee-144">What are my leads closing this month</span></span>
* <span data-ttu-id="056ee-145">Chiamata telefonica ad alta priorità</span><span class="sxs-lookup"><span data-stu-id="056ee-145">High priority phone call</span></span>
* <span data-ttu-id="056ee-146">Contatti mancanti messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="056ee-146">Contact missing emails</span></span>

<span data-ttu-id="056ee-147">I modelli di nome prodotto supportano un intervallo di applicazioni Dynamics 365 e attiveranno i risultati di Dynamics 365 indipendentemente dalla posizione in cui vengono visualizzati in una query:</span><span class="sxs-lookup"><span data-stu-id="056ee-147">Product name patterns support a range of Dynamics 365 applications and will trigger Dynamics 365 results regardless of where they appear in a query:</span></span>

* <span data-ttu-id="056ee-148">D365</span><span class="sxs-lookup"><span data-stu-id="056ee-148">D365</span></span>
* <span data-ttu-id="056ee-149">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="056ee-149">Dynamics 365</span></span>
* <span data-ttu-id="056ee-150">Dynamics365</span><span class="sxs-lookup"><span data-stu-id="056ee-150">Dynamics365</span></span>
* <span data-ttu-id="056ee-151">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="056ee-151">Dynamics CRM</span></span>
* <span data-ttu-id="056ee-152">Dynamics Sales</span><span class="sxs-lookup"><span data-stu-id="056ee-152">Dynamics Sales</span></span>
* <span data-ttu-id="056ee-153">Servizio clienti Dynamics</span><span class="sxs-lookup"><span data-stu-id="056ee-153">Dynamics Customer Service</span></span>
* <span data-ttu-id="056ee-154">Dynamics Service</span><span class="sxs-lookup"><span data-stu-id="056ee-154">Dynamics Service</span></span>
* <span data-ttu-id="056ee-155">Dynamics Field Service</span><span class="sxs-lookup"><span data-stu-id="056ee-155">Dynamics Field Service</span></span>

## <a name="configure-the-dynamics-365-connector"></a><span data-ttu-id="056ee-156">Configurare il connettore Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="056ee-156">Configure the Dynamics 365 connector</span></span>

<span data-ttu-id="056ee-157">Con questa semplice configurazione, è possibile abilitare l'esperienza di ricerca della federazione dynamics 365 per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="056ee-157">With this simple configuration, you can enable the Dynamics 365 federation search experience for people in your organization.</span></span>

1. <span data-ttu-id="056ee-158">[Nell'interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com), passare a [Origini dati](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).</span><span class="sxs-lookup"><span data-stu-id="056ee-158">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [Data sources](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).</span></span>

2. <span data-ttu-id="056ee-159">Nella sezione App e servizi Microsoft, in Microsoft Dynamics 365, selezionare **Gestisci** per aprire il pannello di Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="056ee-159">In the Microsoft apps and services section, under Microsoft Dynamics 365, select **Manage** to open the Microsoft Dynamics 365 panel.</span></span>

3. <span data-ttu-id="056ee-160">Abilitare il connettore per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="056ee-160">Enable the connector for your organization.</span></span>

4. <span data-ttu-id="056ee-161">**Nell'elenco Endpoint** seleziona l'ambiente Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="056ee-161">In the **Endpoints** list, select your Dynamics 365 environment.</span></span>

5. <span data-ttu-id="056ee-162">In **ID connessione** immettere un ID univoco per la connessione.</span><span class="sxs-lookup"><span data-stu-id="056ee-162">In the **Connection ID**, enter a unique ID for this connection.</span></span>

6. <span data-ttu-id="056ee-163">Esaminare e selezionare la casella di controllo consenso.</span><span class="sxs-lookup"><span data-stu-id="056ee-163">Review and select the consent check box.</span></span>

7. <span data-ttu-id="056ee-164">Selezionare **Salva per** completare la configurazione della connessione.</span><span class="sxs-lookup"><span data-stu-id="056ee-164">Select **Save** to finish the connection setup.</span></span>

:::image type="content" alt-text="Screenshot of Dynamics 365 set-up panel in the interfaccia di amministrazione di Microsoft 365" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

<span data-ttu-id="056ee-166">Al termine dell'installazione, le risposte e il verticale di Dynamics 365 verranno visualizzati solo per gli utenti con una licenza dynamics 365 valida e l'accesso all'ambiente Dynamics 365 connesso.</span><span class="sxs-lookup"><span data-stu-id="056ee-166">When the setup is complete, Dynamics 365 answers and vertical will only appear for users with a valid Dynamics 365 license and access to the connected Dynamics 365 environment.</span></span> <span data-ttu-id="056ee-167">In qualsiasi momento, è possibile tornare a queste impostazioni e modificare l'ambiente dell'endpoint di connessione o disattivare la connessione.</span><span class="sxs-lookup"><span data-stu-id="056ee-167">At any time, you can return to these settings and change the connection endpoint environment or deactivate the connection.</span></span>
