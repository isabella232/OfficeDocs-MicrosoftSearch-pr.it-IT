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
ROBOTS: NoIndex
description: Per garantire un'esperienza di accesso semplificata per gli utenti, è possibile configurare il server DNS con un record CNAME
ms.openlocfilehash: 05562bd9379af395ee305ffebdddbf7bfcd1e835
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727898"
---
# <a name="advanced-dns-configuration"></a>Configurazione DNS avanzata


Per essere certi che Bing possa sempre identificare gli utenti dell'organizzazione e consentire loro di accedere all'account aziendale o dell'istituto di istruzione, configurare il server DNS interno o il server proxy per la risoluzione di `www.bing.com` in `ms.bing.com`. A questo scopo, creare una voce DNS per `www.bing.com` da usare come record CNAME per `ms.bing.com`.
  
****

|**Nome**|**Tipo**|**Valore**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |Record CNAME  <br/> |`ms.bing.com`  <br/> |
   
L'uso di un record CNAME in alternativa all'indirizzo IP è da preferirsi perché un record CNAME continuerà a funzionare anche in caso di modifica dell'indirizzo IP. Dopo aver apportato questa modifica al server DNS, i risultati continueranno a essere visualizzati come se provenissero da `www.bing.com`. 
  
Questo approccio non richiede alcuna configurazione aggiuntiva nei computer client e offre un'esperienza semplificata per gli utenti. Quando gli utenti visitano `bing.com`, l'accesso verrà eseguito quasi sempre automaticamente. Nel caso in cui non fosse possibile accedere automaticamente, verrà visualizzata la richiesta di accesso.
