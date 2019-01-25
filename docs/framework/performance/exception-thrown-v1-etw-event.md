---
title: Événement ETW d'exception Thrown_V1
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07932a12916138dd7cbee2576e4fc747898b8063
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610840"
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="10571-102">Événement ETW d'exception Thrown_V1</span><span class="sxs-lookup"><span data-stu-id="10571-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="10571-103">Cet événement capture des informations sur les exceptions levées.</span><span class="sxs-lookup"><span data-stu-id="10571-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="10571-104">Le tableau suivant affiche le mot clé sous lequel l’événement est déclenché, ainsi que le niveau de l’événement.</span><span class="sxs-lookup"><span data-stu-id="10571-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="10571-105">(Pour plus d'informations, consultez [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="10571-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="10571-106">Mot clé pour déclencher l'événement</span><span class="sxs-lookup"><span data-stu-id="10571-106">Keyword for raising the event</span></span>|<span data-ttu-id="10571-107">Niveau</span><span class="sxs-lookup"><span data-stu-id="10571-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="10571-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="10571-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="10571-109">Avertissement (2)</span><span class="sxs-lookup"><span data-stu-id="10571-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="10571-110">Le tableau suivant affiche des informations sur les événements.</span><span class="sxs-lookup"><span data-stu-id="10571-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="10571-111">Événement</span><span class="sxs-lookup"><span data-stu-id="10571-111">Event</span></span>|<span data-ttu-id="10571-112">ID d'événement</span><span class="sxs-lookup"><span data-stu-id="10571-112">Event ID</span></span>|<span data-ttu-id="10571-113">Moment du déclenchement</span><span class="sxs-lookup"><span data-stu-id="10571-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="10571-114">80</span><span class="sxs-lookup"><span data-stu-id="10571-114">80</span></span>|<span data-ttu-id="10571-115">Une exception managée est levée.</span><span class="sxs-lookup"><span data-stu-id="10571-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="10571-116">Le tableau suivant affiche des données liées aux événements.</span><span class="sxs-lookup"><span data-stu-id="10571-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="10571-117">Nom du champ</span><span class="sxs-lookup"><span data-stu-id="10571-117">Field name</span></span>|<span data-ttu-id="10571-118">Type de données</span><span class="sxs-lookup"><span data-stu-id="10571-118">Data type</span></span>|<span data-ttu-id="10571-119">Description</span><span class="sxs-lookup"><span data-stu-id="10571-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="10571-120">Type d'exception</span><span class="sxs-lookup"><span data-stu-id="10571-120">Exception Type</span></span>|<span data-ttu-id="10571-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="10571-121">win:UnicodeString</span></span>|<span data-ttu-id="10571-122">Type de l’exception, par exemple `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="10571-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="10571-123">Message d’exception</span><span class="sxs-lookup"><span data-stu-id="10571-123">Exception Message</span></span>|<span data-ttu-id="10571-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="10571-124">win:UnicodeString</span></span>|<span data-ttu-id="10571-125">Message d’exception réel.</span><span class="sxs-lookup"><span data-stu-id="10571-125">Actual exception message.</span></span>|  
|<span data-ttu-id="10571-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="10571-126">EIPCodeThrow</span></span>|<span data-ttu-id="10571-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="10571-127">win:Pointer</span></span>|<span data-ttu-id="10571-128">Pointeur d’instruction où l’exception s’est produite.</span><span class="sxs-lookup"><span data-stu-id="10571-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="10571-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="10571-129">ExceptionHR</span></span>|<span data-ttu-id="10571-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="10571-130">win:UInt32</span></span>|<span data-ttu-id="10571-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span><span class="sxs-lookup"><span data-stu-id="10571-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="10571-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="10571-132">ExceptionFlags</span></span>|<span data-ttu-id="10571-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="10571-133">win:UInt16</span></span>|<span data-ttu-id="10571-134">0 x 01 : HasInnerException (consultez [événements ETW du CLR](../../../docs/framework/performance/clr-etw-events.md) dans la documentation de Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="10571-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="10571-135">0 x 02 : IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="10571-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="10571-136">0 x 04 : IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="10571-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="10571-137">0 x 08 : IsCorruptedStateException (indique que l’état du processus est endommagé ; consultez [gestion des Exceptions d’état endommagé](https://go.microsoft.com/fwlink/?LinkId=179681) sur MSDN).</span><span class="sxs-lookup"><span data-stu-id="10571-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="10571-138">0 x 10 : IsCLSCompliant (une exception qui dérive de <xref:System.Exception> est conforme CLS ; sinon, il n’est pas conforme CLS).</span><span class="sxs-lookup"><span data-stu-id="10571-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="10571-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="10571-139">ClrInstanceID</span></span>|<span data-ttu-id="10571-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="10571-140">win:UInt16</span></span>|<span data-ttu-id="10571-141">ID unique de l'instance de CLR ou CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="10571-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10571-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10571-142">See also</span></span>
- [<span data-ttu-id="10571-143">Événements ETW du CLR</span><span class="sxs-lookup"><span data-stu-id="10571-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
