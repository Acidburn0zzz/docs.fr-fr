---
title: <add> de <declaredTypes> élément
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: e6aab0b1eca340e212c34e2d25b9b84984dcc7a0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255508"
---
# <a name="add-of-declaredtypes-element"></a><span data-ttu-id="6d075-102">\<Ajouter > de \<declaredTypes > élément</span><span class="sxs-lookup"><span data-stu-id="6d075-102">\<add> of \<declaredTypes> Element</span></span>
<span data-ttu-id="6d075-103">Ajoute un type utilisé par le <xref:System.Runtime.Serialization.DataContractSerializer> pendant la désérialisation.</span><span class="sxs-lookup"><span data-stu-id="6d075-103">Adds a type used by the <xref:System.Runtime.Serialization.DataContractSerializer> during deserialization.</span></span> <span data-ttu-id="6d075-104">Chaque type déclaré inclut les types connus qui seront renvoyés comme champ ou propriété du type déclaré.</span><span class="sxs-lookup"><span data-stu-id="6d075-104">Each declared type includes the known types that will be returned as a field or property of the declared type.</span></span>  
  
 <span data-ttu-id="6d075-105">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="6d075-105">system.runtime.serialization</span></span>  
<span data-ttu-id="6d075-106">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="6d075-106">\<dataContractSerializer></span></span>  
<span data-ttu-id="6d075-107">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="6d075-107">\<declaredTypes></span></span>  
<span data-ttu-id="6d075-108">\<add> of \<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="6d075-108">\<add> of \<declaredTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d075-109">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6d075-109">Syntax</span></span>  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d075-110">Attributs et éléments</span><span class="sxs-lookup"><span data-stu-id="6d075-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6d075-111">Les sections suivantes décrivent des attributs, des éléments enfants et des éléments parents.</span><span class="sxs-lookup"><span data-stu-id="6d075-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d075-112">Attributs</span><span class="sxs-lookup"><span data-stu-id="6d075-112">Attributes</span></span>  
  
|<span data-ttu-id="6d075-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="6d075-113">Attribute</span></span>|<span data-ttu-id="6d075-114">Description</span><span class="sxs-lookup"><span data-stu-id="6d075-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6d075-115">type</span><span class="sxs-lookup"><span data-stu-id="6d075-115">type</span></span>|<span data-ttu-id="6d075-116">Attribut de chaîne requis.</span><span class="sxs-lookup"><span data-stu-id="6d075-116">Required string attribute.</span></span><br /><br /> <span data-ttu-id="6d075-117">Indique le nom du type (espace de noms compris), celui de l'assembly, le numéro de version, la culture et le jeton de clé publique.</span><span class="sxs-lookup"><span data-stu-id="6d075-117">Specifies the type name (including namespace), assembly name, version number, culture, and public key token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d075-118">Éléments enfants</span><span class="sxs-lookup"><span data-stu-id="6d075-118">Child Elements</span></span>  
  
|<span data-ttu-id="6d075-119">Élément</span><span class="sxs-lookup"><span data-stu-id="6d075-119">Element</span></span>|<span data-ttu-id="6d075-120">Description</span><span class="sxs-lookup"><span data-stu-id="6d075-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d075-121">\<knownType></span><span class="sxs-lookup"><span data-stu-id="6d075-121">\<knownType></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|<span data-ttu-id="6d075-122">Spécifie le type connu correspondant au type déclaré en cours d'ajout.</span><span class="sxs-lookup"><span data-stu-id="6d075-122">Specifies the known type for the declared type that is being added.</span></span> <span data-ttu-id="6d075-123">Si le type déclaré est un type générique, vous devez également ajouter un élément de paramètre à l'élément `<knownType>` pour spécifier le paramètre générique utilisé pour renvoyer le type connu.</span><span class="sxs-lookup"><span data-stu-id="6d075-123">If the declared type is a generic type, then you must also add a parameter element to the `<knownType>` element to specify which generic parameter is used to return the known type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6d075-124">Éléments parents</span><span class="sxs-lookup"><span data-stu-id="6d075-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6d075-125">Élément</span><span class="sxs-lookup"><span data-stu-id="6d075-125">Element</span></span>|<span data-ttu-id="6d075-126">Description</span><span class="sxs-lookup"><span data-stu-id="6d075-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d075-127">\<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="6d075-127">\<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|<span data-ttu-id="6d075-128">Contient les types qui requièrent des types connus pendant la désérialisation effectuée par le <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6d075-128">Contains the types that require known types during deserialization by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d075-129">Notes</span><span class="sxs-lookup"><span data-stu-id="6d075-129">Remarks</span></span>  
 <span data-ttu-id="6d075-130">Pour plus d’informations sur les types connus, consultez [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) et <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6d075-130">For more information about known types, see [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) and <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="6d075-131">Consultez le [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) pour obtenir un exemple d’utilisation de cet élément.</span><span class="sxs-lookup"><span data-stu-id="6d075-131">See the [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) for an example of using this element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d075-132">Si vous ajoutez le type <xref:System.Object> comme `<declaredType>`, une <xref:System.Configuration.ConfigurationErrorsException> est levée.</span><span class="sxs-lookup"><span data-stu-id="6d075-132">If you add the <xref:System.Object> type as a `<declaredType>`, a <xref:System.Configuration.ConfigurationErrorsException> is thrown.</span></span> <span data-ttu-id="6d075-133">Ceci est dû au fait que le type <xref:System.Object> ne peut pas être utilisé comme type déclaré dans la configuration.</span><span class="sxs-lookup"><span data-stu-id="6d075-133">This is because the <xref:System.Object> type cannot be used as a declared type in configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d075-134">Exemple</span><span class="sxs-lookup"><span data-stu-id="6d075-134">Example</span></span>  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL" />
</add>
```  
  
## <a name="see-also"></a><span data-ttu-id="6d075-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d075-135">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractSerializer>
- [<span data-ttu-id="6d075-136">Types connus de contrats de données</span><span class="sxs-lookup"><span data-stu-id="6d075-136">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="6d075-137">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="6d075-137">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [<span data-ttu-id="6d075-138">\<add> of \<declaredTypes></span><span class="sxs-lookup"><span data-stu-id="6d075-138">\<add> of \<declaredTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
