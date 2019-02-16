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
ms.openlocfilehash: eb51b93ceaa560e5142ac46d316ba745c614fe34
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068411"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="15d59-103">Creare posizioni in blocco</span><span class="sxs-lookup"><span data-stu-id="15d59-103">Bulk create locations</span></span>

<span data-ttu-id="15d59-104">Scaricare e utilizzare il modello. csv per creare, modificare e salvare in blocco le posizioni.</span><span class="sxs-lookup"><span data-stu-id="15d59-104">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="15d59-105">Nell'angolo in alto a destra della sezione posizioni fare clic su **Importa** .</span><span class="sxs-lookup"><span data-stu-id="15d59-105">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="15d59-106">Fare clic su **download template locations (. csv)**</span><span class="sxs-lookup"><span data-stu-id="15d59-106">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="15d59-107">Salvare e aprire il file. csv</span><span class="sxs-lookup"><span data-stu-id="15d59-107">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="15d59-108">Aggiungere il contenuto del percorso e salvare il file</span><span class="sxs-lookup"><span data-stu-id="15d59-108">Add the location content and save the file</span></span>
    
5. <span data-ttu-id="15d59-109">Nell'angolo in alto a destra della sezione posizioni fare clic su **Importa** .</span><span class="sxs-lookup"><span data-stu-id="15d59-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="15d59-110">Nel riquadro Importa percorsi fare clic su **Sfoglia** e passare al file CSV che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="15d59-110">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="15d59-111">Fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="15d59-111">Click **Import**</span></span>

<span data-ttu-id="15d59-p101">I campi nei modelli delle posizioni di importazione ed esportazione sono gli stessi. È possibile esportare, modificare in blocco e importare le modifiche o iniziare con un modello vuoto per creare in blocco nuove posizioni. Per modificare in blocco le posizioni esistenti, esportarle dal portale di amministrazione, apportare le modifiche necessarie e quindi importarle.</span><span class="sxs-lookup"><span data-stu-id="15d59-p101">The fields in the import and export locations templates are the same. You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations. To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="15d59-115">Prevenire gli errori di importazione</span><span class="sxs-lookup"><span data-stu-id="15d59-115">Prevent import errors</span></span>  
<span data-ttu-id="15d59-p102">Se i dati richiesti sono mancanti o non validi, verrà visualizzato un messaggio di errore. A seconda dell'errore, è possibile che venga generato un file di registro con ulteriori informazioni sulle righe e le colonne che devono essere corrette. Apportare le modifiche necessarie e provare a importare di nuovo il file.</span><span class="sxs-lookup"><span data-stu-id="15d59-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="15d59-119">Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare posizioni.</span><span class="sxs-lookup"><span data-stu-id="15d59-119">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="15d59-120">Per evitare errori, verificare che il file di importazione sia formattato correttamente:</span><span class="sxs-lookup"><span data-stu-id="15d59-120">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="15d59-121">Include la riga di intestazione inclusa nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="15d59-121">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="15d59-122">Include tutte le colonne incluse nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="15d59-122">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="15d59-123">L'ordine di colonna è lo stesso del modello di importazione</span><span class="sxs-lookup"><span data-stu-id="15d59-123">The column order is the same as the import template</span></span>
- <span data-ttu-id="15d59-124">Tali colonne possono essere vuote: ID, last modified, last modified by e Lat/Long</span><span class="sxs-lookup"><span data-stu-id="15d59-124">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="15d59-125">Si cercherà di determinare Lat/Long in base all'indirizzo se il campo è vuoto.</span><span class="sxs-lookup"><span data-stu-id="15d59-125">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="15d59-126">La colonna dello stato non può essere vuota, queste informazioni sono obbligatorie</span><span class="sxs-lookup"><span data-stu-id="15d59-126">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="15d59-127">In base al campo dello stato, i percorsi verranno salvati come bozza, suggeriti, pianificati o verranno pubblicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="15d59-127">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="15d59-128">Inoltre, se si include l'ID di un percorso esistente, verrà sostituito con le informazioni contenute nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="15d59-128">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="15d59-p103">Per le organizzazioni con tenant di più, è possibile esportare i percorsi da un tenant e importarli in un altro. È tuttavia necessario rimuovere tutti i dati nella colonna ID prima di essere importati.</span><span class="sxs-lookup"><span data-stu-id="15d59-p103">For organizations with mulitple tenants, you can export your locations from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="15d59-131">Per ulteriori informazioni sui campi richiesti e consigliati, vedere [aggiungere un percorso](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="15d59-131">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

