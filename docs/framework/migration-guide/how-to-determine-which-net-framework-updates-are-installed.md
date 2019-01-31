---
title: 'Procédure : déterminer les correctifs logiciels et mises à jour de sécurité .NET Framework installés'
description: Découvrez comment déterminer les correctifs logiciels et mises à jour de sécurité .NET Framework installés sur un ordinateur.
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e11b2588471e95b4e47fd0efaf41757430b9bb39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604182"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="8be0e-103">Procédure : déterminer les correctifs logiciels et mises à jour de sécurité .NET Framework installés</span><span class="sxs-lookup"><span data-stu-id="8be0e-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="8be0e-104">Cet article montre comment rechercher les correctifs logiciels et mises à jour de sécurité .NET Framework installés sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8be0e-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="8be0e-105">Toutes les techniques présentées dans cet article nécessitent un compte avec des privilèges administratifs.</span><span class="sxs-lookup"><span data-stu-id="8be0e-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="8be0e-106">Pour rechercher les mises à jour installées à l’aide du Registre</span><span class="sxs-lookup"><span data-stu-id="8be0e-106">To find installed updates using the registry</span></span>

<span data-ttu-id="8be0e-107">Les correctifs logiciels et mises à jour de sécurité installés pour chaque version du .NET Framework installée sur un ordinateur sont répertoriés dans le Registre Windows.</span><span class="sxs-lookup"><span data-stu-id="8be0e-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="8be0e-108">Vous pouvez utiliser le programme Éditeur du Registre (*regedit.exe*) pour afficher ces informations.</span><span class="sxs-lookup"><span data-stu-id="8be0e-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="8be0e-109">Ouvrez le programme **regedit.exe**.</span><span class="sxs-lookup"><span data-stu-id="8be0e-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="8be0e-110">Dans Windows 8 et ultérieur, cliquez avec le bouton droit sur **Démarrer** ![Logo Windows](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), puis sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="8be0e-110">In Windows 8 and later versions, right-click **Start** ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="8be0e-111">Dans la zone **Ouvrir**, entrez **regedit** et sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="8be0e-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="8be0e-112">Dans l'Éditeur du Registre, ouvrez la sous-clé suivante :</span><span class="sxs-lookup"><span data-stu-id="8be0e-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="8be0e-113">Les mises à jour installées sont répertoriées sous les sous-clés qui identifient la version du .NET Framework auquel elles s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="8be0e-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="8be0e-114">Chaque mise à jour est identifiée par un numéro de Base de connaissances (KB).</span><span class="sxs-lookup"><span data-stu-id="8be0e-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="8be0e-115">Dans l'Éditeur du Registre, les versions du .NET Framework et les mises à jour installées pour chaque version sont stockées dans des sous-clés distinctes.</span><span class="sxs-lookup"><span data-stu-id="8be0e-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="8be0e-116">Pour plus d’informations sur la détection des numéros des versions installées, consultez [Guide pratique pour déterminer les versions du .NET Framework installées](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="8be0e-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="8be0e-117">Pour rechercher les mises à jour installées en interrogeant le Registre dans le code</span><span class="sxs-lookup"><span data-stu-id="8be0e-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="8be0e-118">L’exemple suivant détermine par programmation les correctifs logiciels et mises à jour de sécurité .NET Framework installés sur un ordinateur :</span><span class="sxs-lookup"><span data-stu-id="8be0e-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="8be0e-119">Cet exemple produit une sortie semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="8be0e-119">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="8be0e-120">Pour rechercher les mises à jour installées en interrogeant le Registre dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="8be0e-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="8be0e-121">L’exemple suivant montre comment déterminer les correctifs logiciels et mises à jour de sécurité .NET Framework installés sur un ordinateur à l’aide de PowerShell :</span><span class="sxs-lookup"><span data-stu-id="8be0e-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
$DotNetVersions = Get-ChildItem HKLM:\SOFTWARE\WOW6432Node\Microsoft\Updates | Where-Object {$_.name -like
 "*.NET Framework*"}

ForEach($Version in $DotNetVersions){
    
   $Updates = Get-ChildItem $Version.PSPath
    $Version.PSChildName
    ForEach ($Update in $Updates){
       $Update.PSChildName
       }
}
```

<span data-ttu-id="8be0e-122">Cet exemple produit une sortie semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="8be0e-122">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
KB2468871
KB2468871v2
KB2478063
KB2533523
KB2544514
KB2600211
KB2600217
Microsoft .NET Framework 4 Extended
KB2468871
KB2468871v2
KB2478063
KB2533523
KB2544514
KB2600211
KB2600217
```

## <a name="see-also"></a><span data-ttu-id="8be0e-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8be0e-123">See also</span></span>

- [<span data-ttu-id="8be0e-124">Guide pratique pour déterminer les versions du .NET Framework installées</span><span class="sxs-lookup"><span data-stu-id="8be0e-124">How to: Determine which .NET Framework versions are installed</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)
- [<span data-ttu-id="8be0e-125">Installer le .NET Framework pour les développeurs</span><span class="sxs-lookup"><span data-stu-id="8be0e-125">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)
- [<span data-ttu-id="8be0e-126">Versions et dépendances</span><span class="sxs-lookup"><span data-stu-id="8be0e-126">Versions and dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
