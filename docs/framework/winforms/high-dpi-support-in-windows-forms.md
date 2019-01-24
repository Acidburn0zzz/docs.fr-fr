---
title: Prise en charge de haute résolution dans les Windows Forms
ms.date: 05/16/2017
helpviewer_keywords:
- High DPI in Windows Forms
- Dynamic rescaling in Windows Forms
- Windows Forms layout
- Windows Forms dynamic resizing
ms.assetid: 075ea4c3-900c-4f8a-9dd2-13ea6804346b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c591aa19a13af2f5b38c46a886b8e0ee2f76c38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540648"
---
# <a name="high-dpi-support-in-windows-forms"></a><span data-ttu-id="db1e7-102">Prise en charge de haute résolution dans les Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db1e7-102">High DPI support in Windows Forms</span></span>

<span data-ttu-id="db1e7-103">À compter de .NET Framework 4.7, Windows Forms inclut des améliorations pour la haute résolution courants et scénarios de résolution dynamiques.</span><span class="sxs-lookup"><span data-stu-id="db1e7-103">Starting with the .NET Framework 4.7, Windows Forms includes enhancements for common high DPI and dynamic DPI scenarios.</span></span> <span data-ttu-id="db1e7-104">Elles incluent notamment :</span><span class="sxs-lookup"><span data-stu-id="db1e7-104">These include:</span></span> 

- <span data-ttu-id="db1e7-105">Améliorations de la mise à l’échelle et la disposition d’un nombre de Windows Forms des contrôles, tels que le <xref:System.Windows.Forms.MonthCalendar> contrôle et le <xref:System.Windows.Forms.CheckedListBox> contrôle.</span><span class="sxs-lookup"><span data-stu-id="db1e7-105">Improvements in the scaling and layout of a number of Windows Forms controls, such as the <xref:System.Windows.Forms.MonthCalendar> control and the <xref:System.Windows.Forms.CheckedListBox> control.</span></span> 

- <span data-ttu-id="db1e7-106">Mise à l’échelle seul passage.</span><span class="sxs-lookup"><span data-stu-id="db1e7-106">Single-pass scaling.</span></span>  <span data-ttu-id="db1e7-107">Dans le .NET Framework 4.6 et les versions antérieures, la mise à l’échelle a été effectuée via plusieurs passes, ce qui a provoqué des contrôles à l’échelle plus de données nécessaires.</span><span class="sxs-lookup"><span data-stu-id="db1e7-107">In the .NET Framework 4.6 and earlier versions, scaling was performed through multiple passes, which caused some controls to be scaled more than was necessary.</span></span>

- <span data-ttu-id="db1e7-108">Prise en charge pour les scénarios de résolution dynamiques dans lequel l’utilisateur modifie le facteur de PPP ou mise à l’échelle après le lancement d’une application Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="db1e7-108">Support for dynamic DPI scenarios in which the user changes the DPI or scale factor after a Windows Forms application has been launched.</span></span>

<span data-ttu-id="db1e7-109">Dans les versions du .NET Framework en commençant par le .NET Framework 4.7, une prise en charge améliorée de la haute résolution est une fonctionnalité à activer.</span><span class="sxs-lookup"><span data-stu-id="db1e7-109">In versions of the .NET Framework starting with the .NET Framework 4.7, enhanced high DPI support is an opt-in feature.</span></span> <span data-ttu-id="db1e7-110">Vous devez configurer votre application pour tirer parti de celui-ci.</span><span class="sxs-lookup"><span data-stu-id="db1e7-110">You must configure your application to take advantage of it.</span></span>

## <a name="configuring-your-windows-forms-app-for-high-dpi-support"></a><span data-ttu-id="db1e7-111">Configuration de votre application Windows Forms pour la prise en charge de haute résolution</span><span class="sxs-lookup"><span data-stu-id="db1e7-111">Configuring your Windows Forms app for high DPI support</span></span>

<span data-ttu-id="db1e7-112">Les nouvelles fonctionnalités de Windows Forms qui prennent en charge de la prise en charge DPI élevé sont disponibles uniquement dans les applications qui ciblent le .NET Framework 4.7 et sont en cours d’exécution sur les systèmes d’exploitation Windows en commençant par Windows 10 Creators Update.</span><span class="sxs-lookup"><span data-stu-id="db1e7-112">The new Windows Forms features that support high DPI awareness are available only in applications that target the .NET Framework 4.7 and are running on Windows operating systems starting with the Windows 10 Creators Update.</span></span> 

