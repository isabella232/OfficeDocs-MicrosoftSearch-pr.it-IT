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
description: Aggiungere un numero elevato di posizioni contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: 3c7e43b03b97b46769d5e73f20ddae47b3459b59
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901809"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="2d496-103">Creare posizioni in blocco</span><span class="sxs-lookup"><span data-stu-id="2d496-103">Bulk create locations</span></span>

<span data-ttu-id="2d496-104">Scaricare e utilizzare il modello. csv per creare, modificare e salvare in blocco le posizioni.</span><span class="sxs-lookup"><span data-stu-id="2d496-104">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="2d496-105">Nell'angolo in alto a destra della sezione posizioni fare clic su **Importa** .</span><span class="sxs-lookup"><span data-stu-id="2d496-105">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="2d496-106">Fare clic su **download template locations (. csv)**</span><span class="sxs-lookup"><span data-stu-id="2d496-106">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="2d496-107">Salvare e aprire il file. csv</span><span class="sxs-lookup"><span data-stu-id="2d496-107">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="2d496-108">Aggiungere il contenuto del percorso e salvare il file</span><span class="sxs-lookup"><span data-stu-id="2d496-108">Add the location content and save the file</span></span>

    <span data-ttu-id="2d496-109">Il file. csv deve essere salvato come file UTF-8 CSV, altri tipi di file e o codifiche possono causare errori di importazione</span><span class="sxs-lookup"><span data-stu-id="2d496-109">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="2d496-110">Nell'angolo in alto a destra della sezione posizioni fare clic su **Importa** .</span><span class="sxs-lookup"><span data-stu-id="2d496-110">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="2d496-111">Nel riquadro Importa percorsi fare clic su **Sfoglia** e passare al file CSV che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="2d496-111">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="2d496-112">Fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="2d496-112">Click **Import**</span></span>

<span data-ttu-id="2d496-113">I campi nei modelli delle posizioni di importazione ed esportazione sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="2d496-113">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="2d496-114">È possibile esportare, modificare in blocco e importare le modifiche o iniziare con un modello vuoto per creare in blocco nuove posizioni.</span><span class="sxs-lookup"><span data-stu-id="2d496-114">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="2d496-115">Per modificare in blocco le posizioni esistenti, esportarle dal portale di amministrazione, apportare le modifiche necessarie e quindi importarle.</span><span class="sxs-lookup"><span data-stu-id="2d496-115">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="2d496-116">Prevenire gli errori di importazione</span><span class="sxs-lookup"><span data-stu-id="2d496-116">Prevent import errors</span></span>  
<span data-ttu-id="2d496-117">Se i dati richiesti sono mancanti o non validi, verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="2d496-117">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="2d496-118">A seconda dell'errore, è possibile che venga generato un file di registro con ulteriori informazioni sulle righe e le colonne che devono essere corrette.</span><span class="sxs-lookup"><span data-stu-id="2d496-118">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="2d496-119">Apportare le modifiche necessarie e provare a importare di nuovo il file.</span><span class="sxs-lookup"><span data-stu-id="2d496-119">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d496-120">Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare posizioni.</span><span class="sxs-lookup"><span data-stu-id="2d496-120">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="2d496-121">Per evitare errori, verificare che il file di importazione sia formattato correttamente:</span><span class="sxs-lookup"><span data-stu-id="2d496-121">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="2d496-122">Include la riga di intestazione inclusa nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="2d496-122">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="2d496-123">Include tutte le colonne incluse nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="2d496-123">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="2d496-124">L'ordine di colonna è lo stesso del modello di importazione</span><span class="sxs-lookup"><span data-stu-id="2d496-124">The column order is the same as the import template</span></span>
- <span data-ttu-id="2d496-125">Tali colonne possono essere vuote: ID, last modified, last modified by e Lat/Long</span><span class="sxs-lookup"><span data-stu-id="2d496-125">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="2d496-126">Si cercherà di determinare Lat/Long in base all'indirizzo se il campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="2d496-126">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="2d496-127">La colonna dello stato non può essere vuota, queste informazioni sono obbligatorie</span><span class="sxs-lookup"><span data-stu-id="2d496-127">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="2d496-128">In base al campo dello stato, i percorsi verranno salvati come bozza, suggeriti, pianificati o verranno pubblicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2d496-128">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="2d496-129">Inoltre, se si include l'ID di un percorso esistente, verrà sostituito con le informazioni contenute nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="2d496-129">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="2d496-130">Per le organizzazioni con tenant di più, è possibile esportare i percorsi da un tenant e importarli in un altro.</span><span class="sxs-lookup"><span data-stu-id="2d496-130">For organizations with mulitple tenants, you can export your locations from one tenant and import it into another.</span></span> <span data-ttu-id="2d496-131">È tuttavia necessario rimuovere tutti i dati nella colonna ID prima di essere importati.</span><span class="sxs-lookup"><span data-stu-id="2d496-131">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="2d496-132">Per ulteriori informazioni sui campi richiesti e consigliati, vedere [aggiungere un percorso](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="2d496-132">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

