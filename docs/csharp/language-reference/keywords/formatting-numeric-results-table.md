---
title: Tableau des formats des résultats numériques (référence C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d389703c2d82d74760b99059201cb634849aa433
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="formatting-numeric-results-table-c-reference"></a>Tableau des formats des résultats numériques (référence C#)
Vous pouvez mettre en forme un résultat numérique à l’aide de la méthode <xref:System.String.Format%2A?displayProperty=nameWithType>, ou par l’intermédiaire des méthodes <xref:System.Console.Write%2A?displayProperty=nameWithType> ou `String.Format` qui appellent <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, ou à l’aide de [l’interpolation de chaîne](../tokens/interpolated.md). Le format est spécifié à l’aide de chaînes de format. Le tableau suivant contient les chaînes de format standard prises en charge. La chaîne de format prend la forme suivante : `Axx`, où `A` est le spécificateur de format et `xx` est le spécificateur de précision. Le spécificateur de format contrôle le type de mise en forme appliquée à la valeur numérique, tandis que le spécificateur de précision contrôle le nombre de chiffres significatifs ou de décimales de la sortie formatée. La valeur du spécificateur de précision est comprise entre 0 et 99.  
  
 Pour plus d’informations sur les chaînes de format standard et personnalisées, consultez [Mise en forme des types](../../../standard/base-types/formatting-types.md).
  
|Spécificateur de format|Description|Exemples|Sortie|  
|----------------------|-----------------|--------------|------------|  
|C ou c|Devise|Console.Write("{0:C}", 2.5);<br /><br /> Console.Write("{0:C}", -2.5);|$2.50<br /><br /> ($2.50)|  
|D ou d|Decimal|Console.Write("{0:D5}", 25);|00025|  
|E ou e|Scientifique|Console.Write("{0:E}", 250000);|2.500000E+005|  
|F ou f|Virgule fixe|Console.Write("{0:F2}", 25);<br /><br /> Console.Write("{0:F0}", 25);|25.00<br /><br /> 25|  
|G ou g|Général|Console.Write("{0:G}", 2.5);|2.5|  
|N ou n|nombre|Console.Write("{0:N}", 2500000);|2,500,000.00|  
|X ou x|Hexadécimal|Console.Write("{0:X}", 250);<br /><br /> Console.Write("{0:X}", 0xffff);|FA<br /><br /> FFFF|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence C#](../../../csharp/language-reference/index.md)  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [Chaînes de format numériques standard](../../../standard/base-types/standard-numeric-format-strings.md)  
 [Tableaux de référence des types](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [string](../../../csharp/language-reference/keywords/string.md)
