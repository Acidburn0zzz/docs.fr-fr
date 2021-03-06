---
title: Programmation orientée objet (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: 058d8b932e50f784d4a5cefa9fadfb31953687f0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153921"
---
# <a name="object-oriented-programming-visual-basic"></a>Programmation orientée objet (Visual Basic)

Visual Basic fournit une prise en charge complète pour la programmation orientée objet notamment l’encapsulation, héritage et le polymorphisme.

 L’*encapsulation* signifie qu’un groupe de propriétés, méthodes et autres membres corrélés est traité comme une unité ou un objet unique.

 L’*héritage* décrit la possibilité de créer des classes à partir d’une classe existante.

 Le *polymorphisme* signifie que plusieurs classes peuvent être utilisées de manière interchangeable, même si chacune des classes implémente les mêmes propriétés ou méthodes de manière différente.

 Cette section décrit les concepts suivants :

- [Classes et objets](#classes-and-objects)
  - [Membres de classe](#class-members)
    - [Propriétés et champs](#properties-and-fields)
    - [Méthodes](#methods)
    - [Constructeurs](#constructors)
    - [Destructeurs](#destructors)
    - [Événements](#events)
    - [Classes imbriquées](#nested-classes)
  - [Modificateurs d’accès et niveaux d’accès](#access-modifiers-and-access-levels)
    - [Instanciation de classes](#instantiating-classes)
    - [Membres et classes partagées](#shared-classes-and-members)
    - [Types anonymes](#anonymous-types)
- [Héritage](#inheritance)
  - [Substitution de membres](#overriding-members)
- [Interfaces](#interfaces)
- [Génériques](#generics)
- [Délégués](#delegates)

## <a name="classes-and-objects"></a>Classes et objets

Les termes *classe* et *objet* sont parfois employés indifféremment, mais en réalité, les classes décrivent le *type* des objets, alors que les objets sont des *instances* utilisables des classes. Cela explique pourquoi l’opération de création d’un objet est appelée *instanciation*. Si l'on reprend l'analogie avec un plan de construction, une classe est un plan, et un objet est un bâtiment construit à partir de ce plan.

Pour définir une classe :

```vb
Class SampleClass
End Class
```

Visual Basic fournit également une version basique de classes appelée *structures* qui sont utiles lorsque vous avez besoin créer un grand tableau d’objets et de faire pas amené à consommer trop de mémoire pour ce faire.

Pour définir une structure :

```vb
Structure SampleStructure
End Structure
```

Pour plus d'informations, voir :

- [Class (instruction)](../../../visual-basic/language-reference/statements/class-statement.md)
- [Structure (instruction)](../../../visual-basic/language-reference/statements/structure-statement.md)

### <a name="class-members"></a>Membres de classe

Chaque classe peut avoir différents *membres de classe* : des propriétés qui décrivent les données de classe, des méthodes qui définissent le comportement de classe et des événements qui permettent la communication entre les différents objets et classes.

#### <a name="properties-and-fields"></a>Propriétés et champs

Les propriétés et les champs sont des informations contenues dans un objet. Les champs sont similaires aux variables, car ils peuvent être lus ou définis directement.

Pour définir un champ :

```vb
Class SampleClass
    Public SampleField As String
End Class
```

Les propriétés comportent des procédures Get et Set qui apportent davantage de contrôle sur le mode de définition ou de retour des valeurs.

Visual Basic vous permet de créer un champ privé pour stocker la valeur de propriété ou d’utiliser ce que l'on appelle propriétés implémentées automatiquement qui créent ce champ automatiquement en arrière-plan et fournissent la logique de base pour les procédures de propriété.

Pour définir une propriété implémentée automatiquement :

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

Si vous devez exécuter des opérations supplémentaires pour la lecture et l'écriture de la valeur de propriété, définissez un champ pour le stockage de la valeur de propriété et fournissez la logique de base pour son stockage et son extraction :

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

La plupart des propriétés disposent de méthodes ou de procédures destinées à la fois à définir et à obtenir la valeur de propriété. Toutefois, vous pouvez créer des propriétés en lecture seule ou en écriture seule pour empêcher qu'elles soient modifiées ou lues. En Visual Basic, vous pouvez utiliser les mots clés `ReadOnly` et `WriteOnly`. Toutefois, les propriétés implémentées automatiquement ne peuvent pas être en lecture seule ni en écriture seule.

Pour plus d'informations, voir :

- [Property (instruction)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Get (instruction)](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set (instruction)](../../../visual-basic/language-reference/statements/set-statement.md)
- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)

#### <a name="methods"></a>Méthodes

 Une *méthode* correspond à une action qu’un objet peut effectuer.

> [!NOTE]
> En Visual Basic, il existe deux façons de créer une méthode : l'instruction `Sub` est utilisée si la méthode ne retourne pas de valeur ; l'instruction `Function` est utilisée si une méthode retourne une valeur.

Pour définir une méthode de classe :

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

Une classe peut avoir plusieurs implémentations, ou *surcharges*, de la même méthode qui diffèrent du point de vue du nombre de paramètres ou des types de paramètres.

Pour surcharger une méthode :

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

Dans la plupart des cas, vous déclarez une méthode dans une définition de classe. Toutefois, Visual Basic prend également en charge *méthodes d’extension* qui permettent d’ajouter des méthodes à une classe existante en dehors de la définition réelle de la classe.

Pour plus d'informations, voir :

- [Function (instruction)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instruction)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)
- [Méthodes d’extension](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)

#### <a name="constructors"></a>Constructeurs

Les constructeurs sont des méthodes de classe qui s'exécutent automatiquement lorsqu'un objet d'un type donné est créé. Les constructeurs initialisent habituellement les données membres du nouvel objet. Un constructeur ne peut s'exécuter qu'une seule fois lorsqu'une classe est créée. En outre, le code figurant dans le constructeur s'exécute toujours avant tout autre code dans une classe. Toutefois, vous pouvez créer plusieurs surcharges de constructeur de la même façon que vous le faites pour toute autre méthode.

Pour définir un constructeur pour une classe :

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

Pour plus d'informations, voir : [Durée de vie d’objet : Comment les objets sont créés et détruits](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

#### <a name="destructors"></a>Destructeurs

Les destructeurs permettent de détruire les instances des classes. Dans le .NET Framework, le garbage collector gère automatiquement l'allocation et la libération de mémoire pour les objets managés figurant dans votre application. Toutefois, vous pouvez avoir besoin de destructeurs pour nettoyer toutes les ressources non managées créées par votre application. Il ne peut y avoir qu'un seul destructeur pour une même classe.

Pour plus d’informations sur les destructeurs et l’opération de garbage collection dans le .NET Framework, consultez [Garbage collection](../../../standard/garbage-collection/index.md).

#### <a name="events"></a>Événements

Les événements permettent à une classe ou un objet de notifier d'autres classes ou objets lorsqu'une situation intéressante se produit. La classe qui envoie (ou déclenche) l’événement est appelée *éditeur* et les classes qui reçoivent (ou gèrent) l’événement sont appelées *abonnés*. Pour plus d’informations sur les événements, leur déclenchement et leur gestion, consultez [Événements](../../../standard/events/index.md).

- Pour déclarer des événements, utilisez le [Event, instruction](../../../visual-basic/language-reference/statements/event-statement.md).

- Pour déclencher des événements, utilisez le [RaiseEvent, instruction](../../../visual-basic/language-reference/statements/raiseevent-statement.md).

- Pour spécifier des gestionnaires d’événements à l’aide d’une méthode déclarative, utilisez la [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) instruction et le [gère](../../../visual-basic/language-reference/statements/handles-clause.md) clause.

- Pour être en mesure d’ajouter, supprimer et modifier le Gestionnaire d’événements associé à un événement de manière dynamique, utilisez le [AddHandler, instruction](../../../visual-basic/language-reference/statements/addhandler-statement.md) et [RemoveHandler, instruction](../../../visual-basic/language-reference/statements/removehandler-statement.md) conjointement avec la [AddressOf Opérateur](../../../visual-basic/language-reference/operators/addressof-operator.md).

#### <a name="nested-classes"></a>Classes imbriquées

Une classe définie à l’intérieur d’une autre classe est dite *imbriquée*. Par défaut, une classe imbriquée est privée.

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

Pour créer une instance de la classe imbriquée, utilisez le nom de la classe de conteneur suivi d'un point, puis du nom de la classe imbriquée :

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a>Modificateurs d’accès et niveaux d’accès

Toutes les classes et tous les membres de classe peuvent spécifier le niveau d’accès qu’ils fournissent aux autres classes à l’aide des *modificateurs d’accès*.

Les modificateurs d’accès suivants sont disponibles :

|Modificateur Visual Basic|Définition|
|---------------------------|----------------|
|[Public](../../../visual-basic/language-reference/modifiers/public.md)|Tout autre code du même assembly ou d'un autre assembly qui y fait référence peut accéder au type ou au membre.|
|[Private](../../../visual-basic/language-reference/modifiers/private.md)|Seul le code de la même classe peut accéder au type ou au membre.|
|[Protected](../../../visual-basic/language-reference/modifiers/protected.md)|Seul le code de la même classe ou d'une classe dérivée peut accéder au type ou au membre.|
|[Friend](../../../visual-basic/language-reference/modifiers/friend.md)|Tout code du même assembly, mais pas d'un autre assembly, peut accéder au type ou au membre.|
|`Protected Friend`|Tout code du même assembly ou toute classe dérivée dans un autre assembly peut accéder au type ou au membre.|

Pour plus d’informations, consultez [niveaux en Visual Basic d’accès](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

### <a name="instantiating-classes"></a>Instanciation de classes

Pour créer un objet, vous devez instancier une classe ou créer une instance de classe.

```vb
Dim sampleObject as New SampleClass()
```

Après avoir instancié une classe, vous pouvez assigner des valeurs aux propriétés et champs de l'instance et appeler des méthodes de classe.

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

Pour assigner des valeurs aux propriétés pendant le processus d'instanciation de la classe, utilisez des initialiseurs d'objets :

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

Pour plus d'informations, voir :

- [New (opérateur)](../../../visual-basic/language-reference/operators/new-operator.md)
- [Initialiseurs d’objets : Types nommés et anonymes](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a>Membres et classes partagées

 Un membre partagé de la classe est une propriété, une procédure ou un champ qui est partagé par toutes les instances d’une classe.

 Pour définir un membre partagé :

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 Pour accéder au membre partagé, utilisez le nom de la classe sans créer d’objet de cette classe :

```vb
MsgBox(SampleClass.SampleString)
```

 Les modules partagés en Visual Basic ont été partagés uniquement des membres et ne peut pas être instanciées. Membres partagés ne peut pas également accéder aux propriétés non partagées, des champs ou des méthodes

 Pour plus d'informations, voir :

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Module (instruction)](../../../visual-basic/language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a>Types anonymes

Les types anonymes vous permettent de créer des objets sans écrire de définition de classe pour le type de données. À la place, le compilateur se charge de générer une classe. La classe ne possède pas de nom utilisable et contient les propriétés que vous spécifiez lors de la déclaration de l'objet.

Pour créer une instance de type anonyme :

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

Pour plus d'informations, voir : [Les Types anonymes](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

## <a name="inheritance"></a>Héritage

Il vous permet de créer une nouvelle classe qui réutilise, étend et modifie le comportement défini dans une autre classe. La classe dont les membres sont hérités porte le nom de *classe de base* et la classe qui hérite de ces membres porte le nom de *classe dérivée*. Toutefois, toutes les classes en Visual Basic héritent implicitement de la <xref:System.Object> classe qui prend en charge de la hiérarchie de classes .NET et fournit des services de bas niveau à toutes les classes.

> [!NOTE]
> Visual Basic ne prend pas en charge l’héritage multiple. Vous pouvez donc spécifier une seule classe de base pour une classe dérivée.

Pour hériter d'une classe de base :

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

Par défaut, toutes les classes peuvent être héritées. Toutefois, vous pouvez spécifier si une classe ne doit pas être utilisée comme classe de base ou créer une classe qui peut être utilisée uniquement comme classe de base.

Pour spécifier qu'une classe ne peut pas être utilisée comme classe de base :

```vb
NotInheritable Class SampleClass
End Class
```

Pour spécifier qu'une classe peut être utilisée uniquement comme classe de base et ne peut pas être instanciée :

```vb
MustInherit Class BaseClass
End Class
```

Pour plus d'informations, voir :

- [Inherits (instruction)](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a>Substitution de membres

Par défaut, une classe dérivée hérite de tous les membres de sa classe de base. Si vous souhaitez modifier le comportement du membre hérité, vous devez le substituer. Autrement dit, vous pouvez définir une nouvelle implémentation de la méthode, de la propriété ou de l'événement dans la classe dérivée.

Les modificateurs suivants sont utilisés pour contrôler la façon dont les propriétés et les méthodes sont substituées :

|Modificateur Visual Basic|Définition|
|---------------------------|----------------|
|[Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)|Autorise la substitution d'un membre de classe dans une classe dérivée.|
|[Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)|Substitue un membre virtuel (substituable) défini dans la classe de base.|
|[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)|Empêche un membre d'être substitué dans une classe qui hérite.|
|[MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)|Requiert qu'un membre de classe soit substitué dans la classe dérivée.|
|[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)|Masque un membre hérité d'une classe de base.|

## <a name="interfaces"></a>Interfaces

Tout comme les classes, les interfaces définissent un ensemble de propriétés, méthodes et événements. Cependant, contrairement aux classes, les interfaces n'assurent pas l'implémentation. Elles sont implémentées par les classes et définies en tant qu'entités distinctes des classes. Une interface représente un contrat, dans le sens où une classe qui implémente une interface doit implémenter tous les aspects de cette interface exactement telle qu'elle a été définie.

Pour définir une interface :

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

Pour implémenter une interface dans une classe :

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

Pour plus d'informations, voir :

- [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Interface (instruction)](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Implements (instruction)](../../../visual-basic/language-reference/statements/implements-statement.md)

## <a name="generics"></a>Génériques

Classes, structures, interfaces et méthodes dans .NET peuvent inclure *paramètres de type* qui définissent les types d’objets qu’ils peuvent stocker ou utiliser. L’exemple le plus commun de génériques est une collection dans laquelle vous pouvez spécifier le type d’objets à stocker dans une collection.

Pour définir une classe générique :

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

Pour créer une instance de classe générique :

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

Pour plus d'informations, voir :

- [Génériques](../../../standard/generics/index.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

## <a name="delegates"></a>Délégués

 Un *délégué* est un type qui définit une signature de méthode et peut fournir une référence à toute méthode avec une signature compatible. Vous pouvez appeler la méthode par le biais du délégué. Les délégués sont utilisés pour passer des méthodes comme arguments à d'autres méthodes.

> [!NOTE]
> Les gestionnaires d'événements sont tout simplement des méthodes appelées par le biais de délégués. Pour plus d’informations sur l’utilisation de délégués dans la gestion des événements, consultez [Événements](../../../standard/events/index.md).

Pour créer un délégué :

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

Pour créer une référence à une méthode qui correspond à la signature spécifiée par le délégué :

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

Pour plus d'informations, voir :

- [Délégués](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Delegate (instruction)](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [AddressOf (opérateur)](../../../visual-basic/language-reference/operators/addressof-operator.md)

## <a name="see-also"></a>Voir aussi

- [Guide de programmation Visual Basic](../../../visual-basic/programming-guide/index.md)
