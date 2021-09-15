---
title: Confluence Cloud Graph connector for Microsoft Search
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare il connettore di Graph Confluence Cloud per Microsoft Search
ms.openlocfilehash: baf6139257c8bf8e40bc997e2a408efb4fc2549f
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375991"
---
<!---Previous ms.author: kam1 --->

# <a name="confluence-cloud-graph-connector-preview"></a>Confluence Cloud Graph Connector (Anteprima)

Confluence Cloud Graph connettore consente all'organizzazione di indicizzare il contenuto di confluenza. Dopo aver configurato i dati del connettore e dell'indice dal sito Confluence, gli utenti finali possono cercare tali contenuti in Microsoft Search.

>[!NOTE]
>Confluence Cloud Graph Connector è in anteprima. Se si desidera ottenere l'accesso anticipato per provarlo, iscriversi utilizzando [<b>questo modulo. </b>](https://forms.office.com/r/duLxv8Nf8U)  

Questo articolo è per Microsoft 365 amministratori o chiunque configura, esegue e monitora un connettore Graph Confluence Cloud. Integra le istruzioni generali fornite nell'articolo [Configurare il Graph connettore.](configure-connector.md) Se non è già stato fatto, leggere l'intero articolo Configurare il connettore Graph per comprendere il processo di configurazione generale.

