---
title: Étendre le cadre de transparence dans une application WPF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aad070bca408fc608eb000948c1b942d08f02018
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2018
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="31e43-102">Étendre le cadre de transparence dans une application WPF</span><span class="sxs-lookup"><span data-stu-id="31e43-102">Extend Glass Frame Into a WPF Application</span></span>
<span data-ttu-id="31e43-103">Cette rubrique montre comment étendre le cadre de transparence [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] dans la zone cliente d’une application [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31e43-103">This topic demonstrates how to extend the [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] glass frame into the client area of a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31e43-104">Cet exemple fonctionne uniquement sur une machine [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] exécutant le Gestionnaire de fenêtres du Bureau (DWM) avec transparence activée.</span><span class="sxs-lookup"><span data-stu-id="31e43-104">This example will only work on a [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> <span data-ttu-id="31e43-105">La version Home Basic [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] ne prend pas en charge l’effet de transparence.</span><span class="sxs-lookup"><span data-stu-id="31e43-105">[!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="31e43-106">Les zones qui affichent généralement un effet de transparence sur les autres versions de [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] offrent un rendu opaque.</span><span class="sxs-lookup"><span data-stu-id="31e43-106">Areas that would typically render with the transparent glass effect on other editions of [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] are rendered opaque.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31e43-107">Exemple</span><span class="sxs-lookup"><span data-stu-id="31e43-107">Example</span></span>  
 <span data-ttu-id="31e43-108">L’image suivante montre le cadre de transparence étendu dans la barre d’adresse d’Internet Explorer 7.</span><span class="sxs-lookup"><span data-stu-id="31e43-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7.</span></span>  
  
 <span data-ttu-id="31e43-109">**Internet Explorer avec cadre de transparence derrière la barre d’adresse.**</span><span class="sxs-lookup"><span data-stu-id="31e43-109">**Internet Explorer with extended glass frame behind address bar.**</span></span>  
  
 <span data-ttu-id="31e43-110">![IE7 avec trame transparente étendue derrière la barre d'adresse.](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")</span><span class="sxs-lookup"><span data-stu-id="31e43-110">![IE7 with glass frame extended behind address bar.](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")</span></span>  
  
 <span data-ttu-id="31e43-111">Pour étendre le cadre de transparence sur une application [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], un accès à l’élément non géré [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="31e43-111">To extend the glass frame on a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application, access to unmanaged [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] is needed.</span></span> <span data-ttu-id="31e43-112">L’exemple de code suivant effectue un appel de code non géré (pinvoke) pour les deux éléments [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] nécessaires pour étendre le cadre dans la zone cliente.</span><span class="sxs-lookup"><span data-stu-id="31e43-112">The following code example does a Platform Invoke (pinvoke) for the two [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] needed to extend the frame into the client area.</span></span> <span data-ttu-id="31e43-113">Chacun de ces éléments [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] sont déclarés dans une classe appelée **NonClientRegionAPI**.</span><span class="sxs-lookup"><span data-stu-id="31e43-113">Each of these [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] are declared in a class called **NonClientRegionAPI**.</span></span>  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MARGINS  
{  
    public int cxLeftWidth;      // width of left border that retains its size  
    public int cxRightWidth;     // width of right border that retains its size  
    public int cyTopHeight;      // height of top border that retains its size  
    public int cyBottomHeight;   // height of bottom border that retains its size  
};  
  
[DllImport("DwmApi.dll")]  
public static extern int DwmExtendFrameIntoClientArea(  
    IntPtr hwnd,  
    ref MARGINS pMarInset);  
```  
  
```vb  
<StructLayout(LayoutKind.Sequential)>  
        Public Structure MARGINS  
            Public cxLeftWidth As Integer ' width of left border that retains its size  
            Public cxRightWidth As Integer ' width of right border that retains its size  
            Public cyTopHeight As Integer ' height of top border that retains its size  
            Public cyBottomHeight As Integer ' height of bottom border that retains its size  
        End Structure  
  
        <DllImport("DwmApi.dll")>  
        Public Shared Function DwmExtendFrameIntoClientArea(ByVal hwnd As IntPtr, ByRef pMarInset As MARGINS) As Integer  
        End Function  
```  
  
 <span data-ttu-id="31e43-114">[DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx) est la fonction DWM qui étend le cadre dans la zone cliente.</span><span class="sxs-lookup"><span data-stu-id="31e43-114">[DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="31e43-115">Elle nécessite deux paramètres ; un handle de fenêtre et une structure [MARGINS](https://msdn.microsoft.com/library/bb773244.aspx).</span><span class="sxs-lookup"><span data-stu-id="31e43-115">It takes two parameters; a window handle and a [MARGINS](https://msdn.microsoft.com/library/bb773244.aspx) structure.</span></span> <span data-ttu-id="31e43-116">[MARGINS](https://msdn.microsoft.com/library/bb773244.aspx) indique à DWM le niveau d’extension du cadre dans la zone cliente.</span><span class="sxs-lookup"><span data-stu-id="31e43-116">[MARGINS](https://msdn.microsoft.com/library/bb773244.aspx) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31e43-117">Exemple</span><span class="sxs-lookup"><span data-stu-id="31e43-117">Example</span></span>  
 <span data-ttu-id="31e43-118">Pour utiliser la fonction [DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx), un handle de fenêtre doit être obtenu.</span><span class="sxs-lookup"><span data-stu-id="31e43-118">To use the [DwmExtendFrameIntoClientArea](https://msdn.microsoft.com/library/aa969512.aspx) function, a window handle must be obtained.</span></span> <span data-ttu-id="31e43-119">Dans [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], le handle de fenêtre peut être obtenu à partir de la <xref:System.Windows.Interop.HwndSource.Handle%2A> propriété d’un <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="31e43-119">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="31e43-120">Dans l’exemple suivant, le cadre est étendu dans la zone cliente sur le <xref:System.Windows.FrameworkElement.Loaded> l’événement de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="31e43-120">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>  
  
```csharp  
void OnLoaded(object sender, RoutedEventArgs e)  
{  
   try  
   {  
      // Obtain the window handle for WPF application  
      IntPtr mainWindowPtr = new WindowInteropHelper(this).Handle;  
      HwndSource mainWindowSrc = HwndSource.FromHwnd(mainWindowPtr);  
      mainWindowSrc.CompositionTarget.BackgroundColor = Color.FromArgb(0, 0, 0, 0);  
  
      // Get System Dpi  
      System.Drawing.Graphics desktop = System.Drawing.Graphics.FromHwnd(mainWindowPtr);  
      float DesktopDpiX = desktop.DpiX;  
      float DesktopDpiY = desktop.DpiY;  
  
      // Set Margins  
      NonClientRegionAPI.MARGINS margins = new NonClientRegionAPI.MARGINS();  
  
      // Extend glass frame into client area  
      // Note that the default desktop Dpi is 96dpi. The  margins are  
      // adjusted for the system Dpi.  
      margins.cxLeftWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));  
      margins.cxRightWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));  
      margins.cyTopHeight = Convert.ToInt32(((int)topBar.ActualHeight + 5) * (DesktopDpiX / 96));  
      margins.cyBottomHeight = Convert.ToInt32(5 * (DesktopDpiX / 96));  
  
      int hr = NonClientRegionAPI.DwmExtendFrameIntoClientArea(mainWindowSrc.Handle, ref margins);  
      //  
      if (hr < 0)  
      {  
         //DwmExtendFrameIntoClientArea Failed  
      }  
   }  
   // If not Vista, paint background white.  
   catch (DllNotFoundException)  
   {  
      Application.Current.MainWindow.Background = Brushes.White;  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="31e43-121">Exemple</span><span class="sxs-lookup"><span data-stu-id="31e43-121">Example</span></span>  
 <span data-ttu-id="31e43-122">L’exemple suivant montre une simple fenêtre dans laquelle le cadre est étendu dans la zone cliente.</span><span class="sxs-lookup"><span data-stu-id="31e43-122">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="31e43-123">Le cadre est étendu derrière la bordure supérieure contenant les deux <xref:System.Windows.Controls.TextBox> objets.</span><span class="sxs-lookup"><span data-stu-id="31e43-123">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>  
  
```xaml  
<Window x:Class="SDKSample.Window1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    Title="Extended Glass in WPF" Height="300" Width="400"   
    Loaded="OnLoaded" Background="Transparent"  
    >  
  <Grid ShowGridLines="True">  
    <DockPanel Name="mainDock">  
      <!-- The border is used to compute the rendered height with margins.  
           topBar contents will be displayed on the extended glass frame.-->  
      <Border Name="topBar" DockPanel.Dock="Top" >  
        <Grid Name="grid">  
          <Grid.ColumnDefinitions>  
            <ColumnDefinition MinWidth="100" Width="*"/>  
            <ColumnDefinition Width="Auto"/>  
          </Grid.ColumnDefinitions>  
          <TextBox Grid.Column="0" MinWidth="100" Margin="0,0,10,5">Path</TextBox>  
          <TextBox Grid.Column="1" MinWidth="75" Margin="0,0,0,5">Search</TextBox>  
        </Grid>  
      </Border>  
      <Grid DockPanel.Dock="Top" >  
        <Grid.ColumnDefinitions>  
          <ColumnDefinition/>  
        </Grid.ColumnDefinitions>  
        <TextBox Grid.Column="0" AcceptsReturn="True"/>  
      </Grid>  
    </DockPanel>  
  </Grid>  
</Window>  
```  
  
 <span data-ttu-id="31e43-124">L’image suivante montre le cadre de transparence étendu dans une application [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31e43-124">The following image illustrates the glass frame extended into a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application.</span></span>  
  
 <span data-ttu-id="31e43-125">**Cadre de transparence étendu dans une** application [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]**.**</span><span class="sxs-lookup"><span data-stu-id="31e43-125">**Glass Frame Extended into a**  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]  **Application.**</span></span>  
  
 <span data-ttu-id="31e43-126">![Cadre de transparence étendu dans une application WPF.](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")</span><span class="sxs-lookup"><span data-stu-id="31e43-126">![Glass Frame Extended into a WPF application.](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31e43-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31e43-127">See Also</span></span>  
 [<span data-ttu-id="31e43-128">Vue d’ensemble du Gestionnaire de fenêtrage</span><span class="sxs-lookup"><span data-stu-id="31e43-128">Desktop Window Manager Overview</span></span>](https://msdn.microsoft.com/library/aa969540.aspx)  
 [<span data-ttu-id="31e43-129">Vue d’ensemble de gestionnaire de fenêtrage flou</span><span class="sxs-lookup"><span data-stu-id="31e43-129">Desktop Window Manager Blur Overview</span></span>](https://msdn.microsoft.com/library/aa969537.aspx)  
 [<span data-ttu-id="31e43-130">DwmExtendFrameIntoClientArea</span><span class="sxs-lookup"><span data-stu-id="31e43-130">DwmExtendFrameIntoClientArea</span></span>](https://msdn.microsoft.com/library/aa969512.aspx)
