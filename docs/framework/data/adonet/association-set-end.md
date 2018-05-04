---
title: terminaison d'ensemble d'associations
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 440cfdee4581496d9d131fbaf3d1796f38931532
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="association-set-end"></a>terminaison d'ensemble d'associations
Une *ensemble d’associations* identifie le [type d’entité](../../../../docs/framework/data/adonet/entity-type.md) et le [jeu d’entités](../../../../docs/framework/data/adonet/entity-set.md) à la fin d’une [ensemble d’associations](../../../../docs/framework/data/adonet/association-set.md). Les terminaisons d'ensemble d'associations sont définies dans le cadre d'un ensemble d'associations ; un ensemble d'associations doit avoir exactement deux terminaisons d'ensemble d'associations.  
  
 Une définition de terminaison d'ensemble d'associations contient les informations suivantes :  
  
-   Un des types d'entité impliqués dans l'ensemble d'associations. (Requis)  
  
-   Jeu d'entités pour le type d'entité impliqué dans l'ensemble d'associations. (Requis)  
  
## <a name="example"></a>Exemple  
 Le diagramme suivant montre un modèle conceptuel avec deux associations : `WrittenBy` et `PublishedBy`.  
  
 ![Exemple de modèle](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Le diagramme suivant montre un ensemble d'associations (`PublishedBy`) et deux jeux d'entités (`Books` et `Publishers`) selon le modèle conceptuel présenté ci-dessus. Les terminaisons d'ensemble d'associations sont les jeux d'entités `Books` et `Publishers`. BI dans le `Books` jeu d’entités représente une instance de la `Book` type d’entité en cours d’exécution. De même, Pj représente un `Publisher` d’instance dans le `Publishers` jeu d’entités. BiPj représente une instance de la `PublishedBy` association dans le `PublishedBy` ensemble d’associations.  
  
 ![Définit l’exemple](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 Le [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) utilise un langage DSL, appelé langage de définition de schéma conceptuel ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) pour définir des modèles conceptuels. Le CSDL suivant définit un conteneur d'entités avec un ensemble d'associations pour chaque association dans le diagramme ci-dessus. Notez que les terminaisons d'ensemble d'associations sont définies dans le cadre de chaque définition d'ensemble d'associations.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts clés d’Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
