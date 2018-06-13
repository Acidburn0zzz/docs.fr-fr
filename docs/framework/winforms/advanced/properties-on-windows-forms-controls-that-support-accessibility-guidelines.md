---
title: Propriétés des contrôles Windows Forms que prennent en charge les instructions relatives à l'accessibilité
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: b466dcf42561d8ced7b224215538a807c94b174b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524486"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>Propriétés des contrôles Windows Forms que prennent en charge les instructions relatives à l'accessibilité
Dans la boîte à outils standard pour les Windows Forms prennent en charge plusieurs règles d’accessibilité, y compris l’exposition du focus clavier et d’exposer les éléments de l’écran.  
  
## <a name="planning-ahead-for-accessibility"></a>Planification de l’accessibilité  
 Les propriétés des contrôles peuvent être utilisées pour prendre en charge d’autres règles d’accessibilité comme indiqué dans le tableau suivant. En outre, vous devez utiliser des menus pour accéder aux fonctionnalités du programme.  
  
|Propriété de contrôle|Considérations d’accessibilité|  
|----------------------|--------------------------------------|  
|AccessibleDescription|La description est signalée à l’accessibilité, notamment des lecteurs d’écran. Les aides à l’accessibilité sont des programmes et des dispositifs spécialisés qui aident les personnes handicapées à utiliser plus efficacement les ordinateurs.|  
|AccessibleName|Le nom qui sera indiqué aux outils d’accessibilité.|  
|AccessibleRole|Décrit l’utilisation de l’élément dans l’interface utilisateur.|  
|TabIndex|Crée un chemin de navigation cohérent dans le formulaire. Il est important pour les contrôles sans étiquette intrinsèque, tels que des zones de texte, pour que leur étiquette associée les précède immédiatement dans l’ordre de tabulation.|  
|Texte|Utilisez le caractère « & » pour créer des clés d’accès. À l’aide des touches d’accès est la partie de fournir un accès clavier documenté aux fonctionnalités.|  
|Taille de police|Si la taille de police n’est pas réglable, elle doit être la valeur 10 points ou plus. Une fois que la taille de police du formulaire est définie, tous les contrôles ajoutés au formulaire par la suite aura la même taille.|  
|ForeColor|Si cette propriété est définie à la valeur par défaut, les préférences de couleur de l’utilisateur seront être utilisées dans le formulaire.|  
|BackColor|Si cette propriété est définie à la valeur par défaut, les préférences de couleur de l’utilisateur seront être utilisées dans le formulaire.|  
|BackgroundImage|Laissez cette propriété vide pour rendre le texte plus lisible.|  
  
## <a name="see-also"></a>Voir aussi  
 [Procédure pas à pas : création d'une application Windows accessible](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)
