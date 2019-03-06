---
title: 'Procédure : Encoder et décoder une image GIF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding GIF images [WPF]
- encoding image formats [WPF]
- decoding GIF images [WPF]
- decoding image formats [WPF]
- GIF decoding [WPF]
- GIF encoding [WPF]
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
ms.openlocfilehash: 245cc2db2c3cd0187c17bc992343eb8ab30da2ea
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353411"
---
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="81932-102">Procédure : Encoder et décoder une image GIF</span><span class="sxs-lookup"><span data-stu-id="81932-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="81932-103">Les exemples suivants montrent comment décoder et encoder une [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] de l’image à l’aide spécifique au <xref:System.Windows.Media.Imaging.GifBitmapDecoder> et <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objets.</span><span class="sxs-lookup"><span data-stu-id="81932-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81932-104">Exemple</span><span class="sxs-lookup"><span data-stu-id="81932-104">Example</span></span>  
 <span data-ttu-id="81932-105">Cet exemple montre comment décoder une [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] à l’aide de l’image un <xref:System.Windows.Media.Imaging.GifBitmapDecoder> à partir d’un <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="81932-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="81932-106">Exemple</span><span class="sxs-lookup"><span data-stu-id="81932-106">Example</span></span>  
 <span data-ttu-id="81932-107">Cet exemple montre comment encoder un <xref:System.Windows.Media.Imaging.BitmapSource> dans un [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] à l’aide de l’image un <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span><span class="sxs-lookup"><span data-stu-id="81932-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="81932-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81932-108">See also</span></span>
- [<span data-ttu-id="81932-109">Vue d’ensemble de la création d’images</span><span class="sxs-lookup"><span data-stu-id="81932-109">Imaging Overview</span></span>](imaging-overview.md)
