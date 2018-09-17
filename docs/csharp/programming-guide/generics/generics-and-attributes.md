---
title: Génériques et attributs (Guide de programmation C#)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 0fe2d61001584aa7c175500bfa754b2ae2244660
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/16/2018
ms.locfileid: "45675533"
---
# <a name="generics-and-attributes-c-programming-guide"></a>Génériques et attributs (Guide de programmation C#)
Les attributs peuvent être appliqués aux types génériques de la même manière qu’aux types non génériques. Pour plus d’informations sur l’application des attributs, consultez [Attributs](../../../csharp/programming-guide/concepts/attributes/index.md).  
  
 Les attributs personnalisés sont uniquement autorisés à référencer des types génériques ouverts, qui sont des types génériques pour lesquels aucun argument de type n’est fourni, et des types génériques construits fermés, qui fournissent des arguments pour tous les paramètres de type.  
  
 Les exemples suivants utilisent cet attribut personnalisé :  
  
 [!code-csharp[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]  
  
 Un attribut peut référencer un type générique ouvert :  
  
 [!code-csharp[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]  
  
 Spécifiez plusieurs paramètres de type à l’aide du nombre approprié de virgules. Dans cet exemple, `GenericClass2` a deux paramètres de type :  
  
 [!code-csharp[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]  
  
 Un attribut peut référencer un type générique construit fermé :  
  
 [!code-csharp[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]  
  
 Un attribut qui référence un paramètre de type générique entraîne une erreur de compilation :  
  
 [!code-csharp[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]  
  
 Un type générique ne peut pas hériter d’<xref:System.Attribute> :  
  
 [!code-csharp[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]  
  
 Pour obtenir des informations sur un type générique ou un paramètre de type au moment de l’exécution, vous pouvez utiliser les méthodes de <xref:System.Reflection>. Pour plus d’informations, consultez [Génériques et réflexion](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
## <a name="see-also"></a>Voir aussi

- [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
- [Génériques](../../../csharp/programming-guide/generics/index.md)  
- [Attributs](../../../../docs/standard/attributes/index.md)
