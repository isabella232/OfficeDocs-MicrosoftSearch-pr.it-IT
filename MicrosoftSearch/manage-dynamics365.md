---
title: Ricerca federativa dynamics 365 (anteprima)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
description: Gestire la modalità di visualizzazione del contenuto di Dynamics 365 nei risultati della ricerca
ms.openlocfilehash: 8a87e4026937ba01132c10815dc2f91d27da79c9
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973644"
---
# <a name="dynamics-365-federation-search-preview"></a>Ricerca federativa dynamics 365 (anteprima)

## <a name="microsoft-search-federation-and-connectors"></a>Microsoft Search Federazione e connettori

Per rendere più Microsoft Search, stiamo introducendo la federazione Microsoft Search federazione. Con la ricerca federata, le organizzazioni possono rendere accessibili i dati in questi scenari in Microsoft Search:

* Dati nei sistemi soggetti a rigorosi requisiti di conformità
* Dati che non possono uscire dai limiti del sistema
* Dati sensibili archiviati in locale che l'organizzazione non desidera indicizzare nel cloud

I dati a cui si accede tramite una connessione di ricerca federata non vengono indicizzati Microsoft Search. Inoltre, utilizzando i connettori predefiniti di Microsoft, è facile configurare le connessioni di ricerca federate. Il connettore Dynamics 365 è attualmente in anteprima. Se vuoi partecipare all'anteprima, contattaci [all'indirizzo aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview). Per l'intervallo di tempo di [rilascio, vedere Microsoft Search roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=Microsoft%20Search).

## <a name="dynamics-365-federation-connector"></a>Connettore di federazione dynamics 365

Microsoft Dynamics 365 è una linea di applicazioni aziendali intelligenti progettate per la pianificazione delle risorse aziendali e la gestione delle relazioni con i clienti. Con la federazione di Dynamics 365, Microsoft Search offre un'esperienza di ricerca senza problemi, consentendo agli utenti di trovare facilmente i dati aziendali e dei clienti più rilevanti archiviati in Dynamics 365. Il connettore di federazione di Dynamics 365 offre alcuni vantaggi principali:

* **Facile da amministrare:** Processo semplificato per configurare e gestire la connessione di ricerca a un'istanza di Dynamics 365.
* **Facile da usare:** Gli utenti possono trovare facilmente e rapidamente le informazioni chiave archiviate in Dynamics 365, inclusi account, contatti, opportunità aperte e altro ancora.
* **Contenuto più ricco:** Per rendere più utili i risultati della ricerca di Dynamics 365, includono informazioni chiave come lead, contatti e dettagli dell'account.
* **Protezione dei dati incorporata:** I risultati di Dynamics 365 verranno visualizzati solo per gli utenti che hanno accesso all'istanza connessa.
* **Esperienza di ricerca unificata:** Per mantenere un'esperienza coerente, i risultati di Dynamics 365 sono coerenti in tutti i punti di ingresso della ricerca. Ovunque si eserciti la ricerca, si otterrà gli stessi risultati con lo stesso aspetto.

## <a name="what-users-experience"></a>Esperienza degli utenti

Le risposte di Dynamics 365 vengono visualizzate nei risultati di ricerca in tutti i Microsoft Search canvas, tra cui SharePoint Online, Bing e Office.

:::image type="content" alt-text="Screenshot delle risposte di Dynamics 365 su SharePoint, Bing e Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

Dalla risposta, è facile vedere altri risultati di ricerca di Dynamics 365 usando il **collegamento Altri risultati di Dynamics 365.** Porta gli utenti a una pagina dei risultati di Dynamics 365 dedicata con più risultati rilevanti per la query.

:::image type="content" alt-text="Screenshot of Dynamics 365 vertical and results on SharePoint, Bing, and Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

Se si fa clic o si tocca un risultato, viene aperto Dynamics 365 e vengono visualizzate le informazioni dettagliate.

:::image type="content" alt-text="Screenshot della pagina dei dettagli in Dynamics 365." source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

Indipendentemente da dove gli utenti avviano la ricerca, l'esperienza sarà coerente e consentirà loro di trovare rapidamente i risultati di Dynamics 365 più pertinenti. Per una dimostrazione, vedere il video di Microsoft Build 2021.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4P83t]

## <a name="supported-query-patterns"></a>Modelli di query supportati

Entrambe le query in linguaggio naturale e nome prodotto sono supportate quando si usa Microsoft Search per trovare i risultati di Dynamics 365. Inoltre, per le query di Dynamics 365 non viene distinzione tra maiuscole e minuscole. Utilizzare modelli di linguaggio naturale per trovare contatti, account e opportunità, in base al nome o alla posizione del cliente, e altre query utilizzate di frequente. Ecco alcuni esempi:

* Who è il contatto per Contoso
* Opportunità aperte per Contoso
* Quali sono le opportunità aperte a Seattle
* Quali sono gli account a Seattle
* Quali sono i contatti di Seattle
* Quali sono i lead che chiudono questo mese
* Chiamata telefonica ad alta priorità
* Contatti mancanti messaggi di posta elettronica

I modelli di nome prodotto supportano un intervallo di applicazioni Dynamics 365 e attiveranno i risultati di Dynamics 365 indipendentemente dalla posizione in cui vengono visualizzati in una query:

* D365
* Dynamics 365
* Dynamics365
* Dynamics CRM
* Dynamics Sales
* Servizio clienti Dynamics
* Dynamics Service
* Dynamics Field Service

## <a name="configure-the-dynamics-365-connector"></a>Configurare il connettore Dynamics 365

Con questa semplice configurazione, è possibile abilitare l'esperienza di ricerca della federazione dynamics 365 per gli utenti dell'organizzazione.

1. Nella finestra [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com), passare a [Origini dati](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).

2. Nella sezione App e servizi Microsoft, in Microsoft Dynamics 365, selezionare **Gestisci** per aprire il pannello di Microsoft Dynamics 365.

3. Abilitare il connettore per l'organizzazione.

4. **Nell'elenco Endpoint** seleziona l'ambiente Dynamics 365.

5. In **ID connessione** immettere un ID univoco per la connessione.

6. Esaminare e selezionare la casella di controllo consenso.

7. Selezionare **Salva per** completare la configurazione della connessione.

:::image type="content" alt-text="Screenshot del pannello di configurazione di Dynamics 365 nella interfaccia di amministrazione di Microsoft 365." source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

Al termine dell'installazione, le risposte e il verticale di Dynamics 365 verranno visualizzati solo per gli utenti con una licenza dynamics 365 valida e l'accesso all'ambiente Dynamics 365 connesso. In qualsiasi momento, è possibile tornare a queste impostazioni e modificare l'ambiente dell'endpoint di connessione o disattivare la connessione.
