---
title: 'Comment : déterminer les paramètres pris en charge par un encodeur'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 7f7c270c4ae590c070103d51f116158869b678c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521977"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>Comment : déterminer les paramètres pris en charge par un encodeur
Vous pouvez ajuster les paramètres d’image, par exemple au niveau de qualité et de la compression, mais vous devez connaître les paramètres sont pris en charge par un encodeur d’image donné. Le <xref:System.Drawing.Image> classe fournit le <xref:System.Drawing.Image.GetEncoderParameterList%2A> méthode afin que vous puissiez déterminer quels paramètres d’image sont pris en charge pour un encodeur spécifique. Vous spécifiez l’encodeur avec un GUID. Le <xref:System.Drawing.Image.GetEncoderParameterList%2A> méthode retourne un tableau de <xref:System.Drawing.Imaging.EncoderParameter> objets.  
  
## <a name="example"></a>Exemple  
 L’exemple de code suivant génère les paramètres pris en charge pour l’encodeur JPEG. Utilisez la liste des catégories de paramètre et les GUID associés dans le <xref:System.Drawing.Imaging.Encoder> vue d’ensemble de la classe pour déterminer la catégorie de chaque paramètre.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Cet exemple nécessite :  
  
-   une application Windows Forms ;  
  
-   A <xref:System.Windows.Forms.PaintEventArgs>, qui est un paramètre de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide pratique pour répertorier les encodeurs installés](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Types de bitmaps](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [Utilisation d’encodeurs et de décodeurs d’images dans GDI+ managé](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