<span data-ttu-id="db1e7-113">En outre, pour configurer la prise en charge de haute résolution dans votre application Windows Forms, vous devez procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="db1e7-113">In addition, to configure high DPI support in your Windows Forms application, you must do the following:</span></span>

- <span data-ttu-id="db1e7-114">Déclarer la compatibilité avec Windows 10.</span><span class="sxs-lookup"><span data-stu-id="db1e7-114">Declare compatibility with Windows 10.</span></span>

  <span data-ttu-id="db1e7-115">Pour ce faire, ajoutez le code suivant à votre fichier manifeste :</span><span class="sxs-lookup"><span data-stu-id="db1e7-115">To do this, add the following to your manifest file:</span></span>

  ```xml
  <compatibility xmlns="urn:schemas-microsoft.com:compatibility.v1">
    <application>
      <!-- Windows 10 compatibility -->
      <supportedOS Id="{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}" />
    </application>
  </compatibility>
  ```

- <span data-ttu-id="db1e7-116">Activer la sensibilisation à la résolution par moniteur dans le *app.config* fichier.</span><span class="sxs-lookup"><span data-stu-id="db1e7-116">Enable per-monitor DPI awareness in the *app.config* file.</span></span>

  <span data-ttu-id="db1e7-117">Windows Forms propose un nouveau [ `<System.Windows.Forms.ApplicationConfigurationSection>` ](../../../docs/framework/configure-apps/file-schema/winforms/index.md) élément pour prendre en charge les nouvelles fonctionnalités et les personnalisations ajoutées en commençant par le .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="db1e7-117">Windows Forms introduces a new [`<System.Windows.Forms.ApplicationConfigurationSection>`](../../../docs/framework/configure-apps/file-schema/winforms/index.md) element to support new features and customizations added starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="db1e7-118">Pour tirer parti des nouvelles fonctionnalités qui prennent en charge la haute résolution, ajoutez le code suivant au fichier de configuration de votre application.</span><span class="sxs-lookup"><span data-stu-id="db1e7-118">To take advantage of the new features that support high DPI, add the following to your application configuration file.</span></span>   

  ```xml
  <System.Windows.Forms.ApplicationConfigurationSection>
    <add key="DpiAwareness" value="PerMonitorV2" />
  </System.Windows.Forms.ApplicationConfigurationSection>      
  ```
   
  > [!IMPORTANT]
  > <span data-ttu-id="db1e7-119">Dans les versions précédentes du .NET Framework, vous avez utilisé le manifeste pour ajouter la prise en charge de haute résolution.</span><span class="sxs-lookup"><span data-stu-id="db1e7-119">In previous versions of the .NET Framework, you used the manifest to add high DPI support.</span></span> <span data-ttu-id="db1e7-120">Cette approche n’est plus recommandée, car il substitue les paramètres définis dans le fichier app.config.</span><span class="sxs-lookup"><span data-stu-id="db1e7-120">This approach is no longer recommended, since it overrides settings defined on the app.config file.</span></span>
   
- <span data-ttu-id="db1e7-121">Appelez la méthode statique <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> (méthode).</span><span class="sxs-lookup"><span data-stu-id="db1e7-121">Call the static <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>
   
  <span data-ttu-id="db1e7-122">Il doit s’agir du premier appel de méthode dans le point d’entrée de votre application.</span><span class="sxs-lookup"><span data-stu-id="db1e7-122">This should be the first method call in your application entry point.</span></span> <span data-ttu-id="db1e7-123">Exemple :</span><span class="sxs-lookup"><span data-stu-id="db1e7-123">For example:</span></span>
   
  ```csharp
  static void Main()
  {
      Application.EnableVisualStyles();
      Application.SetCompatibleTextRenderingDefault(false);
      Application.Run(new Form2());   
  }
  ```

## <a name="opting-out-of-individual-high-dpi-features"></a><span data-ttu-id="db1e7-124">Désactivation de la fonctionnalités de PPP élevées individuelles</span><span class="sxs-lookup"><span data-stu-id="db1e7-124">Opting out of individual high DPI features</span></span>

