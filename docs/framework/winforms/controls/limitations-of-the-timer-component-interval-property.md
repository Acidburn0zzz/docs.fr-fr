---
title: Limitations du composant Timer Windows Forms&#39;propriété d’intervalle s
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 4808d115ff842c6c0e6b036da9fe20bb1b48f8a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536024"
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a><span data-ttu-id="9c7ab-102">Limitations du composant Timer Windows Forms&#39;propriété d’intervalle s</span><span class="sxs-lookup"><span data-stu-id="9c7ab-102">Limitations of the Windows Forms Timer Component&#39;s Interval Property</span></span>
<span data-ttu-id="9c7ab-103">Windows Forms <xref:System.Windows.Forms.Timer> composant a un <xref:System.Windows.Forms.Timer.Interval%2A> propriété qui spécifie le nombre de millisecondes qui s’écouler entre deux événements de minuterie suivant.</span><span class="sxs-lookup"><span data-stu-id="9c7ab-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="9c7ab-104">À moins que le composant est désactivé, une minuterie continue à recevoir le <xref:System.Windows.Forms.Timer.Tick> événement à intervalles réguliers à peu près égales.</span><span class="sxs-lookup"><span data-stu-id="9c7ab-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="9c7ab-105">Ce composant est conçu pour un environnement Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9c7ab-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="9c7ab-106">Si vous avez besoin d’un minuteur adapté à un environnement de serveur, consultez l’article [Introduction aux minuteurs serveur](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="9c7ab-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="9c7ab-107">La propriété Interval</span><span class="sxs-lookup"><span data-stu-id="9c7ab-107">The Interval Property</span></span>  
 <span data-ttu-id="9c7ab-108">Le <xref:System.Windows.Forms.Timer.Interval%2A> propriété présente quelques limitations à prendre en compte les quand vous programmez un <xref:System.Windows.Forms.Timer> composant :</span><span class="sxs-lookup"><span data-stu-id="9c7ab-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
-   <span data-ttu-id="9c7ab-109">Si votre application ou une autre application effectue des demandes importantes sur le système, telles que les boucles longues, calculs complexes, ou le lecteur, réseau ou des accès de port, votre application ne disposeront pas d’événements de la minuterie aussi souvent que le <xref:System.Windows.Forms.Timer.Interval%2A> propriété spécifie.</span><span class="sxs-lookup"><span data-stu-id="9c7ab-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
-   <span data-ttu-id="9c7ab-110">L’intervalle n’est pas garantie devant s’écouler exactement le moment.</span><span class="sxs-lookup"><span data-stu-id="9c7ab-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="9c7ab-111">Pour garantir l’exactitude, la minuterie doit consulter l’horloge système en fonction des besoins, plutôt que de suivre en interne le temps écoulé.</span><span class="sxs-lookup"><span data-stu-id="9c7ab-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
-   <span data-ttu-id="9c7ab-112">La précision de la <xref:System.Windows.Forms.Timer.Interval%2A> propriété est exprimée en millisecondes.</span><span class="sxs-lookup"><span data-stu-id="9c7ab-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="9c7ab-113">Certains ordinateurs fournissent un compteur haute résolution d’une résolution supérieure aux millisecondes.</span><span class="sxs-lookup"><span data-stu-id="9c7ab-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="9c7ab-114">La disponibilité d’un tel compteur varie selon le matériel de processeur de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="9c7ab-114">The availability of such a counter depends on the processor hardware of your computer.</span></span> <span data-ttu-id="9c7ab-115">Pour plus d’informations, consultez l’article 172338, « Comment utiliser QueryPerformanceCounter à temps Code, » dans la Base de connaissances Microsoft à http://support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9c7ab-115">For more information, see article 172338, "How To Use QueryPerformanceCounter to Time Code," in the Microsoft Knowledge Base at http://support.microsoft.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c7ab-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c7ab-116">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="9c7ab-117">Timer, composant</span><span class="sxs-lookup"><span data-stu-id="9c7ab-117">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="9c7ab-118">Vue d’ensemble du composant Timer</span><span class="sxs-lookup"><span data-stu-id="9c7ab-118">Timer Component Overview</span></span>](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
