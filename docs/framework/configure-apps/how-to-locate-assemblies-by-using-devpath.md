---
title: "Comment : localiser des assemblys à l'aide de DEVPATH"
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 918acf069c63d3aa8187f0f04e1f6c55ec961458
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a><span data-ttu-id="98fb3-102">Comment : localiser des assemblys à l'aide de DEVPATH</span><span class="sxs-lookup"><span data-stu-id="98fb3-102">How to: Locate Assemblies by Using DEVPATH</span></span>
<span data-ttu-id="98fb3-103">Les développeurs souhaitent peut-être vous assurer qu’un assembly partagé qu’ils développent fonctionne correctement avec plusieurs applications.</span><span class="sxs-lookup"><span data-stu-id="98fb3-103">Developers might want to make sure that a shared assembly they are building works correctly with multiple applications.</span></span> <span data-ttu-id="98fb3-104">Au lieu de mettre en permanence l’assembly dans le global assembly cache au cours du cycle de développement, le développeur peut créer une variable d’environnement DEVPATH pointant vers le répertoire de sortie de l’assembly.</span><span class="sxs-lookup"><span data-stu-id="98fb3-104">Instead of continually putting the assembly in the global assembly cache during the development cycle, the developer can create a DEVPATH environment variable that points to the build output directory for the assembly.</span></span>  
  
 <span data-ttu-id="98fb3-105">Par exemple, supposez que vous générez un assembly partagé appelé MySharedAssembly et le répertoire de sortie soit C:\MySharedAssembly\Debug.</span><span class="sxs-lookup"><span data-stu-id="98fb3-105">For example, assume that you are building a shared assembly called MySharedAssembly and the output directory is C:\MySharedAssembly\Debug.</span></span> <span data-ttu-id="98fb3-106">Vous pouvez placer C:\MySharedAssembly\Debug dans la variable DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="98fb3-106">You can put C:\MySharedAssembly\Debug in the DEVPATH variable.</span></span> <span data-ttu-id="98fb3-107">Vous devez spécifier le [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) élément dans le fichier de configuration machine.</span><span class="sxs-lookup"><span data-stu-id="98fb3-107">You must then specify the [\<developmentMode>](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) element in the machine configuration file.</span></span> <span data-ttu-id="98fb3-108">Cet élément indique le common language runtime d’utiliser DEVPATH pour localiser les assemblys.</span><span class="sxs-lookup"><span data-stu-id="98fb3-108">This element tells the common language runtime to use DEVPATH to locate assemblies.</span></span>  
  
 <span data-ttu-id="98fb3-109">L’assembly partagé doit être détectable par le runtime.</span><span class="sxs-lookup"><span data-stu-id="98fb3-109">The shared assembly must be discoverable by the runtime.</span></span>  <span data-ttu-id="98fb3-110">Pour spécifier un répertoire privé pour la résolution des références d’assembly, utilisez le [ \<codeBase > élément](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) ou [ \<probing > élément](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) dans un fichier de configuration, comme décrit dans [Spécifiant l’emplacement d’un Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="98fb3-110">To specify a private directory for resolving assembly references use the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) or [\<probing> Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in a configuration file, as described in [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  <span data-ttu-id="98fb3-111">Vous pouvez également placer l’assembly dans un sous-répertoire du répertoire de l’application.</span><span class="sxs-lookup"><span data-stu-id="98fb3-111">You can also put the assembly in a subdirectory of the application directory.</span></span> <span data-ttu-id="98fb3-112">Pour plus d’informations, consultez [Méthode de localisation des assemblys par le runtime](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="98fb3-112">For more information, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98fb3-113">Il s’agit d’une fonctionnalité avancée, conçue uniquement pour le développement.</span><span class="sxs-lookup"><span data-stu-id="98fb3-113">This is an advanced feature, intended only for development.</span></span>  
  
 <span data-ttu-id="98fb3-114">L’exemple suivant montre comment le runtime recherche les assemblys dans les répertoires spécifiés par la variable d’environnement DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="98fb3-114">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98fb3-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="98fb3-115">Example</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="98fb3-116">Ce paramètre par défaut est false.</span><span class="sxs-lookup"><span data-stu-id="98fb3-116">This setting defaults to false.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98fb3-117">Utilisez ce paramètre uniquement au moment du développement.</span><span class="sxs-lookup"><span data-stu-id="98fb3-117">Use this setting only at development time.</span></span> <span data-ttu-id="98fb3-118">Le runtime ne vérifie pas les versions sur les assemblys avec nom fort trouvés dans DEVPATH.</span><span class="sxs-lookup"><span data-stu-id="98fb3-118">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="98fb3-119">Elle utilise simplement le premier assembly qu’il trouve.</span><span class="sxs-lookup"><span data-stu-id="98fb3-119">It simply uses the first assembly it finds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98fb3-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98fb3-120">See Also</span></span>  
 [<span data-ttu-id="98fb3-121">Configuration des applications .NET Framework</span><span class="sxs-lookup"><span data-stu-id="98fb3-121">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
