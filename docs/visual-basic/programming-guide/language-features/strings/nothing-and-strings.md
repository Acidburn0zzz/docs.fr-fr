---
title: Nothing et les chaînes en Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d7693e712884a500495e4573900e7d9a049c2879
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing et les chaînes en Visual Basic
Le runtime Visual Basic et le [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] évaluer `Nothing` différemment lorsqu’il s’agit de chaînes.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Runtime Visual Basic et le .NET Framework  
 Prenons l'exemple suivant :  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 Le runtime Visual Basic prend généralement la valeur `Nothing` comme une chaîne vide (« »). Le [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] est pas le cas, toutefois et lève une exception lorsqu’une tentative est effectuée pour effectuer une opération de chaîne sur `Nothing`.  
  
## <a name="see-also"></a>Voir aussi  
 [Introduction aux chaînes en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
