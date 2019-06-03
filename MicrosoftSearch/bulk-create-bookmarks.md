---
title: Creare in blocco i segnalibri
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
ROBOTS: NoIndex
description: Creare più segnalibri contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: 1b3922215534391c65547a4ece22310261626036
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591423"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="8bf58-103">Creare in blocco i segnalibri</span><span class="sxs-lookup"><span data-stu-id="8bf58-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bf58-104">Questo articolo si applica al portale di amministrazione di Microsoft Search in Bing.</span><span class="sxs-lookup"><span data-stu-id="8bf58-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="8bf58-105">Stiamo trasferendo il portale nell’interfaccia di amministrazione di Microsoft 365, e lo stesso sarà poi rimosso.</span><span class="sxs-lookup"><span data-stu-id="8bf58-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="8bf58-106">Per iniziare, è consigliabile usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bf58-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="8bf58-107">[Panoramica di Microsoft Search](overview-microsoft-search.md).</span><span class="sxs-lookup"><span data-stu-id="8bf58-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="8bf58-108">Scaricare e usare il modello CSV per creare, modificare e salvare in blocco i segnalibri.</span><span class="sxs-lookup"><span data-stu-id="8bf58-108">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="8bf58-109">Per modificare in blocco segnalibri esistenti, esportarli dal portale di amministrazione, apportare le modifiche necessarie e quindi importarli.</span><span class="sxs-lookup"><span data-stu-id="8bf58-109">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="8bf58-110">Nell'angolo superiore destro della sezione Segnalibri, fare clic su **importa**</span><span class="sxs-lookup"><span data-stu-id="8bf58-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="8bf58-111">Fare clic su **Scarica modello segnalibri (CSV)**</span><span class="sxs-lookup"><span data-stu-id="8bf58-111">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="8bf58-112">Salvare e aprire il file CSV</span><span class="sxs-lookup"><span data-stu-id="8bf58-112">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="8bf58-113">Aggiungere contenuto e impostazioni dei segnalibri e salvare il file</span><span class="sxs-lookup"><span data-stu-id="8bf58-113">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="8bf58-114">Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione</span><span class="sxs-lookup"><span data-stu-id="8bf58-114">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="8bf58-115">Nell'angolo superiore destro della sezione Segnalibri fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="8bf58-115">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="8bf58-116">Nel riquadro Importa i segnalibri fare clic su \*\*Sfoglia \*\*e passare al file CSV da importare</span><span class="sxs-lookup"><span data-stu-id="8bf58-116">In the Import bookmarks pane, select **Browse** and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="8bf58-117">Fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="8bf58-117">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="8bf58-118">Evitare gli errori di importazione</span><span class="sxs-lookup"><span data-stu-id="8bf58-118">Prevent import errors</span></span>      
<span data-ttu-id="8bf58-119">Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="8bf58-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="8bf58-120">A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere.</span><span class="sxs-lookup"><span data-stu-id="8bf58-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="8bf58-121">Apportare le modifiche necessarie e ritentare l'importazione del file.</span><span class="sxs-lookup"><span data-stu-id="8bf58-121">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="8bf58-122">Fino a quando non sono stati risolti tutti gli errori, non è possibile creare o modificare i segnalibri.</span><span class="sxs-lookup"><span data-stu-id="8bf58-122">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="8bf58-123">Per evitare errori, verificare che il file di importazione sia formattato correttamente, ossia che:</span><span class="sxs-lookup"><span data-stu-id="8bf58-123">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="8bf58-124">Includa la riga di intestazione presente nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="8bf58-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="8bf58-125">Includa tutte le colonne presenti nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="8bf58-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="8bf58-126">L'ordine delle colonne equivalga a quello del modello di importazione</span><span class="sxs-lookup"><span data-stu-id="8bf58-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="8bf58-127">Queste colonne possono essere vuote: ID, Ultima modifica e Autore ultima modifica</span><span class="sxs-lookup"><span data-stu-id="8bf58-127">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="8bf58-128">La colonna Stato non può essere vuota, perché si tratta di informazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="8bf58-128">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="8bf58-129">In base al campo Stato, i segnalibri saranno salvati come bozza, suggeriti o pianificati, oppure saranno pubblicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8bf58-129">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="8bf58-130">Inoltre, se si include l'Id di un segnalibro esistente, verrà sostituito con le informazioni presenti nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="8bf58-130">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="8bf58-131">Per le organizzazioni con più tenant, è possibile esportare i segnalibri da un tenant e importarli in un altro.</span><span class="sxs-lookup"><span data-stu-id="8bf58-131">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="8bf58-132">È tuttavia necessario rimuovere i dati dalla colonna Id prima dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="8bf58-132">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="8bf58-133">Per altre informazioni sui campi obbligatori e consigliati, vedere [Creare segnalibri](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="8bf58-133">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
