---
title: type d'entité
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 026b0aef7cf2de8fe222721191afa459859701ee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108262"
---
# <a name="entity-type"></a>type d'entité
Le *type d’entité* est le bloc de construction fondamental pour décrire la structure de données avec le modèle EDM (Entity Data Model). Dans un modèle conceptuel, un type d'entité représente la structure des concepts de niveau supérieur, comme les clients ou les commandes. Un type d'entité est un modèle pour les instances de type d'entité. Chaque modèle contient les informations suivantes :  
  
-   Nom unique. (Obligatoire.)  
  
-   Un [clé d’entité](../../../../docs/framework/data/adonet/entity-key.md) défini par une ou plusieurs propriétés. (Obligatoire.)  
  
-   Données sous la forme de [propriétés](../../../../docs/framework/data/adonet/property.md). (Facultatif)  
  
-   [Propriétés de navigation](../../../../docs/framework/data/adonet/navigation-property.md) qui permettent de naviguer parmi [fin](../../../../docs/framework/data/adonet/association-end.md) d’un [association](../../../../docs/framework/data/adonet/association-type.md) à l’autre extrémité. (facultatif)  
  
 Dans une application, une instance d'un type d'entité représente un objet spécifique (tel qu'un client ou une commande spécifique). Chaque instance d’un type d’entité doit avoir une valeur unique [clé d’entité](../../../../docs/framework/data/adonet/entity-key.md) au sein d’un [jeu d’entités](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Deux instances de type d'entité sont considérées égales seulement si elles sont du même type et si les valeurs de leurs clés d'entité sont identiques.  
  
## <a name="example"></a>Exemple  
 Le diagramme suivant montre un modèle conceptuel avec trois types d'entité : `Book`, `Publisher` et `Author`.  
  
 ![Exemple de modèle avec trois types d’entité](./media/entity-type/example-model-three-entity-types.gif)  
  
 Notez que les propriétés de chaque type d'entité qui composent sa clé d'entité sont signalées par « (Key) ».  
  
 Le [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) utilise un langage spécifique à un domaine (DSL) appelé langage de définition de schéma conceptuel ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) pour définir des modèles conceptuels. Le CSDL suivant définit le type d'entité `Book` présenté dans le diagramme ci-dessus :  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Voir aussi

- [Concepts clés d'Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
- [facette](../../../../docs/framework/data/adonet/facet.md)
