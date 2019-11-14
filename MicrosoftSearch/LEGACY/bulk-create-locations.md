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
description: Aggiungere un numero elevato di posizioni contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311697"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="4d116-103">Creare posizioni in blocco</span><span class="sxs-lookup"><span data-stu-id="4d116-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d116-104">Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="4d116-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="4d116-105">Il portale di amministrazione di Microsoft Search in Bing sta per essere trasferito nell'interfaccia di amministrazione di Microsoft 365 e successivamente verrà rimosso.</span><span class="sxs-lookup"><span data-stu-id="4d116-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="4d116-106">Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d116-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="4d116-107">[Panoramica di Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="4d116-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="4d116-108">Scaricare e utilizzare il modello. csv per creare, modificare e salvare in blocco le posizioni.</span><span class="sxs-lookup"><span data-stu-id="4d116-108">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="4d116-109">Nell'angolo in alto a destra della sezione posizioni fare clic su **Importa** .</span><span class="sxs-lookup"><span data-stu-id="4d116-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="4d116-110">Fare clic su **download template locations (. csv)**</span><span class="sxs-lookup"><span data-stu-id="4d116-110">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="4d116-111">Salvare e aprire il file CSV</span><span class="sxs-lookup"><span data-stu-id="4d116-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="4d116-112">Aggiungere il contenuto del percorso e salvare il file</span><span class="sxs-lookup"><span data-stu-id="4d116-112">Add the location content and save the file</span></span>

    <span data-ttu-id="4d116-113">Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione</span><span class="sxs-lookup"><span data-stu-id="4d116-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="4d116-114">Nell'angolo in alto a destra della sezione posizioni fare clic su **Importa** .</span><span class="sxs-lookup"><span data-stu-id="4d116-114">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="4d116-115">Nel riquadro Importa percorsi fare clic su **Sfoglia** e passare al file CSV che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="4d116-115">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="4d116-116">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="4d116-116">Click **Import**</span></span>

<span data-ttu-id="4d116-117">I campi nei modelli delle posizioni di importazione ed esportazione sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="4d116-117">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="4d116-118">È possibile esportare, modificare in blocco e importare le modifiche o iniziare con un modello vuoto per creare in blocco nuove posizioni.</span><span class="sxs-lookup"><span data-stu-id="4d116-118">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="4d116-119">Per modificare in blocco le posizioni esistenti, esportarle dal portale di amministrazione, apportare le modifiche necessarie e quindi importarle.</span><span class="sxs-lookup"><span data-stu-id="4d116-119">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="4d116-120">Evitare gli errori di importazione</span><span class="sxs-lookup"><span data-stu-id="4d116-120">Prevent import errors</span></span>  
<span data-ttu-id="4d116-121">Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="4d116-121">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="4d116-122">A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere.</span><span class="sxs-lookup"><span data-stu-id="4d116-122">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="4d116-123">Apportare le modifiche necessarie e ritentare l'importazione del file.</span><span class="sxs-lookup"><span data-stu-id="4d116-123">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4d116-124">Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare posizioni.</span><span class="sxs-lookup"><span data-stu-id="4d116-124">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="4d116-125">Per evitare errori, verificare che il file di importazione sia formattato correttamente, ossia che:</span><span class="sxs-lookup"><span data-stu-id="4d116-125">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="4d116-126">Includa la riga di intestazione presente nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="4d116-126">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="4d116-127">Includa tutte le colonne presenti nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="4d116-127">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="4d116-128">L'ordine delle colonne equivalga a quello del modello di importazione</span><span class="sxs-lookup"><span data-stu-id="4d116-128">The column order is the same as the import template</span></span>
- <span data-ttu-id="4d116-129">Tali colonne possono essere vuote: ID, last modified, last modified by e Lat/Long</span><span class="sxs-lookup"><span data-stu-id="4d116-129">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="4d116-130">Si cercherà di determinare Lat/Long in base all'indirizzo se il campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="4d116-130">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="4d116-131">La colonna Stato non può essere vuota, perché si tratta di informazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="4d116-131">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="4d116-132">In base al campo dello stato, i percorsi verranno salvati come bozza, suggeriti, pianificati o verranno pubblicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4d116-132">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="4d116-133">Inoltre, se si include l'ID di un percorso esistente, verrà sostituito con le informazioni contenute nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="4d116-133">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="4d116-134">Per i partner che gestiscono più organizzazioni, è possibile esportare i percorsi da un org e importarli in un altro.</span><span class="sxs-lookup"><span data-stu-id="4d116-134">For partners who manage multiple organizations, you can export your locations from one org and import them into another.</span></span> <span data-ttu-id="4d116-135">È tuttavia necessario rimuovere i dati dalla colonna Id prima dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="4d116-135">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="4d116-136">Per ulteriori informazioni sui campi richiesti e consigliati, vedere [aggiungere un percorso](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="4d116-136">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

