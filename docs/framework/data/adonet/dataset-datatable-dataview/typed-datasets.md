---
title: Datasets typés
ms.date: 03/30/2017
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
ms.openlocfilehash: 67c1d3a190c5a4f046d7c7da5ebbf98395a96341
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="typed-datasets"></a>Datasets typés
En plus d'un accès par liaison tardive aux valeurs via des variables faiblement typées, l'objet <xref:System.Data.DataSet> permet un accès aux données par l'intermédiaire d'une métaphore fortement typée. Tables et colonnes qui font partie de la **DataSet** accessibles à l’aide de noms conviviaux et de variables fortement typées.  
  
 Typé **DataSet** est une classe qui dérive d’un **DataSet**. Par conséquent, il hérite de toutes les méthodes, événements et propriétés d’un **DataSet**. En outre, un typé **DataSet** fournit des méthodes fortement typées, propriétés et événements. Cela signifie que vous pouvez accéder à des tables et à des colonnes par leur nom au lieu d’utiliser les méthodes associées à des collections. À l’exception d’améliorer la lisibilité du code, un typé **DataSet** autorise également le code de Visual Studio .NET éditeur compléter automatiquement les lignes en cours de frappe.  
  
 En outre, fortement typé **DataSet** donne accès aux valeurs avec le type approprié au moment de la compilation. Avec fortement typé **DataSet**, erreurs d’incompatibilité de type sont interceptées lorsque le code est compilé et non au moment de l’exécution.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Génération de DataSets fortement typés](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 Décrit comment créer et utiliser fortement typé **DataSet**.  
  
 [Annotation de DataSets typés](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 Explique comment annoter le schéma XML Schema definition language (XSD) utilisé pour générer un fortement typée **DataSet**afin de donner aux **DataSet** noms conviviaux d’éléments sans pour autant modifier le schéma sous-jacent.  
  
## <a name="see-also"></a>Voir aussi  
 [DataSets, DataTables et DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Fournisseurs managés ADO.NET et centre de développement DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
