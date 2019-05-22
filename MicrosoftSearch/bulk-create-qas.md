---
title: Creare in blocco domande e risposte
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
description: Rispondere rapidamente alle domande frequenti con gli strumenti di importazione nel portale di amministrazione di Microsoft Search
ms.openlocfilehash: f535cb7ae843def536976cb1f05c8601de592cbb
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968305"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="ed3f5-103">Creare in blocco domande e risposte</span><span class="sxs-lookup"><span data-stu-id="ed3f5-103">Bulk create Q&As</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed3f5-104">Le impostazioni di Microsoft Search in Bing sono ora disponibili nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ed3f5-105">Per iniziare, [assegnare amministratori della ricerca](https://docs.microsoft.com/it-IT/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="ed3f5-106">Scaricare e usare il modello CSV per creare o modificare in blocco domande e risposte.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-106">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="ed3f5-107">È anche un modo semplice per salvare in blocco bozze di domande e risposte che richiedono ulteriori modifiche o aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-107">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="ed3f5-108">Se è necessario modificare in blocco domande e risposte esistenti, esportarle dal portale di amministrazione, apportare le modifiche necessarie e quindi importarle.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-108">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="ed3f5-109">Nell'angolo superiore destro della sezione Domande e risposte, fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-109">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="ed3f5-110">Fare clic su **Scarica modello domande e risposte (CSV)**.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-110">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="ed3f5-111">Salvare e aprire il file CSV</span><span class="sxs-lookup"><span data-stu-id="ed3f5-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="ed3f5-112">Aggiungere contenuto e impostazioni delle domande e risposte e salvare il file.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-112">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="ed3f5-113">Il file CSV deve essere salvato come file UTF-8 CSV, altre codifiche e/o tipi di file potrebbero causare errori di importazione</span><span class="sxs-lookup"><span data-stu-id="ed3f5-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="ed3f5-114">Nell'angolo superiore destro della sezione Domande e risposte, fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-114">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="ed3f5-115">Nel riquadro Importa domande e risposte fare clic su \*\*Sfoglia \*\*e passare al file CSV da importare.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-115">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="ed3f5-116">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-116">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="ed3f5-117">Evitare gli errori di importazione</span><span class="sxs-lookup"><span data-stu-id="ed3f5-117">Prevent import errors</span></span>      
<span data-ttu-id="ed3f5-118">Se i dati necessari sono mancanti o non validi, si riceverà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-118">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="ed3f5-119">A seconda dell'errore, può essere generato un file di log con altre informazioni sulle righe e sulle colonne da correggere.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-119">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="ed3f5-120">Apportare le modifiche necessarie e ritentare l'importazione del file.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-120">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="ed3f5-121">Fino a quando non sono stati risolti tutti gli errori, non è possibile creare o modificare le domande e risposte.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-121">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="ed3f5-122">Per evitare errori, verificare che il file di importazione sia formattato correttamente, ossia che:</span><span class="sxs-lookup"><span data-stu-id="ed3f5-122">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="ed3f5-123">Includa la riga di intestazione presente nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="ed3f5-123">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="ed3f5-124">Includa tutte le colonne presenti nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="ed3f5-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="ed3f5-125">L'ordine delle colonne equivalga a quello del modello di importazione</span><span class="sxs-lookup"><span data-stu-id="ed3f5-125">The column order is the same as the import template</span></span>
- <span data-ttu-id="ed3f5-126">Queste colonne possono essere vuote: ID, Ultima modifica e Autore ultima modifica</span><span class="sxs-lookup"><span data-stu-id="ed3f5-126">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="ed3f5-127">La colonna Stato non può essere vuota, perché si tratta di informazioni obbligatorie</span><span class="sxs-lookup"><span data-stu-id="ed3f5-127">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="ed3f5-128">In base al campo Stato, le domande e risposte saranno salvate come bozza, suggerite o pianificate, oppure saranno pubblicate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-128">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="ed3f5-129">Se si include l'Id di una domanda e risposta esistente, verrà sostituito con le informazioni presenti nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-129">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="ed3f5-130">Per le organizzazioni con più tenant, è possibile esportare le domande e risposte da un tenant e importarle in un altro.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-130">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="ed3f5-131">È tuttavia necessario rimuovere i dati dalla colonna Id prima dell'importazione.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-131">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="ed3f5-132">Per altre informazioni sui campi obbligatori e consigliati, vedere [Creare domande e risposte](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="ed3f5-132">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

