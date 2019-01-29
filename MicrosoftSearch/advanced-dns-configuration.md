---
title: Configurazione DNS avanzata
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
description: Garantire un'esperienza di accesso semplice per gli utenti mediante la configurazione di server DNS utilizzando un record CNAME
ms.openlocfilehash: fa797b95f346d6d03bd020da146bb330c715e392
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612441"
---
# <a name="advanced-dns-configuration"></a>Configurazione DNS avanzata

Per garantire Bing possono sempre identificare gli utenti all'interno dell'organizzazione e correttamente accedere li al proprio account di lavoro o della scuola, configurare i server DNS interno o server proxy per risolvere da `www.bing.com` a `ms.bing.com`. A tale scopo, creare una voce DNS per `www.bing.com` da un record CNAME per `ms.bing.com`.
  
****

|**Nome**|**Tipo**|**Valore**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
Utilizzo di un record CNAME anziché l'indirizzo IP è preferibile dopo un record CNAME continuerà a funzionare se viene modificato l'indirizzo IP. Dopo aver apportato la modifica DNS, i risultati continuerà a essere visualizzato agli utenti come se provenire da `www.bing.com`. 
  
Questo non richiede configurazioni aggiuntive nei computer client e offre un'esperienza trasparente per gli utenti. Quando si passa a `bing.com`, si verrà automaticamente eseguito l'accesso in più coerente e se non possono essere firmati automatico, verrà richiesto di farlo.
