---
title: "Comment : produire une valeur en fonction d'une liste d'éléments liés"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: d61631949382c177000b85aa8f4e093c3532c7ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556833"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="162ae-102">Comment : produire une valeur en fonction d'une liste d'éléments liés</span><span class="sxs-lookup"><span data-stu-id="162ae-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="162ae-103"><xref:System.Windows.Data.MultiBinding> vous permet de lier une propriété de cible de liaison à une liste de propriétés de la source, puis appliquer une logique pour produire une valeur avec les entrées données.</span><span class="sxs-lookup"><span data-stu-id="162ae-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="162ae-104">Cet exemple montre comment utiliser <xref:System.Windows.Data.MultiBinding>.</span><span class="sxs-lookup"><span data-stu-id="162ae-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="162ae-105">Exemple</span><span class="sxs-lookup"><span data-stu-id="162ae-105">Example</span></span>  
 <span data-ttu-id="162ae-106">Dans l’exemple suivant, `NameListData` fait référence à une collection d’objets `PersonName`, qui sont des objets contenant deux propriétés, `firstName` et `lastName`.</span><span class="sxs-lookup"><span data-stu-id="162ae-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="162ae-107">L’exemple suivant produit un <xref:System.Windows.Controls.TextBlock> qui présente d’abord le prénom et le nom d’une personne avec le nom de famille.</span><span class="sxs-lookup"><span data-stu-id="162ae-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="162ae-108">Pour comprendre comment est généré le format nom-prénom, jetons un œil à l’implémentation du `NameConverter` :</span><span class="sxs-lookup"><span data-stu-id="162ae-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="162ae-109">`NameConverter` implémente l'interface <xref:System.Windows.Data.IMultiValueConverter>.</span><span class="sxs-lookup"><span data-stu-id="162ae-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="162ae-110">`NameConverter` prend les valeurs des liaisons individuelles et les stocke dans le tableau d’objets de valeurs.</span><span class="sxs-lookup"><span data-stu-id="162ae-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="162ae-111">L’ordre dans lequel le <xref:System.Windows.Data.Binding> éléments s’affichent sous la <xref:System.Windows.Data.MultiBinding> élément est l’ordre dans lequel ces valeurs sont stockées dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="162ae-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="162ae-112">La valeur de la <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribut est référencé par l’argument du paramètre de la <xref:System.Windows.Data.MultiBinding.Converter%2A> méthode qui effectue un commutateur sur le paramètre pour déterminer comment mettre en forme le nom.</span><span class="sxs-lookup"><span data-stu-id="162ae-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="162ae-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="162ae-113">See Also</span></span>  
 [<span data-ttu-id="162ae-114">Convertir des données liées</span><span class="sxs-lookup"><span data-stu-id="162ae-114">Convert Bound Data</span></span>](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)  
 [<span data-ttu-id="162ae-115">Vue d’ensemble de la liaison de données</span><span class="sxs-lookup"><span data-stu-id="162ae-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="162ae-116">Rubriques de guide pratique</span><span class="sxs-lookup"><span data-stu-id="162ae-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
