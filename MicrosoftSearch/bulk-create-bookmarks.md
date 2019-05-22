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
description: Creare più segnalibri contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: 560cda6f94060d428f2d18cc61bd2430cb31b474
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968349"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="69e28-103">Creare in blocco i segnalibri</span><span class="sxs-lookup"><span data-stu-id="69e28-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69e28-104">Le impostazioni di Microsoft Search in Bing sono ora disponibili nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69e28-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="69e28-105">Per iniziare, [assegnare amministratori della ricerca](https://docs.microsoft.com/it-IT/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="69e28-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="69e28-106">Scaricare e usare il modello CSV per creare, modificare e salvare in blocco i segnalibri.</span><span class="sxs-lookup"><span data-stu-id="69e28-106">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="69e28-107">Per modificare in blocco segnalibri esistenti, esportarli dal portale di amministrazione, apportare le modifiche necessarie e quindi importarli.</span><span class="sxs-lookup"><span data-stu-id="69e28-107">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="69e28-108">Nell'angolo superiore destro della sezione Segnalibri, fare clic su **importa**</span><span class="sxs-lookup"><span data-stu-id="69e28-108">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="69e28-109">Fare clic su **Scarica modello segnalibri (CSV)**</span><span class="sxs-lookup"><span data-stu-id="69e28-109">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="69e28-110">Salvare e aprire il file CSV</span><span class="sxs-lookup"><span data-stu-id="69e28-110">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="69e28-111">Aggiungere contenuto e impostazioni dei segnalibri e salvare il file</span><span class="sxs-lookup"><span data-stu-id="69e28-111">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="69e28-112">Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione</span><span class="sxs-lookup"><span data-stu-id="69e28-112">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="69e28-113">Nell'angolo superiore destro della sezione Segnalibri fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="69e28-113">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="69e28-114">Nel riquadro Importa i segnalibri fare clic su \*\*Sfoglia \*\*e passare al file CSV da importare</span><span class="sxs-lookup"><span data-stu-id="69e28-114">In the Import bookmarks pane, select **Browse** and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="69e28-115">Fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="69e28-115">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="69e28-116">Evitare gli errori di importazione</span><span class="sxs-lookup"><span data-stu-id="69e28-116">Prevent import errors</span></span>      
<span data-ttu-id="69e28-117">Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="69e28-117">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="69e28-118">A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere.</span><span class="sxs-lookup"><span data-stu-id="69e28-118">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="69e28-119">Apportare le modifiche necessarie e ritentare l'importazione del file.</span><span class="sxs-lookup"><span data-stu-id="69e28-119">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="69e28-120">Fino a quando non sono stati risolti tutti gli errori, non è possibile creare o modificare i segnalibri.</span><span class="sxs-lookup"><span data-stu-id="69e28-120">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="69e28-121">Per evitare errori, verificare che il file di importazione sia formattato correttamente, ossia che:</span><span class="sxs-lookup"><span data-stu-id="69e28-121">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="69e28-122">Includa la riga di intestazione presente nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="69e28-122">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="69e28-123">Includa tutte le colonne presenti nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="69e28-123">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="69e28-124">L'ordine delle colonne equivalga a quello del modello di importazione</span><span class="sxs-lookup"><span data-stu-id="69e28-124">The column order is the same as the import template</span></span>
- <span data-ttu-id="69e28-125">Queste colonne possono essere vuote: ID, Ultima modifica e Autore ultima modifica</span><span class="sxs-lookup"><span data-stu-id="69e28-125">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="69e28-126">La colonna Stato non può essere vuota, perché si tratta di informazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="69e28-126">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="69e28-127">In base al campo Stato, i segnalibri saranno salvati come bozza, suggeriti o pianificati, oppure saranno pubblicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="69e28-127">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="69e28-128">Inoltre, se si include l'Id di un segnalibro esistente, verrà sostituito con le informazioni presenti nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="69e28-128">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="69e28-129">Per le organizzazioni con più tenant, è possibile esportare i segnalibri da un tenant e importarli in un altro.</span><span class="sxs-lookup"><span data-stu-id="69e28-129">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="69e28-130">È tuttavia necessario rimuovere i dati dalla colonna Id prima dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="69e28-130">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="69e28-131">Per altre informazioni sui campi obbligatori e consigliati, vedere [Creare segnalibri](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="69e28-131">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
