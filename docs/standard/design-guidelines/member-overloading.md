---
title: Surcharge de membre
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c77f08cd573dc40083718b783ae01233ca00766
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="member-overloading"></a>Surcharge de membre
Surcharge de membre équivaut à la création de deux membres ou plus sur le même type qui diffèrent uniquement par le nombre ou le type de paramètres, mais ont le même nom. Par exemple, dans la commande suivante, la `WriteLine` méthode est surchargée :  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 Étant donné que seuls les constructeurs, les méthodes et les propriétés indexées peuvent avoir des paramètres, seuls les membres peuvent être surchargés.  
  
 La surcharge est une des techniques plus importants pour améliorer la facilité d’utilisation, la productivité et la lisibilité des bibliothèques réutilisables. La surcharge sur le nombre de paramètres rend possible fournir des versions plus simples des constructeurs et méthodes. La surcharge sur le type de paramètre rend possible d’utiliser le même nom de membre pour effectuer des opérations identiques sur un ensemble sélectionné de différents types de membres.  
  
 **✓ FAIRE** essayez d’utiliser des noms de paramètres descriptifs pour indiquer la valeur par défaut utilisée par les surcharges plus courts.  
  
 **X Évitez** Variant de façon arbitraire les noms de paramètres dans les surcharges. Si un paramètre d’une surcharge représente la même entrée en tant que paramètre dans une autre surcharge, les paramètres doivent avoir le même nom.  
  
 **X Évitez** incohérent dans l’ordre des paramètres de surcharge membres. Paramètres portant le même nom doivent apparaître dans la même position dans toutes les surcharges.  
  
 **✓ FAIRE** créer uniquement la surcharge la plus longue virtuelle (si l’extensibilité est requise). Les surcharges plus courtes doivent appeler simplement une surcharge plus longue.  
  
 **X ne sont pas** utiliser `ref` ou `out` modificateurs pour surcharger les membres.  
  
 Certains langages ne peut pas résoudre les appels aux surcharges comme suit. En outre, ces surcharges ont généralement une sémantique complètement différente et ne doivent pas être surcharges mais les deux méthodes distinctes à la place.  
  
 **X ne sont pas** ont des surcharges avec des paramètres à la même position et les types semblables, mais avec une sémantique différente.  
  
 **✓ FAIRE** autoriser `null` à passer les arguments facultatifs.  
  
 **✓ FAIRE** utiliser membre surcharge plutôt que de définir des membres avec des arguments par défaut.  
  
 Arguments par défaut ne sont pas compatibles CLS.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Tous droits réservés.*  
  
 *Réimprimées avec l’autorisation de Pearson éducation, Inc. à partir de [règles de conception d’infrastructure : Conventions, idiomes et des modèles pour les bibliothèques .NET réutilisable, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina et Brad Abrams, publié le 22 octobre 2008 par Addison-Wesley Professional dans le cadre de la série de développement Microsoft Windows.*  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions de conception des membres](../../../docs/standard/design-guidelines/member.md)  
 [Règles de conception de .NET Framework](../../../docs/standard/design-guidelines/index.md)
