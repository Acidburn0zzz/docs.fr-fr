---
title: "Procédure : Implémenter des événements d'interface - Guide de programmation C#"
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: dfd0602ef92f9b0f84a8e1434ef834a328d60f03
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200271"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a>Procédure : Implémenter des événements d'interface (Guide de programmation C#)
Une [interface](../../../csharp/language-reference/keywords/interface.md) peut déclarer un [événement](../../../csharp/language-reference/keywords/event.md). L’exemple suivant montre comment implémenter des événements d’interface dans une classe. En gros, les règles sont les mêmes que quand vous implémentez une propriété ou une méthode d’interface.  
  
## <a name="to-implement-interface-events-in-a-class"></a>Pour implémenter des événements d’interface dans une classe  
  
Déclarez l’événement dans votre classe, puis appelez-le aux emplacements appropriés.  
  
```csharp
namespace ImplementInterfaceEvents  
{  
    public interface IDrawingObject  
    {  
        event EventHandler ShapeChanged;  
    }  
    public class MyEventArgs : EventArgs   
    {  
        // class members  
    }  
    public class Shape : IDrawingObject  
    {  
        public event EventHandler ShapeChanged;  
        void ChangeShape()  
        {  
            // Do something here before the event…  

            OnShapeChanged(new MyEventArgs(/*arguments*/));  

            // or do something here after the event.   
        }  
        protected virtual void OnShapeChanged(MyEventArgs e)  
        {  
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a>Exemple  
L’exemple suivant montre comment gérer la situation peu courante dans laquelle votre classe hérite de plusieurs interfaces et chaque interface a un événement ayant le même nom. Dans ce cas, vous devez fournir une implémentation d’interface explicite pour au moins l’un des événements. Quand vous écrivez une implémentation d’interface explicite pour un événement, vous devez également écrire les accesseurs d’événement `add` et `remove`. Normalement, ces éléments sont fournis par le compilateur, mais dans le cas en question le compilateur ne peut pas les fournir.  
  
En fournissant vos propres accesseurs, vous pouvez spécifier si les deux événements sont représentés par le même événement dans votre classe ou par des événements différents. Par exemple, si les événements doivent être déclenchés à des moments différents en fonction des spécifications de l’interface, vous pouvez associer chaque événement à une implémentation distincte dans votre classe. Dans l’exemple suivant, les abonnés déterminent l’événement `OnDraw` qu’il recevront en effectuant un cast de la référence de la forme en `IShape` ou `IDrawingObject`.  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a>Voir aussi

- [Guide de programmation C#](../../../csharp/programming-guide/index.md)
- [Événements](../../../csharp/programming-guide/events/index.md)
- [Délégués](../../../csharp/programming-guide/delegates/index.md)
- [Implémentation d’interface explicite](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md)
- [Guide pratique pour déclencher les événements de la classe de base dans les classes dérivées](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)
