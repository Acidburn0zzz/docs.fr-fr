---
title: marshaler des données avec COM Interop
ms.date: 09/07/2017
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0d94223223568efe921af3a340815a966cc6c6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33388353"
---
# <a name="marshaling-data-with-com-interop"></a><span data-ttu-id="58090-102">marshaler des données avec COM Interop</span><span class="sxs-lookup"><span data-stu-id="58090-102">Marshaling Data with COM Interop</span></span>
<span data-ttu-id="58090-103">COM Interop prend en charge l'utilisation des objets COM à partir de code managé, ainsi que l'exposition des objets managés à COM.</span><span class="sxs-lookup"><span data-stu-id="58090-103">COM interop provides support for both using COM objects from managed code and exposing managed objects to COM.</span></span> <span data-ttu-id="58090-104">La prise en charge du marshaling des données vers et depuis COM est complète et fournit quasiment toujours le comportement de marshaling approprié.</span><span class="sxs-lookup"><span data-stu-id="58090-104">Support for marshaling data to and from COM is extensive and almost always provides the correct marshaling behavior.</span></span>  
  
 <span data-ttu-id="58090-105">Le [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] comprend les outils COM Interop suivants :</span><span class="sxs-lookup"><span data-stu-id="58090-105">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] includes the following COM interop tools:</span></span>  
  
-   <span data-ttu-id="58090-106">[Importateur de bibliothèques de types (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), qui convertit une bibliothèque de types COM en un assembly d’interopérabilité.</span><span class="sxs-lookup"><span data-stu-id="58090-106">[Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), which converts a COM type library to an interop assembly.</span></span> <span data-ttu-id="58090-107">À partir de cet assembly, le service de marshaling d’interopérabilité génère des wrappers qui effectuent le marshaling des données entre la mémoire managée et non managée.</span><span class="sxs-lookup"><span data-stu-id="58090-107">From this assembly, the interop marshaling service generates wrappers that perform data marshaling between managed and unmanaged memory.</span></span>  
  
-   <span data-ttu-id="58090-108">[Exportateur de bibliothèques de types (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), qui produit une bibliothèque de types COM à partir d’un assembly et génère un wrapper qui effectue le marshaling lors des appels de méthode.</span><span class="sxs-lookup"><span data-stu-id="58090-108">[Type Library Exporter (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which produces a COM type library from an assembly and generates a wrapper that performs marshaling during method calls.</span></span>  
  
 <span data-ttu-id="58090-109">Les sections suivantes fournissent des liens vers des rubriques qui décrivent les processus de personnalisation des wrappers d’interopérabilité quand vous pouvez (ou devez) fournir au marshaleur des informations supplémentaires concernant les types.</span><span class="sxs-lookup"><span data-stu-id="58090-109">The following sections link to topics that describe the processes for customizing interop wrappers when you can (or must) supply the marshaler with additional type information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58090-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="58090-110">In This Section</span></span>  
<span data-ttu-id="58090-111">[Guide pratique pour créer manuellement des wrappers](how-to-create-wrappers-manually.md) </span><span class="sxs-lookup"><span data-stu-id="58090-111">[How to: Create Wrappers Manually](how-to-create-wrappers-manually.md) </span></span>  
<span data-ttu-id="58090-112">Décrit comment créer manuellement un wrapper COM dans du code source managé.</span><span class="sxs-lookup"><span data-stu-id="58090-112">Describes how to create a COM wrapper manually in managed source code.</span></span> 
 
 [<span data-ttu-id="58090-113">Guide pratique pour migrer le modèle DCOM de code managé vers WCF</span><span class="sxs-lookup"><span data-stu-id="58090-113">How to: Migrate Managed-Code DCOM to WCF</span></span>](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 <span data-ttu-id="58090-114">Décrit comment migrer du code DCOM managé vers WCF pour obtenir la solution la plus sécurisée.</span><span class="sxs-lookup"><span data-stu-id="58090-114">Describes how to migrate managed DCOM code to WCF for the most secure solution.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="58090-115">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="58090-115">Related Sections</span></span>  
 <span data-ttu-id="58090-116">[Types de données COM](https://msdn.microsoft.com/library/sak564ww(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="58090-116">[COM Data Types](https://msdn.microsoft.com/library/sak564ww(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="58090-117">Fournit les types de données managés et non managés correspondants.</span><span class="sxs-lookup"><span data-stu-id="58090-117">Provides corresponding managed and unmanaged data types.</span></span>  
  
 <span data-ttu-id="58090-118">[Personnalisation des wrappers CCW (COM Callable Wrapper)](https://msdn.microsoft.com/library/3bwc828w(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="58090-118">[Customizing COM Callable Wrappers](https://msdn.microsoft.com/library/3bwc828w(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="58090-119">Décrit comment marshaler explicitement des types de données à l’aide de l’attribut <xref:System.Runtime.InteropServices.MarshalAsAttribute> au moment du design.</span><span class="sxs-lookup"><span data-stu-id="58090-119">Describes how to explicitly marshal data types using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute at design time.</span></span>  
  
 <span data-ttu-id="58090-120">[Personnalisation des wrappers RCW (Runtime Callable Wrapper)](https://msdn.microsoft.com/library/e753eftz(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="58090-120">[Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/library/e753eftz(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="58090-121">Décrit comment ajuster le comportement de marshaling des types dans un assembly d’interopérabilité et comment définir des types COM manuellement.</span><span class="sxs-lookup"><span data-stu-id="58090-121">Describes how to adjust the marshaling behavior of types in an interop assembly and how to define COM types manually.</span></span>  
  
 <span data-ttu-id="58090-122">[Interopérabilité COM avancée](https://msdn.microsoft.com/library/bd9cdfyx(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="58090-122">[Advanced COM Interoperability](https://msdn.microsoft.com/library/bd9cdfyx(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="58090-123">Fournit des liens vers des informations sur l'incorporation de composants COM dans une application .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="58090-123">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>  
  
 <span data-ttu-id="58090-124">[Récapitulatif de la conversion d’un assembly en bibliothèque de types](https://msdn.microsoft.com/library/xk1120c3(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="58090-124">[Assembly to Type Library Conversion Summary](https://msdn.microsoft.com/library/xk1120c3(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="58090-125">Décrit le processus d'exportation et de conversion d'un assembly en une bibliothèque de types.</span><span class="sxs-lookup"><span data-stu-id="58090-125">Describes the assembly to type library export conversion process.</span></span>  
  
 <span data-ttu-id="58090-126">[Récapitulatif de la conversion d’une bibliothèque de types en assembly](https://msdn.microsoft.com/library/k83zzh38(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="58090-126">[Type Library to Assembly Conversion Summary](https://msdn.microsoft.com/library/k83zzh38(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="58090-127">Décrit le processus d'importation et de conversion d'une bibliothèque de types en un assembly.</span><span class="sxs-lookup"><span data-stu-id="58090-127">Describes the type library to assembly import conversion process.</span></span>  
  
 <span data-ttu-id="58090-128">[Interopérabilité à l’aide de types génériques](https://msdn.microsoft.com/library/ms229590(v=vs.100).aspx)</span><span class="sxs-lookup"><span data-stu-id="58090-128">[Interoperating Using Generic Types](https://msdn.microsoft.com/library/ms229590(v=vs.100).aspx)</span></span>  
 <span data-ttu-id="58090-129">Décrit les actions prises en charge lors de l'utilisation de types génériques pour l'interopérabilité COM.</span><span class="sxs-lookup"><span data-stu-id="58090-129">Describes which actions are supported when using generic types for COM interoperability.</span></span>
