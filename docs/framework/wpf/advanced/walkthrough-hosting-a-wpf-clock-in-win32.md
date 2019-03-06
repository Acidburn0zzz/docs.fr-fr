---
title: 'Procédure pas à pas : Hébergement d’un WPF Clock dans Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: a58d7e5848ccd62b889b8a7645c08a35822b3352
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352722"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="d3b19-102">Procédure pas à pas : Hébergement d’un WPF Clock dans Win32</span><span class="sxs-lookup"><span data-stu-id="d3b19-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>
<span data-ttu-id="d3b19-103">Pour placer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] à l’intérieur de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, utilisez <xref:System.Windows.Interop.HwndSource>, qui fournit le HWND qui contient votre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenu.</span><span class="sxs-lookup"><span data-stu-id="d3b19-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="d3b19-104">Tout d’abord, vous créez le <xref:System.Windows.Interop.HwndSource>, en lui attribuant des paramètres similaires à CreateWindow.</span><span class="sxs-lookup"><span data-stu-id="d3b19-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span>  <span data-ttu-id="d3b19-105">Vous indiquez ensuite le <xref:System.Windows.Interop.HwndSource> sur le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenu que vous voulez qu’il.</span><span class="sxs-lookup"><span data-stu-id="d3b19-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span>  <span data-ttu-id="d3b19-106">Enfin, vous obtenez le HWND de la <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="d3b19-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="d3b19-107">Cette procédure pas à pas montre comment créer un mixte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] à l’intérieur de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application qui implémente de nouveau le système d’exploitation **propriétés de Date et heure** boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d3b19-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d3b19-108">Prérequis</span><span class="sxs-lookup"><span data-stu-id="d3b19-108">Prerequisites</span></span>  
 <span data-ttu-id="d3b19-109">Consultez [interopérabilité WPF et Win32](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="d3b19-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="d3b19-110">Comment utiliser ce didacticiel</span><span class="sxs-lookup"><span data-stu-id="d3b19-110">How to Use This Tutorial</span></span>  
 <span data-ttu-id="d3b19-111">Ce didacticiel se concentre sur les étapes importantes de la production d’une application d’interopérabilité.</span><span class="sxs-lookup"><span data-stu-id="d3b19-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="d3b19-112">Le didacticiel est complété par un exemple, [interopérabilité Win32 Clock, exemple](https://go.microsoft.com/fwlink/?LinkID=160051), mais que l’exemple est reflètent le produit final.</span><span class="sxs-lookup"><span data-stu-id="d3b19-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="d3b19-113">Ce didacticiel décrit les étapes comme si vous commenciez avec un existant [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] projet de votre choix, éventuellement un projet préexistant et vous ajoutiez un hébergé [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] à votre application.</span><span class="sxs-lookup"><span data-stu-id="d3b19-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="d3b19-114">Vous pouvez comparer votre produit final avec [interopérabilité Win32 Clock, exemple](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="d3b19-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="d3b19-115">Procédure pas à pas de Windows Presentation Foundation dans Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="d3b19-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>  
 <span data-ttu-id="d3b19-116">Le graphique suivant illustre le produit final prévu pour ce didacticiel :</span><span class="sxs-lookup"><span data-stu-id="d3b19-116">The following graphic shows the intended end product of this tutorial:</span></span>  
  
 <span data-ttu-id="d3b19-117">![Boîte de dialogue Propriétés de date et d’heure](./media/interoparch06.PNG "InteropArch06")</span><span class="sxs-lookup"><span data-stu-id="d3b19-117">![Date and Time Properties dialog box](./media/interoparch06.PNG "InteropArch06")</span></span>  
  
 <span data-ttu-id="d3b19-118">Vous pouvez recréer cette boîte de dialogue en créant C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] projet [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]et à l’aide de l’éditeur de boîtes de dialogue pour créer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="d3b19-118">You can recreate this dialog by creating C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and using the dialog editor to create the following:</span></span>  
  
 <span data-ttu-id="d3b19-119">![Boîte de dialogue Propriétés de date et d’heure](./media/interoparch07.PNG "InteropArch07")</span><span class="sxs-lookup"><span data-stu-id="d3b19-119">![Date and Time Properties dialog box](./media/interoparch07.PNG "InteropArch07")</span></span>  
  
 <span data-ttu-id="d3b19-120">(Vous n’avez pas besoin d’utiliser [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] à utiliser <xref:System.Windows.Interop.HwndSource>, et vous n’avez pas besoin d’utiliser C++ pour écrire [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programmes, mais cela est un moyen classique pour ce faire et se prête bien à une explication de didacticiel pas à pas).</span><span class="sxs-lookup"><span data-stu-id="d3b19-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>  
  
 <span data-ttu-id="d3b19-121">Vous devez suivre cinq sous-étapes particulières pour placer un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] horloge dans la boîte de dialogue :</span><span class="sxs-lookup"><span data-stu-id="d3b19-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>  
  
