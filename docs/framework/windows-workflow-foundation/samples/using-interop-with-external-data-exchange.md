---
title: Utilisation d'Interop avec l'échange interne de données
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4acec4209ddadd181774ae754cb1d6b94a21685e
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2018
---
# <a name="using-interop-with-external-data-exchange"></a>Utilisation d'Interop avec l'échange interne de données
Le <xref:System.Activities.Statements.Interop> activité peut être utilisée pour exécuter des activités à partir de Windows Workflow Foundation (WF) dans [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] et [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3) et le flux de travail dans Windows Workflow Foundation dans [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4). Cet exemple montre comment configurer et exécuter un workflow WF3 qui utilise <xref:System.Workflow.Activities.ExternalDataExchangeService> (et les activités personnalisées correspondantes pour appeler les méthodes et gérer les événements) à l'aide de l'activité <xref:System.Activities.Statements.Interop> dans un service de workflow WF4.  
  
> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à la page [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les exemples [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a>Pour utiliser cet exemple  
  
1.  Ouvrez le fichier ExternalDataExchange.sln dans [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Pour créer l'exemple, appuyez sur Ctrl+Maj+B.  
  
3.  Pour exécuter l'exemple, appuyez sur F5.
