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
ROBOTS: NoIndex
description: Aggiungere più posizioni contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: 186f6973de1ff87b62b5f07a47eb41acdd842010
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591396"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="47ad8-103">Creare posizioni in blocco</span><span class="sxs-lookup"><span data-stu-id="47ad8-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47ad8-104">Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="47ad8-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="47ad8-105">Stiamo trasferendo il portale nell’interfaccia di amministrazione di Microsoft 365, e lo stesso sarà poi rimosso.</span><span class="sxs-lookup"><span data-stu-id="47ad8-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="47ad8-106">Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="47ad8-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="47ad8-107">[Panoramica di Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="47ad8-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="47ad8-108">Scaricare e usare il modello CSV per creare, modificare e salvare in blocco le posizioni.</span><span class="sxs-lookup"><span data-stu-id="47ad8-108">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="47ad8-109">Nell'angolo superiore destro della sezione Posizioni, fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="47ad8-109">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
2. <span data-ttu-id="47ad8-110">Fare clic su **Scarica il modello delle posizioni (.CSV)**</span><span class="sxs-lookup"><span data-stu-id="47ad8-110">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="47ad8-111">Salvare e aprire il file CSV</span><span class="sxs-lookup"><span data-stu-id="47ad8-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="47ad8-112">Aggiungere il contenuto della posizione e salvare il file</span><span class="sxs-lookup"><span data-stu-id="47ad8-112">Add the location content and save the file</span></span>

    <span data-ttu-id="47ad8-113">Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione</span><span class="sxs-lookup"><span data-stu-id="47ad8-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="47ad8-114">Nell'angolo superiore destro della sezione Posizioni, fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="47ad8-114">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
6. <span data-ttu-id="47ad8-115">Nel riquadro Importa posizioni fare clic su \*\*Sfoglia \*\*e passare al file CSV da importare.</span><span class="sxs-lookup"><span data-stu-id="47ad8-115">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="47ad8-116">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="47ad8-116">Click **Import**.</span></span>

<span data-ttu-id="47ad8-117">I campi nei modelli di importazione ed esportazione sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="47ad8-117">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="47ad8-118">È possibile esportare, modificare in blocco e importare le modifiche oppure iniziare con un modello vuoto per creare in blocco nuove posizioni.</span><span class="sxs-lookup"><span data-stu-id="47ad8-118">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="47ad8-119">Per modificare in blocco posizioni esistenti, esportarle dal portale di amministrazione, apportare le modifiche necessarie e quindi importarle.</span><span class="sxs-lookup"><span data-stu-id="47ad8-119">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="47ad8-120">Evitare gli errori di importazione</span><span class="sxs-lookup"><span data-stu-id="47ad8-120">Prevent import errors</span></span>  
<span data-ttu-id="47ad8-121">Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="47ad8-121">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="47ad8-122">A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere.</span><span class="sxs-lookup"><span data-stu-id="47ad8-122">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="47ad8-123">Apportare le modifiche necessarie e ritentare l'importazione del file.</span><span class="sxs-lookup"><span data-stu-id="47ad8-123">Make necessary edits and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="47ad8-124">Fino a quando non sono stati risolti tutti gli errori, non è possibile creare o modificare le posizioni.</span><span class="sxs-lookup"><span data-stu-id="47ad8-124">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="47ad8-125">Per evitare errori, verificare che il file di importazione sia formattato correttamente, ossia che:</span><span class="sxs-lookup"><span data-stu-id="47ad8-125">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="47ad8-126">Includa la riga di intestazione presente nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="47ad8-126">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="47ad8-127">Includa tutte le colonne presenti nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="47ad8-127">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="47ad8-128">L'ordine delle colonne equivalga a quello del modello di importazione</span><span class="sxs-lookup"><span data-stu-id="47ad8-128">The column order is the same as the import template</span></span>
- <span data-ttu-id="47ad8-129">Queste colonne possono essere vuote: ID, Ultima modifica, Autore ultima modifica e Latitudine/longitudine</span><span class="sxs-lookup"><span data-stu-id="47ad8-129">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="47ad8-130">Sse il campo è vuoto, si proverà a determinare la latitudine e la longitudine in base all'indirizzo</span><span class="sxs-lookup"><span data-stu-id="47ad8-130">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="47ad8-131">La colonna Stato non può essere vuota, perché si tratta di informazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="47ad8-131">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="47ad8-132">In base al campo Stato, le posizioni saranno salvate come bozza, suggerite o pianificate, oppure saranno pubblicate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="47ad8-132">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="47ad8-133">Se si include l'Id di una posizione esistente, verrà sostituito con le informazioni presenti nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="47ad8-133">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="47ad8-134">Per le organizzazioni con più tenant, è possibile esportare le posizioni da un tenant e importarle in un altro.</span><span class="sxs-lookup"><span data-stu-id="47ad8-134">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="47ad8-135">È tuttavia necessario rimuovere i dati dalla colonna Id prima dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="47ad8-135">But you must remove the data in the Id column before you import.</span></span>
  
<span data-ttu-id="47ad8-136">Per altre informazioni sui campi obbligatori e consigliati, vedere [Aggiungere una posizione](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="47ad8-136">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