Ogni passaggio del processo di installazione è elencato di seguito insieme a una nota che indica che è necessario seguire le [](#troubleshooting) istruzioni di configurazione generali o altre istruzioni che si applicano solo al connettore di Graph Confluence Cloud, incluse informazioni su Risoluzione dei problemi e [limitazioni.](#limitations)


## <a name="before-you-get-started"></a>Prima di iniziare
È necessario essere l'amministratore del tenant M365 dell'organizzazione e l'amministratore del sito di confluenza dell'organizzazione.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Passaggio 1: Aggiungere un connettore Graph nella interfaccia di amministrazione di Microsoft 365
Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="step-2-name-the-connection"></a>Passaggio 2: assegnare un nome alla connessione
Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="step-3-configure-the-connection-settings"></a>Passaggio 3: Configurare le impostazioni di connessione
Per connettersi al sito confluenza, utilizzare l'URL del sito. Un URL del sito cloud di confluenza in genere è simile a *https://<organization_name>.atlassian.net/*. È possibile scegliere Autenticazione di base o OAuth 2.0 (scelta consigliata) per eseguire l'autenticazione nel sito di confluenza.

### <a name="basic-auth"></a>Autenticazione di base
Immetti il nome utente dell'account (in genere l'ID di posta elettronica) e il token API per l'autenticazione tramite l'autenticazione di base. Per altre informazioni sulla generazione di un token API, fai riferimento alla documentazione di Atlassian su come gestire i token API per il [tuo account di Atlassian.](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

### <a name="oauth-20"></a>OAuth 2.0
Registra un'app in Confluence Cloud in modo che l'app Microsoft Search possa accedere all'istanza. Per ulteriori informazioni, vedere la documentazione del supporto atlante su come [abilitare OAuth 2.0.](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)

I passaggi seguenti forniscono indicazioni su come registrare l'app:

1. Accedi alla console [per sviluppatori di Atlassian](https://developer.atlassian.com/console/myapps/) con il tuo account amministratore di Atlassian Confluence.
2. Fare clic `Create` su e selezionare `OAuth 2.0 integration`
3. Specifica un nome appropriato per l'applicazione e crea la nuova app.
4. Passare al `Permissions` riquadro di spostamento a sinistra. Fare `Add` clic su per `Confluence API` . Dopo l'aggiunta, fare clic su e `Configure` aggiungere gli ambiti seguenti: , `Read Confluence space summary` , , , , e `Read Confluence content properties` `Read Confluence detailed content` `Read Confluence content summary` `Read content permission in Confluence` `Read user` `Read user groups` `Search Confluence content and space summaries` .
5. Passare al `Authorization` riquadro di spostamento a sinistra. Aggiungere l'URL di `https://gcs.office.com/v1.0/admin/oauth/callback` richiamata e salvare le modifiche.
6. Passare al `Settings` riquadro di spostamento a sinistra. Si otterrà il `Client ID` e `Secret` da questa pagina.

Durante la registrazione dell'app con i dettagli sopra riportati, ottieni **l'ID client** e **il segreto**. Completare il passaggio delle impostazioni di connessione usando questi passaggi.

## <a name="step-4-select-properties-and-filter-data"></a>Passaggio 4: Selezionare le proprietà e filtrare i dati

In questo passaggio è possibile aggiungere o rimuovere le proprietà disponibili dall'origine dati Confluence. Microsoft 365 ha già selezionato alcune proprietà per impostazione predefinita.

Con una stringa CQL (Confluence Query Language), è possibile specificare le condizioni per la sincronizzazione delle pagine. È come una **clausola Where** in un'istruzione **SQL Select.** Ad esempio, è possibile scegliere di indicizzare solo le pagine modificate negli ultimi due anni. Per informazioni sulla creazione di una stringa di query personalizzata, vedere [Ricerca avanzata tramite CQL.](https://developer.atlassian.com/server/confluence/advanced-searching-using-cql/) Per impostazione predefinita, tutti i blog e le pagine verranno indicizzati dal connettore.

Usa il pulsante dei risultati di anteprima per verificare i valori di esempio delle proprietà selezionate e della stringa CQL.

## <a name="step-5-manage-search-permissions"></a>Passaggio 5: Gestire le autorizzazioni di ricerca

Confluence Cloud Graph connector supporta le autorizzazioni di ricerca visibili a  **Tutti** o Solo gli utenti con **accesso a questa origine dati.** Se si sceglie **Tutti**, i dati indicizzati verranno visualizzati nei risultati della ricerca per tutti gli utenti. Se si sceglie **Solo gli utenti con accesso** a questa origine dati, i dati indicizzati verranno visualizzati nei risultati della ricerca per gli utenti che hanno accesso a tali origini.

In Confluence Cloud, le autorizzazioni di sicurezza per utenti e gruppi vengono definite utilizzando le autorizzazioni di spazio e le restrizioni di pagina. Confluence Cloud Graph Connector applica le autorizzazioni di spazio se non sono presenti restrizioni di pagina. Le restrizioni a livello di pagina, se presenti, avranno la precedenza sulle autorizzazioni per lo spazio.

Se si **sceglie** Solo gli utenti con accesso a questa origine dati, è necessario scegliere ulteriormente se il sito di confluenza dispone di utenti di cui è stato eseguito il provisioning di Azure Active Directory (AAD) o di utenti non AAD.

Per identificare l'opzione adatta all'organizzazione:

1. Scegliere **l'opzione AAD** se l'ID  di posta elettronica degli utenti di confluenza è uguale all'UPN (UserPrincipalName) degli utenti in AAD.
2. Scegliere **l'opzione Non-AAD** se l'ID  di posta elettronica degli utenti di confluenza è diverso da UserPrincipalName (UPN) degli utenti in AAD. 

>[!NOTE]
> * Se si sceglie AAD come tipo di origine dell'identità, il connettore mappa gli ID di posta elettronica degli utenti ottenuti da Confluence direttamente alla proprietà UPN da AAD.
> * Se hai scelto "Non-AAD" per il tipo di identità, vedi Eseguire il mapping delle identità [non di Azure AD](map-non-aad.md) per istruzioni sul mapping delle identità. È possibile utilizzare questa opzione per fornire l'espressione regolare di mapping da ID posta elettronica a UPN.

## <a name="step-6-assign-property-labels"></a>Passaggio 6: Assegnare etichette di proprietà

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="step-7-manage-schema"></a>Passaggio 7: Gestire lo schema

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

## <a name="step-8-choose-refresh-settings"></a>Passaggio 8: Scegliere le impostazioni di aggiornamento

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

>[!NOTE]
>Per gli aggiornamenti delle autorizzazioni di accesso, verrà applicata solo la ricerca per indicizzazione completa pianificata.

## <a name="step-9-review-connection"></a>Passaggio 9: Esaminare la connessione

Seguire le istruzioni generali [per l'installazione](./configure-connector.md).

Dopo aver pubblicato la connessione, è necessario personalizzare la pagina dei risultati della ricerca. Per informazioni sulla personalizzazione dei risultati della ricerca, vedere [Personalizzare la pagina dei risultati della ricerca.](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)

## <a name="troubleshooting"></a>Risoluzione dei problemi
Di seguito è riportato un elenco degli errori comuni rilevati durante la configurazione del connettore e dei possibili motivi.

| Passaggio di configurazione | Messaggio di errore | Possibili motivi |
| ------------ | ------------ | ------------ |
| Impostazioni di connessione | La richiesta non è valida o non è corretta. | URL del sito di confluenza non corretto |
| Impostazioni di connessione | Impossibile raggiungere il servizio cloud Confluence per il sito di confluenza. | URL del sito di confluenza non corretto |
| Impostazioni di connessione | Il client non dispone dell'autorizzazione per eseguire l'azione. | Token API non valido fornito per l'autenticazione di base |
| Selezionare le proprietà | Nessun messaggio di errore e nessun risultato di anteprima | Verificare se la query CQL è valida |

## <a name="limitations"></a>Limitazioni
Confluence Cloud Graph connector ha le seguenti limitazioni note nella versione più recente:

- Confluence Cloud Connector non indicizza i file allegati e i commenti.
- Le distribuzioni di Server di indicizzazione e Data Center verranno rilasciate come connettore separato.