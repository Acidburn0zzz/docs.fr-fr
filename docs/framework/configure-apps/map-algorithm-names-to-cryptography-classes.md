---
title: Mappage de noms d'algorithmes à des classes de chiffrement
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2dc03c3aa6808ed4ce0c22f4e69fa8c98cb7aebd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="22265-102">Mappage de noms d'algorithmes à des classes de chiffrement</span><span class="sxs-lookup"><span data-stu-id="22265-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="22265-103">Il existe quatre méthodes, un développeur peut créer un objet de chiffrement à l’aide de la [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="22265-103">There are four ways a developer can create a cryptography object using the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]:</span></span>  
  
-   <span data-ttu-id="22265-104">Créer un objet à l’aide de la **nouveau** opérateur.</span><span class="sxs-lookup"><span data-stu-id="22265-104">Create an object by using the **new** operator.</span></span>  
  
-   <span data-ttu-id="22265-105">Créer un objet qui implémente un algorithme de chiffrement particulier en appelant le **créer** méthode sur la classe abstraite pour cet algorithme.</span><span class="sxs-lookup"><span data-stu-id="22265-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
-   <span data-ttu-id="22265-106">Créer un objet qui implémente un algorithme de chiffrement particulier en appelant le <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> (méthode).</span><span class="sxs-lookup"><span data-stu-id="22265-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="22265-107">Créer un objet qui implémente une classe d’algorithmes de chiffrement (par exemple, un chiffrement symétrique) en appelant le **créer** méthode sur la classe abstraite pour ce type d’algorithme (tel que <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span><span class="sxs-lookup"><span data-stu-id="22265-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="22265-108">Par exemple, qu'un développeur souhaite calculer le hachage SHA1 d’un jeu d’octets.</span><span class="sxs-lookup"><span data-stu-id="22265-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="22265-109">Le <xref:System.Security.Cryptography> espace de noms contient deux implémentations de l’algorithme SHA1, une implémentation managée de purement et une autre qui encapsule CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="22265-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="22265-110">Le développeur peut choisir d’instancier une implémentation particulière de SHA1 (telles que la <xref:System.Security.Cryptography.SHA1Managed>) en appelant le **nouveau** opérateur.</span><span class="sxs-lookup"><span data-stu-id="22265-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="22265-111">Toutefois, si elle n’a pas d’importance le common language runtime charge tant que la classe implémente l’algorithme de hachage SHA1, le développeur peut créer un objet en appelant le <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> (méthode).</span><span class="sxs-lookup"><span data-stu-id="22265-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="22265-112">Cette méthode appelle **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, qui doit retourner une implémentation de l’algorithme de hachage SHA1.</span><span class="sxs-lookup"><span data-stu-id="22265-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="22265-113">Le développeur peut également appeler **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** car, par défaut, la configuration de chiffrement comprend des noms courts pour les algorithmes fournis dans le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22265-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="22265-114">Si l’algorithme de hachage est utilisé n’a pas d’importance, le développeur peut appeler le <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> (méthode), qui retourne un objet qui implémente une transformation de hachage.</span><span class="sxs-lookup"><span data-stu-id="22265-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="22265-115">Mappage des noms d’algorithmes dans les fichiers de Configuration</span><span class="sxs-lookup"><span data-stu-id="22265-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="22265-116">Par défaut, le runtime retourne un <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> objet pour les quatre scénarios.</span><span class="sxs-lookup"><span data-stu-id="22265-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="22265-117">Toutefois, un administrateur d’ordinateur permettre modifier le type d’objet renvoyées par les méthodes dans les deux derniers scénarios.</span><span class="sxs-lookup"><span data-stu-id="22265-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="22265-118">Pour ce faire, vous devez mapper un nom d’algorithme convivial à la classe que vous souhaitez utiliser dans le fichier de configuration de l’ordinateur (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="22265-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="22265-119">L’exemple suivant montre comment configurer le runtime de sorte que **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, et  **System.Security.Cryptography.HashAlgorithm.Create** renvoyer un `MySHA1HashClass` objet.</span><span class="sxs-lookup"><span data-stu-id="22265-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="22265-120">Vous pouvez spécifier le nom de l’attribut dans le [< cryptoClass\> élément](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (l’exemple précédent nomme l’attribut `MySHA1Hash`).</span><span class="sxs-lookup"><span data-stu-id="22265-120">You can specify the name of the attribute in the [<cryptoClass\> element](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="22265-121">La valeur de l’attribut dans le  **\<cryptoClass >** élément est une chaîne que le common language runtime utilise pour rechercher la classe.</span><span class="sxs-lookup"><span data-stu-id="22265-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="22265-122">Vous pouvez utiliser n’importe quelle chaîne qui répond aux exigences spécifiées dans [en spécifiant des noms de types qualifiés complets](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="22265-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="22265-123">Plusieurs noms d’algorithmes peuvent mapper à la même classe.</span><span class="sxs-lookup"><span data-stu-id="22265-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="22265-124">Le [ \<nameEntry > élément](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) mappe une classe à un nom d’algorithme convivial.</span><span class="sxs-lookup"><span data-stu-id="22265-124">The [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="22265-125">Le **nom** attribut peut être soit une chaîne qui est utilisée lors de l’appel du **System.Security.Cryptography.CryptoConfig.CreateFromName** méthode ou le nom d’une classe de chiffrement abstraite dans le <xref:System.Security.Cryptography> espace de noms.</span><span class="sxs-lookup"><span data-stu-id="22265-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="22265-126">La valeur de la **classe** attribut est le nom de l’attribut dans le  **\<cryptoClass >** élément.</span><span class="sxs-lookup"><span data-stu-id="22265-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22265-127">Vous pouvez obtenir un algorithme SHA1 en appelant le <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> ou **Security.CryptoConfig.CreateFromName("SHA1")** (méthode).</span><span class="sxs-lookup"><span data-stu-id="22265-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="22265-128">Chaque méthode garantit uniquement qu’il retourne un objet qui implémente l’algorithme SHA1.</span><span class="sxs-lookup"><span data-stu-id="22265-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="22265-129">Vous n’avez pas à mapper chaque nom convivial d’un algorithme à la même classe dans le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="22265-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="22265-130">Pour obtenir la liste de noms par défaut et les classes de mappage, consultez <xref:System.Security.Cryptography.CryptoConfig>.</span><span class="sxs-lookup"><span data-stu-id="22265-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22265-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="22265-131">See Also</span></span>  
 [<span data-ttu-id="22265-132">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="22265-132">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 [<span data-ttu-id="22265-133">Configuration des classes de chiffrement</span><span class="sxs-lookup"><span data-stu-id="22265-133">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)
