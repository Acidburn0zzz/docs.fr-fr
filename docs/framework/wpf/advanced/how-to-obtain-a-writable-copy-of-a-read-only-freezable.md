---
title: "Comment : obtenir une copie en écriture d'un Freezable en lecture seule"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 894a2e42ca3f5cbb159c3129227f4b03e71fc4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543619"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="4bcc5-102">Comment : obtenir une copie en écriture d'un Freezable en lecture seule</span><span class="sxs-lookup"><span data-stu-id="4bcc5-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="4bcc5-103">Cet exemple montre comment utiliser le <xref:System.Windows.Freezable.Clone%2A> méthode pour créer une copie en lecture seule accessible en écriture <xref:System.Windows.Freezable>.</span><span class="sxs-lookup"><span data-stu-id="4bcc5-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="4bcc5-104">Après un <xref:System.Windows.Freezable> objet est marqué comme en lecture seule (« figé »), vous ne pouvez pas le modifier.</span><span class="sxs-lookup"><span data-stu-id="4bcc5-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="4bcc5-105">Toutefois, vous pouvez utiliser la <xref:System.Windows.Freezable.Clone%2A> méthode pour créer un clone modifiable de l’objet figé.</span><span class="sxs-lookup"><span data-stu-id="4bcc5-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bcc5-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="4bcc5-106">Example</span></span>  
 <span data-ttu-id="4bcc5-107">L’exemple suivant crée un clone modifiable de figé <xref:System.Windows.Media.SolidColorBrush> objet.</span><span class="sxs-lookup"><span data-stu-id="4bcc5-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="4bcc5-108">Pour plus d’informations sur <xref:System.Windows.Freezable> , consultez la [vue d’ensemble des objets Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4bcc5-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bcc5-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4bcc5-109">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CloneCurrentValue%2A>  
 [<span data-ttu-id="4bcc5-110">Vue d’ensemble des objets Freezable</span><span class="sxs-lookup"><span data-stu-id="4bcc5-110">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="4bcc5-111">Rubriques de guide pratique</span><span class="sxs-lookup"><span data-stu-id="4bcc5-111">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
