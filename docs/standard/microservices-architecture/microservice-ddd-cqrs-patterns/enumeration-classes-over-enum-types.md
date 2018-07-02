---
title: Utilisation de classes d’énumération plutôt que de types enum
description: Architecture des microservices .NET pour les applications .NET en conteneur | Utilisation de classes d’énumération plutôt que de types enum
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 1b2569caa7e7a6a899a6765d2e39d0fff8e37e2f
ms.sourcegitcommit: 6c480773ae896f45af4671fb3e26611a50e4dd81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2018
ms.locfileid: "35251192"
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="99432-103">Utilisation de classes d’énumération plutôt que de types enum</span><span class="sxs-lookup"><span data-stu-id="99432-103">Using enumeration classes instead of enum types</span></span>

<span data-ttu-id="99432-104">Les [énumérations](../../../../docs/csharp/language-reference/keywords/enum.md) (ou *types enum* en abrégé) constituent un wrapper de langage simple autour d’un type intégral.</span><span class="sxs-lookup"><span data-stu-id="99432-104">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="99432-105">Vous souhaiterez peut-être limiter leur utilisation au stockage d’une valeur d’un ensemble fermé de valeurs.</span><span class="sxs-lookup"><span data-stu-id="99432-105">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="99432-106">La classification basée sur les tailles (petite, moyenne, grande) est un bon exemple.</span><span class="sxs-lookup"><span data-stu-id="99432-106">Classification based on sizes (small, medium, large) is a good example.</span></span> <span data-ttu-id="99432-107">L’utilisation d’enums pour le flux de contrôle ou d’abstractions plus puissantes peut être un [code smell](http://deviq.com/code-smells/).</span><span class="sxs-lookup"><span data-stu-id="99432-107">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="99432-108">Ce type d’utilisation a pour effet de fragiliser le code avec de nombreuses instructions de flux de contrôle qui vérifient les valeurs de l’enum.</span><span class="sxs-lookup"><span data-stu-id="99432-108">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="99432-109">À la place, vous pouvez créer des classes d’énumération qui activent toutes les fonctionnalités avancées d’un langage orienté objet.</span><span class="sxs-lookup"><span data-stu-id="99432-109">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="99432-110">Toutefois, ce n’est pas un sujet très important et, dans de nombreux cas, vous pouvez toujours simplifier en utilisant des [types enum](../../../../docs/csharp/language-reference/keywords/enum.md) standard, si vous préférez.</span><span class="sxs-lookup"><span data-stu-id="99432-110">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../../docs/csharp/language-reference/keywords/enum.md) if that's your preference.</span></span>

## <a name="implementing-an-enumeration-base-class"></a><span data-ttu-id="99432-111">Implémentation d’une classe d’énumération de base</span><span class="sxs-lookup"><span data-stu-id="99432-111">Implementing an Enumeration base class</span></span>

<span data-ttu-id="99432-112">Le microservice Ordering (Commandes) dans eShopOnContainers fournit un exemple d’implémentation de classe d’énumération de base, comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="99432-112">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; }
    public int Id { get; }

    protected Enumeration()
    {
    }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString()
    {
        return Name;
    }

    public static IEnumerable<T> GetAll<T>() where T : Enumeration, new()
    {
        var type = typeof(T);
        var fields = type.GetTypeInfo().GetFields(BindingFlags.Public |
            BindingFlags.Static |
            BindingFlags.DeclaredOnly);
        foreach (var info in fields)
        {
            var instance = new T();
            var locatedValue = info.GetValue(instance) as T;
            if (locatedValue != null)
            {
                yield return locatedValue;
            }
        }
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;
        if (otherValue == null)
        {
            return false;
        }
        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);
        return typeMatches && valueMatches;
    }

    public int CompareTo(object other)
    {
        return Id.CompareTo(((Enumeration)other).Id);
    }

    // Other utility methods ...
}
```

<span data-ttu-id="99432-113">Vous pouvez utiliser cette classe comme type dans n’importe quel objet entité ou de valeur, comme pour la classe d’énumération CardType suivante :</span><span class="sxs-lookup"><span data-stu-id="99432-113">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class:</span></span>

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    protected CardType() { }

    public CardType(int id, string name)
        : base(id, name)
    {
    }

    public static IEnumerable<CardType> List()
    {
        return new[] { Amex, Visa, MasterCard };
    }
    // Other util methods
}
```

## <a name="additional-resources"></a><span data-ttu-id="99432-114">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="99432-114">Additional resources</span></span>

-   <span data-ttu-id="99432-115">**Enum’s are evil—update**
    [*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="99432-115">**Enum’s are evil—update**
[*https://www.planetgeek.ch/2009/07/01/enums-are-evil/*](https://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="99432-116">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="99432-116">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="99432-117">**Jimmy Bogard. Enumeration classes**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="99432-117">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="99432-118">**Steve Smith. Enum Alternatives in C#**
    [*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="99432-118">**Steve Smith. Enum Alternatives in C#**
[*https://ardalis.com/enum-alternatives-in-c*](https://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="99432-119">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="99432-119">**Enumeration.cs.**</span></span> <span data-ttu-id="99432-120">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="99432-120">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="99432-121">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="99432-121">**CardType.cs**.</span></span> <span data-ttu-id="99432-122">Exemple de classe d’énumération dans eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="99432-122">Sample Enumeration class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="99432-123">[Précédent] (implement-value-objects.md) [Suivant] (domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="99432-123">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
