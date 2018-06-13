---
title: 'Comment : utiliser EdmGen.exe pour valider les fichiers de modèle et les fichiers de mappage'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 197af6ae86de4057b864ef211c36f19aad83b003
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755797"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Comment : utiliser EdmGen.exe pour valider les fichiers de modèle et les fichiers de mappage
Cette rubrique montre comment utiliser le [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) outil pour valider le modèle et les fichiers de mappage. Pour plus d’informations, consultez [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Pour valider le modèle School à l'aide d'EdmGen.exe  
  
1.  Créez la base de données School. Pour plus d’informations, consultez [création de la base de données School](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Générez le modèle School. Pour plus d’informations, consultez [Comment : utiliser des EdmGen.exe pour générer des fichiers de modèle et de mappage](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  À l'invite de commandes, exécutez la commande suivante sans saut de ligne :  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : configurer manuellement un projet Entity Framework](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [Outils ADO.NET Entity Data Model](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [Comment : prégénérer des vues pour améliorer les performances des requêtes](http://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [Guide pratique pour utiliser EdmGen.exe pour générer le code de couche objet](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
