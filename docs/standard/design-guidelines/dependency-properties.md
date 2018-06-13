---
title: Propriétés de dépendance
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 039015f895a491d8709815d6aff52eb6139d779f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576114"
---
# <a name="dependency-properties"></a><span data-ttu-id="2e5b0-102">Propriétés de dépendance</span><span class="sxs-lookup"><span data-stu-id="2e5b0-102">Dependency Properties</span></span>
<span data-ttu-id="2e5b0-103">Une propriété de dépendance (DP) est une propriété normale qui stocke sa valeur dans une banque de propriétés au lieu de stocker dans une variable de type (champ), par exemple.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-103">A dependency property (DP) is a regular property that stores its value in a property store instead of storing it in a type variable (field), for example.</span></span>  
  
 <span data-ttu-id="2e5b0-104">Une propriété de dépendance jointe est un type de propriété de dépendance modélisée en tant que les méthodes Get et Set statiques qui représente « propriétés », description des relations entre les objets et leurs conteneurs (par exemple, la position d’un `Button` de l’objet sur un `Panel` conteneur).</span><span class="sxs-lookup"><span data-stu-id="2e5b0-104">An attached dependency property is a kind of dependency property modeled as static Get and Set methods representing "properties" describing relationships between objects and their containers (e.g., the position of a `Button` object on a `Panel` container).</span></span>  
  
 <span data-ttu-id="2e5b0-105">**✓ FAIRE** fournissent les propriétés de dépendance, si vous avez besoin des propriétés pour prendre en charge des fonctionnalités WPF telles que les styles, les déclencheurs, liaison de données, des animations, ressources dynamiques et d’héritage.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-105">**✓ DO** provide the dependency properties, if you need the properties to support WPF features such as styling, triggers, data binding, animations, dynamic resources, and inheritance.</span></span>  
  
## <a name="dependency-property-design"></a><span data-ttu-id="2e5b0-106">Conception de propriété de dépendance</span><span class="sxs-lookup"><span data-stu-id="2e5b0-106">Dependency Property Design</span></span>  
 <span data-ttu-id="2e5b0-107">**✓ FAIRE** hériter <xref:System.Windows.DependencyObject>, ou l’un de ses sous-types, lors de l’implémentation des propriétés de dépendance.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-107">**✓ DO** inherit from <xref:System.Windows.DependencyObject>, or one of its subtypes, when implementing dependency properties.</span></span> <span data-ttu-id="2e5b0-108">Ce type fournit une implémentation très efficace d’une banque de propriétés et prend automatiquement en charge la liaison de données WPF.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-108">The type provides a very efficient implementation of a property store and automatically supports WPF data binding.</span></span>  
  
 <span data-ttu-id="2e5b0-109">**✓ FAIRE** fournir une propriété CLR normale et un champ statique public en lecture seule le stockage d’une instance de <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> pour chaque propriété de dépendance.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-109">**✓ DO** provide a regular CLR property and public static read-only field storing an instance of <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> for each dependency property.</span></span>  
  
 <span data-ttu-id="2e5b0-110">**✓ FAIRE** implémenter des propriétés de dépendance en appelant des méthodes d’instance <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> et <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-110">**✓ DO** implement dependency properties by calling instance methods <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> and <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2e5b0-111">**✓ FAIRE** nom du champ de propriété de dépendance statique par suffixant le nom de la propriété « Property ».</span><span class="sxs-lookup"><span data-stu-id="2e5b0-111">**✓ DO** name the dependency property static field by suffixing the name of the property with "Property."</span></span>  
  
 <span data-ttu-id="2e5b0-112">**X ne sont pas** définir explicitement les valeurs par défaut des propriétés de dépendance dans le code ; les définir dans les métadonnées.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-112">**X DO NOT** set default values of dependency properties explicitly in code; set them in metadata instead.</span></span>  
  
 <span data-ttu-id="2e5b0-113">Si vous définissez explicitement une valeur par défaut de la propriété, vous risquez d’empêcher cette propriété soient définies par des moyens implicites, par exemple, un style.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-113">If you set a property default explicitly, you might prevent that property from being set by some implicit means, such as a styling.</span></span>  
  
 <span data-ttu-id="2e5b0-114">**X ne sont pas** placez le code dans les accesseurs de propriété autre que le code standard pour accéder au champ statique.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-114">**X DO NOT** put code in the property accessors other than the standard code to access the static field.</span></span>  
  
 <span data-ttu-id="2e5b0-115">Que code ne sera pas s’exécuter si la propriété est définie par des moyens implicites, par exemple, un style, étant donné que les styles d’utilise directement le champ statique.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-115">That code won’t execute if the property is set by implicit means, such as a styling, because styling uses the static field directly.</span></span>  
  
 <span data-ttu-id="2e5b0-116">**X ne sont pas** utilise les propriétés de dépendance pour stocker des données sécurisées.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-116">**X DO NOT** use dependency properties to store secure data.</span></span> <span data-ttu-id="2e5b0-117">Propriétés de dépendance même privée est accessible publiquement.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-117">Even private dependency properties can be accessed publicly.</span></span>  
  
