---
title: "Comment : spécifier le moment où des exceptions d'accès concurrentiel sont levées"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: 6890cc130f4f4101c02bb88c5f5666bcd5cf9b98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360817"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a><span data-ttu-id="57595-102">Comment : spécifier le moment où des exceptions d'accès concurrentiel sont levées</span><span class="sxs-lookup"><span data-stu-id="57595-102">How to: Specify When Concurrency Exceptions are Thrown</span></span>
<span data-ttu-id="57595-103">Dans [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], une exception <xref:System.Data.Linq.ChangeConflictException> est levée lorsque des objets ne sont pas mis à jour en raison de conflits d'accès concurrentiel optimiste.</span><span class="sxs-lookup"><span data-stu-id="57595-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when objects do not update because of optimistic concurrency conflicts.</span></span> <span data-ttu-id="57595-104">Pour plus d’informations, consultez [d’accès concurrentiel optimiste : vue d’ensemble](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="57595-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="57595-105">Avant de soumettre vos modifications à la base de données, vous pouvez spécifier quand des exceptions d'accès concurrentiel doivent être levées :</span><span class="sxs-lookup"><span data-stu-id="57595-105">Before you submit your changes to the database, you can specify when concurrency exceptions should be thrown:</span></span>  
  
-   <span data-ttu-id="57595-106">Lever l'exception au premier échec (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span><span class="sxs-lookup"><span data-stu-id="57595-106">Throw the exception at the first failure (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).</span></span>  
  
-   <span data-ttu-id="57595-107">Terminer toutes les tentatives de mise à jour, cumuler les échecs et signaler les échecs cumulés dans l'exception (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span><span class="sxs-lookup"><span data-stu-id="57595-107">Finish all update tries, accumulate all failures, and report the accumulated failures in the exception (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).</span></span>  
  
 <span data-ttu-id="57595-108">Lorsqu'elle est levée, l'exception <xref:System.Data.Linq.ChangeConflictException> donne accès à une collection <xref:System.Data.Linq.ChangeConflictCollection>.</span><span class="sxs-lookup"><span data-stu-id="57595-108">When thrown, the <xref:System.Data.Linq.ChangeConflictException> exception provides access to a <xref:System.Data.Linq.ChangeConflictCollection> collection.</span></span> <span data-ttu-id="57595-109">Cette collection fournit des détails pour chaque conflit (mappé à une seule tentative de mise à jour non réussie), y compris l'accès à la collection <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>.</span><span class="sxs-lookup"><span data-stu-id="57595-109">This collection provides details for each conflict (mapped to a single failed update try), including access to the <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A> collection.</span></span> <span data-ttu-id="57595-110">Chaque conflit entre membres mappe à un seul membre dans la mise à jour au cours de laquelle le contrôle d'accès concurrentiel a échoué.</span><span class="sxs-lookup"><span data-stu-id="57595-110">Each member conflict maps to a single member in the update that failed the concurrency check.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57595-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="57595-111">Example</span></span>  
 <span data-ttu-id="57595-112">Le code suivant présente des exemples des deux valeurs.</span><span class="sxs-lookup"><span data-stu-id="57595-112">The following code shows examples of both values.</span></span>  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="57595-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="57595-113">See Also</span></span>  
 [<span data-ttu-id="57595-114">Guide pratique pour gérer les conflits de changement</span><span class="sxs-lookup"><span data-stu-id="57595-114">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="57595-115">Apport et soumission de modifications de données</span><span class="sxs-lookup"><span data-stu-id="57595-115">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
