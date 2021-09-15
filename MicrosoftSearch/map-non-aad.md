---
title: Mapping di identità non AAD
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Passaggi su come eseguire il mapping delle identità non AAD
ms.openlocfilehash: f433da10347ef59acf7675ec65da8acbd7f0f347
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "59334510"
---
# <a name="map-your-non-azure-ad-identities"></a>Mappare le identità non di Azure AD  

Questo articolo illustra i passaggi per eseguire il mapping delle identità non di Azure AD alle identità di Azure AD in modo che gli utenti dell'elenco di controllo di accesso (ACL) con identità non Azure AD possano visualizzare i risultati della ricerca dei connettori nell'ambito.

Questi passaggi sono rilevanti solo per gli amministratori della ricerca che configurano un connettore [Confluence Cloud,](confluence-cloud-connector.md) [ServiceNow Knowledge,](servicenow-knowledge-connector.md) [ServiceNow Catalog](servicenow-catalog-connector.md) o [Salesforce](salesforce-connector.md) da Microsoft con autorizzazioni di ricerca per "Solo le persone con accesso a questa origine dati" e il tipo di identità "Non-AAD".

>[!NOTE]
>Se si sta configurando un  connettore Salesforce e si seleziona Solo le persone con accesso a questa origine dati e tipo di identità **AAD** nella schermata delle autorizzazioni di ricerca, fare riferimento all'articolo [Mappare](map-aad.md) le identità di Azure AD per la procedura su come eseguire il mapping delle identità di Azure AD.  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a>Passaggi per il mapping delle proprietà non di Azure AD

### <a name="1-select-an-azure-ad-user-property"></a>1. Selezionare una proprietà utente di Azure AD  

È possibile selezionare la proprietà utente di Azure AD per cui si sta creando il mapping. Questa è la proprietà di destinazione a cui si intende mappare le identità non di Azure AD.  

È possibile selezionare una delle proprietà di Azure AD seguenti:

| Azure AD, proprietà    | Definizione           | Esempio         |
| :------------------- | :------------------- |:--------------- |
| Nome dell'entità utente (UPN)  | Un UPN è costituito da un prefisso UPN (il nome dell'account utente) e da un suffisso UPN (un nome di dominio DNS). Il prefisso viene unito al suffisso utilizzando il simbolo "@". | us1@contoso.onmicrosoft.com |
| Azure AD ID                 | Un ID di Azure AD per un determinato utente è il GUID univoco dell'utente.                 | 58006c96-9e6e-45ea-8c88-4a56851eefad            |
| ID di sicurezza (SID) di Active Directory                  | SID (Security Identifier) è un identificatore univoco utilizzato da Active Directory per identificare gli oggetti come entità di sicurezza.                  | S-1-5-21-453406510-812318184-4183662089             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a>2. Selezionare le proprietà utente non di Azure AD da mappare

È possibile selezionare proprietà non di Azure AD estrarte dall'origine dati a cui applicare espressioni regolari. Per ulteriori informazioni su dove trovare queste proprietà nell'origine dati, vedere le pagine [Confluence Cloud,](confluence-cloud-connector.md) [ServiceNow Knowledge,](servicenow-knowledge-connector.md) [ServiceNow Catalog](servicenow-catalog-connector.md) e [Salesforce.](salesforce-connector.md)  

È possibile selezionare una proprietà utente non di Azure AD nell'elenco a discesa e fornire un'espressione regolare da applicare a tali valori di proprietà utente.

Di seguito sono riportati alcuni esempi di espressioni regolari e i relativi output applicati a una stringa di esempio: 

| Stringa di esempio                  | Espressione regolare                 | Output dell'espressione regolare nella stringa di esempio           |
| :------------------- | :------------------- |:---------------|
| Alexis Vasquez  | .* | Alexis Vasquez |
| Alexis Vasquez                 | ..$                 | ez            |
| Alexis Vasquez                  | (\w+)$                  | Vasquez             |

È possibile aggiungere tutte le proprietà utente non di Azure AD per cui si desiderano espressioni. È possibile applicare espressioni regolari diverse alla stessa proprietà utente se la formula finale lo garantisce.  

### <a name="3-create-formula-to-complete-mapping"></a>3. Creare la formula per completare il mapping

È possibile combinare gli output delle espressioni regolari applicate a ognuna delle proprietà utente non di Azure AD per formare la proprietà di Azure AD selezionata nel passaggio 1.

Nella casella della formula " " corrisponde all'output dell'espressione regolare applicata alla prima proprietà {0} non di Azure AD selezionata.  " {1} corrisponde all'output dell'espressione regolare applicata alla *seconda* proprietà non di Azure AD selezionata. " {2} corrisponde all'output dell'espressione regolare applicata alla *terza* proprietà non di Azure AD e così via.  

Di seguito sono riportati alcuni esempi di formule con output di espressioni regolari di esempio e output di formule: 

| Formula di esempio                  | Valore {0} dell'utente di esempio                 | Valore {1} dell'utente di esempio           | Output della formula                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1} @contoso.com  | firstname | lastname |firstname.lastname@contoso.com
| {0}@domain.com                 | userid                 |             |userid@domain.com

Dopo aver fornito la formula,  è possibile fare clic su Anteprima per visualizzare un'anteprima di 5 utenti casuali dall'origine dati con i rispettivi mapping utente applicati. L'output dell'anteprima include il valore delle proprietà utente non di Azure AD selezionate nel passaggio 2 per tali utenti e l'output della formula finale fornita nel passaggio 3 per tale utente. Indica inoltre se l'output della formula può essere risolto in un utente di Azure AD nel tenant tramite un'icona "Operazione riuscita" o "Operazione non riuscita".  

>[!NOTE]
>È comunque possibile procedere con la creazione della connessione se uno o più mapping utente hanno lo stato "Non riuscito" dopo aver fatto clic su **Anteprima.** L'anteprima mostra 5 utenti casuali e i relativi mapping dall'origine dati. Se il mapping specificato non esegue il mapping di tutti gli utenti, è possibile che si verifichi questo caso.

## <a name="sample-non-azure-ad-mapping"></a>Esempio di mapping non Azure AD

Vedi lo snapshot seguente per un esempio di mapping non Azure AD.

![Snapshot di esempio di come compilare la pagina di mapping non di Azure AD.](media/non-aad-mapping.png)

## <a name="limitations"></a>Limitazioni  

- È supportato un solo mapping per tutti gli utenti. I mapping condizionali non sono supportati.  

- Non è possibile modificare il mapping dopo la pubblicazione della connessione.  

- Solo le espressioni basate su regex per le proprietà utente non AAD sono attualmente supportate per la trasformazione.

- È possibile scegliere di mappare solo 3 identità di Azure AD (UPN, ID Azure AD e SID AD).