---
title: Creare segnalibri in blocco
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
description: Creare un numero elevato di segnalibri contemporaneamente con gli strumenti di importazione per il portale di amministrazione di Microsoft Search
ms.openlocfilehash: 07694de1f546a1431f371fa24ffc5721ea66337c
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068403"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="e1807-103">Creare segnalibri in blocco</span><span class="sxs-lookup"><span data-stu-id="e1807-103">Bulk create bookmarks</span></span>

<span data-ttu-id="e1807-p101">Scaricare e utilizzare il modello. csv per creare, modificare e salvare in blocco i segnalibri. Per modificare in blocco i segnalibri esistenti, esportarli dal portale di amministrazione, apportare le modifiche necessarie e quindi importarli.</span><span class="sxs-lookup"><span data-stu-id="e1807-p101">Download and use the .csv template to bulk create, edit, and save bookmarks. To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="e1807-106">Nell'angolo in alto a destra della sezione Segnalibri fare clic su **Importa** .</span><span class="sxs-lookup"><span data-stu-id="e1807-106">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="e1807-107">Fare clic su **Scarica modello di segnalibri (. csv)**</span><span class="sxs-lookup"><span data-stu-id="e1807-107">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="e1807-108">Salvare e aprire il file. csv</span><span class="sxs-lookup"><span data-stu-id="e1807-108">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="e1807-109">Aggiungere il contenuto e le impostazioni dei segnalibri e salvare il file</span><span class="sxs-lookup"><span data-stu-id="e1807-109">Add the bookmark content and settings and save the file</span></span>
    
5. <span data-ttu-id="e1807-110">Nell'angolo in alto a destra della sezione Segnalibri fare clic su **Importa** .</span><span class="sxs-lookup"><span data-stu-id="e1807-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="e1807-111">Nel riquadro Importa segnalibri fare clic su **Sfoglia** e passare al file CSV che si desidera importare.</span><span class="sxs-lookup"><span data-stu-id="e1807-111">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="e1807-112">Fare clic su **Importa**</span><span class="sxs-lookup"><span data-stu-id="e1807-112">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="e1807-113">Prevenire gli errori di importazione</span><span class="sxs-lookup"><span data-stu-id="e1807-113">Prevent import errors</span></span>      
<span data-ttu-id="e1807-p102">Se i dati richiesti sono mancanti o non validi, verrà visualizzato un messaggio di errore. A seconda dell'errore, è possibile che venga generato un file di registro con ulteriori informazioni sulle righe e le colonne che devono essere corrette. Apportare le modifiche necessarie e provare a importare di nuovo il file.</span><span class="sxs-lookup"><span data-stu-id="e1807-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="e1807-117">Fino a quando non vengono risolti tutti gli errori, non è possibile creare o modificare i segnalibri.</span><span class="sxs-lookup"><span data-stu-id="e1807-117">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="e1807-118">Per evitare errori, verificare che il file di importazione sia formattato correttamente:</span><span class="sxs-lookup"><span data-stu-id="e1807-118">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="e1807-119">Include la riga di intestazione inclusa nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="e1807-119">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="e1807-120">Include tutte le colonne incluse nel modello di importazione</span><span class="sxs-lookup"><span data-stu-id="e1807-120">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="e1807-121">L'ordine di colonna è lo stesso del modello di importazione</span><span class="sxs-lookup"><span data-stu-id="e1807-121">The column order is the same as the import template</span></span>
- <span data-ttu-id="e1807-122">Tali colonne possono essere vuote: ID, Ultima modifica e Ultima modifica da</span><span class="sxs-lookup"><span data-stu-id="e1807-122">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="e1807-123">La colonna dello stato non può essere vuota, queste informazioni sono obbligatorie</span><span class="sxs-lookup"><span data-stu-id="e1807-123">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="e1807-124">In base al campo dello stato, i segnalibri verranno salvati come bozza, suggeriti, pianificati o verranno pubblicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e1807-124">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="e1807-125">Inoltre, se si include l'ID di un segnalibro esistente, verrà sostituito con le informazioni contenute nel file di importazione.</span><span class="sxs-lookup"><span data-stu-id="e1807-125">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="e1807-p103">Per le organizzazioni con tenant di più, è possibile esportare i segnalibri da un tenant e importarli in un altro. È tuttavia necessario rimuovere tutti i dati nella colonna ID prima di essere importati.</span><span class="sxs-lookup"><span data-stu-id="e1807-p103">For organizations with mulitple tenants, you can export your bookmarks from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="e1807-128">Per ulteriori informazioni sui campi richiesti e consigliati, vedere [creare segnalibri](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="e1807-128">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
