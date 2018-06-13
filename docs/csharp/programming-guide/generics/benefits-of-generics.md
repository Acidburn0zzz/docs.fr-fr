---
title: Avantages des génériques (guide de programmation C#)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
ms.openlocfilehash: bd0a133c6ce1a9623bfe8598d1dc786c44e6eaad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336828"
---
# <a name="benefits-of-generics-c-programming-guide"></a>Avantages des génériques (guide de programmation C#)
Les génériques constituent la solution à une limitation dans les versions antérieures du Common Language Runtime et du langage C# dans lesquelles la généralisation s’effectue par un cast de types vers et depuis le type de base universel <xref:System.Object>. En créant une classe générique, vous pouvez créer une collection qui est de type sécurisé au moment de la compilation.  
  
 Les restrictions relatives à l’utilisation de classes de collections non génériques peuvent être illustrées par l’écriture d’un programme court qui utilise la classe de collection <xref:System.Collections.ArrayList> de la bibliothèque de classes .NET. Une instance de la classe <xref:System.Collections.ArrayList> peut stocker n’importe quel type référence ou valeur.  
  
 [!code-csharp[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]  
  
 Mais cette commodité a un coût. Tout type référence ou valeur qui est ajouté à un <xref:System.Collections.ArrayList> est implicitement upcasté en <xref:System.Object>. Si les éléments sont des types valeur, ils doivent faire l’objet d’un boxing quand ils sont ajoutés à la liste, et d’un unboxing quand ils sont récupérés. Les opérations de casting aussi bien que les opérations de boxing/unboxing affectent les performances. L’effet du boxing et de l’unboxing peut être très significatif quand vous devez itérer au sein de collections volumineuses.  
  
 L’autre limitation réside dans le manque de vérification au moment de la compilation. Étant donné que <xref:System.Collections.ArrayList> effectue un cast de tous les éléments en <xref:System.Object>, il n’existe aucun moyen d’empêcher le code client de procéder comme suit au moment de la compilation :  
  
 [!code-csharp[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]  
  
 Bien que parfaitement acceptable et parfois intentionnelle si vous créez une collection hétérogène, la combinaison de chaînes et de `ints` dans un seul <xref:System.Collections.ArrayList> est plus vraisemblablement une erreur de programmation, et cette erreur ne sera pas détectée avant l’exécution.  
  
 Dans les versions 1.0 et 1.1 du langage C#, le seul moyen d’éviter les dangers du code généralisé dans les classes de collections de bibliothèques de classes de base .NET Framework était d’écrire vos propres collections spécifiques à un type. Bien sûr, puisqu’une classe de ce genre n’est pas réutilisable pour plusieurs types de données, vous perdez les avantages de la généralisation, et vous devez réécrire la classe pour chaque type qui sera stocké.  
  
 Ce dont <xref:System.Collections.ArrayList> et d’autres classes semblables ont vraiment besoin est un moyen permettant au code client de spécifier, pour chaque instance, le type de données particulier qu’elles ont l’intention d’utiliser. Cela élimine la nécessité d’effectuer un upcast en <xref:System.Object> et permettrait également au compilateur d’effectuer un contrôle de type. En d’autres termes, <xref:System.Collections.ArrayList> a besoin d’un paramètre de type. C’est exactement ce que fournissent les génériques. Dans la collection <xref:System.Collections.Generic.List%601> générique, dans l’espace de noms <xref:System.Collections.Generic>, la même opération d’ajout d’éléments à la collection ressemble à ceci :  
  
 [!code-csharp[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]  
  
 Pour le code client, la seule syntaxe ajoutée avec <xref:System.Collections.Generic.List%601> par rapport à <xref:System.Collections.ArrayList> est l’argument de type dans la déclaration et l’instanciation. En échange de cette complexité de codage légèrement supérieure, vous pouvez créer une liste qui est non seulement plus sûre qu’<xref:System.Collections.ArrayList>, mais également considérablement plus rapide, surtout quand les éléments de la liste sont des types valeur.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.Collections.Generic>  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [Introduction aux génériques](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [Conversion boxing et unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)  
 [Quand utiliser les collections génériques](../../../standard/collections/when-to-use-generic-collections.md)  
 [Instructions relatives aux collections](../../../standard/design-guidelines/guidelines-for-collections.md)   
