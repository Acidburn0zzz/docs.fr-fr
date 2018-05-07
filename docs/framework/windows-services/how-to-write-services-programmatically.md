---
title: 'Comment : écrire les services par programmation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
author: ghogen
manager: douge
ms.openlocfilehash: 99fd44723bba21127e2a5e0ba3e9bfc4b90b52d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-services-programmatically"></a>Comment : écrire les services par programmation
Si vous choisissez de ne pas utiliser le modèle de projet de Service Windows, vous pouvez écrire vos propres services en définissant l’héritage et autres éléments d’infrastructure vous-même. Lorsque vous créez un service par programme, vous devez effectuer plusieurs étapes qui prendrait autrement en charge le modèle pour vous :  
  
-   Vous devez configurer votre classe de service d’hériter la <xref:System.ServiceProcess.ServiceBase> classe.  
  
-   Vous devez créer un `Main` méthode pour votre projet de service qui définit les services à exécuter et les appels le <xref:System.ServiceProcess.ServiceBase.Run%2A> méthode dessus.  
  
-   Vous devez substituer la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> et <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procédures et remplissage dans n’importe quel code souhaité pour s’exécuter.  
  
### <a name="to-write-a-service-programmatically"></a>Pour créer un service par programme  
  
1.  Créer un projet vide et une référence aux espaces de noms nécessaires en suivant ces étapes :  
  
    1.  Dans **l’Explorateur de solutions**, cliquez sur le **références** nœud et cliquez sur **ajouter une référence**.  
  
    2.  Sur le **.NET Framework** onglet, accédez à **System.dll** et cliquez sur **sélectionnez**.  
  
    3.  Faites défiler vers **sur System.Diagnostics.dll** et cliquez sur **sélectionnez**.  
  
    4.  Cliquez sur **OK**.  
  
2.  Ajoutez une classe et le configurer pour qu’elle hérite de <xref:System.ServiceProcess.ServiceBase>:  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  Ajoutez le code suivant pour configurer votre classe de service :  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  Créer un `Main` méthode pour votre classe et l’utiliser pour définir le service que votre classe contiendra ; `userService1` est le nom de la classe :  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  Remplacer la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> (méthode) et définissez le traitement doit se produire lorsque votre service est démarré.  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  Substituez toutes les méthodes que vous souhaitez définir traitement personnalisé et écrire du code pour déterminer les actions que le service doit accomplir dans chaque cas.  
  
7.  Ajoutez les programmes d'installation nécessaires à votre application de service. Pour plus d’informations, consultez [Comment : ajouter des programmes d’installation à votre Application de Service](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
8.  Générez votre projet en sélectionnant **générer la Solution** à partir de la **générer** menu.  
  
    > [!NOTE]
    >  N'appuyez pas sur la touche F5 pour exécuter votre projet : vous ne pouvez pas exécuter un projet de service de cette manière.  
  
9. Créez un projet d’installation et les actions personnalisées pour installer votre service. Pour obtenir un exemple, consultez [procédure pas à pas : création d’une Application de Service Windows dans le Concepteur de composants](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
10. Installez le service. Pour plus d'informations, consultez [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Introduction aux applications de service Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Guide pratique pour créer des services Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Guide pratique pour ajouter des programmes d’installation à votre application de service](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Guide pratique pour enregistrer des informations relatives aux services](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [Procédure pas à pas : création d’une application de service Windows dans le Concepteur de composants](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
