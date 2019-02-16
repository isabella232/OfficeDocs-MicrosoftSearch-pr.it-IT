---
title: Creazione in blocco di Q&As
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
description: Aggiungere rapidamente le risposte alle domande frequenti con gli strumenti di importazione nel portale di amministrazione di Microsoft Search
ms.openlocfilehash: 53f1d167948f6b621ad139620553df51b0cb91c2
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068395"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="c761d-103">Creazione in blocco di Q&As</span><span class="sxs-lookup"><span data-stu-id="c761d-103">Bulk create Q&As</span></span>

<span data-ttu-id="c761d-p101">Scaricare e utilizzare il modello. csv per creare o modificare in blocco la massa di Q&As. È anche un modo semplice per salvare in blocco Draft Q&As che richiedono ulteriori modifiche o aggiornamenti. Se è necessario modificare in blocco i Q&As esistenti, esportarli dal portale di amministrazione, apportare le modifiche necessarie e quindi importarli.</span><span class="sxs-lookup"><span data-stu-id="c761d-p101">Download and use the .csv template to bulk create or bulk edit Q&As. It's also a simple way to bulk save draft Q&As that need additional edits or updates. If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="c761d-107">Nell'angolo in alto a destra della sezione Q&As, fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="c761d-107">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="c761d-108">Fare clic su **Scarica modello di Q&A (. csv)**</span><span class="sxs-lookup"><span data-stu-id="c761d-108">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="c761d-109">Salvare e aprire il file. csv</span><span class="sxs-lookup"><span data-stu-id="c761d-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="c761d-110">Aggiungere il contenuto e le impostazioni di Q&A e salvare il file</span><span class="sxs-lookup"><span data-stu-id="c761d-110">Add the Q&A content and settings and save the file</span></span>
    
5. <span data-ttu-id="c761d-111">Nell'angolo in alto a destra della sezione Q&As, fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="c761d-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="c761d-112">Nel riquadro Importa Q&As, fare clic su **Sfoglia** e passare al file. csv che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="c761d-112">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="c761d-113">Fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="c761d-113">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="c761d-114">Prevenire gli errori di importazione</span><span class="sxs-lookup"><span data-stu-id="c761d-114">Prevent import errors</span></span>      
<span data-ttu-id="c761d-p102">Se i dati richiesti sono mancanti o non validi, verrà visualizzato un messaggio di errore. A seconda dell'errore, è possibile che venga generato un file di registro con ulteriori informazioni sulle righe e le colonne che devono essere corrette. Apportare le modifiche necessarie e provare a importare di nuovo il file.</span><span class="sxs-lookup"><span data-stu-id="c761d-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="c761d-118">Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare Q&As.</span><span class="sxs-lookup"><span data-stu-id="c761d-118">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="c761d-119">Per evitare errori, verificare che il file di importazione sia formattato correttamente:</span><span class="sxs-lookup"><span data-stu-id="c761d-119">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="c761d-120">Include la riga di intestazione inclusa nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="c761d-120">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="c761d-121">Include tutte le colonne incluse nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="c761d-121">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="c761d-122">L'ordine di colonna è lo stesso del modello di importazione</span><span class="sxs-lookup"><span data-stu-id="c761d-122">The column order is the same as the import template</span></span>
- <span data-ttu-id="c761d-123">Tali colonne possono essere vuote: ID, Ultima modifica e Ultima modifica da</span><span class="sxs-lookup"><span data-stu-id="c761d-123">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="c761d-124">La colonna dello stato non può essere vuota, queste informazioni sono obbligatorie</span><span class="sxs-lookup"><span data-stu-id="c761d-124">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="c761d-125">In base al campo dello stato, Q&As verrà salvato come bozza, suggerito, pianificato o verrà pubblicato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c761d-125">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="c761d-126">Inoltre, se si include l'ID di un Q&A esistente, verrà sostituito con le informazioni contenute nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="c761d-126">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="c761d-p103">Per le organizzazioni con tenant di più, è possibile esportare i Q&As da un tenant e importarli in un altro. È tuttavia necessario rimuovere tutti i dati nella colonna ID prima di essere importati.</span><span class="sxs-lookup"><span data-stu-id="c761d-p103">For organizations with mulitple tenants, you can export your Q&As from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="c761d-129">Per ulteriori informazioni sui campi richiesti e consigliati, vedere [create Q&As](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="c761d-129">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

