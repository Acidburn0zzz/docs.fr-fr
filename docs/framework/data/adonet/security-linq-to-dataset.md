---
title: Sécurité (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: 6116b2b8-75f4-4d8b-aea6-c13e55cda50b
ms.openlocfilehash: 43d529b6f74b58783cc2aaa7a81b2f75790b4e40
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364959"
---
# <a name="security-linq-to-dataset"></a>Sécurité (LINQ to DataSet)
Cette rubrique traite des questions de sécurité dans [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  
  
## <a name="passing-a-query-to-an-untrusted-component"></a>Passage d'une requête à un composant non approuvé  
 A [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] requête peut être formulée dans un point du programme et exécutée dans un autre. Au point précis où elle est formulée, la requête peut référencer tout élément qui y est visible, comme des membres privés de la classe à laquelle appartient la méthode appelante, ou des symboles représentant les variables/arguments locaux. Au moment de l'exécution, la requête pourra accéder aux membres qu'elle a référencés au moment de la formulation, même si le code appelant ne les voit pas. Le code qui exécute la requête ne peut avoir aucune visibilité arbitraire du fait qu'il ne peut pas choisir les éléments auxquels il peut accéder. Il accède strictement aux mêmes éléments que la requête, et uniquement à travers la requête.  
  
 Pour cela, il faut qu'en passant une référence à une requête à une autre partie du code, le composant recevant la requête soit approuvé auprès de tous les membres publics et privés auxquels la requête fait référence. En règle générale, [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] requêtes ne doivent pas être passés à des composants non approuvés, à moins que la requête a été construite avec soin afin qu’il n’expose pas les informations devant rester confidentielles.  
  
## <a name="external-input"></a>Entrée externe  
 Les applications reçoivent souvent des entrées externes (provenant d'un utilisateur ou d'un autre agent externe) et exécutent des actions en fonction de ces entrées.  Dans le cas de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], l’application peut construire une requête d’une certaine manière, en fonction de l’entrée externe ou utiliser une entrée dans la requête externe. Les requêtes [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] acceptent des paramètres partout où des littéraux sont admis. Les développeurs d'applications devraient utiliser des requêtes paramétrées, plutôt que d'injecter des littéraux directement dans la requête à partir d'un agent externe.  
  
 Toute entrée provenant directement ou indirectement d'un utilisateur ou d'un agent externe doit avoir un contenu qui se base sur la syntaxe du langage cible afin d'exécuter des actions non autorisées. C'est ce que l'on appelle une « attaque par injection de code SQL », terme dérivé d'un modèle d'attaque où le langage cible est Transact-SQL. L’entrée utilisateur injectée directement dans la requête est utilisée pour effacer une table de base de données, provoquer un déni de service, ou modifier d’une manière ou d’une autre la nature de l’opération en cours. Bien qu'il soit possible de composer des requêtes dans [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], cette opération est effectuée via l'API de modèle objet. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] requêtes ne sont pas composées par manipulation ou concaténation, tels qu’ils sont en Transact-SQL, ne sont pas vulnérables aux attaques d’injection SQL dans le sens classique du terme.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide de programmation](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
