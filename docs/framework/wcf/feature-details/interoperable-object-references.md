---
title: Références d'objets interopérables
ms.date: 03/30/2017
ms.assetid: cb8da4c8-08ca-4220-a16b-e04c8f527f1b
ms.openlocfilehash: 5d2f7d93544cafab7cfe5d8dcbb8a4c5d5c5b576
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582420"
---
# <a name="interoperable-object-references"></a><span data-ttu-id="58677-102">Références d'objets interopérables</span><span class="sxs-lookup"><span data-stu-id="58677-102">Interoperable Object References</span></span>
<span data-ttu-id="58677-103">Par défaut, le <xref:System.Runtime.Serialization.DataContractSerializer> sérialise les objets par valeur.</span><span class="sxs-lookup"><span data-stu-id="58677-103">By default the <xref:System.Runtime.Serialization.DataContractSerializer> serializes objects by value.</span></span> <span data-ttu-id="58677-104">Vous pouvez utiliser la propriété <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> pour indiquer au sérialiseur de contrat de données qu'il conserve les références d'objet lors de la sérialisation des objets du type.</span><span class="sxs-lookup"><span data-stu-id="58677-104">You can use the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> property to instruct the Data Contract Serializer to preserve object references when serializing objects of the type.</span></span>  
  
## <a name="generated-xml"></a><span data-ttu-id="58677-105">XML généré</span><span class="sxs-lookup"><span data-stu-id="58677-105">Generated XML</span></span>  
 <span data-ttu-id="58677-106">À titre d'exemple, considérez l'objet suivant :</span><span class="sxs-lookup"><span data-stu-id="58677-106">As an example, consider the following object:</span></span>  
  
```  
[DataContract]  
public class X  
{  
    SomeClass someInstance = new SomeClass();  
    [DataMember]  
    public SomeClass A = someInstance;  
    [DataMember]  
    public SomeClass B = someInstance;  
}  
  
public class SomeClass   
{  
}  
```  
  
 <span data-ttu-id="58677-107">Lorsque <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> a la valeur `false` (valeur par défaut), le code XML suivant est généré :</span><span class="sxs-lookup"><span data-stu-id="58677-107">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `false` (the default), the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A>contents of someInstance</A>  
   <B>contents of someInstance</B>  
</X>  
```  
  
 <span data-ttu-id="58677-108">Lorsque <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> a la valeur `true`, le code XML suivant est généré :</span><span class="sxs-lookup"><span data-stu-id="58677-108">With <xref:System.Runtime.Serialization.DataContractSerializer.PreserveObjectReferences%2A> set to `true`, the following XML is generated:</span></span>  
  
```xml  
<X>  
   <A id="1">contents of someInstance</A>  
   <B ref="1" />  
</X>  
```  
  
 <span data-ttu-id="58677-109">Toutefois, <xref:System.Runtime.Serialization.XsdDataContractExporter> ne décrit pas les attributs `id` et `ref` dans son schéma, y compris quand la propriété `preserveObjectReferences` a la valeur `true`.</span><span class="sxs-lookup"><span data-stu-id="58677-109">However, <xref:System.Runtime.Serialization.XsdDataContractExporter> does not describe the `id` and `ref` attributes in its schema, even when the `preserveObjectReferences` property is set to `true`.</span></span>  
  
## <a name="using-isreference"></a><span data-ttu-id="58677-110">Utilisation d'IsReference</span><span class="sxs-lookup"><span data-stu-id="58677-110">Using IsReference</span></span>  
 <span data-ttu-id="58677-111">Pour générer des informations de référence d'objet valides d'après le schéma qui les décrit, appliquez l'attribut <xref:System.Runtime.Serialization.DataContractAttribute> à un type et attribuez à l'indicateur <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> la valeur `true`.</span><span class="sxs-lookup"><span data-stu-id="58677-111">To generate object reference information that is valid according to the schema that describes it, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to a type, and set the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> flag to `true`.</span></span> <span data-ttu-id="58677-112">En utilisant `IsReference` dans la classe illustrée dans l'exemple `X` précédent :</span><span class="sxs-lookup"><span data-stu-id="58677-112">Using `IsReference` in the previous example class `X`:</span></span>  
  
 `[DataContract(IsReference=true)] public class X`  
  
 `{`  
  
 `SomeClass someInstance = new SomeClass();`  
  
 `[DataMember]`  
  
 `public SomeClass A = someInstance;`  
  
 `[DataMember]`  
  
 `public SomeClass B = someInstance;`  
  
 `}`  
  
 `public class SomeClass`  
  
 `{`  
  
 `}`  
  
 <span data-ttu-id="58677-113">Le XML généré est le suivant :</span><span class="sxs-lookup"><span data-stu-id="58677-113">The generated XML is as follows:</span></span>  
  
 `<X>`  
  
 `<A id="1">`  
  
 `<Value>contents of A</Value>`  
  
 `</A>`  
  
 `<B ref="1">`  
  
 `</B>`  
  
 `</X>`  
  
 <span data-ttu-id="58677-114">L'utilisation d'`IsReference` garantit la conformité dans l'aller-retour du message.</span><span class="sxs-lookup"><span data-stu-id="58677-114">Using `IsReference` ensures compliance on message round-tripping.</span></span> <span data-ttu-id="58677-115">Sans lui, lorsqu'un type est généré à partir du schéma, les données renvoyées comme XML pour ce type ne sont pas forcément compatibles avec le schéma supposé initialement.</span><span class="sxs-lookup"><span data-stu-id="58677-115">Without it, when a type is generated from schema, what is sent back as XML for that type is not necessarily compatible with the schema originally assumed.</span></span> <span data-ttu-id="58677-116">En d'autres termes, bien que les attributs `id` et `ref` aient été sérialisés, le schéma d'origine aurait pu empêcher ces attributs (ou tous les attributs) d'apparaître dans le XML.</span><span class="sxs-lookup"><span data-stu-id="58677-116">In other words, although the `id` and `ref` attributes were serialized, the original schema could have barred these attributes (or all attributes) from occurring in the XML.</span></span> <span data-ttu-id="58677-117">Lorsqu'`IsReference` est appliqué à un membre de données, ce dernier continue à être reconnu comme étant « référençable » lorsqu'il fait l'aller-retour.</span><span class="sxs-lookup"><span data-stu-id="58677-117">With `IsReference` applied to a data member, the member continues to be recognized as "referenceable" when roundtripped.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58677-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58677-118">See also</span></span>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>
- <xref:System.Runtime.Serialization.CollectionDataContractAttribute.IsReference%2A>
