---
title: '&lt;providerOption&gt; élément'
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: fa3410cc2c8812c59528676bfad6cd7e887c5f73
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ltprovideroptiongt-element"></a><span data-ttu-id="9416e-102">&lt;providerOption&gt; élément</span><span class="sxs-lookup"><span data-stu-id="9416e-102">&lt;providerOption&gt; Element</span></span>
<span data-ttu-id="9416e-103">Spécifie les attributs de version du compilateur pour un fournisseur de langage.</span><span class="sxs-lookup"><span data-stu-id="9416e-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="9416e-104">\<Élément de configuration ></span><span class="sxs-lookup"><span data-stu-id="9416e-104">\<configuration Element></span></span>  
<span data-ttu-id="9416e-105">\<System.CodeDom (élément) ></span><span class="sxs-lookup"><span data-stu-id="9416e-105">\<system.codedom Element></span></span>  
<span data-ttu-id="9416e-106">\<compilateurs élément ></span><span class="sxs-lookup"><span data-stu-id="9416e-106">\<compilers Element></span></span>  
<span data-ttu-id="9416e-107">\<compilateur > élément</span><span class="sxs-lookup"><span data-stu-id="9416e-107">\<compiler> Element</span></span>  
<span data-ttu-id="9416e-108">\<providerOption > élément</span><span class="sxs-lookup"><span data-stu-id="9416e-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9416e-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="9416e-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9416e-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="9416e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9416e-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="9416e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9416e-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="9416e-112">Attributes</span></span>  
  
|<span data-ttu-id="9416e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="9416e-113">Attribute</span></span>|<span data-ttu-id="9416e-114">Description</span><span class="sxs-lookup"><span data-stu-id="9416e-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="9416e-115">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="9416e-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="9416e-116">Spécifie le nom de l’option ; par exemple, « CompilerVersion ».</span><span class="sxs-lookup"><span data-stu-id="9416e-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="9416e-117">Attribut requis.</span><span class="sxs-lookup"><span data-stu-id="9416e-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="9416e-118">Spécifie la valeur de l’option ; par exemple, « v3.5 ».</span><span class="sxs-lookup"><span data-stu-id="9416e-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9416e-119">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="9416e-119">Child Elements</span></span>  
 <span data-ttu-id="9416e-120">Aucun.</span><span class="sxs-lookup"><span data-stu-id="9416e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9416e-121">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="9416e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9416e-122">Élément</span><span class="sxs-lookup"><span data-stu-id="9416e-122">Element</span></span>|<span data-ttu-id="9416e-123">Description</span><span class="sxs-lookup"><span data-stu-id="9416e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9416e-124">\<configuration>, élément</span><span class="sxs-lookup"><span data-stu-id="9416e-124">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="9416e-125">Élément racine dans chaque fichier de configuration utilisé par le Common Language Runtime et les applications .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9416e-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="9416e-126">\<System.CodeDom > élément</span><span class="sxs-lookup"><span data-stu-id="9416e-126">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="9416e-127">Spécifie les paramètres de configuration du compilateur pour les fournisseurs de langages disponibles.</span><span class="sxs-lookup"><span data-stu-id="9416e-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="9416e-128">\<compilateurs > élément</span><span class="sxs-lookup"><span data-stu-id="9416e-128">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="9416e-129">Conteneur pour les éléments de configuration du compilateur ; contient zéro ou plusieurs `<compiler>` éléments.</span><span class="sxs-lookup"><span data-stu-id="9416e-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="9416e-130">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="9416e-130">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="9416e-131">Spécifie les attributs de configuration du compilateur pour un fournisseur de langage.</span><span class="sxs-lookup"><span data-stu-id="9416e-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9416e-132">Notes</span><span class="sxs-lookup"><span data-stu-id="9416e-132">Remarks</span></span>  
 <span data-ttu-id="9416e-133">Dans le .NET Framework version 3.5, les fournisseurs de code Code Document Object Model (CodeDOM) peuvent prendre en charge les options spécifiques au fournisseur à l’aide de la `<providerOption>` élément.</span><span class="sxs-lookup"><span data-stu-id="9416e-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="9416e-134">Le .NET Framework 3.5 inclut des assemblys mis à jour de .NET Framework 2.0 et fournit des assemblys 3.5 qui contiennent de nouveaux types.</span><span class="sxs-lookup"><span data-stu-id="9416e-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="9416e-135">Les fournisseurs de code Microsoft c# et Visual Basic sont contenus dans des assemblys .NET Framework 2.0, mais ont été mis à jour pour prendre en charge les compilateurs de la version 3.5.</span><span class="sxs-lookup"><span data-stu-id="9416e-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="9416e-136">Par défaut, les fournisseurs de code mis à jour génèrent du code pour les compilateurs de la version 2.0.</span><span class="sxs-lookup"><span data-stu-id="9416e-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="9416e-137">Vous pouvez utiliser la `<providerOption>` élément pour modifier la version de compilateur cible en 3.5.</span><span class="sxs-lookup"><span data-stu-id="9416e-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="9416e-138">Pour ce faire, spécifiez « CompilerVersion » pour le `name` attribut et « v3.5 » pour le `value` attribut.</span><span class="sxs-lookup"><span data-stu-id="9416e-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="9416e-139">Vous devez faire précéder le numéro de version avec un « v » en minuscules.</span><span class="sxs-lookup"><span data-stu-id="9416e-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="9416e-140">Vous pouvez rendre la spécification de version global en ajoutant la `<providerOption>` élément vers le fichier Machine.config de .NET Framework 2.0 ou le fichier Web.config racine.</span><span class="sxs-lookup"><span data-stu-id="9416e-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="9416e-141">Si vous mettez à jour la version du compilateur par défaut à 3.5 dans le fichier Machine.config, vous pouvez le modifier à 2.0 sur chaque application à l’aide de la `<providerOption>` élément dans le fichier de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="9416e-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="9416e-142">Les implémenteurs de fournisseur de code codeDOM peuvent traiter des options personnalisées en fournissant un constructeur qui accepte un `providerOptions` paramètre de type <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="9416e-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9416e-143">Exemple</span><span class="sxs-lookup"><span data-stu-id="9416e-143">Example</span></span>  
 <span data-ttu-id="9416e-144">L’exemple suivant montre comment spécifier la version 3.5 du fournisseur de code c# doit être utilisée.</span><span class="sxs-lookup"><span data-stu-id="9416e-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9416e-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9416e-145">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="9416e-146">Schéma des fichiers de configuration</span><span class="sxs-lookup"><span data-stu-id="9416e-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="9416e-147">\<compilateurs > élément</span><span class="sxs-lookup"><span data-stu-id="9416e-147">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [<span data-ttu-id="9416e-148">Spécification des noms de types complets</span><span class="sxs-lookup"><span data-stu-id="9416e-148">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [<span data-ttu-id="9416e-149">compilateur, élément pour les compilateurs pour compilation (schéma des paramètres ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="9416e-149">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
