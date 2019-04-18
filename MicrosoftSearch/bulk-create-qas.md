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
description: Aggiungere rapidamente le risposte alle domande frequenti con gli strumenti di importazione nel portale di amministrazione di Microsoft Search
ms.openlocfilehash: 28fcf57c44f809e7f9b0c1b27042f4549067a0f8
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901817"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="9aa23-103">Creare in blocco domande e risposte</span><span class="sxs-lookup"><span data-stu-id="9aa23-103">Bulk create Q&As</span></span>

<span data-ttu-id="9aa23-104">Scaricare e utilizzare il modello. csv per creare o modificare in blocco la massa di Q&As.</span><span class="sxs-lookup"><span data-stu-id="9aa23-104">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="9aa23-105">È anche un modo semplice per salvare in blocco Draft Q&As che richiedono ulteriori modifiche o aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="9aa23-105">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="9aa23-106">Se è necessario modificare in blocco i Q&As esistenti, esportarli dal portale di amministrazione, apportare le modifiche necessarie e quindi importarli.</span><span class="sxs-lookup"><span data-stu-id="9aa23-106">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="9aa23-107">Nell'angolo in alto a destra della sezione Q&As, fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="9aa23-107">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="9aa23-108">Fare clic su **Scarica modello di Q&A (. csv)**</span><span class="sxs-lookup"><span data-stu-id="9aa23-108">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="9aa23-109">Salvare e aprire il file. csv</span><span class="sxs-lookup"><span data-stu-id="9aa23-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="9aa23-110">Aggiungere il contenuto e le impostazioni di Q&A e salvare il file</span><span class="sxs-lookup"><span data-stu-id="9aa23-110">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="9aa23-111">Il file. csv deve essere salvato come file UTF-8 CSV, altri tipi di file e o codifiche possono causare errori di importazione</span><span class="sxs-lookup"><span data-stu-id="9aa23-111">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="9aa23-112">Nell'angolo in alto a destra della sezione Q&As, fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="9aa23-112">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="9aa23-113">Nel riquadro Importa Q&As, fare clic su **Sfoglia** e passare al file. csv che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="9aa23-113">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="9aa23-114">Fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="9aa23-114">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="9aa23-115">Prevenire gli errori di importazione</span><span class="sxs-lookup"><span data-stu-id="9aa23-115">Prevent import errors</span></span>      
<span data-ttu-id="9aa23-116">Se i dati richiesti sono mancanti o non validi, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="9aa23-116">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="9aa23-117">A seconda dell'errore, è possibile che venga generato un file di registro con ulteriori informazioni sulle righe e le colonne che devono essere corrette.</span><span class="sxs-lookup"><span data-stu-id="9aa23-117">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="9aa23-118">Apportare le modifiche necessarie e provare a importare di nuovo il file.</span><span class="sxs-lookup"><span data-stu-id="9aa23-118">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="9aa23-119">Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare Q&As.</span><span class="sxs-lookup"><span data-stu-id="9aa23-119">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="9aa23-120">Per evitare errori, verificare che il file di importazione sia formattato correttamente:</span><span class="sxs-lookup"><span data-stu-id="9aa23-120">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="9aa23-121">Include la riga di intestazione inclusa nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="9aa23-121">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="9aa23-122">Include tutte le colonne incluse nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="9aa23-122">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="9aa23-123">L'ordine di colonna è lo stesso del modello di importazione</span><span class="sxs-lookup"><span data-stu-id="9aa23-123">The column order is the same as the import template</span></span>
- <span data-ttu-id="9aa23-124">Tali colonne possono essere vuote: ID, Ultima modifica e Ultima modifica da</span><span class="sxs-lookup"><span data-stu-id="9aa23-124">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="9aa23-125">La colonna dello stato non può essere vuota, queste informazioni sono obbligatorie</span><span class="sxs-lookup"><span data-stu-id="9aa23-125">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="9aa23-126">In base al campo dello stato, Q&As verrà salvato come bozza, suggerito, pianificato o verrà pubblicato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9aa23-126">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="9aa23-127">Inoltre, se si include l'ID di un Q&A esistente, verrà sostituito con le informazioni contenute nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="9aa23-127">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="9aa23-128">Per le organizzazioni con tenant di più, è possibile esportare i Q&As da un tenant e importarli in un altro.</span><span class="sxs-lookup"><span data-stu-id="9aa23-128">For organizations with mulitple tenants, you can export your Q&As from one tenant and import it into another.</span></span> <span data-ttu-id="9aa23-129">È tuttavia necessario rimuovere tutti i dati nella colonna ID prima di essere importati.</span><span class="sxs-lookup"><span data-stu-id="9aa23-129">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="9aa23-130">Per ulteriori informazioni sui campi richiesti e consigliati, vedere [create Q&As](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="9aa23-130">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

