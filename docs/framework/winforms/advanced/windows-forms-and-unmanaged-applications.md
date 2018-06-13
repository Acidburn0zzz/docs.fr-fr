---
title: Applications Windows Forms et non managées
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: c51645fb64f512b5974000f89e8e98f884a7381d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526199"
---
# <a name="windows-forms-and-unmanaged-applications"></a>Applications Windows Forms et non managées
Les contrôles et les applications Windows Forms peuvent interagir avec des applications non managées, avec certaines restrictions. Les sections suivantes décrivent les scénarios et les configurations pris en charge et non pris en charge par les applications et les contrôles Windows Forms.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Vue d'ensemble des applications Windows Forms et non managées](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 Propose des informations générales sur l'utilisation et l'implémentation des contrôles Windows Forms qui fonctionnent avec les applications non managées.  
  
 [Guide pratique pour prendre en charge COM Interop en affichant un Windows Form avec la méthode ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 Fournit un exemple de code qui montre comment utiliser la méthode <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> pour exécuter un Windows Form dans une application non managée.  
  
 [Comment : prendre en charge l’interopérabilité COM en affichant chaque Windows Form sur son propre thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Fournit un exemple de code qui montre comment exécuter un Windows Form sur son propre thread.  
  
 Consultez également [Procédure pas à pas : prise en charge de COM Interop en affichant chaque Windows Forms sur son propre thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## <a name="reference"></a>Référence  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 Permet de créer un thread distinct pour un Windows Form.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 Démarre une boucle de message pour un thread.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Marshale les appels à partir d’une application non managée vers un formulaire.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Exposition de composants .NET Framework à COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Propose des informations générales sur l'utilisation de types .NET Framework dans les applications non managées.
