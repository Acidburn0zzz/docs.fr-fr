---
title: Téléchargement du package de validation du registre des noms d'émetteurs
ms.date: 03/30/2017
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
ms.openlocfilehash: 03b68f4b9dc6fde02c951968067e0311e4981d33
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398747"
---
# <a name="downloading-the-validating-issuer-name-registry-package"></a><span data-ttu-id="0e377-102">Téléchargement du package de validation du registre des noms d'émetteurs</span><span class="sxs-lookup"><span data-stu-id="0e377-102">Downloading the Validating Issuer Name Registry Package</span></span>
<span data-ttu-id="0e377-103">Cette rubrique explique comment télécharger et utiliser le Registre des noms d’émetteurs de validation (VINR, Validating Issuer Name Registry) dans votre projet.</span><span class="sxs-lookup"><span data-stu-id="0e377-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>  
  
## <a name="downloading-the-validating-issuer-name-registry"></a><span data-ttu-id="0e377-104">Téléchargement du Registre des noms d’émetteurs de validation</span><span class="sxs-lookup"><span data-stu-id="0e377-104">Downloading the Validating Issuer Name Registry</span></span>  
 <span data-ttu-id="0e377-105">Le Registre VINR est disponible sous forme de package NuGet, qui ajoute les assemblys et les références nécessaires à votre projet.</span><span class="sxs-lookup"><span data-stu-id="0e377-105">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="0e377-106">Si vous n’avez pas encore installé NuGet, accédez à [nuget.org](http://nuget.org) pour l’installer.</span><span class="sxs-lookup"><span data-stu-id="0e377-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="0e377-107">Vous pouvez voir l’historique de gestion de version de l’extension en accédant à sa page sur NuGet : [Registre des noms d’émetteurs de validation Microsoft sur NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span><span class="sxs-lookup"><span data-stu-id="0e377-107">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-gui"></a><span data-ttu-id="0e377-108">Téléchargement du Registre des noms d’émetteurs de validation à l’aide de l’interface graphique utilisateur du Gestionnaire de package</span><span class="sxs-lookup"><span data-stu-id="0e377-108">Downloading the Validating Issuer Name Registry by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="0e377-109">Dans Visual Studio, cliquez sur votre projet dans l’**Explorateur de solutions**, puis sélectionnez **Gérer les packages NuGet**.</span><span class="sxs-lookup"><span data-stu-id="0e377-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="0e377-110">Dans la fenêtre **Gérer les packages NuGet**, cliquez sur la zone de recherche et tapez `ValidatingIssuerNameRegistry`, puis appuyez sur **Entrée**.</span><span class="sxs-lookup"><span data-stu-id="0e377-110">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="0e377-111">Dans le volet de résultats, cliquez sur le bouton **Installer** pour le premier résultat.</span><span class="sxs-lookup"><span data-stu-id="0e377-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="0e377-112">Le téléchargement du package commence.</span><span class="sxs-lookup"><span data-stu-id="0e377-112">The package will begin downloading.</span></span> <span data-ttu-id="0e377-113">Avant l’ajout du package à votre projet, la boîte de dialogue d’acceptation de licence s’affiche.</span><span class="sxs-lookup"><span data-stu-id="0e377-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="0e377-114">Si vous êtes d’accord avec les termes du contrat de licence, cliquez sur **Accepter**.</span><span class="sxs-lookup"><span data-stu-id="0e377-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="0e377-115">Les assemblys VINR les plus récents seront téléchargés et ajoutés à votre projet.</span><span class="sxs-lookup"><span data-stu-id="0e377-115">The latest VINR assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-console"></a><span data-ttu-id="0e377-116">Téléchargement du Registre des noms d’émetteurs de validation à l’aide de la console du Gestionnaire de package</span><span class="sxs-lookup"><span data-stu-id="0e377-116">Downloading the Validating Issuer Name Registry by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="0e377-117">Dans Visual Studio, cliquez sur **Outils**, **Gestionnaire de package de bibliothèque**, puis **Console du Gestionnaire de package**.</span><span class="sxs-lookup"><span data-stu-id="0e377-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="0e377-118">La **Console du Gestionnaire de package** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="0e377-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="0e377-119">Tapez le texte suivant et appuyez sur **Entrée** :</span><span class="sxs-lookup"><span data-stu-id="0e377-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  <span data-ttu-id="0e377-120">Les assemblys VINR les plus récents seront téléchargés et ajoutés à votre projet.</span><span class="sxs-lookup"><span data-stu-id="0e377-120">The latest VINR assemblies will be downloaded and added to your project.</span></span>
