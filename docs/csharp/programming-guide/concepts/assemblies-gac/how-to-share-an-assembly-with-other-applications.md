---
title: 'Procédure : Partager un assembly avec d’autres applications (C#)'
ms.date: 07/20/2015
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: d440000ef509199bf69f06c2f3b5d0819e48f724
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713575"
---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a>Procédure : Partager un assembly avec d’autres applications (C#)
Les assemblys peuvent être privés ou partagés. Par défaut, la plupart des programmes simples se composent d’un assembly privé, car ils ne sont pas destinés à être utilisés par d’autres applications.  
  
 Pour partager un assembly avec d’autres applications, celui-ci doit être placé dans le [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).  
  
### <a name="sharing-an-assembly"></a>Partage d’un assembly  
  
1.  Créez votre assembly. Pour plus d’informations, consultez [Création d’assemblys](../../../../framework/app-domains/create-assemblies.md).  
  
2.  Attribuez un nom fort à votre assembly. Pour plus d'informations, voir [Procédure : signer un assembly avec un nom fort](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
3.  Assignez des informations de version à votre assembly. Pour plus d’informations, consultez [Versioning des assemblys](../../../../../docs/framework/app-domains/assembly-versioning.md).  
  
4.  Ajoutez votre assembly au Global Assembly Cache. Pour plus d'informations, voir [Procédure : Installer un assembly dans le Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
5.  Accédez aux types contenus dans l’assembly à partir d’autres applications. Pour plus d'informations, voir [Procédure : Référencer un assembly avec un nom fort](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).  
  
## <a name="see-also"></a>Voir aussi

- [Guide de programmation C#](../../../../csharp/programming-guide/index.md)
- [Programmation à l’aide d’assemblys](../../../../framework/app-domains/programming-with-assemblies.md)