## <a name="attached-dependency-property-design"></a><span data-ttu-id="2e5b0-118">Conception de propriété de dépendance jointe</span><span class="sxs-lookup"><span data-stu-id="2e5b0-118">Attached Dependency Property Design</span></span>  
 <span data-ttu-id="2e5b0-119">Propriétés de dépendance décrites dans la section précédente représentent les propriétés intrinsèques du type déclarant ; par exemple, le `Text` propriété est une propriété de `TextButton`, qui le déclare.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-119">Dependency properties described in the preceding section represent intrinsic properties of the declaring type; for example, the `Text` property is a property of `TextButton`, which declares it.</span></span> <span data-ttu-id="2e5b0-120">Un type spécial de propriété de dépendance est la propriété de dépendance jointe.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-120">A special kind of dependency property is the attached dependency property.</span></span>  
  
 <span data-ttu-id="2e5b0-121">Un exemple classique d’une propriété jointe est le <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> propriété.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-121">A classic example of an attached property is the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="2e5b0-122">La propriété représente la position de colonne pas de (la grille) du bouton, mais elle s’applique uniquement si le bouton est contenu dans une grille, et par conséquent, il est « attaché » aux boutons de grilles.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-122">The property represents Button’s (not Grid’s) column position, but it is only relevant if the Button is contained in a Grid, and so it's "attached" to Buttons by Grids.</span></span>  
  
```  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 <span data-ttu-id="2e5b0-123">La définition d’une propriété jointe ressemble principalement similaire à celle d’une propriété de dépendance standard, à ceci près que les accesseurs sont représentées par les méthodes Get et Set statiques :</span><span class="sxs-lookup"><span data-stu-id="2e5b0-123">The definition of an attached property looks mostly like that of a regular dependency property, except that the accessors are represented by static Get and Set methods:</span></span>  
  
```  
public class Grid {  
  
    public static int GetColumn(DependencyObject obj) {  
        return (int)obj.GetValue(ColumnProperty);  
    }  
  
    public static void SetColumn(DependencyObject obj, int value) {  
        obj.SetValue(ColumnProperty,value);  
    }  
  