1.  <span data-ttu-id="d3b19-122">Activer votre [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] projet pour appeler du code managé (**/CLR**) en modifiant les paramètres du projet dans [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3b19-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="d3b19-123">Créer un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> dans une DLL distincte.</span><span class="sxs-lookup"><span data-stu-id="d3b19-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>  
  
3.  <span data-ttu-id="d3b19-124">Put qui [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> à l’intérieur d’un <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="d3b19-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>  
  
4.  <span data-ttu-id="d3b19-125">Procurez-vous un HWND pour qui <xref:System.Windows.Controls.Page> à l’aide de la <xref:System.Windows.Interop.HwndSource.Handle%2A> propriété.</span><span class="sxs-lookup"><span data-stu-id="d3b19-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>  
  
5.  <span data-ttu-id="d3b19-126">Utilisez [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] décider où placer le HWND dans la plus grande [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span><span class="sxs-lookup"><span data-stu-id="d3b19-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>  
  
## <a name="clr"></a><span data-ttu-id="d3b19-127">/clr</span><span class="sxs-lookup"><span data-stu-id="d3b19-127">/clr</span></span>  
 <span data-ttu-id="d3b19-128">La première étape consiste à convertir ce unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] projet en une seule peut appeler du code managé.</span><span class="sxs-lookup"><span data-stu-id="d3b19-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span>  <span data-ttu-id="d3b19-129">Vous utilisez l’option de compilateur/CLR, qui sera liée aux DLL nécessaires que vous souhaitez utiliser, puis ajustez la méthode Main pour une utilisation avec [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d3b19-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="d3b19-130">Pour activer l’utilisation du code managé dans le projet C++ : Avec le bouton droit sur les projet win32clock, puis sélectionnez **propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span>  <span data-ttu-id="d3b19-131">Sur le **général** page de propriétés (valeur par défaut), modifier la prise en charge du Common Language Runtime à `/clr`.</span><span class="sxs-lookup"><span data-stu-id="d3b19-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>  
  
 <span data-ttu-id="d3b19-132">Ensuite, ajoutez des références aux DLL nécessaires pour [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll et UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="d3b19-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="d3b19-133">Les instructions suivantes supposent que le système d’exploitation est installé sur le lecteur C:.</span><span class="sxs-lookup"><span data-stu-id="d3b19-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>  
  
1.  <span data-ttu-id="d3b19-134">Cliquez sur les projet win32clock, puis sélectionnez **références...** et à l’intérieur de cette boîte de dialogue :</span><span class="sxs-lookup"><span data-stu-id="d3b19-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>  
  
2.  <span data-ttu-id="d3b19-135">Cliquez sur les projet win32clock, puis sélectionnez **références...** .</span><span class="sxs-lookup"><span data-stu-id="d3b19-135">Right-click win32clock project and select **References...**.</span></span>  
  
3.  <span data-ttu-id="d3b19-136">Cliquez sur **ajouter une nouvelle référence**, onglet Parcourir, entrez C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d3b19-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>  
  
4.  <span data-ttu-id="d3b19-137">Répétez pour PresentationFramework.dll : C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="d3b19-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>  
  
5.  <span data-ttu-id="d3b19-138">Répétez pour WindowsBase.dll : C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="d3b19-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>  
  
6.  <span data-ttu-id="d3b19-139">Répétez pour UIAutomationTypes.dll : C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="d3b19-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>  
  
7.  <span data-ttu-id="d3b19-140">Répétez pour UIAutomationProvider.dll : C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="d3b19-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>  
  
8.  <span data-ttu-id="d3b19-141">Cliquez sur **ajouter une nouvelle référence**, sélectionnez System.dll, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>  
  
9. <span data-ttu-id="d3b19-142">Cliquez sur **OK** pour quitter les Pages de propriétés win32clock pour l’ajout de références.</span><span class="sxs-lookup"><span data-stu-id="d3b19-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
 <span data-ttu-id="d3b19-143">Enfin, ajoutez le `STAThreadAttribute` à la `_tWinMain` méthode pour une utilisation avec [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d3b19-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 <span data-ttu-id="d3b19-144">Cet attribut indique à la [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] que lorsqu’il initialise [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], il doit utiliser un modèle de thread unique cloisonné (STA), qui est nécessaire pour [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (et [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="d3b19-144">This attribute tells the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>  
  
## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="d3b19-145">Créer une page Windows Presentation Framework</span><span class="sxs-lookup"><span data-stu-id="d3b19-145">Create a Windows Presentation Framework Page</span></span>  
 <span data-ttu-id="d3b19-146">Ensuite, vous créez une DLL qui définit un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="d3b19-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="d3b19-147">Il est souvent plus facile de créer le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> en tant qu’application autonome et d’écriture et de débogage la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] partie de cette façon.</span><span class="sxs-lookup"><span data-stu-id="d3b19-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span>  <span data-ttu-id="d3b19-148">Une fois terminé, ce projet peut être activé dans une DLL en double-cliquant sur le projet, en cliquant sur **propriétés**, accédant à l’Application et la modification du type de sortie à la bibliothèque de classes Windows.</span><span class="sxs-lookup"><span data-stu-id="d3b19-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>  
  
 <span data-ttu-id="d3b19-149">Le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] projet dll peut être combiné avec le [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] (solution comprenant deux projets) avec le bouton droit sur la solution, sélectionnez **projet**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>  
  
 <span data-ttu-id="d3b19-150">À utiliser qui [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll à partir de la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] projet, vous devez ajouter une référence :</span><span class="sxs-lookup"><span data-stu-id="d3b19-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>  
  
1.  <span data-ttu-id="d3b19-151">Cliquez sur les projet win32clock, puis sélectionnez **références...** .</span><span class="sxs-lookup"><span data-stu-id="d3b19-151">Right-click win32clock project and select **References...**.</span></span>  
  
2.  <span data-ttu-id="d3b19-152">Cliquez sur **ajouter une nouvelle référence**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-152">Click **Add New Reference**.</span></span>  
  
3.  <span data-ttu-id="d3b19-153">Cliquez sur l’onglet **Projets**.  Sélectionnez WPFClock, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="d3b19-153">Click the **Projects** tab.  Select WPFClock, click OK.</span></span>  
  
4.  <span data-ttu-id="d3b19-154">Cliquez sur **OK** pour quitter les Pages de propriétés win32clock pour l’ajout de références.</span><span class="sxs-lookup"><span data-stu-id="d3b19-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
## <a name="hwndsource"></a><span data-ttu-id="d3b19-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="d3b19-155">HwndSource</span></span>  
 <span data-ttu-id="d3b19-156">Ensuite, vous utilisez <xref:System.Windows.Interop.HwndSource> pour rendre le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> ressembler un HWND.</span><span class="sxs-lookup"><span data-stu-id="d3b19-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span>  <span data-ttu-id="d3b19-157">Ajoutez ce bloc de code dans un fichier C++ :</span><span class="sxs-lookup"><span data-stu-id="d3b19-157">You add this block of code to a C++ file:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
  
    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
        HwndSource^ source = gcnew HwndSource(  
            0, // class style  
            WS_VISIBLE | WS_CHILD, // style  
            0, // exstyle  
            x, y, width, height,  
            "hi", // NAME  
            IntPtr(parent)        // parent window   
            );  
  
        UIElement^ page = gcnew WPFClock::Clock();  
        source->RootVisual = page;  
        return (HWND) source->Handle.ToPointer();  
    }  
}  
}  
```  
  
 <span data-ttu-id="d3b19-158">Il s’agit d’un long bloc de code qui mérite une explication.</span><span class="sxs-lookup"><span data-stu-id="d3b19-158">This is a long piece of code that could use some explanation.</span></span>  <span data-ttu-id="d3b19-159">La première partie est constituée de diverses clauses qui vous évitent d’avoir à qualifier complètement tous les appels :</span><span class="sxs-lookup"><span data-stu-id="d3b19-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 <span data-ttu-id="d3b19-160">Puis vous définissez une fonction qui crée le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] du contenu, met un <xref:System.Windows.Interop.HwndSource> autour d’elle et retourne le HWND :</span><span class="sxs-lookup"><span data-stu-id="d3b19-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 <span data-ttu-id="d3b19-161">Tout d’abord, vous créez un <xref:System.Windows.Interop.HwndSource>, dont les paramètres sont similaires à CreateWindow :</span><span class="sxs-lookup"><span data-stu-id="d3b19-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 <span data-ttu-id="d3b19-162">Ensuite vous créez la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] classe de contenu en appelant son constructeur :</span><span class="sxs-lookup"><span data-stu-id="d3b19-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 <span data-ttu-id="d3b19-163">Vous connectez ensuite la page à la <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="d3b19-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
source->RootVisual = page;  
```  
  
 <span data-ttu-id="d3b19-164">Et dans la dernière ligne, retournez le HWND pour le <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="d3b19-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a><span data-ttu-id="d3b19-165">Positionnement du Hwnd</span><span class="sxs-lookup"><span data-stu-id="d3b19-165">Positioning the Hwnd</span></span>  
 <span data-ttu-id="d3b19-166">Maintenant que vous avez un HWND contenant le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] horloge, vous devez placer le HWND dans le [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d3b19-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span>  <span data-ttu-id="d3b19-167">Si vous saviez exactement où placer le HWND, vous suffirait de communiquer cette taille et l’emplacement pour le `GetHwnd` fonction que vous avez défini précédemment.</span><span class="sxs-lookup"><span data-stu-id="d3b19-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span>  <span data-ttu-id="d3b19-168">Toutefois, étant donné que vous avez utilisé un fichier de ressources pour définir la boîte de dialogue, vous ne savez pas exactement où les HWND sont positionnés.</span><span class="sxs-lookup"><span data-stu-id="d3b19-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span>  <span data-ttu-id="d3b19-169">Vous pouvez utiliser la [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] éditeur de boîtes de dialogue pour placer un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] statique contrôler l’emplacement où l’horloge (« insérer l’horloge ici ») et l’utiliser pour positionner le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] horloge.</span><span class="sxs-lookup"><span data-stu-id="d3b19-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>  
  
 <span data-ttu-id="d3b19-170">Lorsque vous gérez WM_INITDIALOG, vous utilisez `GetDlgItem` pour récupérer le HWND de l’espace réservé STATIC :</span><span class="sxs-lookup"><span data-stu-id="d3b19-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 <span data-ttu-id="d3b19-171">Vous devez calculer la taille et la position de cet espace réservé STATIC, afin de pouvoir placer les [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] d’horloge à cet endroit :</span><span class="sxs-lookup"><span data-stu-id="d3b19-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>  
  
 <span data-ttu-id="d3b19-172">RECT rectangle;</span><span class="sxs-lookup"><span data-stu-id="d3b19-172">RECT rectangle;</span></span>  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 <span data-ttu-id="d3b19-173">Ensuite, masquez l’espace réservé STATIC :</span><span class="sxs-lookup"><span data-stu-id="d3b19-173">Then you hide the placeholder STATIC:</span></span>  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 <span data-ttu-id="d3b19-174">Et créer le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND dans cet emplacement de l’horloge :</span><span class="sxs-lookup"><span data-stu-id="d3b19-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 <span data-ttu-id="d3b19-175">Pour rendre le didacticiel intéressant et créer une véritable [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] horloge, vous devez créer un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contrôle d’horloge à ce stade.</span><span class="sxs-lookup"><span data-stu-id="d3b19-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="d3b19-176">Cette procédure se fait principalement en langage de balisage, avec quelques gestionnaires d’événements dans le code-behind.</span><span class="sxs-lookup"><span data-stu-id="d3b19-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="d3b19-177">Étant donné que ce didacticiel est sur l’interopérabilité et pas la conception des contrôles, le code complet de le [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] horloge est fourni ici comme un bloc de code, sans instructions discrètes pour le développement ou la signification de chaque partie.</span><span class="sxs-lookup"><span data-stu-id="d3b19-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="d3b19-178">N’hésitez pas à tester ce code pour changer l’apparence ou la fonctionnalité du contrôle.</span><span class="sxs-lookup"><span data-stu-id="d3b19-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>  
  
 <span data-ttu-id="d3b19-179">Voici le code XAML :</span><span class="sxs-lookup"><span data-stu-id="d3b19-179">Here is the markup:</span></span>  
  
 [!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 <span data-ttu-id="d3b19-180">Voici le code-behind correspondant :</span><span class="sxs-lookup"><span data-stu-id="d3b19-180">And here is the accompanying code-behind:</span></span>  
  
 [!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 <span data-ttu-id="d3b19-181">Le résultat final ressemble à ceci :</span><span class="sxs-lookup"><span data-stu-id="d3b19-181">The final result looks like:</span></span>  
  
 <span data-ttu-id="d3b19-182">![Boîte de dialogue Propriétés de date et d’heure](./media/interoparch08.PNG "InteropArch08")</span><span class="sxs-lookup"><span data-stu-id="d3b19-182">![Date and Time Properties dialog box](./media/interoparch08.PNG "InteropArch08")</span></span>  
  
 <span data-ttu-id="d3b19-183">Pour comparer votre résultat final au code qui a produit cette capture d’écran, consultez [interopérabilité Win32 Clock, exemple](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="d3b19-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b19-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3b19-184">See also</span></span>
- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="d3b19-185">Interopérabilité WPF et Win32</span><span class="sxs-lookup"><span data-stu-id="d3b19-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- [<span data-ttu-id="d3b19-186">Interopérabilité Win32 Clock, exemple</span><span class="sxs-lookup"><span data-stu-id="d3b19-186">Win32 Clock Interoperation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160051)
