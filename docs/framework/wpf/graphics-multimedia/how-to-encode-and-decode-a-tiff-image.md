---
title: 'Comment : encoder et décoder une image TIFF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TIFF encoding [WPF]
- encoding TIFF images [WPF]
- encoding image formats [WPF]
- decoding TIFF images [WPF]
- decoding image formats [WPF]
- TIFF decoding [WPF]
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
ms.openlocfilehash: 94bea19b997f0ee266176ba985a3cd8ff6781cfd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559485"
---
# <a name="how-to-encode-and-decode-a-tiff-image"></a><span data-ttu-id="9ca32-102">Comment : encoder et décoder une image TIFF</span><span class="sxs-lookup"><span data-stu-id="9ca32-102">How to: Encode and Decode a TIFF Image</span></span>
<span data-ttu-id="9ca32-103">Les exemples suivants montrent comment décoder et encoder une [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] de l’image à l’aide spécifique au <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> et <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> objets.</span><span class="sxs-lookup"><span data-stu-id="9ca32-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] image using the specific <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> and <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ca32-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="9ca32-104">Example</span></span>  
 <span data-ttu-id="9ca32-105">Cet exemple montre comment décoder une [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] à l’aide de l’image un <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> d’un <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="9ca32-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] image using a <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="9ca32-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="9ca32-106">Example</span></span>  
 <span data-ttu-id="9ca32-107">Cet exemple montre comment encoder un <xref:System.Windows.Media.Imaging.BitmapSource> dans un [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] à l’aide de l’image un <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="9ca32-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] image using a <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="9ca32-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9ca32-108">See Also</span></span>  
 [<span data-ttu-id="9ca32-109">Vue d’ensemble de la création d’images</span><span class="sxs-lookup"><span data-stu-id="9ca32-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