    public static readonly DependencyProperty ColumnProperty =  
        DependencyProperty.RegisterAttached(  
            "Column",  
            typeof(int),  
            typeof(Grid)  
    );  
}  
```  
  
## <a name="dependency-property-validation"></a><span data-ttu-id="2e5b0-124">Validation de propriété de dépendance</span><span class="sxs-lookup"><span data-stu-id="2e5b0-124">Dependency Property Validation</span></span>  
 <span data-ttu-id="2e5b0-125">Propriétés implémentent souvent ce que l'on appelle la validation.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-125">Properties often implement what is called validation.</span></span> <span data-ttu-id="2e5b0-126">La logique de validation s’exécute lorsqu’une tentative est faite pour modifier la valeur d’une propriété.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-126">Validation logic executes when an attempt is made to change the value of a property.</span></span>  
  
 <span data-ttu-id="2e5b0-127">Malheureusement, les accesseurs de propriété de dépendance ne peut pas contenir de code de validation arbitraire.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-127">Unfortunately dependency property accessors cannot contain arbitrary validation code.</span></span> <span data-ttu-id="2e5b0-128">Au lieu de cela, logique de validation de propriété de dépendance doit être spécifié au cours de l’inscription de la propriété.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-128">Instead, dependency property validation logic needs to be specified during property registration.</span></span>  
  
 <span data-ttu-id="2e5b0-129">**X ne sont pas** placer la logique de validation de propriété de dépendance dans les accesseurs de la propriété.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-129">**X DO NOT** put dependency property validation logic in the property’s accessors.</span></span> <span data-ttu-id="2e5b0-130">Au lieu de cela, passez un rappel de validation à `DependencyProperty.Register` (méthode).</span><span class="sxs-lookup"><span data-stu-id="2e5b0-130">Instead, pass a validation callback to `DependencyProperty.Register` method.</span></span>  
  
## <a name="dependency-property-change-notifications"></a><span data-ttu-id="2e5b0-131">Notifications de modification de propriété de dépendance</span><span class="sxs-lookup"><span data-stu-id="2e5b0-131">Dependency Property Change Notifications</span></span>  
 <span data-ttu-id="2e5b0-132">**X ne sont pas** implémenter la logique de notification de modification dans les accesseurs de propriété de dépendance.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-132">**X DO NOT** implement change notification logic in dependency property accessors.</span></span> <span data-ttu-id="2e5b0-133">Propriétés de dépendance ont une fonctionnalité de notifications de modification intégrée qui doit être utilisée, vous devez fournir un rappel de notification de modification pour le <xref:System.Windows.PropertyMetadata>.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-133">Dependency properties have a built-in change notifications feature that must be used by supplying a change notification callback to the <xref:System.Windows.PropertyMetadata>.</span></span>  
  
## <a name="dependency-property-value-coercion"></a><span data-ttu-id="2e5b0-134">Contrainte de valeur de propriété de dépendance</span><span class="sxs-lookup"><span data-stu-id="2e5b0-134">Dependency Property Value Coercion</span></span>  
 <span data-ttu-id="2e5b0-135">La contrainte de propriété a lieu lorsque la valeur donnée à un accesseur Set de propriété est modifiée par la méthode setter avant que la banque de propriétés est réellement modifiée.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-135">Property coercion takes place when the value given to a property setter is modified by the setter before the property store is actually modified.</span></span>  
  
 <span data-ttu-id="2e5b0-136">**X ne sont pas** implémenter la logique de la contrainte dans les accesseurs de propriété de dépendance.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-136">**X DO NOT** implement coercion logic in dependency property accessors.</span></span>  
  
 <span data-ttu-id="2e5b0-137">Propriétés de dépendance ont une fonctionnalité intégrée de la contrainte, et il peut être utilisé, vous devez fournir un rappel de la contrainte à la `PropertyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="2e5b0-137">Dependency properties have a built-in coercion feature, and it can be used by supplying a coercion callback to the `PropertyMetadata`.</span></span>  
  
 <span data-ttu-id="2e5b0-138">*Portions © 2005, 2009 Microsoft Corporation. Tous droits réservés.*</span><span class="sxs-lookup"><span data-stu-id="2e5b0-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2e5b0-139">*Réimprimées avec l’autorisation de Pearson éducation, Inc. à partir de [règles de conception d’infrastructure : Conventions, idiomes et des modèles pour les bibliothèques .NET réutilisable, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina et Brad Abrams, publié le 22 octobre 2008 par Addison-Wesley Professional dans le cadre de la série de développement Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="2e5b0-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e5b0-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e5b0-140">See Also</span></span>  
 [<span data-ttu-id="2e5b0-141">Règles de conception de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2e5b0-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="2e5b0-142">Modèles de design courants</span><span class="sxs-lookup"><span data-stu-id="2e5b0-142">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)
