---
title: Connettore Salesforce Graph per Microsoft Search
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore Salesforce Graph per Microsoft Search
ms.openlocfilehash: 6771bc0b234bc2570a8b1fa7174b9b9244cf3958
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097449"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a>Connettore grafico Salesforce (anteprima)

Il connettore Grafico Salesforce consente all'organizzazione di indicizzare gli oggetti Contatti, Opportunità, Lead e Account nell'istanza salesforce. Dopo aver configurato il connettore e il contenuto dell'indice da Salesforce, gli utenti finali possono cercare tali elementi da qualsiasi client Microsoft Search.

> [!NOTE]
> Leggere [**l'articolo setup for your Graph connector**](configure-connector.md) to understand the general Graph connectors setup process.

Questo articolo è per tutti gli utenti che configurano, eseere e monitorano un connettore Grafico Salesforce. Integra il processo di configurazione generale e mostra le istruzioni applicabili solo per il connettore Grafico Salesforce. In questo articolo sono inoltre incluse informazioni [sulle limitazioni.](#limitations)

>[!IMPORTANT]
>Il connettore Salesforce Graph attualmente supporta Estate '19 o versione successiva.

## <a name="before-you-get-started"></a>Prima di iniziare

Per connettersi all'istanza di Salesforce, è necessario l'URL dell'istanza di Salesforce, l'ID client e il segreto client per l'autenticazione OAuth. La procedura seguente illustra come l'utente o l'amministratore di Salesforce può ottenere queste informazioni dall'account Salesforce:

- Accedere all'istanza di Salesforce e passare al programma di installazione

- Passa a App -> App Manager.

- Selezionare **Nuova app connessa.**

- Completare la sezione API come segue:

    - Selezionare la casella di controllo **Abilita impostazioni Oauth.**

    - Specificare l'URL di richiamata come: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)

    - Selezionare questi ambiti OAuth necessari.

        - Accedere e gestire i dati (api)

        - Eseguire richieste per conto dell'utente in qualsiasi momento (refresh_token, offline_access)

    - Selezionare la casella di controllo **Richiedi segreto per il flusso del server Web.**

    - Salva l'app.
    
      > [!div class="mx-imgBorder"]
      > ![Sezione API nell'istanza salesforce dopo che l'amministratore ha immesso tutte le configurazioni necessarie elencate in precedenza.](media/salesforce-connector/sf1.png)

- Copiare la chiave consumer e il segreto consumer. Queste informazioni verranno utilizzate come ID client e segreto client quando si configurano le impostazioni di connessione per il connettore Graph nel portale di amministrazione di Microsoft 365.

  > [!div class="mx-imgBorder"]
  > ![Risultati restituiti dalla sezione API nell'istanza salesforce dopo che l'amministratore ha inviato tutte le configurazioni necessarie. Consumer Key si trova nella parte superiore della colonna sinistra e Consumer Secret si trova nella parte superiore della colonna destra.](media/salesforce-connector/clientsecret.png)
  
- Prima di chiudere l'istanza di Salesforce, segui questi passaggi per assicurarti che i token di aggiornamento non scadono:
    - Passare ad App -> App Manager
    - Trova l'app creata e seleziona l'elenco a discesa a destra. Selezionare **Gestisci**
    - Selezionare **i criteri di modifica**
    - Per i criteri di token di aggiornamento, selezionare **Aggiorna token valido fino a quando non viene revocato**

  > [!div class="mx-imgBorder"]
  > ![Selezionare il criterio di aggiornamento token denominato "Il token di aggiornamento è valido fino a quando non viene revocato"](media/salesforce-connector/oauthpolicies.png)

È ora possibile utilizzare [l'interfaccia di amministrazione di M365](https://admin.microsoft.com/) per completare il resto del processo di configurazione per il connettore Graph.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nell'interfaccia di amministrazione di Microsoft 365

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Passaggio 2: Assegnare un nome alla connessione

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: Configurare le impostazioni di connessione

Per l'URL dell'istanza, utilizzare https://[dominio].my.salesforce.com dove dominio sarebbe il dominio Salesforce per l'organizzazione.

Immetti l'ID client e il segreto client ottenuti dall'istanza di Salesforce e seleziona Accedi.

La prima volta che si tenta di accedere con queste impostazioni, viene visualizzato un popup che richiede di accedere a Salesforce con il nome utente e la password di amministratore. Lo screenshot seguente mostra il popup. Immetti le credenziali e seleziona "Accedi".

  ![Login pop up asking for Username and password.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  >Se il popup non viene visualizzato, è possibile che venga bloccato nel browser, pertanto è necessario consentire i popup e i reindirizzamenti.

Verificare che la connessione sia stata eseguita correttamente cercando un banner verde che indica "Connessione riuscita" come illustrato nello screenshot seguente.

  > [!div class="mx-imgBorder"]
  > ![Screenshot dell'accesso riuscito. Il banner verde che indica "Connessione riuscita" si trova sotto il campo per l'URL dell'istanza salesforce](media/salesforce-connector/sf5.png)

## <a name="step-4-manage-search-permissions"></a>Passaggio 4: Gestire le autorizzazioni di ricerca

Sarà necessario scegliere quali utenti potranno visualizzare i risultati della ricerca da questa origine dati. Se si consente solo a determinati utenti di Azure Active Directory (Azure AD) o non di Azure AD di visualizzare i risultati della ricerca, assicurarsi di mappare le identità.

## <a name="step-4a-select-permissions"></a>Passaggio 4a: Selezionare le autorizzazioni

È possibile scegliere di inserire elenchi di controllo di accesso (ACL) dall'istanza salesforce oppure consentire a tutti gli utenti dell'organizzazione di visualizzare i risultati della ricerca da questa origine dati. Gli elenchi di controllo di accesso possono includere identità di Azure Active Directory (AAD) (utenti federati da Azure AD a Salesforce), identità non Azure AD (utenti Salesforce nativi con identità corrispondenti in Azure AD) o entrambe.

>[!NOTE]
>Se si utilizza un provider di identità di terze parti come ID ping o secureAuth, è necessario selezionare "non AAD" come tipo di identità.

> [!div class="mx-imgBorder"]
> ![Schermata Di selezione delle autorizzazioni completata da un amministratore. L'amministratore ha selezionato l'opzione "Solo le persone con accesso a questa origine dati" e ha anche selezionato "AAD" da un menu a discesa di tipi di identità.](media/salesforce-connector/sf6.png)

Se si è scelto di inserire un elenco di controllo di accesso dall'istanza di Salesforce e si è selezionato "non-AAD" per il tipo di identità, vedere Eseguire il mapping delle identità [non azure AD](map-non-aad.md) per istruzioni sul mapping delle identità.

## <a name="step-4b-map-aad-identities"></a>Passaggio 4b: Mappare le identità AAD

Se si è scelto di inserire un elenco di controllo di accesso dall'istanza di Salesforce e si è selezionato "AAD" per il tipo di identità, vedere Eseguire il mapping delle identità di [Azure AD](map-aad.md) per istruzioni sul mapping delle identità. Per informazioni su come configurare Azure AD SSO per Salesforce, vedere questa [esercitazione.](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial)

## <a name="step-5-assign-property-labels"></a>Passaggio 5: Assegnare etichette di proprietà

Puoi assegnare una proprietà di origine a ogni etichetta scegliendo da un menu di opzioni. Anche se questo passaggio non è obbligatorio, la presenza di alcune etichette di proprietà migliorerà la pertinenza della ricerca e garantirà risultati di ricerca migliori per gli utenti finali. Per impostazione predefinita, ad alcune etichette come "Title", "URL", "CreatedBy" e "LastModifiedBy" sono già state assegnate proprietà di origine.

## <a name="step-6-manage-schema"></a>Passaggio 6: Gestire lo schema

È possibile selezionare le proprietà di origine da indicizzare in modo che siano visualizzate nei risultati della ricerca. Per impostazione predefinita, la Connessione guidata seleziona uno schema di ricerca basato su un set di proprietà di origine. È possibile modificarlo selezionando le caselle di controllo per ogni proprietà e attributo nella pagina dello schema di ricerca. Gli attributi dello schema di ricerca includono ricerca, query, recupero e affinamento ricerca.
Affinamento consente di definire le proprietà che possono essere successivamente utilizzate come criteri di affinamento ricerca o filtri personalizzati nell'esperienza di ricerca.  

> [!div class="mx-imgBorder"]
> ![Selezionare lo schema per ogni proprietà di origine. Le opzioni sono Query, Ricerca, Recupera e Affina](media/salesforce-connector/sf9.png)

## <a name="step-7-set-the-refresh-schedule"></a>Passaggio 7: Impostare la pianificazione dell'aggiornamento

Il connettore Salesforce supporta solo le pianificazioni di aggiornamento per le ricerche per indicizzazione complete attualmente.

>[!IMPORTANT]
>Una ricerca per indicizzazione completa consente di individuare gli oggetti eliminati e gli utenti precedentemente sincronizzati con l'indice di Microsoft Search.

La pianificazione consigliata è una settimana per una ricerca per indicizzazione completa.

## <a name="step-8-review-connection"></a>Passaggio 8: esaminare la connessione

Seguire le istruzioni [generali per l'installazione.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitazioni

- Il connettore Graph attualmente non supporta la condivisione e la condivisione basata sul territorio basata su Apex tramite gruppi personali di Salesforce.
- Esiste un bug noto nell'API Salesforce utilizzata dal connettore Graph, in cui le impostazioni predefinite private a livello di organizzazione per i lead non sono attualmente rispettate.  
- Se per un profilo è impostata la sicurezza a livello di campo (FLS, Field Level Security), il connettore Graph non inserisce tale campo per i profili nell'organizzazione Salesforce. Di conseguenza, gli utenti non saranno in grado di cercare valori per tali campi, né verranno visualizzati nei risultati.  
- Nella schermata Gestisci schema questi nomi di proprietà standard comuni sono elencati una sola volta, le opzioni sono **Query,** **Ricerca,** Recupera e Affina e si applicano a tutti o nessuno.
    - Nome
    - URL
    - Descrizione
    - Fax
    - Telefono
    - MobilePhone
    - Posta elettronica
    - Tipo
    - Titolo
    - AccountId
    - AccountName
    - AccountUrl
    - AccountOwner
    - AccountOwnerUrl
    - Proprietario
    - OwnerUrl
    - CreatedBy
    - CreatedByUrl
    - LastModifiedBy
    - LastModifiedByUrl
    - LastModifiedDate
    - ObjectName
