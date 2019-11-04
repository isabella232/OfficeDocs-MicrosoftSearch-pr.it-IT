---
title: Microsoft SQL Connector per Microsoft Search
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurare Microsoft SQL Connector per Microsoft Search.
ms.openlocfilehash: a5e0b26277345814ed095b54583ea635341295ad
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949839"
---
# <a name="microsoft-sql-server-connector"></a>Connettore Microsoft SQL Server

Con un connettore di Microsoft SQL Server, l'organizzazione può individuare e indicizzare i dati da un database di SQL Server locale. Il connettore indicizza il contenuto specificato in Microsoft Search. Per mantenere l'indice aggiornato con i dati di origine, supporta le ricerche per indicizzazione periodiche complete e incrementali. Con il connettore SQL Server, è anche possibile limitare l'accesso ai risultati della ricerca per alcuni utenti.

Questo articolo è per gli amministratori di Microsoft 365 o per tutti coloro che configurano, eseguono e monitorano un connettore di Microsoft SQL Server. In questo articolo viene illustrato come configurare le funzionalità di connettore e connettore, le limitazioni e le tecniche di risoluzione dei problemi.

## <a name="install-a-data-gateway"></a>Installare un gateway di dati
Per accedere ai dati di terze parti, è necessario installare e configurare un gateway Microsoft Power BI. Per ulteriori informazioni, vedere [Install and on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) .  

## <a name="connect-to-a-data-source"></a>Connettersi a un'origine dati
Per connettere il connettore Microsoft SQL Server a un'origine dati, è necessario configurare il server di database che si desidera sottoporre a ricerca per indicizzazione e il gateway locale. È quindi possibile connettersi al database con il metodo di autenticazione necessario.

> [!NOTE]
> È necessario che il database esegua SQL Server versione 2008 o successiva.

Per eseguire la ricerca nel contenuto del database, è necessario specificare le query SQL quando si configura il connettore. Queste query SQL devono assegnare un nome a tutte le colonne di database che si desidera indicizzare, ad esempio le proprietà di origine, compresi i join SQL che è necessario eseguire per ottenere tutte le colonne. Per limitare l'accesso ai risultati della ricerca, è necessario specificare gli elenchi di controllo di accesso (ACL, Access Control List) con query SQL quando si configura il connettore di Microsoft SQL Server.

## <a name="full-crawl-required"></a>Ricerca per indicizzazione completa (obbligatorio)
In questo passaggio viene configurata la query SQL che esegue una ricerca per indicizzazione completa del database. La **ricerca per**indicizzazione completa consente di selezionare tutte le colonne o le proprietà che si desidera rendere **Queryable**, **reperibili o recuperabili**. È inoltre possibile specificare le colonne ACL per limitare l'accesso ai risultati della ricerca a utenti o gruppi specifici.

> [!Tip]
> Per ottenere tutte le colonne necessarie, è possibile partecipare a più tabelle.

![Script che mostra OrderTable e AclTable con proprietà di esempio](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Selezionare le colonne di dati (obbligatorio) e le colonne ACL (facoltativo)
In questo esempio viene illustrata la selezione di cinque colonne di dati che contengono i dati per la ricerca: OrderId, OrderTitle, OrderDesc, CreatedDateTime ed andeleted. Per impostare le autorizzazioni di visualizzazione per ogni riga di dati, è facoltativamente possibile selezionare le colonne ACL seguenti: AllowedUsers, AllowedGroups, DeniedUsers e DeniedGroups. Tutte queste **colonne di dati**possono essere rese **Queryable**, reperibili o **recuperabili**.

Selezionare colonne di dati come illustrato in questa query di esempio:`SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

### <a name="watermark-required"></a>Filigrana (obbligatoria)
Per evitare sovraccarichi del database, il connettore esegue il batch e riprende le query di ricerca per indicizzazione complete con una colonna di filigrana full-crawl. Se si utilizza il valore della colonna filigrana, ogni batch successivo viene recuperato e l'esecuzione di query viene ripresa dall'ultimo checkpoint. In sostanza si tratta di un meccanismo per controllare l'aggiornamento dei dati per le ricerche per indicizzazione complete.

Creare frammenti di query per le filigrane come illustrato negli esempi seguenti:
* `WHERE (CreatedDateTime > @watermark)`. Citare il nome della colonna della filigrana `@watermark`con la parola chiave riservata. Se l'ordinamento della colonna della filigrana è crescente, utilizzare `>`; in caso contrario `<`, utilizzare.
* `ORDER BY CreatedDateTime ASC`. Ordinare la colonna della filigrana in ordine crescente o decrescente.

Nella configurazione illustrata nella figura seguente, `CreatedDateTime` è la colonna della filigrana selezionata. Per recuperare il primo batch di righe, specificare il tipo di dati della colonna filigrana. In questo caso, il tipo di dati `DateTime`è.

![](media/MSSQL-watermark.png)

La prima query recupera la prima **N** di righe utilizzando: "CreatedDateTime > January 1, 1753 00:00:00" (valore minimo del tipo di dati DateTime). Dopo il recupero del primo batch, il valore massimo `CreatedDateTime` restituito nel batch viene salvato come checkpoint se le righe sono ordinate in ordine crescente. Un esempio è il 1 ° marzo 2019 03:00:00. Viene quindi recuperato il batch successivo di **N** righe utilizzando "CreatedDateTime > 1 marzo 2019 03:00:00" nella query.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorare le righe eliminate temporaneamente (facoltativo)
Per escludere la possibilità di indicizzare le righe eliminate temporaneamente nel database, specificare il nome e il valore della colonna di eliminazione temporanea che indica che la riga è stata eliminata.

![Soft delete Settings: "soft delete column" e "value of soft delete column che indica una riga eliminata"](media/MSSQL-softdelete.png)

## <a name="incremental-crawl-optional"></a>Ricerca per indicizzazione incrementale (facoltativa)
In questo passaggio facoltativo, fornire una query SQL per eseguire una ricerca per indicizzazione incrementale del database. Con questa query, il connettore Microsoft SQL Server apporta le modifiche apportate ai dati dall'ultima ricerca per indicizzazione incrementale. Come **nella ricerca per**indicizzazione completa, selezionare tutte le colonne che si desidera rendere **Queryable**, reperibili o **recuperabili**. Specificare lo stesso insieme di colonne ACL specificato nella query di ricerca per indicizzazione completa.

I componenti nell'immagine seguente sono simili ai componenti di ricerca per indicizzazione completi con una sola eccezione. In questo caso, "ModifiedDateTime" è la colonna della filigrana selezionata. Esaminare i [passaggi per la ricerca per indicizzazione completa](#full-crawl-required) per informazioni su come scrivere la query di ricerca per indicizzazione incrementale e vedere come esempio l'immagine seguente.

![Script di ricerca per indicizzazione incrementale che mostra OrderTable, AclTable e proprietà di esempio che è possibile utilizzare.](media/MSSQL-incrcrawl.png)

## <a name="limitations"></a>Limitazioni
Il connettore di Microsoft SQL Server presenta queste limitazioni nella versione di anteprima:
* È necessario che il database locale esegua SQL Server versione 2008 o successiva.
* Gli elenchi ACL sono supportati solo utilizzando un nome dell'entità utente (UPN), Azure Active Directory (Azure AD) o la sicurezza di Active Directory.
* L'indicizzazione del contenuto RTF all'interno delle colonne di database non è supportata. Esempi di contenuto di questo tipo sono HTML, JSON, XML, BLOB e analisi dei documenti che esistono come collegamenti all'interno delle colonne di database.

