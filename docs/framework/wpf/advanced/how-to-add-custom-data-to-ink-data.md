---
title: "Comment : ajouter des données personnalisées aux données de l'encre"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ca44d6a2c42219f7aec76f8007010c24c610138
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="9fd07-102">Comment : ajouter des données personnalisées aux données de l'encre</span><span class="sxs-lookup"><span data-stu-id="9fd07-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="9fd07-103">Vous pouvez ajouter des données personnalisées à encre sera enregistré lors de l’encre est enregistré sous la forme d’encre sérialisée format ISF (Ink).</span><span class="sxs-lookup"><span data-stu-id="9fd07-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="9fd07-104">Vous pouvez enregistrer les données personnalisées pour le <xref:System.Windows.Ink.DrawingAttributes>, le <xref:System.Windows.Ink.StrokeCollection>, ou <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="9fd07-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="9fd07-105">La possibilité d’enregistrer des données personnalisées sur trois objets vous donne la possibilité de choisir le meilleur emplacement pour enregistrer les données.</span><span class="sxs-lookup"><span data-stu-id="9fd07-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="9fd07-106">Ces trois classes utilisent des méthodes semblables pour stocker et accéder aux données personnalisées.</span><span class="sxs-lookup"><span data-stu-id="9fd07-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="9fd07-107">Seuls les types suivants peuvent être enregistrés en tant que données personnalisées :</span><span class="sxs-lookup"><span data-stu-id="9fd07-107">Only the following types can be saved as custom data:</span></span>  
  
-   <xref:System.Boolean>  
  
-   <span data-ttu-id="9fd07-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-108"><xref:System.Boolean>[]</span></span>  
  
-   <xref:System.Byte>  
  
-   <span data-ttu-id="9fd07-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-109"><xref:System.Byte>[]</span></span>  
  
-   <xref:System.Char>  
  
-   <span data-ttu-id="9fd07-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-110"><xref:System.Char>[]</span></span>  
  
-   <xref:System.DateTime>  
  
-   <span data-ttu-id="9fd07-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-111"><xref:System.DateTime>[]</span></span>  
  
-   <xref:System.Decimal>  
  
-   <span data-ttu-id="9fd07-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-112"><xref:System.Decimal>[]</span></span>  
  
-   <xref:System.Double>  
  
-   <span data-ttu-id="9fd07-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-113"><xref:System.Double>[]</span></span>  
  
-   <xref:System.Int16>  
  
-   <span data-ttu-id="9fd07-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-114"><xref:System.Int16>[]</span></span>  
  
-   <xref:System.Int32>  
  
-   <span data-ttu-id="9fd07-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-115"><xref:System.Int32>[]</span></span>  
  
-   <xref:System.Int64>  
  
-   <span data-ttu-id="9fd07-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-116"><xref:System.Int64>[]</span></span>  
  
-   <xref:System.Single>  
  
-   <span data-ttu-id="9fd07-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-117"><xref:System.Single>[]</span></span>  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <span data-ttu-id="9fd07-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-118"><xref:System.UInt16>[]</span></span>  
  
-   <xref:System.UInt32>  
  
-   <span data-ttu-id="9fd07-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-119"><xref:System.UInt32>[]</span></span>  
  
-   <xref:System.UInt64>  
  
-   <span data-ttu-id="9fd07-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="9fd07-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fd07-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="9fd07-121">Example</span></span>  
 <span data-ttu-id="9fd07-122">L’exemple suivant montre comment ajouter et récupérer des données personnalisées à partir d’un <xref:System.Windows.Ink.StrokeCollection>.</span><span class="sxs-lookup"><span data-stu-id="9fd07-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="9fd07-123">L’exemple suivant crée une application qui affiche un <xref:System.Windows.Controls.InkCanvas> et deux boutons.</span><span class="sxs-lookup"><span data-stu-id="9fd07-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="9fd07-124">Le bouton, `switchAuthor`, Active deux stylets être utilisé par deux auteurs.</span><span class="sxs-lookup"><span data-stu-id="9fd07-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="9fd07-125">Le bouton `changePenColors` modifie la couleur de chaque trait sur la <xref:System.Windows.Controls.InkCanvas> en fonction de l’auteur.</span><span class="sxs-lookup"><span data-stu-id="9fd07-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="9fd07-126">L’application définit deux <xref:System.Windows.Ink.DrawingAttributes> des objets et ajoute une propriété personnalisée à chacun d’eux qui indique l’auteur ayant dessiné le <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="9fd07-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="9fd07-127">Lorsque l’utilisateur clique sur `changePenColors`, l’application modifie l’apparence du trait selon la valeur de la propriété personnalisée.</span><span class="sxs-lookup"><span data-stu-id="9fd07-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