<span data-ttu-id="db1e7-125">Définition de la `DpiAwareness` valeur `PerMonitorV2` Active les fonctionnalités de la reconnaissance PPP élevées tout pris en charge par les versions du .NET Framework en commençant par le .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="db1e7-125">Setting the `DpiAwareness` value to `PerMonitorV2` enables all high DPI awareness features supported by .NET Framework versions starting with the .NET Framework 4.7.</span></span> <span data-ttu-id="db1e7-126">En règle générale, cela est suffisant pour la plupart des applications Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="db1e7-126">Typically, this is adequate for most Windows Forms applications.</span></span> <span data-ttu-id="db1e7-127">Toutefois, vous souhaiterez refuser un ou plusieurs des fonctionnalités individuelles.</span><span class="sxs-lookup"><span data-stu-id="db1e7-127">However, you may want to opt out of one or more individual features.</span></span> <span data-ttu-id="db1e7-128">La raison la plus importante pour cette opération est que votre code d’application existant gère déjà cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="db1e7-128">The most important reason for doing this is that your existing application code already handles that feature.</span></span>  <span data-ttu-id="db1e7-129">Par exemple, si votre application gère la mise à l’échelle automatique, vous souhaiterez désactiver la fonctionnalité de redimensionnement automatique comme suit :</span><span class="sxs-lookup"><span data-stu-id="db1e7-129">For example, if your application handles auto scaling, you might want to disable the auto-resizing feature as follows:</span></span>

```xml
<System.Windows.Forms.ApplicationConfigurationSection>
  <add key="DpiAwareness" value="PerMonitorV2" />
  <add key="EnableWindowsFormsHighDpiAutoResizing" value="false" /> 
</System.Windows.Forms.ApplicationConfigurationSection>    
```

