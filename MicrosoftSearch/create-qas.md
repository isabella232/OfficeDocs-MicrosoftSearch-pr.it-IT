---
title: Creare domande e risposte
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: d432b9d9-3792-47a0-9a13-30a1a83caabc
description: Come creare risposte alle domande frequenti per i risultati del lavoro in Microsoft Search
ms.openlocfilehash: 9713608450688a0841aa64d1f3198183b10e05ee
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612498"
---
# <a name="create-qas"></a>Creare domande e risposte

Le domande e risposte forniscono una risposta o informazioni agli utenti, compreso un collegamento facoltativo. In teoria, una domanda e risposta include tutti i dettagli che gli utenti stanno cercando, evitando loro di consultare l'origine. È possibile formattare il contenuto delle domande e risposte e includere immagini, elenchi e tabelle.
  
## <a name="create-a-qa"></a>Creare una domanda e risposta

Per informazioni sulla creazione di titoli, descrizioni e parole chiave efficaci e altro ancora, vedere [Pianificare il contenuto](plan-your-content.md).
  
1. Passare al portale di amministrazione di Microsoft Search
    
2. Nel riquadro di spostamento fare clic su **Domande e risposte**
    
3. Nella parte superiore della pagina fare clic su **Aggiungi domande e risposte**.
    
    Viene visualizzata la pagina Modifica domande e risposte, con un'anteprima dell'aspetto della domanda e risposta in Bing. Quando si aggiungono le informazioni necessarie, l'anteprima verrà aggiornata automaticamente.
    
4. Immettere un **Titolo**
    
    Questo titolo è l'intestazione che viene visualizzata nel risultato. Può contenere fino a 120 caratteri ed è consigliabile usare un formato di domanda.
    
5. Se necessario, immettere l'**URL** della pagina, del sito o del percorso a cui rimanderà il segnalibro 
    
    In questo modo gli utenti che hanno bisogno di ulteriori informazioni possono raggiungere facilmente l'origine per saperne di più.
    
6. Immettere una **Descrizione** della risposta
    
    Dovrebbe rispondere alla domanda che viene posta nel titolo. È possibile copiare il contenuto HTML esistente e incollarlo qui. Eventuali tag non supportati verranno ignorati.
    
7. Usare i tag HTML e le opzioni predefinite per formattare il testo, aggiungere immagini, elenchi, tabelle e altro ancora
    
    Usare l'anteprima nella parte superiore della pagina per vedere come verranno visualizzati i tag e la formattazione in Bing. Per informazioni su:
    
  - Tag HTML, vedere l'elenco seguente dei tag HTML supportati
    
  - Opzioni predefinite, fare clic su **Guida di Markdown** (icona con il punto interrogativo) 
    
8. Immettere le **Parole chiave** cui si vuole associare l'attivazione della domanda e risposta 
    
    Come succede con i segnalibri, quando un utente cerca le parole chiave che sono stati incluse, la domanda e risposta verrà inclusa nei risultati del lavoro. Provare ad aggiungere tutte le varianti possibili, incluso il titolo della domanda e risposta.
    
9. Selezionare **Associa automaticamente le parole chiave simili** per espandere il set di parole chiave 
    
    Questo abilita una corrispondenza più ampia dei termini di ricerca e assicura che la domanda e risposta venga inclusa nei risultati di lavoro pertinenti.
    
10. Immettere le **Parole chiave riservate**
    
    Se una parola chiave attiva più domande e risposte, Microsoft Search posizionerà quella più popolare in alto e mostrerà le altre come collegamenti correlati. Usare una o più parole chiave riservate per fare in modo che una domanda e risposta venga sempre visualizzata come primo risultato. Le parole chiave riservate non possono essere condivise tra le domande e risposte. Inoltre, non è consigliabile condividere le parole chiave riservate tra le domande e risposte e i segnalibri. Se un segnalibro e una domanda e risposta condividono una parola chiave o una parola chiave riservata, il segnalibro avrà sempre la precedenza e la domanda e risposta non verrà visualizzata.
    
## <a name="add-qa-settings"></a>Aggiungere le impostazioni delle domande e risposte

Le impostazioni delle domande e risposte offrono un maggior controllo su quando viene visualizzata una domanda e risposta e su chi la vede.
  
- Date
    
    Impostare una data di inizio e una data di fine facoltativa per controllare quando una domanda e risposta verrà pubblicata o quando scadrà.
    
- Paese/area geografica
    
    Se si selezionano paesi o aree geografiche, solo gli utenti in quelle posizioni vedranno la domanda e risposta.
    
- Gruppi
    
    Usare le impostazioni dei gruppi per rendere disponibile un risultato di domanda e risposta solo ai membri di un determinato gruppo. Ad esempio, se si creano le domande e risposte relative solo ai dipendenti del reparto risorse Umane, è possibile mappare questa impostazione al gruppo di sicurezza delle risorse Umane pertinente.
    
- Dispositivo e sistema operativo
    
    Se si selezionano tipi di dispositivi o sistemi operativi, solo gli utenti che usano quei dispositivi o sistemi operativi vedranno la domanda e risposta.
    
- Varianti mirate
    
    Usare questa impostazione per modificare il contenuto della domanda e risposta in base al dispositivo e alla posizione dell'utente.
    
## <a name="use-a-browser-extension-to-create-content"></a>Usare un'estensione del browser per creare contenuto

Scaricare e installare l'estensione del browser per autori di contenuti per Microsoft Edge o Chrome dalla sezione Strumenti del portale di amministrazione. Per usare l'estensione, accedere e passare alla pagina o al sito che si vuole aggiungere come domanda e risposta. Rivedere e modificare il contenuto suggerito, comprese le parole chiave, aggiungere eventuale altro contenuto e salvare la domanda e risposta.
  
Se vengono trovate più domande e risposte, esaminare ognuna di esse e stabilire se si vuole pubblicarla, salvarla come bozza o salvarle tutte come bozza.
  
## <a name="supported-html-tags"></a>Tag HTML supportati

È possibile usare contenuto HTML esistente o aggiungere tag HTML alla descrizione della risposta. I tag non supportati vengono ignorati.
  
- blockquote
    
- div
    
- em
    
- h1, h2, h3, and h4
    
- ol, ul, and li
    
- p
    
- pre
    
- span
    
- strong
    
- table, thead, tbody, tr, th, and td
    
- u
    
- a
    
- code
    
- br
    
- hr
    
- img

  

