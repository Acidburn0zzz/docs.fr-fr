---
title: Utilisation de System.Transactions dans ASP.NET
ms.date: 03/30/2017
ms.assetid: 1982c300-7ea6-4242-95ed-dc28ccfacac9
ms.openlocfilehash: df9a9f1878b2268d1d6bc3d9b05d0ad8d7bcc3f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134578"
---
# <a name="using-systemtransactions-in-aspnet"></a>Utilisation de System.Transactions dans ASP.NET
Cette rubrique explique comment utiliser <xref:System.Transactions> dans une application [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] .  
  
## <a name="enable-distributedtransactionpermission-in-aspnet"></a>Activation de DistributedTransactionPermission dans ASP.NET  
 <xref:System.Transactions> prend en charge les appelants de confiance partielle et est marqué avec le **AllowPartiallyTrustedCallers** attribut (APTCA). Les niveaux de confiance pour les <xref:System.Transactions> sont définis d’après les types de ressource (par exemple, la mémoire système, les ressources partagées au niveau du processus, les ressources système et d’autres ressources) exposés par <xref:System.Transactions> et le niveau de confiance requis pour accéder à ces ressources. Dans un environnement de confiance partielle, un assembly qui n’a pas un niveau de confiance totale ne peut utiliser que les transactions du domaine d’application (dans ce cas, les seules ressources protégées correspondent à la mémoire système), sauf s’il dispose de l’autorisation <xref:System.Transactions.DistributedTransactionPermission>.  
  
 <xref:System.Transactions.DistributedTransactionPermission> est demandée chaque fois que la gestion de la transaction est remontée pour être géré par Microsoft Distributed Transaction Coordinator (MSDTC). Ce genre de scénario utilise des ressources au niveau du processus et, en particulier, une ressource globale servant d’espace réservé dans le journal MSDTC. Par exemple, le composant web frontal d’une base de données ou une application qui utilise une base de donnée en tant que partie des services qu’il fournit.  
  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] dispose de son propre jeu de niveaux de confiance et associe un jeu d’autorisations spécifique à ces niveaux de confiance via des fichiers de stratégie. Pour plus d’informations, consultez [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100)). Lors de la première installation du Kit de développement logiciel (SDK) Windows, aucun des fichiers de stratégie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] par défaut n’est associé à <xref:System.Transactions.DistributedTransactionPermission>. Ainsi, lorsque votre transaction est remontée dans une application [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] pour gestion par le MSDTC, la remontée échoue avec une <xref:System.Security.SecurityException> lors de la demande de <xref:System.Transactions.DistributedTransactionPermission>. Pour activer la remontée des transactions au sein d’un environnement [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] de confiance partielle, vous devez accorder l’autorisation <xref:System.Transactions.DistributedTransactionPermission> aux mêmes niveaux de confiance par défaut que ceux de l’autorisation <xref:System.Data.SqlClient.SqlClientPermission>. Vous pouvez configurer vos propres niveaux de confiance et fichier de stratégie personnalisés pour la prise en charge ou modifier les fichiers de stratégie par défaut : **Web_hightrust.config** et **Web_mediumtrust.config**.  
  
 Pour modifier les fichiers de stratégie, ajoutez un **SecurityClass** élément pour **DistributedTransactionPermission** à la **SecurityClasses** élément sous la  **PolicyLevel** élément et ajoutez un **IPermission** élément sous le [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] **NamedPermissionSet** pour System.Transactions. Le fichier de configuration suivant illustre ceci.  
  
```xml  
<SecurityClasses>  
   <SecurityClass Name="DistributedTransactionPermission" Description="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
...  
</SecurityClasses>  
  
<PermissionSet  
  class="NamedPermissionSet"  
  version="1"  
  Name="ASP.Net">  
     <IPermission  
        class="System.Transactions.DistributedTransactionPermission, System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
        version="1"  
        Unrestricted="true"  
     />  
...  
</PermissionSet>  
```  
  
 Pour plus d’informations sur [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] stratégie de sécurité, consultez [securityPolicy élément (schéma des paramètres ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100)).  
  
## <a name="dynamic-compilation"></a>Compilation dynamique  
 Pour importer et utiliser <xref:System.Transactions> dans une application [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] compilée dynamiquement lors de l’accès, insérez une référence à l’assembly <xref:System.Transactions> dans le fichier de configuration. Cette référence doit être ajoutée sous la section **compilation**/**assemblies** du fichier de configuration **Web.config** racine par défaut ou du fichier de configuration d’une application Web spécifique. Cela est illustré par l'exemple suivant.  
  
```xml  
<configuration>  
   <system.web>  
      <compilation>  
         <assemblies>  
      <add assembly="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
         </assemblies>  
      </compilation>  
   </system.web>  
</configuration>  
```  
  
 Pour plus d’informations, consultez [add, élément d’assemblies pour compilation (schéma des paramètres ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/37e2zyhb(v=vs.100)).  
  
## <a name="see-also"></a>Voir aussi

- [ASP.NET Trust Levels and Policy Files](https://docs.microsoft.com/previous-versions/aspnet/wyts434y(v=vs.100))
- [securityPolicy élément (Schéma des paramètres ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/zhs35b56(v=vs.100))
- [Remontée de la gestion des transactions](../../../../docs/framework/data/transactions/transaction-management-escalation.md)
