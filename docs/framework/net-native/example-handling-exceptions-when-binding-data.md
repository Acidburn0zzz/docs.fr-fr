---
title: 'Exemple : gestion des exceptions pendant la liaison de données'
ms.date: 03/30/2017
ms.assetid: bd63ed96-9853-46dc-ade5-7bd1b0f39110
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c4b73ed36d3334e983b960ce972292a190bad85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393586"
---
# <a name="example-handling-exceptions-when-binding-data"></a><span data-ttu-id="e7044-102">Exemple : gestion des exceptions pendant la liaison de données</span><span class="sxs-lookup"><span data-stu-id="e7044-102">Example: Handling Exceptions When Binding Data</span></span>
> [!NOTE]
>  <span data-ttu-id="e7044-103">Cette rubrique fait référence à .NET Native Developer Preview, qui correspond à la version préliminaire du logiciel.</span><span class="sxs-lookup"><span data-stu-id="e7044-103">This topic refers to the .NET Native Developer Preview, which is pre-release software.</span></span> <span data-ttu-id="e7044-104">Vous pouvez télécharger la préversion sur le [site web Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=394611) (inscription nécessaire).</span><span class="sxs-lookup"><span data-stu-id="e7044-104">You can download the preview from the [Microsoft Connect website](http://go.microsoft.com/fwlink/?LinkId=394611) (requires registration).</span></span>  
  
 <span data-ttu-id="e7044-105">L’exemple suivant montre comment résoudre une exception [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) qui est levée quand une application compilée avec la chaîne d’outils [!INCLUDE[net_native](../../../includes/net-native-md.md)] essaie de lier des données.</span><span class="sxs-lookup"><span data-stu-id="e7044-105">The following example shows how to resolve a [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exception that is thrown when an app compiled with the [!INCLUDE[net_native](../../../includes/net-native-md.md)] tool chain tries to bind data.</span></span> <span data-ttu-id="e7044-106">Voici les informations sur l'exception :</span><span class="sxs-lookup"><span data-stu-id="e7044-106">Here’s the exception information:</span></span>  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:   
App.ViewModels.MainPageVM  
```  
  
 <span data-ttu-id="e7044-107">Voici la pile des appels associée :</span><span class="sxs-lookup"><span data-stu-id="e7044-107">Here's the associated call stack:</span></span>  
  
```  
Reflection::Execution::ReflectionDomainSetupImplementation.CreateNonInvokabilityException+0x238  
Reflection::Core::ReflectionDomain.CreateNonInvokabilityException+0x2e  
Reflection::Core::Execution::ExecutionEnvironment.+0x316  
System::Reflection::Runtime::PropertyInfos::RuntimePropertyInfo.GetValue+0x1cb  
System::Reflection::PropertyInfo.GetValue+0x22  
System::Runtime::InteropServices::WindowsRuntime::CustomPropertyImpl.GetValue+0x42  
App!$66_Interop::McgNative.Func_IInspectable_IInspectable+0x158  
App!$66_Interop::McgNative::__vtable_Windows_UI_Xaml_Data__ICustomProperty.GetValue__STUB+0x46  
Windows_UI_Xaml!DirectUI::PropertyProviderPropertyAccess::GetValue+0x3f   
Windows_UI_Xaml!DirectUI::PropertyAccessPathStep::GetValue+0x31   
Windows_UI_Xaml!DirectUI::PropertyPathListener::ConnectPathStep+0x113  
```  
  
## <a name="what-was-the-app-doing"></a><span data-ttu-id="e7044-108">Que faisait l'application ?</span><span class="sxs-lookup"><span data-stu-id="e7044-108">What was the app doing?</span></span>  
 <span data-ttu-id="e7044-109">À la base de la pile, des frames issus de l’espace de noms [Windows.UI.Xaml](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.aspx) indiquent que le moteur de rendu XAML était en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="e7044-109">At the base of the stack, frames from the [Windows.UI.Xaml](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.aspx) namespace indicate that the XAML rendering engine was running.</span></span>   <span data-ttu-id="e7044-110">L'utilisation de la méthode <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> indique une recherche basée sur la réflexion de la valeur d'une propriété sur le type dont les métadonnées ont été supprimées.</span><span class="sxs-lookup"><span data-stu-id="e7044-110">The use of the <xref:System.Reflection.PropertyInfo.GetValue%2A?displayProperty=nameWithType> method indicates a reflection-based lookup of a property’s value on the type whose metadata was removed.</span></span>  
  
 <span data-ttu-id="e7044-111">La première étape pour fournir une directive de métadonnées consisterait à ajouter des métadonnées `serialize` pour le type afin que ses propriétés soient toutes accessibles :</span><span class="sxs-lookup"><span data-stu-id="e7044-111">The first step in providing a metadata directive would be to add `serialize` metadata for the type so that its properties are all accessible:</span></span>  
  
```xml  
<Type Name="App.ViewModels.MainPageVM" Serialize="Required Public" />  
```  
  
## <a name="is-this-an-isolated-case"></a><span data-ttu-id="e7044-112">S'agit-il d'un cas isolé ?</span><span class="sxs-lookup"><span data-stu-id="e7044-112">Is this an isolated case?</span></span>  
 <span data-ttu-id="e7044-113">Dans ce scénario, si la liaison de données contient des métadonnées incomplètes pour un `ViewModel`, cela peut également être le cas pour d'autres.</span><span class="sxs-lookup"><span data-stu-id="e7044-113">In this scenario, if data binding has incomplete metadata for one `ViewModel`, it may for others, too.</span></span>  <span data-ttu-id="e7044-114">Si le code est structuré de façon à ce que les modèles d'affichage de l'application se trouvent tous dans l'espace de noms `App.ViewModels`, vous pouvez utiliser une directive runtime plus générale :</span><span class="sxs-lookup"><span data-stu-id="e7044-114">If the code is structured in a way that the app’s view models are all in the `App.ViewModels` namespace, you could use a more general runtime directive:</span></span>  
  
```xml  
<Namespace Name="App.ViewModels " Serialize="Required Public" />  
```  
  
## <a name="could-the-code-be-rewritten-to-not-use-reflection"></a><span data-ttu-id="e7044-115">Le code peut-il être réécrit de manière à ne pas utiliser la réflexion ?</span><span class="sxs-lookup"><span data-stu-id="e7044-115">Could the code be rewritten to not use reflection?</span></span>  
 <span data-ttu-id="e7044-116">Comme la liaison de données repose sur la réflexion, modifier le code pour éviter la réflexion est impossible.</span><span class="sxs-lookup"><span data-stu-id="e7044-116">Because data binding is reflection-intensive, changing the code to avoid reflection isn’t feasible.</span></span>  
  
 <span data-ttu-id="e7044-117">Toutefois, certains procédés permettent de spécifier le `ViewModel` pour la page XAML afin que la chaîne d'outils associe les liaisons de propriété au type approprié au moment de la compilation et conserve les métadonnées sans utiliser de directive runtime.</span><span class="sxs-lookup"><span data-stu-id="e7044-117">However, there are ways to specify the `ViewModel` to the XAML page so that the tool chain can associate property bindings with the correct type at compile time and keep the metadata without using a runtime directive.</span></span>  <span data-ttu-id="e7044-118">Par exemple, vous pouvez appliquer l’attribut [Windows.UI.Xaml.Data.BindableAttribute](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.data.bindableattribute.aspx) sur les propriétés.</span><span class="sxs-lookup"><span data-stu-id="e7044-118">For example, you could apply the [Windows.UI.Xaml.Data.BindableAttribute](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.data.bindableattribute.aspx) attribute on properties.</span></span> <span data-ttu-id="e7044-119">Ainsi, le compilateur XAML génère les informations de recherche nécessaires et évite la présence d'une directive runtime dans le fichier Default.rd.xml.</span><span class="sxs-lookup"><span data-stu-id="e7044-119">This causes the XAML compiler to generate the required lookup information and avoids requiring a runtime directive in the Default.rd.xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7044-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7044-120">See Also</span></span>  
 [<span data-ttu-id="e7044-121">Prise en main</span><span class="sxs-lookup"><span data-stu-id="e7044-121">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)  
 [<span data-ttu-id="e7044-122">Exemple : résolution des problèmes de programmation dynamique</span><span class="sxs-lookup"><span data-stu-id="e7044-122">Example: Troubleshooting Dynamic Programming</span></span>](../../../docs/framework/net-native/example-troubleshooting-dynamic-programming.md)
