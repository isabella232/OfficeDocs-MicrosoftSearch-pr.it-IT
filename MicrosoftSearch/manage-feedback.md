---
title: Gestione dei commenti e suggerimenti degli utenti
ms.author: lebhansa
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Esaminare e agire in base al feedback degli utenti in Microsoft Search
ms.openlocfilehash: 37ea70862cd4881170288339427f5ab1f150bf31
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702013"
---
# <a name="managing-user-feedback"></a>Gestione dei commenti e suggerimenti degli utenti

La creazione di un'esperienza di ricerca ottimale per gli utenti è una partnership tra Microsoft e l'amministratore della ricerca. Il feedback degli utenti ci consente di valutare continuamente il prodotto e ottimizzarlo per un'esperienza ottimale. Alcuni commenti e suggerimenti, tuttavia, sono meglio indirizzati dall'utente.

Microsoft offre ora strumenti che consentono di esaminare e gestire il feedback fornito dagli utenti sull'esperienza di ricerca.

## <a name="how-users-submit-feedback"></a>Modalità di invio del feedback da parte degli utenti

Poiché gli utenti dell'organizzazione Microsoft Search, possono avere feedback sull'esperienza. Quando fanno clic su un collegamento di feedback nella pagina dei risultati, possono categorizzare il proprio feedback e includere commenti aggiuntivi.

![Modulo di feedback globale.](media/feedback/feedback-global-dialog.png)

Gli utenti hanno anche la possibilità di inviare la query e altre informazioni di diagnostica, insieme alla categoria e ai commenti, a Microsoft. [Altre informazioni](https://privacy.microsoft.com/en-US/privacystatement) sulla privacy e su come proteggiamo questi dati. I dati di diagnostica contengono le informazioni più importanti che Microsoft deve usare per il miglioramento del prodotto.

La maggior parte degli invii di feedback viene visualizzata nella [sezione Feedback](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) dell'Microsoft Search di amministrazione. I commenti inviati con la categoria I **want to suggest an internal link** vengono visualizzati come segnalibri suggeriti nella sezione [Bookmarks](https://admin-ignite.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) e possono essere visualizzati filtrando lo **stato Suggerito.**

## <a name="review-feedback"></a>Commenti e suggerimenti

Nella pagina [Feedback](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) è possibile esaminare ed esportare il feedback inviato da persone dell'organizzazione negli ultimi 30 giorni. Una volta che un utente invia il feedback, verrà visualizzato in questo elenco entro 20 minuti. È possibile utilizzare il pulsante Aggiorna per verificare di avere a che fare con i dati più aggiornati

Utilizzando un filtro, è possibile visualizzare il feedback per tipi di risposta specifici. È inoltre possibile filtrare in base all'origine e all'intervallo di date.

È possibile utilizzare la casella di ricerca sopra l'elenco dei commenti e suggerimenti per cercare commenti e suggerimenti su una query specifica.

Nell'elenco dei commenti e suggerimenti, la colonna Verbatim indica anche il feedback dell'utente che include un commento o un suggerimento. Per leggerla, fare clic sulla query per aprire il **riquadro** Dettagli.

>[!NOTE]
>Durante l'implementazione iniziale nelle esperienze di ricerca di amministratori e utenti finali, potrebbero essere necessario fino a due settimane prima che gli elementi di feedback vengano visualizzati nel portale di amministrazione.

## <a name="update-feedback-state"></a>Aggiornare lo stato di feedback

Quando arriva il feedback, sarà in uno stato *Nuovo* e rimarrà lì fino a quando non lo cambi in *Risolto* o *Duplicato.*

Per modificare questo stato:

1. Accanto alla query, selezionare **Altre opzioni** (tre punti verticali).
1. Scegliere Contrassegna **come risolto o** Contrassegna **come duplicato dal menu.**
1. L'elenco verrà aggiornato e verrà visualizzato lo stato aggiornato.

Puoi anche aggiornare lo stato per più elementi, selezionarli e quindi selezionare Altre opzioni accanto a uno qualsiasi di questi elementi.

## <a name="export-feedback"></a>Esportare commenti e suggerimenti

Se vuoi condividere il feedback della ricerca con altri utenti o conservarli per più di 30 giorni, fai clic su **Esporta.** Verrà .csv automaticamente un file denominato Feedback con la data, ad esempio "Feedbacks_10_31_2020.csv".

## <a name="send-user-feedback-to-microsoft"></a>Inviare commenti e suggerimenti degli utenti a Microsoft

Per impostazione predefinita, tutti i commenti e suggerimenti degli utenti vengono inviati a Microsoft e vengono aggiunte all'utente. Per interrompere l'invio di commenti e suggerimenti a Microsoft, fare clic **su Gestisci impostazioni** e deselezionare la casella di controllo Invia **automaticamente feedback utente a Microsoft.** L'applicazione di questa modifica può richiedere fino a 24 ore.

Se si è deciso di non inviare automaticamente commenti e suggerimenti a Microsoft, è comunque possibile inviare singoli commenti e suggerimenti a Microsoft.

1. Seleziona il feedback che vuoi condividere.
1. Nella barra delle azioni seleziona Altro (tre puntini) e fai clic **su Invia feedback a Microsoft.**

1. Lo stato nella colonna Inviato a Microsoft verrà modificato in In sospeso. Quando il feedback viene inviato, verrà modificato in Sì.

Se condividi il feedback automaticamente o manualmente, non include mai query e altre informazioni di diagnostica per gli utenti che hanno scelto di non includere queste informazioni.

## <a name="suggestions-on-how-to-use-feedback"></a>Suggerimenti su come usare il feedback

L'amministratore della ricerca deve comprendere le persone principali dell'organizzazione e i tipi di contenuto con cui gli utenti interagiscono e ricercano in genere. Grazie a questa conoscenza, puoi usare il feedback per apportare miglioramenti mirati all'esperienza di ricerca degli utenti.

1. "Non ho trovato quello che cercavo" e un feedback simile può essere usato per identificare il contenuto desiderato dagli utenti, ma non è attualmente incluso nell'indice di ricerca. La determinazione di questo spesso richiede indagini e inferenza in base alla comprensione degli utenti. Una volta trovato, decidi quali metodi di inclusione del contenuto sarebbero più appropriati:
    1. I segnalibri sono utili per le origini di contenuto con una pagina di destinazione di alta qualità e una varietà limitata di termini di ricerca, in modo che la community di utenti otterrà un risultato di alta qualità dal segnalibro e potrà quindi trovare in modo efficiente ciò che sta cercando.
    1. D&A sono utili per singole risposte abbastanza frequenti, ma che non cambiano.
    1. I connettori sono utili per le origini di contenuto con un'ampia gamma di contenuti e un'ampia varietà di termini di ricerca.
1. "I risultati hanno richiesto troppo tempo per il caricamento" & "È stato rilevato un problema" potrebbero essere indicatori di un problema più ampio. La ricerca di questo feedback ogni giorno può essere utile e, se vengono visualizzati più casi, è possibile verificare l'esperienza di ricerca per se stessi e aprire un caso di supporto con Microsoft, se necessario. Questo tipo di feedback è importante anche per Microsoft ed è un ottimo motivo per inviarci tutti i commenti e suggerimenti.
1. "Voglio suggerire un collegamento interno" può essere valutato per essere aggiunto come segnalibri o contenuto connesso. Il tuo primo pensiero dovrebbe essere un segnalibro; se il segnalibro ha un utilizzo elevato, è possibile prendere in considerazione l'utilizzo di contenuto tramite un connettore per consentire un'esperienza di ricerca ancora più ricca.
