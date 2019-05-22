---
title: Creare posizioni in blocco
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
description: Aggiungere più posizioni contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: 1d360fda2851083def0bcbd8fcffd77cfa15240e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968292"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="35ca2-103">Creare posizioni in blocco</span><span class="sxs-lookup"><span data-stu-id="35ca2-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35ca2-104">Le impostazioni di Microsoft Search in Bing sono ora disponibili nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35ca2-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="35ca2-105">Per iniziare, [assegnare amministratori della ricerca](https://docs.microsoft.com/it-IT/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="35ca2-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="35ca2-106">Scaricare e usare il modello CSV per creare, modificare e salvare in blocco le posizioni.</span><span class="sxs-lookup"><span data-stu-id="35ca2-106">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="35ca2-107">Nell'angolo superiore destro della sezione Posizioni, fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="35ca2-107">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
2. <span data-ttu-id="35ca2-108">Fare clic su **Scarica il modello delle posizioni (.CSV)**</span><span class="sxs-lookup"><span data-stu-id="35ca2-108">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="35ca2-109">Salvare e aprire il file CSV</span><span class="sxs-lookup"><span data-stu-id="35ca2-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="35ca2-110">Aggiungere il contenuto della posizione e salvare il file</span><span class="sxs-lookup"><span data-stu-id="35ca2-110">Add the location content and save the file</span></span>

    <span data-ttu-id="35ca2-111">Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione</span><span class="sxs-lookup"><span data-stu-id="35ca2-111">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="35ca2-112">Nell'angolo superiore destro della sezione Posizioni, fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="35ca2-112">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
6. <span data-ttu-id="35ca2-113">Nel riquadro Importa posizioni fare clic su \*\*Sfoglia \*\*e passare al file CSV da importare.</span><span class="sxs-lookup"><span data-stu-id="35ca2-113">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="35ca2-114">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="35ca2-114">Click **Import**.</span></span>

<span data-ttu-id="35ca2-115">I campi nei modelli di importazione ed esportazione sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="35ca2-115">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="35ca2-116">È possibile esportare, modificare in blocco e importare le modifiche oppure iniziare con un modello vuoto per creare in blocco nuove posizioni.</span><span class="sxs-lookup"><span data-stu-id="35ca2-116">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="35ca2-117">Per modificare in blocco posizioni esistenti, esportarle dal portale di amministrazione, apportare le modifiche necessarie e quindi importarle.</span><span class="sxs-lookup"><span data-stu-id="35ca2-117">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="35ca2-118">Evitare gli errori di importazione</span><span class="sxs-lookup"><span data-stu-id="35ca2-118">Prevent import errors</span></span>  
<span data-ttu-id="35ca2-119">Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="35ca2-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="35ca2-120">A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere.</span><span class="sxs-lookup"><span data-stu-id="35ca2-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="35ca2-121">Apportare le modifiche necessarie e ritentare l'importazione del file.</span><span class="sxs-lookup"><span data-stu-id="35ca2-121">Make necessary edits and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35ca2-122">Fino a quando non sono stati risolti tutti gli errori, non è possibile creare o modificare le posizioni.</span><span class="sxs-lookup"><span data-stu-id="35ca2-122">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="35ca2-123">Per evitare errori, verificare che il file di importazione sia formattato correttamente, ossia che:</span><span class="sxs-lookup"><span data-stu-id="35ca2-123">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="35ca2-124">Includa la riga di intestazione presente nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="35ca2-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="35ca2-125">Includa tutte le colonne presenti nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="35ca2-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="35ca2-126">L'ordine delle colonne equivalga a quello del modello di importazione</span><span class="sxs-lookup"><span data-stu-id="35ca2-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="35ca2-127">Queste colonne possono essere vuote: ID, Ultima modifica, Autore ultima modifica e Latitudine/longitudine</span><span class="sxs-lookup"><span data-stu-id="35ca2-127">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="35ca2-128">Sse il campo è vuoto, si proverà a determinare la latitudine e la longitudine in base all'indirizzo</span><span class="sxs-lookup"><span data-stu-id="35ca2-128">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="35ca2-129">La colonna Stato non può essere vuota, perché si tratta di informazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="35ca2-129">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="35ca2-130">In base al campo Stato, le posizioni saranno salvate come bozza, suggerite o pianificate, oppure saranno pubblicate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="35ca2-130">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="35ca2-131">Se si include l'Id di una posizione esistente, verrà sostituito con le informazioni presenti nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="35ca2-131">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="35ca2-132">Per le organizzazioni con più tenant, è possibile esportare le posizioni da un tenant e importarle in un altro.</span><span class="sxs-lookup"><span data-stu-id="35ca2-132">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="35ca2-133">È tuttavia necessario rimuovere i dati dalla colonna Id prima dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="35ca2-133">But you must remove the data in the Id column before you import.</span></span>
  
<span data-ttu-id="35ca2-134">Per altre informazioni sui campi obbligatori e consigliati, vedere [Aggiungere una posizione](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="35ca2-134">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