<span data-ttu-id="db1e7-130">Pour obtenir la liste des clés individuelles et leurs valeurs, consultez [élément de Configuration Add Windows Forms](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span><span class="sxs-lookup"><span data-stu-id="db1e7-130">For a list of individual keys and their values, see [Windows Forms Add Configuration Element](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md).</span></span>

## <a name="new-dpi-change-events"></a><span data-ttu-id="db1e7-131">Nouveaux événements de modification de PPP</span><span class="sxs-lookup"><span data-stu-id="db1e7-131">New DPI change events</span></span>

<span data-ttu-id="db1e7-132">À compter de .NET Framework 4.7, trois nouveaux événements vous autorise à gérer par programme les modifications de résolution dynamiques :</span><span class="sxs-lookup"><span data-stu-id="db1e7-132">Starting with the .NET Framework 4.7, three new events allow you to programmatically handle dynamic DPI changes:</span></span>

- <span data-ttu-id="db1e7-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, qui est déclenché quand le paramètre DPI d’un contrôle est modifié par programme après un événement de modification de PPP pour le contrôle de son parent ou formulaire s’est produite.</span><span class="sxs-lookup"><span data-stu-id="db1e7-133"><xref:System.Windows.Forms.Control.DpiChangedAfterParent>, which is fired when the DPI setting for a control is changed programmatically after a DPI change event for it's parent control or form has occurred.</span></span>
- <span data-ttu-id="db1e7-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, qui est déclenché lorsque le paramètre DPI d’un contrôle est modifié par programme avant qu’un événement de modification de PPP pour son contrôle parent ou le formulaire s’est produite.</span><span class="sxs-lookup"><span data-stu-id="db1e7-134"><xref:System.Windows.Forms.Control.DpiChangedBeforeParent>, which is fired when the DPI setting for a control is changed programmatically before a DPI change event for its parent control or form has occurred.</span></span>
- <span data-ttu-id="db1e7-135"><xref:System.Windows.Forms.Form.DpiChanged>, qui est déclenché lorsque le paramètre DPI est modifié sur le périphérique d’affichage dans lequel le formulaire est actuellement affiché.</span><span class="sxs-lookup"><span data-stu-id="db1e7-135"><xref:System.Windows.Forms.Form.DpiChanged>, which is fired when the DPI setting changes on the display device where the form is currently displayed.</span></span>

## <a name="new-helper-methods-and-properties"></a><span data-ttu-id="db1e7-136">Propriétés et nouvelles méthodes d’assistance</span><span class="sxs-lookup"><span data-stu-id="db1e7-136">New helper methods and properties</span></span>

<span data-ttu-id="db1e7-137">Le .NET Framework 4.7 ajoute également un nombre de nouvelles méthodes d’assistance et des propriétés qui fournissent des informations sur la mise à l’échelle PPP et que vous puissiez effectuer la mise à l’échelle PPP.</span><span class="sxs-lookup"><span data-stu-id="db1e7-137">The .NET Framework 4.7 also adds a number of new helper methods and properties that provide information about DPI scaling and allow you to perform DPI scaling.</span></span> <span data-ttu-id="db1e7-138">Elles incluent notamment :</span><span class="sxs-lookup"><span data-stu-id="db1e7-138">These include:</span></span>

- <span data-ttu-id="db1e7-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, qui convertit une valeur exprimé en coordonnées logiques en pixels de périphérique.</span><span class="sxs-lookup"><span data-stu-id="db1e7-139"><xref:System.Windows.Forms.Control.LogicalToDeviceUnits%2A>, which converts a value from logical to device pixels.</span></span>

- <span data-ttu-id="db1e7-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, qui met à l’échelle d’une image bitmap à la valeur PPP logique pour un périphérique.</span><span class="sxs-lookup"><span data-stu-id="db1e7-140"><xref:System.Windows.Forms.Control.ScaleBitmapLogicalToDevice%2A>, which scales a bitmap image to the logical DPI for a device.</span></span>

- <span data-ttu-id="db1e7-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, qui retourne la valeur PPP pour l’appareil en cours.</span><span class="sxs-lookup"><span data-stu-id="db1e7-141"><xref:System.Windows.Forms.Control.DeviceDpi%2A>, which returns the DPI for the current device.</span></span>

## <a name="versioning-considerations"></a><span data-ttu-id="db1e7-142">Considérations relatives à la gestion des versions</span><span class="sxs-lookup"><span data-stu-id="db1e7-142">Versioning considerations</span></span>

<span data-ttu-id="db1e7-143">Outre l’exécution sur .NET Framework 4.7 et Windows 10 Creators Update, votre application peut également exécuter dans un environnement dans lequel il n’est pas compatible avec les améliorations de PPP élevées.</span><span class="sxs-lookup"><span data-stu-id="db1e7-143">In addition to running on .NET Framework 4.7 and Windows 10 Creators Update, your application may also run in an environment in which it isn't compatible with high DPI improvements.</span></span> <span data-ttu-id="db1e7-144">Dans ce cas, vous devez développer une procédure de secours pour votre application.</span><span class="sxs-lookup"><span data-stu-id="db1e7-144">In this case, you'll need to develop a fallback for your application.</span></span> <span data-ttu-id="db1e7-145">Vous pouvez le faire pour effectuer [dessin personnalisé](./controls/user-drawn-controls.md) pour gérer la mise à l’échelle.</span><span class="sxs-lookup"><span data-stu-id="db1e7-145">You can do this to perform [custom drawing](./controls/user-drawn-controls.md) to handle scaling.</span></span>

<span data-ttu-id="db1e7-146">Pour ce faire, vous devez également déterminer le système d’exploitation sur lequel votre application est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="db1e7-146">To do this, you also need to determine the operating system on which your app is running.</span></span> <span data-ttu-id="db1e7-147">Vous pouvez le faire avec un code semblable au suivant :</span><span class="sxs-lookup"><span data-stu-id="db1e7-147">You can do that with code like the following:</span></span>

```csharp
// Create a reference to the OS version of Windows 10 Creators Update.
Version OsMinVersion = new Version(10, 0, 15063, 0);

// Access the platform/version of the current OS.
Console.WriteLine(Environment.OSVersion.Platform.ToString());
Console.WriteLine(Environment.OSVersion.VersionString);

// Compare the current version to the minimum required version.
Console.WriteLine(Environment.OSVersion.Version.CompareTo(OsMinVersion));
```

<span data-ttu-id="db1e7-148">Notez que votre application ne détecte avec succès Windows 10 si elle n’a pas été répertoriée comme un système d’exploitation pris en charge dans le manifeste d’application.</span><span class="sxs-lookup"><span data-stu-id="db1e7-148">Note that your application won't successfully detect Windows 10 if it wasn't listed as a supported operating system in the application manifest.</span></span>

<span data-ttu-id="db1e7-149">Vous pouvez également vérifier la version du .NET Framework que l’application a été développée pour :</span><span class="sxs-lookup"><span data-stu-id="db1e7-149">You can also check the version of the .NET Framework that the application was built against:</span></span>

```csharp
Console.WriteLine(AppDomain.CurrentDomain.SetupInformation.TargetFrameworkName);
```

## <a name="see-also"></a><span data-ttu-id="db1e7-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db1e7-150">See also</span></span>

- [<span data-ttu-id="db1e7-151">Windows Forms Add, élément de Configuration</span><span class="sxs-lookup"><span data-stu-id="db1e7-151">Windows Forms Add Configuration Element</span></span>](../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md)
- [<span data-ttu-id="db1e7-152">Réglage de la taille et de l'échelle des Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db1e7-152">Adjusting the Size and Scale of Windows Forms</span></span>](../../../docs/framework/winforms/adjusting-the-size-and-scale-of-windows-forms.md)
