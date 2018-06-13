---
title: 'Comment : ajouter plusieurs jeux de paramètres à votre application en C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 029dffc878c62613e291620a2bd86971f369d15a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520807"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Comment : ajouter plusieurs jeux de paramètres à votre application en C# #
Dans certains cas, vous souhaiterez ont plusieurs ensembles de paramètres dans une application. Par exemple, si vous développez une application où un groupe particulier de paramètres est supposé changer fréquemment, il peut être judicieux de les placer dans un fichier unique afin que le fichier peut être remplacé en gros, sans affecter les autres paramètres. Visual Studio vous permet de vous permet d’ajouter plusieurs jeux de paramètres à votre projet. Jeux de paramètres supplémentaires sont accessibles via l’objet Properties.Settings.  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a>Pour ajouter un jeu supplémentaire de paramètres à votre Application  
  
1.  Dans le menu **Projet**, sélectionnez **Ajouter un nouvel élément**. La boîte de dialogue **Ajouter un nouvel élément** s’ouvre.  
  
2.  Dans le **ajouter un nouvel élément** boîte de dialogue, sélectionnez **fichier de paramètres**, tapez un nom pour le fichier, puis cliquez sur **ajouter** pour ajouter un nouveau fichier de paramètres à votre solution.  
  
3.  Dans **l’Explorateur de solutions**, faites glisser le nouveau fichier de paramètres dans le **propriétés** dossier. Ainsi, vos nouveaux paramètres soient disponibles dans le code.  
  
4.  Ajouter et utiliser des paramètres de ce fichier comme vous le feriez pour tout autre fichier de paramètres. Vous pouvez accéder à ce groupe de paramètres via l’objet Properties.Settings.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de paramètres d'application et de paramètres utilisateur](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Vue d'ensemble des paramètres d'application](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
