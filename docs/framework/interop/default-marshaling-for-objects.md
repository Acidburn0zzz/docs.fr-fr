---
title: Marshaling par défaut pour les objets
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- objects, interop marshaling
- interop marshaling, objects
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94377fb2079689e7b6af2c94fa24ca2214a5c729
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2018
ms.locfileid: "34312181"
---
# <a name="default-marshaling-for-objects"></a><span data-ttu-id="6736c-102">Marshaling par défaut pour les objets</span><span class="sxs-lookup"><span data-stu-id="6736c-102">Default Marshaling for Objects</span></span>
<span data-ttu-id="6736c-103">Les paramètres et les champs de type <xref:System.Object?displayProperty=nameWithType> peuvent être exposés à un code non managé sous la forme de l’un des types suivants :</span><span class="sxs-lookup"><span data-stu-id="6736c-103">Parameters and fields typed as <xref:System.Object?displayProperty=nameWithType> can be exposed to unmanaged code as one of the following types:</span></span>  
  
-   <span data-ttu-id="6736c-104">Un variant quand l’objet est un paramètre.</span><span class="sxs-lookup"><span data-stu-id="6736c-104">A variant when the object is a parameter.</span></span>  
  
-   <span data-ttu-id="6736c-105">Une interface quand l’objet est un champ de structure.</span><span class="sxs-lookup"><span data-stu-id="6736c-105">An interface when the object is a structure field.</span></span>  
  
 <span data-ttu-id="6736c-106">Seul COM interop prend en charge le marshaling des types d’objets.</span><span class="sxs-lookup"><span data-stu-id="6736c-106">Only COM interop supports marshaling for object types.</span></span> <span data-ttu-id="6736c-107">Le comportement par défaut est de marshaler des objets vers des variants COM.</span><span class="sxs-lookup"><span data-stu-id="6736c-107">The default behavior is to marshal objects to COM variants.</span></span> <span data-ttu-id="6736c-108">Ces règles s’appliquent uniquement au type **Object** et ne s’appliquent pas aux objets fortement typés issus de la classe **Object**.</span><span class="sxs-lookup"><span data-stu-id="6736c-108">These rules apply only to the type **Object** and do not apply to strongly typed objects that derive from the **Object** class.</span></span>  
  
 <span data-ttu-id="6736c-109">Cette rubrique fournit les informations supplémentaires suivantes sur le marshaling des types d’objets :</span><span class="sxs-lookup"><span data-stu-id="6736c-109">This topic provides the following additional information about marshaling object types:</span></span>  
  
-   [<span data-ttu-id="6736c-110">Options de marshaling</span><span class="sxs-lookup"><span data-stu-id="6736c-110">Marshaling Options</span></span>](#cpcondefaultmarshalingforobjectsanchor7)  
  
-   [<span data-ttu-id="6736c-111">Marshaling d’un objet vers une interface</span><span class="sxs-lookup"><span data-stu-id="6736c-111">Marshaling Object to Interface</span></span>](#cpcondefaultmarshalingforobjectsanchor2)  
  
-   [<span data-ttu-id="6736c-112">Marshaling d’un objet vers un variant</span><span class="sxs-lookup"><span data-stu-id="6736c-112">Marshaling Object to Variant</span></span>](#cpcondefaultmarshalingforobjectsanchor3)  
  
-   [<span data-ttu-id="6736c-113">Marshaling d’un variant vers un objet</span><span class="sxs-lookup"><span data-stu-id="6736c-113">Marshaling Variant to Object</span></span>](#cpcondefaultmarshalingforobjectsanchor4)  
  
-   [<span data-ttu-id="6736c-114">Marshaling des variants ByRef</span><span class="sxs-lookup"><span data-stu-id="6736c-114">Marshaling ByRef Variants</span></span>](#cpcondefaultmarshalingforobjectsanchor6)  
  
<a name="cpcondefaultmarshalingforobjectsanchor7"></a>   
## <a name="marshaling-options"></a><span data-ttu-id="6736c-115">Options de marshaling</span><span class="sxs-lookup"><span data-stu-id="6736c-115">Marshaling Options</span></span>  
 <span data-ttu-id="6736c-116">Le tableau suivant montre les options de marshaling pour le type de données **Object**.</span><span class="sxs-lookup"><span data-stu-id="6736c-116">The following table shows the marshaling options for the **Object** data type.</span></span> <span data-ttu-id="6736c-117">L’attribut <xref:System.Runtime.InteropServices.MarshalAsAttribute> fournit plusieurs valeurs d’énumération <xref:System.Runtime.InteropServices.UnmanagedType> pour marshaler des objets.</span><span class="sxs-lookup"><span data-stu-id="6736c-117">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal objects.</span></span>  
  
|<span data-ttu-id="6736c-118">Type d'énumération</span><span class="sxs-lookup"><span data-stu-id="6736c-118">Enumeration type</span></span>|<span data-ttu-id="6736c-119">Description du format non managé</span><span class="sxs-lookup"><span data-stu-id="6736c-119">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="6736c-120">**UnmanagedType.Struct**</span><span class="sxs-lookup"><span data-stu-id="6736c-120">**UnmanagedType.Struct**</span></span><br /><br /> <span data-ttu-id="6736c-121">(valeur par défaut des paramètres)</span><span class="sxs-lookup"><span data-stu-id="6736c-121">(default for parameters)</span></span>|<span data-ttu-id="6736c-122">Variant de style COM.</span><span class="sxs-lookup"><span data-stu-id="6736c-122">A COM-style variant.</span></span>|  
|<span data-ttu-id="6736c-123">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="6736c-123">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="6736c-124">Interface **IDispatch**, si possible ; sinon, interface **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="6736c-124">An **IDispatch** interface, if possible; otherwise, an **IUnknown** interface.</span></span>|  
|<span data-ttu-id="6736c-125">**UnmanagedType.IUnknown**</span><span class="sxs-lookup"><span data-stu-id="6736c-125">**UnmanagedType.IUnknown**</span></span><br /><br /> <span data-ttu-id="6736c-126">(valeur par défaut des champs)</span><span class="sxs-lookup"><span data-stu-id="6736c-126">(default for fields)</span></span>|<span data-ttu-id="6736c-127">Interface **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="6736c-127">An **IUnknown** interface.</span></span>|  
|<span data-ttu-id="6736c-128">**UnmanagedType.IDispatch**</span><span class="sxs-lookup"><span data-stu-id="6736c-128">**UnmanagedType.IDispatch**</span></span>|<span data-ttu-id="6736c-129">Interface **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="6736c-129">An **IDispatch** interface.</span></span>|  
  
 <span data-ttu-id="6736c-130">L’exemple suivant montre la définition d’interface managée de `MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="6736c-130">The following example shows the managed interface definition for `MarshalObject`.</span></span>  
  
```vb  
Interface MarshalObject  
   Sub SetVariant(o As Object)  
   Sub SetVariantRef(ByRef o As Object)  
   Function GetVariant() As Object  
  
   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)  
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _  
      As Object)  
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object  
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)  
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _  
      As Object)  
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object  
End Interface  
```  
  
```csharp  
interface MarshalObject {  
   void SetVariant(Object o);  
   void SetVariantRef(ref Object o);  
   Object GetVariant();  
  
   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);  
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);  
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();  
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);  
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);  
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();  
}  
```  
  
 <span data-ttu-id="6736c-131">Le code suivant exporte l’interface `MarshalObject` vers une bibliothèque de types.</span><span class="sxs-lookup"><span data-stu-id="6736c-131">The following code exports the `MarshalObject` interface to a type library.</span></span>  
  
```  
interface MarshalObject {  
   HRESULT SetVariant([in] VARIANT o);  
   HRESULT SetVariantRef([in,out] VARIANT *o);  
   HRESULT GetVariant([out,retval] VARIANT *o)   
   HRESULT SetIDispatch([in] IDispatch *o);  
   HRESULT SetIDispatchRef([in,out] IDispatch **o);  
   HRESULT GetIDispatch([out,retval] IDispatch **o)   
   HRESULT SetIUnknown([in] IUnknown *o);  
   HRESULT SetIUnknownRef([in,out] IUnknown **o);  
   HRESULT GetIUnknown([out,retval] IUnknown **o)   
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="6736c-132">Le marshaleur d’interopérabilité libère automatiquement tout objet alloué à l’intérieur du variant après l’appel.</span><span class="sxs-lookup"><span data-stu-id="6736c-132">The interop marshaler automatically frees any allocated object inside the variant after the call.</span></span>  
  
 <span data-ttu-id="6736c-133">L’exemple suivant illustre un type valeur mis en forme.</span><span class="sxs-lookup"><span data-stu-id="6736c-133">The following example shows a formatted value type.</span></span>  
  
```vb  
Public Structure ObjectHolder  
   Dim o1 As Object  
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object  
End Structure  
```  
  
```csharp  
public struct ObjectHolder {  
   Object o1;  
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;  
}  
```  
  
 <span data-ttu-id="6736c-134">Le code suivant exporte le type mis en forme vers une bibliothèque de types.</span><span class="sxs-lookup"><span data-stu-id="6736c-134">The following code exports the formatted type to a type library.</span></span>  
  
```  
struct ObjectHolder {  
   VARIANT o1;  
   IDispatch *o2;  
}  
```  
  
<a name="cpcondefaultmarshalingforobjectsanchor2"></a>   
## <a name="marshaling-object-to-interface"></a><span data-ttu-id="6736c-135">Marshaling d’un objet vers une interface</span><span class="sxs-lookup"><span data-stu-id="6736c-135">Marshaling Object to Interface</span></span>  
 <span data-ttu-id="6736c-136">Quand un objet est exposé à COM en tant qu’interface, cette interface est l’interface de classe pour le type managé <xref:System.Object> (l’interface **_Object**).</span><span class="sxs-lookup"><span data-stu-id="6736c-136">When an object is exposed to COM as an interface, that interface is the class interface for the managed type <xref:System.Object> (the **_Object** interface).</span></span> <span data-ttu-id="6736c-137">Cette interface est de type **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) ou **IUnknown** (**UnmanagedType.IUnknown**) dans la bibliothèque de types résultante.</span><span class="sxs-lookup"><span data-stu-id="6736c-137">This interface is typed as an **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) or an **IUnknown** (**UnmanagedType.IUnknown**) in the resulting type library.</span></span> <span data-ttu-id="6736c-138">Les clients COM peuvent appeler dynamiquement les membres de la classe managée ou tout membre implémenté par ses classes dérivées via l’interface **_Object**.</span><span class="sxs-lookup"><span data-stu-id="6736c-138">COM clients can dynamically invoke the members of the managed class or any members implemented by its derived classes through the **_Object** interface.</span></span> <span data-ttu-id="6736c-139">Le client peut également appeler **QueryInterface** pour obtenir toute autre interface explicitement implémentée par le type managé.</span><span class="sxs-lookup"><span data-stu-id="6736c-139">The client can also call **QueryInterface** to obtain any other interface explicitly implemented by the managed type.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor3"></a>   
## <a name="marshaling-object-to-variant"></a><span data-ttu-id="6736c-140">Marshaling d’un objet vers un variant</span><span class="sxs-lookup"><span data-stu-id="6736c-140">Marshaling Object to Variant</span></span>  
 <span data-ttu-id="6736c-141">Quand un objet est marshalé en variant, le type variant interne est déterminé au moment de l’exécution en fonction des règles suivantes :</span><span class="sxs-lookup"><span data-stu-id="6736c-141">When an object is marshaled to a variant, the internal variant type is determined at run time, based on the following rules:</span></span>  
  
-   <span data-ttu-id="6736c-142">Si la référence d’objet est null (**Nothing** en Visual Basic), l’objet est marshalé en variant de type **VT_EMPTY**.</span><span class="sxs-lookup"><span data-stu-id="6736c-142">If the object reference is null (**Nothing** in Visual Basic), the object is marshaled to a variant of type **VT_EMPTY**.</span></span>  
  
-   <span data-ttu-id="6736c-143">Si l’objet est une instance d’un type énuméré dans le tableau suivant, le type variant résultant est déterminé par les règles du marshaleur et illustré dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="6736c-143">If the object is an instance of any type listed in the following table, the resulting variant type is determined by the rules built into the marshaler and shown in the table.</span></span>  
  
-   <span data-ttu-id="6736c-144">Les autres objets qui nécessitent de contrôler explicitement le comportement de marshaling peuvent implémenter l’interface <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="6736c-144">Other objects that need to explicitly control the marshaling behavior can implement the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="6736c-145">Dans ce cas, le type variant est déterminé par le code de type retourné à partir de la méthode <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6736c-145">In that case, the variant type is determined by the type code returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6736c-146">Sinon, l’objet est marshalé en tant que variant de type **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="6736c-146">Otherwise, the object is marshaled as a variant of type **VT_UNKNOWN**.</span></span>  
  
### <a name="marshaling-system-types-to-variant"></a><span data-ttu-id="6736c-147">Marshaling de types système vers des variants</span><span class="sxs-lookup"><span data-stu-id="6736c-147">Marshaling System Types to Variant</span></span>  
 <span data-ttu-id="6736c-148">Le tableau suivant montre les types d’objets managés et leurs types variant COM correspondants.</span><span class="sxs-lookup"><span data-stu-id="6736c-148">The following table shows managed object types and their corresponding COM variant types.</span></span> <span data-ttu-id="6736c-149">Ces types sont convertis uniquement quand la signature de la méthode appelée est de type <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6736c-149">These types are converted only when the signature of the method being called is of type <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
|<span data-ttu-id="6736c-150">Type d'objet</span><span class="sxs-lookup"><span data-stu-id="6736c-150">Object type</span></span>|<span data-ttu-id="6736c-151">Type variant COM</span><span class="sxs-lookup"><span data-stu-id="6736c-151">COM variant type</span></span>|  
|-----------------|----------------------|  
|<span data-ttu-id="6736c-152">Référence d’objet null (**Nothing** en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6736c-152">Null object reference (**Nothing** in Visual Basic).</span></span>|<span data-ttu-id="6736c-153">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="6736c-153">**VT_EMPTY**</span></span>|  
|<xref:System.DBNull?displayProperty=nameWithType>|<span data-ttu-id="6736c-154">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="6736c-154">**VT_NULL**</span></span>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|<span data-ttu-id="6736c-155">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="6736c-155">**VT_ERROR**</span></span>|  
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|<span data-ttu-id="6736c-156">**VT_ERROR** avec **E_PARAMNOTFOUND**</span><span class="sxs-lookup"><span data-stu-id="6736c-156">**VT_ERROR** with **E_PARAMNOTFOUND**</span></span>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|<span data-ttu-id="6736c-157">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="6736c-157">**VT_DISPATCH**</span></span>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|<span data-ttu-id="6736c-158">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="6736c-158">**VT_UNKNOWN**</span></span>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|<span data-ttu-id="6736c-159">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="6736c-159">**VT_CY**</span></span>|  
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="6736c-160">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="6736c-160">**VT_BOOL**</span></span>|  
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="6736c-161">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="6736c-161">**VT_I1**</span></span>|  
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="6736c-162">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="6736c-162">**VT_UI1**</span></span>|  
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="6736c-163">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="6736c-163">**VT_I2**</span></span>|  
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="6736c-164">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="6736c-164">**VT_UI2**</span></span>|  
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="6736c-165">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="6736c-165">**VT_I4**</span></span>|  
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="6736c-166">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="6736c-166">**VT_UI4**</span></span>|  
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="6736c-167">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="6736c-167">**VT_I8**</span></span>|  
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="6736c-168">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="6736c-168">**VT_UI8**</span></span>|  
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="6736c-169">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="6736c-169">**VT_R4**</span></span>|  
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="6736c-170">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="6736c-170">**VT_R8**</span></span>|  
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="6736c-171">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="6736c-171">**VT_DECIMAL**</span></span>|  
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="6736c-172">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="6736c-172">**VT_DATE**</span></span>|  
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="6736c-173">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="6736c-173">**VT_BSTR**</span></span>|  
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="6736c-174">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="6736c-174">**VT_INT**</span></span>|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="6736c-175">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="6736c-175">**VT_UINT**</span></span>|  
|<xref:System.Array?displayProperty=nameWithType>|<span data-ttu-id="6736c-176">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="6736c-176">**VT_ARRAY**</span></span>|  
  
 <span data-ttu-id="6736c-177">En utilisant l’interface `MarshalObject` définie dans l’exemple précédent, l’exemple de code suivant démontre comment passer plusieurs types de variants à un serveur COM.</span><span class="sxs-lookup"><span data-stu-id="6736c-177">Using the `MarshalObject` interface defined in the previous example, the following code example demonstrates how to pass various types of variants to a COM server.</span></span>  
  
```vb  
Dim mo As New MarshalObject()  
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.  
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.  
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.  
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.  
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.  
```  
  
```csharp  
MarshalObject mo = new MarshalObject();  
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.  
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.  
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.  
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.  
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.  
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.  
```  
  
 <span data-ttu-id="6736c-178">Les types COM qui n’ont pas de types managés correspondants peuvent être marshalés à l’aide des classes wrapper comme <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper> et <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span><span class="sxs-lookup"><span data-stu-id="6736c-178">COM types that do not have corresponding managed types can be marshaled using wrapper classes such as <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, and <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span></span> <span data-ttu-id="6736c-179">L’exemple de code suivant démontre comment utiliser ces wrappers pour passer différents types de variants à un serveur COM.</span><span class="sxs-lookup"><span data-stu-id="6736c-179">The following code example demonstrates how to use these wrappers to pass various types of variants to a COM server.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
' Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(New UnknownWrapper(inew))  
' Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(New DispatchWrapper(inew))  
' Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(New ErrorWrapper(&H80054002))  
' Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))  
```  
  
```csharp  
using System.Runtime.InteropServices;  
// Pass inew as a variant of type VT_UNKNOWN interface.  
mo.SetVariant(new UnknownWrapper(inew));  
// Pass inew as a variant of type VT_DISPATCH interface.  
mo.SetVariant(new DispatchWrapper(inew));  
// Pass a value as a variant of type VT_ERROR interface.  
mo.SetVariant(new ErrorWrapper(0x80054002));  
// Pass a value as a variant of type VT_CURRENCY interface.  
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));  
```  
  
 <span data-ttu-id="6736c-180">Les classes wrapper sont définies dans l’espace de noms <xref:System.Runtime.InteropServices>.</span><span class="sxs-lookup"><span data-stu-id="6736c-180">The wrapper classes are defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>  
  
### <a name="marshaling-the-iconvertible-interface-to-variant"></a><span data-ttu-id="6736c-181">Marshaling de l’interface IConvertible vers un variant</span><span class="sxs-lookup"><span data-stu-id="6736c-181">Marshaling the IConvertible Interface to Variant</span></span>  
 <span data-ttu-id="6736c-182">D’autres types que ceux répertoriés dans la section précédente peuvent contrôler la manière dont ils sont marshalés en implémentant l’interface <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="6736c-182">Types other than those listed in the previous section can control how they are marshaled by implementing the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="6736c-183">Si l’objet implémente l’interface **IConvertible**, le type variant COM est déterminé au moment de l’exécution par la valeur de l’énumération <xref:System.TypeCode> retournée à partir de la méthode <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6736c-183">If the object implements the **IConvertible** interface, the COM variant type is determined at run time by the value of the <xref:System.TypeCode> enumeration returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="6736c-184">Le tableau suivant montre les valeurs possibles pour l’énumération **TypeCode** et le type variant COM correspondant pour chaque valeur.</span><span class="sxs-lookup"><span data-stu-id="6736c-184">The following table shows the possible values for the **TypeCode** enumeration and the corresponding COM variant type for each value.</span></span>  
  
|<span data-ttu-id="6736c-185">TypeCode</span><span class="sxs-lookup"><span data-stu-id="6736c-185">TypeCode</span></span>|<span data-ttu-id="6736c-186">Type variant COM</span><span class="sxs-lookup"><span data-stu-id="6736c-186">COM variant type</span></span>|  
|--------------|----------------------|  
|<span data-ttu-id="6736c-187">**TypeCode.Empty**</span><span class="sxs-lookup"><span data-stu-id="6736c-187">**TypeCode.Empty**</span></span>|<span data-ttu-id="6736c-188">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="6736c-188">**VT_EMPTY**</span></span>|  
|<span data-ttu-id="6736c-189">**TypeCode.Object**</span><span class="sxs-lookup"><span data-stu-id="6736c-189">**TypeCode.Object**</span></span>|<span data-ttu-id="6736c-190">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="6736c-190">**VT_UNKNOWN**</span></span>|  
|<span data-ttu-id="6736c-191">**TypeCode.DBNull**</span><span class="sxs-lookup"><span data-stu-id="6736c-191">**TypeCode.DBNull**</span></span>|<span data-ttu-id="6736c-192">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="6736c-192">**VT_NULL**</span></span>|  
|<span data-ttu-id="6736c-193">**TypeCode.Boolean**</span><span class="sxs-lookup"><span data-stu-id="6736c-193">**TypeCode.Boolean**</span></span>|<span data-ttu-id="6736c-194">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="6736c-194">**VT_BOOL**</span></span>|  
|<span data-ttu-id="6736c-195">**TypeCode.Char**</span><span class="sxs-lookup"><span data-stu-id="6736c-195">**TypeCode.Char**</span></span>|<span data-ttu-id="6736c-196">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="6736c-196">**VT_UI2**</span></span>|  
|<span data-ttu-id="6736c-197">**TypeCode.Sbyte**</span><span class="sxs-lookup"><span data-stu-id="6736c-197">**TypeCode.Sbyte**</span></span>|<span data-ttu-id="6736c-198">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="6736c-198">**VT_I1**</span></span>|  
|<span data-ttu-id="6736c-199">**TypeCode.Byte**</span><span class="sxs-lookup"><span data-stu-id="6736c-199">**TypeCode.Byte**</span></span>|<span data-ttu-id="6736c-200">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="6736c-200">**VT_UI1**</span></span>|  
|<span data-ttu-id="6736c-201">**TypeCode.Int16**</span><span class="sxs-lookup"><span data-stu-id="6736c-201">**TypeCode.Int16**</span></span>|<span data-ttu-id="6736c-202">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="6736c-202">**VT_I2**</span></span>|  
|<span data-ttu-id="6736c-203">**TypeCode.UInt16**</span><span class="sxs-lookup"><span data-stu-id="6736c-203">**TypeCode.UInt16**</span></span>|<span data-ttu-id="6736c-204">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="6736c-204">**VT_UI2**</span></span>|  
|<span data-ttu-id="6736c-205">**TypeCode.Int32**</span><span class="sxs-lookup"><span data-stu-id="6736c-205">**TypeCode.Int32**</span></span>|<span data-ttu-id="6736c-206">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="6736c-206">**VT_I4**</span></span>|  
|<span data-ttu-id="6736c-207">**TypeCode.UInt32**</span><span class="sxs-lookup"><span data-stu-id="6736c-207">**TypeCode.UInt32**</span></span>|<span data-ttu-id="6736c-208">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="6736c-208">**VT_UI4**</span></span>|  
|<span data-ttu-id="6736c-209">**TypeCode.Int64**</span><span class="sxs-lookup"><span data-stu-id="6736c-209">**TypeCode.Int64**</span></span>|<span data-ttu-id="6736c-210">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="6736c-210">**VT_I8**</span></span>|  
|<span data-ttu-id="6736c-211">**TypeCode.UInt64**</span><span class="sxs-lookup"><span data-stu-id="6736c-211">**TypeCode.UInt64**</span></span>|<span data-ttu-id="6736c-212">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="6736c-212">**VT_UI8**</span></span>|  
|<span data-ttu-id="6736c-213">**TypeCode.Single**</span><span class="sxs-lookup"><span data-stu-id="6736c-213">**TypeCode.Single**</span></span>|<span data-ttu-id="6736c-214">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="6736c-214">**VT_R4**</span></span>|  
|<span data-ttu-id="6736c-215">**TypeCode.Double**</span><span class="sxs-lookup"><span data-stu-id="6736c-215">**TypeCode.Double**</span></span>|<span data-ttu-id="6736c-216">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="6736c-216">**VT_R8**</span></span>|  
|<span data-ttu-id="6736c-217">**TypeCode.Decimal**</span><span class="sxs-lookup"><span data-stu-id="6736c-217">**TypeCode.Decimal**</span></span>|<span data-ttu-id="6736c-218">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="6736c-218">**VT_DECIMAL**</span></span>|  
|<span data-ttu-id="6736c-219">**TypeCode.DateTime**</span><span class="sxs-lookup"><span data-stu-id="6736c-219">**TypeCode.DateTime**</span></span>|<span data-ttu-id="6736c-220">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="6736c-220">**VT_DATE**</span></span>|  
|<span data-ttu-id="6736c-221">**TypeCode.String**</span><span class="sxs-lookup"><span data-stu-id="6736c-221">**TypeCode.String**</span></span>|<span data-ttu-id="6736c-222">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="6736c-222">**VT_BSTR**</span></span>|  
|<span data-ttu-id="6736c-223">Non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6736c-223">Not supported.</span></span>|<span data-ttu-id="6736c-224">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="6736c-224">**VT_INT**</span></span>|  
|<span data-ttu-id="6736c-225">Non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6736c-225">Not supported.</span></span>|<span data-ttu-id="6736c-226">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="6736c-226">**VT_UINT**</span></span>|  
|<span data-ttu-id="6736c-227">Non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6736c-227">Not supported.</span></span>|<span data-ttu-id="6736c-228">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="6736c-228">**VT_ARRAY**</span></span>|  
|<span data-ttu-id="6736c-229">Non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6736c-229">Not supported.</span></span>|<span data-ttu-id="6736c-230">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="6736c-230">**VT_RECORD**</span></span>|  
|<span data-ttu-id="6736c-231">Non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6736c-231">Not supported.</span></span>|<span data-ttu-id="6736c-232">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="6736c-232">**VT_CY**</span></span>|  
|<span data-ttu-id="6736c-233">Non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6736c-233">Not supported.</span></span>|<span data-ttu-id="6736c-234">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="6736c-234">**VT_VARIANT**</span></span>|  
  
 <span data-ttu-id="6736c-235">La valeur du variant COM est déterminée en appelant l’interface **IConvertible.To** *Type*, où **To** *Type* est la routine de conversion qui correspond au type retourné par **IConvertible.GetTypeCode**.</span><span class="sxs-lookup"><span data-stu-id="6736c-235">The value of the COM variant is determined by calling the **IConvertible.To** *Type* interface, where **To** *Type* is the conversion routine that corresponds to the type that was returned from **IConvertible.GetTypeCode**.</span></span> <span data-ttu-id="6736c-236">Par exemple, un objet qui retourne **TypeCode.Double** depuis **IConvertible.GetTypeCode** est marshalé en tant que variant COM de type **VT_R8**.</span><span class="sxs-lookup"><span data-stu-id="6736c-236">For example, an object that returns **TypeCode.Double** from **IConvertible.GetTypeCode** is marshaled as a COM variant of type **VT_R8**.</span></span> <span data-ttu-id="6736c-237">Vous pouvez obtenir la valeur du variant (stockée dans le champ **dblVal** du variant COM) en effectuant un cast en une interface **IConvertible** et en appelant la méthode <xref:System.IConvertible.ToDouble%2A>.</span><span class="sxs-lookup"><span data-stu-id="6736c-237">You can obtain the value of the variant (stored in the **dblVal** field of the COM variant) by casting to the **IConvertible** interface and calling the <xref:System.IConvertible.ToDouble%2A> method.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor4"></a>   
## <a name="marshaling-variant-to-object"></a><span data-ttu-id="6736c-238">Marshaling d’un variant vers un objet</span><span class="sxs-lookup"><span data-stu-id="6736c-238">Marshaling Variant to Object</span></span>  
 <span data-ttu-id="6736c-239">Lors du marshaling d’un variant vers un objet, le type, et parfois la valeur, du variant marshalé détermine le type d’objet produit.</span><span class="sxs-lookup"><span data-stu-id="6736c-239">When marshaling a variant to an object, the type, and sometimes the value, of the marshaled variant determines the type of object produced.</span></span> <span data-ttu-id="6736c-240">Le tableau suivant identifie chaque type variant et le type d’objet correspondant que le marshaleur crée quand un variant est passé de COM au .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6736c-240">The following table identifies each variant type and the corresponding object type that the marshaler creates when a variant is passed from COM to the .NET Framework.</span></span>  
  
|<span data-ttu-id="6736c-241">Type variant COM</span><span class="sxs-lookup"><span data-stu-id="6736c-241">COM variant type</span></span>|<span data-ttu-id="6736c-242">Type d'objet</span><span class="sxs-lookup"><span data-stu-id="6736c-242">Object type</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="6736c-243">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="6736c-243">**VT_EMPTY**</span></span>|<span data-ttu-id="6736c-244">Référence d’objet null (**Nothing** en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6736c-244">Null object reference (**Nothing** in Visual Basic).</span></span>|  
|<span data-ttu-id="6736c-245">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="6736c-245">**VT_NULL**</span></span>|<xref:System.DBNull?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-246">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="6736c-246">**VT_DISPATCH**</span></span>|<span data-ttu-id="6736c-247">**System.__ComObject** ou null si (pdispVal == null)</span><span class="sxs-lookup"><span data-stu-id="6736c-247">**System.__ComObject** or null if (pdispVal == null)</span></span>|  
|<span data-ttu-id="6736c-248">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="6736c-248">**VT_UNKNOWN**</span></span>|<span data-ttu-id="6736c-249">**System.__ComObject** ou null si (punkVal == null)</span><span class="sxs-lookup"><span data-stu-id="6736c-249">**System.__ComObject** or null if (punkVal == null)</span></span>|  
|<span data-ttu-id="6736c-250">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="6736c-250">**VT_ERROR**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-251">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="6736c-251">**VT_BOOL**</span></span>|<xref:System.Boolean?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-252">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="6736c-252">**VT_I1**</span></span>|<xref:System.SByte?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-253">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="6736c-253">**VT_UI1**</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-254">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="6736c-254">**VT_I2**</span></span>|<xref:System.Int16?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-255">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="6736c-255">**VT_UI2**</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-256">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="6736c-256">**VT_I4**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-257">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="6736c-257">**VT_UI4**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-258">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="6736c-258">**VT_I8**</span></span>|<xref:System.Int64?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-259">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="6736c-259">**VT_UI8**</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-260">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="6736c-260">**VT_R4**</span></span>|<xref:System.Single?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-261">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="6736c-261">**VT_R8**</span></span>|<xref:System.Double?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-262">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="6736c-262">**VT_DECIMAL**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-263">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="6736c-263">**VT_DATE**</span></span>|<xref:System.DateTime?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-264">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="6736c-264">**VT_BSTR**</span></span>|<xref:System.String?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-265">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="6736c-265">**VT_INT**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-266">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="6736c-266">**VT_UINT**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-267">**VT_ARRAY** &#124; **VT_**\*</span><span class="sxs-lookup"><span data-stu-id="6736c-267">**VT_ARRAY** &#124; **VT_**\*</span></span>|<xref:System.Array?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-268">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="6736c-268">**VT_CY**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  
|<span data-ttu-id="6736c-269">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="6736c-269">**VT_RECORD**</span></span>|<span data-ttu-id="6736c-270">Type valeur boxed correspondant.</span><span class="sxs-lookup"><span data-stu-id="6736c-270">Corresponding boxed value type.</span></span>|  
|<span data-ttu-id="6736c-271">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="6736c-271">**VT_VARIANT**</span></span>|<span data-ttu-id="6736c-272">Non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6736c-272">Not supported.</span></span>|  
  
 <span data-ttu-id="6736c-273">Les types variant passés à partir de COM vers le code managé, puis repassés à COM peuvent ne pas conserver le même type variant durant la durée de l’appel.</span><span class="sxs-lookup"><span data-stu-id="6736c-273">Variant types passed from COM to managed code and then back to COM might not retain the same variant type for the duration of the call.</span></span> <span data-ttu-id="6736c-274">Envisagez ce qui se passe quand un variant de type **VT_DISPATCH** est passé à partir de COM vers le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6736c-274">Consider what happens when a variant of type **VT_DISPATCH** is passed from COM to the .NET Framework.</span></span> <span data-ttu-id="6736c-275">Lors du marshaling, le variant est converti en <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6736c-275">During marshaling, the variant is converted to a <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6736c-276">Si **Object** est ensuite repassé à COM, il est remarshalé vers un variant de type **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="6736c-276">If the **Object** is then passed back to COM, it is marshaled back to a variant of type **VT_UNKNOWN**.</span></span> <span data-ttu-id="6736c-277">Rien ne garantit que le variant produit quand un objet est marshalé à partir de code managé vers COM sera du même type que le variant utilisé à l’origine pour produire l’objet.</span><span class="sxs-lookup"><span data-stu-id="6736c-277">There is no guarantee that the variant produced when an object is marshaled from managed code to COM will be the same type as the variant initially used to produce the object.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor6"></a>   
## <a name="marshaling-byref-variants"></a><span data-ttu-id="6736c-278">Marshaling des variants ByRef</span><span class="sxs-lookup"><span data-stu-id="6736c-278">Marshaling ByRef Variants</span></span>  
 <span data-ttu-id="6736c-279">Bien que les variants puissent eux-mêmes être passés par valeur ou par référence, l’indicateur **VT_BYREF** peut être également utilisé avec n’importe quel type de variant pour indiquer que le contenu du variant est passé par référence plutôt que par valeur.</span><span class="sxs-lookup"><span data-stu-id="6736c-279">Although variants themselves can be passed by value or by reference, the **VT_BYREF** flag can also be used with any variant type to indicate that the contents of the variant are being passed by reference instead of by value.</span></span> <span data-ttu-id="6736c-280">La différence entre le marshaling de variants par référence et le marshaling d’un variant dont l’indicateur **VT_BYREF** est défini peut prêter à confusion.</span><span class="sxs-lookup"><span data-stu-id="6736c-280">The difference between marshaling variants by reference and marshaling a variant with the **VT_BYREF** flag set can be confusing.</span></span> <span data-ttu-id="6736c-281">L’illustration suivante clarifie ces différences.</span><span class="sxs-lookup"><span data-stu-id="6736c-281">The following illustration clarifies the differences.</span></span>  
  
 <span data-ttu-id="6736c-282">![Variant passé sur la pile](./media/interopvariant.gif "interopvariant")</span><span class="sxs-lookup"><span data-stu-id="6736c-282">![Variant passed on the stack](./media/interopvariant.gif "interopvariant")</span></span>  
<span data-ttu-id="6736c-283">Variants passés par valeur et par référence</span><span class="sxs-lookup"><span data-stu-id="6736c-283">Variants passed by value and by reference</span></span>  
  
 <span data-ttu-id="6736c-284">**Comportement par défaut pour le marshaling d’objets et de variants par valeur**</span><span class="sxs-lookup"><span data-stu-id="6736c-284">**Default behavior for marshaling objects and variants by value**</span></span>  
  
-   <span data-ttu-id="6736c-285">Lors du passage d’objets à partir de code managé vers COM, le contenu de l’objet est copié dans un nouveau variant créé par le marshaleur à l’aide des règles définies dans [Marshaling d’un objet vers un variant](#cpcondefaultmarshalingforobjectsanchor3).</span><span class="sxs-lookup"><span data-stu-id="6736c-285">When passing objects from managed code to COM, the contents of the object are copied into a new variant created by the marshaler, using the rules defined in [Marshaling Object to Variant](#cpcondefaultmarshalingforobjectsanchor3).</span></span> <span data-ttu-id="6736c-286">Les changements apportés au variant côté non managé ne sont pas retournés vers l’objet d’origine au retour de l’appel.</span><span class="sxs-lookup"><span data-stu-id="6736c-286">Changes made to the variant on the unmanaged side are not propagated back to the original object on return from the call.</span></span>  
  
-   <span data-ttu-id="6736c-287">Lors du passage de variants à partir de COM vers du code managé, le contenu du variant est copié dans un objet nouvellement créé à l’aide des règles définies dans [Marshaling d’un variant vers un objet](#cpcondefaultmarshalingforobjectsanchor4).</span><span class="sxs-lookup"><span data-stu-id="6736c-287">When passing variants from COM to managed code, the contents of the variant are copied to a newly created object, using the rules defined in [Marshaling Variant to Object](#cpcondefaultmarshalingforobjectsanchor4).</span></span> <span data-ttu-id="6736c-288">Les changements apportés à l’objet côté managé ne sont pas retournés vers le variant d’origine au retour de l’appel.</span><span class="sxs-lookup"><span data-stu-id="6736c-288">Changes made to the object on the managed side are not propagated back to the original variant on return from the call.</span></span>  
  
 <span data-ttu-id="6736c-289">**Comportement par défaut pour le marshaling d’objets et de variants par référence**</span><span class="sxs-lookup"><span data-stu-id="6736c-289">**Default behavior for marshaling objects and variants by reference**</span></span>  
  
 <span data-ttu-id="6736c-290">Pour retourner des changements à l’appelant, les paramètres doivent être passés par référence.</span><span class="sxs-lookup"><span data-stu-id="6736c-290">To propagate changes back to the caller, the parameters must be passed by reference.</span></span> <span data-ttu-id="6736c-291">Par exemple, vous pouvez utiliser le mot clé **ref** en C# (ou **ByRef** en code managé Visual Basic) pour passer des paramètres par référence.</span><span class="sxs-lookup"><span data-stu-id="6736c-291">For example, you can use the **ref** keyword in C# (or **ByRef** in Visual Basic managed code) to pass parameters by reference.</span></span> <span data-ttu-id="6736c-292">Dans COM, les paramètres de référence sont passés à l’aide d’un pointeur tel que **variant \***.</span><span class="sxs-lookup"><span data-stu-id="6736c-292">In COM, reference parameters are passed using a pointer such as a **variant \***.</span></span>  
  
-   <span data-ttu-id="6736c-293">Lors du passage d’un objet à COM par référence, le marshaleur crée un variant et copie le contenu de la référence d’objet dans le variant avant que l’appel ne soit effectué.</span><span class="sxs-lookup"><span data-stu-id="6736c-293">When passing an object to COM by reference, the marshaler creates a new variant and copies the contents of the object reference into the variant before the call is made.</span></span> <span data-ttu-id="6736c-294">Le variant est passé à la fonction non managée où l’utilisateur est libre de changer le contenu du variant.</span><span class="sxs-lookup"><span data-stu-id="6736c-294">The variant is passed to the unmanaged function where the user is free to change the contents of the variant.</span></span> <span data-ttu-id="6736c-295">Au retour de l’appel, tout changement apporté au variant côté non managé est retourné vers l’objet d’origine.</span><span class="sxs-lookup"><span data-stu-id="6736c-295">On return from the call, any changes made to the variant on the unmanaged side are propagated back to the original object.</span></span> <span data-ttu-id="6736c-296">Si le type de variant est différent du type du variant passé à l’appel, les changements sont retournés à un objet d’un type différent.</span><span class="sxs-lookup"><span data-stu-id="6736c-296">If the type of the variant differs from the type of the variant passed to the call, then the changes are propagated back to an object of a different type.</span></span> <span data-ttu-id="6736c-297">Cela signifie que le type de l’objet passé dans l’appel peut être différent du type de l’objet retourné à partir de l’appel.</span><span class="sxs-lookup"><span data-stu-id="6736c-297">That is, the type of the object passed into the call can differ from the type of the object returned from the call.</span></span>  
  
-   <span data-ttu-id="6736c-298">Lors du passage d’un variant au code managé par référence, le marshaleur crée un objet et copie le contenu du variant dans l’objet avant que l’appel ne soit effectué.</span><span class="sxs-lookup"><span data-stu-id="6736c-298">When passing a variant to managed code by reference, the marshaler creates a new object and copies the contents of the variant into the object before making the call.</span></span> <span data-ttu-id="6736c-299">Une référence à l’objet est passée à la fonction managée, où l’utilisateur est libre de changer l’objet.</span><span class="sxs-lookup"><span data-stu-id="6736c-299">A reference to the object is passed to the managed function, where the user is free to change the object.</span></span> <span data-ttu-id="6736c-300">Au retour de l’appel, tout changement apporté à l’objet référencé est retourné vers le variant d’origine.</span><span class="sxs-lookup"><span data-stu-id="6736c-300">On return from the call, any changes made to the referenced object are propagated back to the original variant.</span></span> <span data-ttu-id="6736c-301">Si le type de l’objet est différent du type de l’objet passé dans l’appel, le type du variant d’origine est changé et la valeur est retournée dans le variant.</span><span class="sxs-lookup"><span data-stu-id="6736c-301">If the type of the object differs from the type of the object passed in to the call, the type of the original variant is changed and the value is propagated back into the variant.</span></span> <span data-ttu-id="6736c-302">Là encore, le type du variant passé dans l’appel peut être différent du type du variant retourné à partir de l’appel.</span><span class="sxs-lookup"><span data-stu-id="6736c-302">Again, the type of the variant passed into the call can differ from the type of the variant returned from the call.</span></span>  
  
 <span data-ttu-id="6736c-303">**Comportement par défaut pour le marshaling d’un variant où l’indicateur VT_BYREF a été défini**</span><span class="sxs-lookup"><span data-stu-id="6736c-303">**Default behavior for marshaling a variant with the VT_BYREF flag set**</span></span>  
  
-   <span data-ttu-id="6736c-304">Un variant passé à du code managé par valeur peut avoir l’indicateur **VT_BYREF** défini pour indiquer que le variant contient une référence plutôt qu’une valeur.</span><span class="sxs-lookup"><span data-stu-id="6736c-304">A variant being passed to managed code by value can have the **VT_BYREF** flag set to indicate that the variant contains a reference instead of a value.</span></span> <span data-ttu-id="6736c-305">Dans ce cas, le variant est toujours marshalé vers un objet, car le variant est passé par valeur.</span><span class="sxs-lookup"><span data-stu-id="6736c-305">In this case, the variant is still marshaled to an object because the variant is being passed by value.</span></span> <span data-ttu-id="6736c-306">Le marshaleur déréférence automatiquement le contenu du variant et le copie dans un objet nouvellement créé avant d’effectuer l’appel.</span><span class="sxs-lookup"><span data-stu-id="6736c-306">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="6736c-307">L’objet est ensuite passé à la fonction managée ; cependant, au retour de l’appel, l’objet n’est pas retourné dans le variant d’origine.</span><span class="sxs-lookup"><span data-stu-id="6736c-307">The object is then passed into the managed function; however, on return from the call, the object is not propagated back into the original variant.</span></span> <span data-ttu-id="6736c-308">Les changements apportés à l’objet managé sont perdus.</span><span class="sxs-lookup"><span data-stu-id="6736c-308">Changes made to the managed object are lost.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="6736c-309">Il est impossible de changer la valeur d’un variant passé par valeur, même si l’indicateur **VT_BYREF** de ce variant est défini.</span><span class="sxs-lookup"><span data-stu-id="6736c-309">There is no way to change the value of a variant passed by value, even if the variant has the **VT_BYREF** flag set.</span></span>  
  
-   <span data-ttu-id="6736c-310">Un variant passé à du code managé par référence peut aussi avoir l’indicateur **VT_BYREF** défini pour indiquer que le variant contient une autre référence.</span><span class="sxs-lookup"><span data-stu-id="6736c-310">A variant being passed to managed code by reference can also have the **VT_BYREF** flag set to indicate that the variant contains another reference.</span></span> <span data-ttu-id="6736c-311">Si c’est le cas, le variant est marshalé vers un objet **ref** parce qu’il est passé par référence.</span><span class="sxs-lookup"><span data-stu-id="6736c-311">If it does, the variant is marshaled to a **ref** object because the variant is being passed by reference.</span></span> <span data-ttu-id="6736c-312">Le marshaleur déréférence automatiquement le contenu du variant et le copie dans un objet nouvellement créé avant d’effectuer l’appel.</span><span class="sxs-lookup"><span data-stu-id="6736c-312">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="6736c-313">Au retour de l’appel, la valeur de l’objet est retournée vers la référence située dans le variant d’origine uniquement si l’objet est du même type que l’objet passé.</span><span class="sxs-lookup"><span data-stu-id="6736c-313">On return from the call, the value of the object is propagated back to the reference within the original variant only if the object is the same type as the object passed in.</span></span> <span data-ttu-id="6736c-314">Autrement dit, la propagation ne change pas le type d’un variant avec l’indicateur **VT_BYREF** défini.</span><span class="sxs-lookup"><span data-stu-id="6736c-314">That is, propagation does not change the type of a variant with the **VT_BYREF** flag set.</span></span> <span data-ttu-id="6736c-315">Si le type de l’objet est modifié durant l’appel, une exception <xref:System.InvalidCastException> se produit au retour de l’appel.</span><span class="sxs-lookup"><span data-stu-id="6736c-315">If the type of the object is changed during the call, an <xref:System.InvalidCastException> occurs on return from the call.</span></span>  
  
 <span data-ttu-id="6736c-316">Le tableau suivant résume les règles de propagation pour les variants et les objets.</span><span class="sxs-lookup"><span data-stu-id="6736c-316">The following table summarizes the propagation rules for variants and objects.</span></span>  
  
|<span data-ttu-id="6736c-317">From</span><span class="sxs-lookup"><span data-stu-id="6736c-317">From</span></span>|<span data-ttu-id="6736c-318">À</span><span class="sxs-lookup"><span data-stu-id="6736c-318">To</span></span>|<span data-ttu-id="6736c-319">Changements retournés</span><span class="sxs-lookup"><span data-stu-id="6736c-319">Changes propagated back</span></span>|  
|----------|--------|-----------------------------|  
|<span data-ttu-id="6736c-320">**Variant**  *v*</span><span class="sxs-lookup"><span data-stu-id="6736c-320">**Variant**  *v*</span></span>|<span data-ttu-id="6736c-321">**Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6736c-321">**Object**  *o*</span></span>|<span data-ttu-id="6736c-322">Never</span><span class="sxs-lookup"><span data-stu-id="6736c-322">Never</span></span>|  
|<span data-ttu-id="6736c-323">**Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6736c-323">**Object**  *o*</span></span>|<span data-ttu-id="6736c-324">**Variant**  *v*</span><span class="sxs-lookup"><span data-stu-id="6736c-324">**Variant**  *v*</span></span>|<span data-ttu-id="6736c-325">Never</span><span class="sxs-lookup"><span data-stu-id="6736c-325">Never</span></span>|  
|<span data-ttu-id="6736c-326">**Variant**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="6736c-326">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="6736c-327">**Ref Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6736c-327">**Ref Object**  *o*</span></span>|<span data-ttu-id="6736c-328">Toujours</span><span class="sxs-lookup"><span data-stu-id="6736c-328">Always</span></span>|  
|<span data-ttu-id="6736c-329">**Ref object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6736c-329">**Ref object**  *o*</span></span>|<span data-ttu-id="6736c-330">**Variant**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="6736c-330">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="6736c-331">Toujours</span><span class="sxs-lookup"><span data-stu-id="6736c-331">Always</span></span>|  
|<span data-ttu-id="6736c-332">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span><span class="sxs-lookup"><span data-stu-id="6736c-332">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span></span>|<span data-ttu-id="6736c-333">**Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6736c-333">**Object**  *o*</span></span>|<span data-ttu-id="6736c-334">Never</span><span class="sxs-lookup"><span data-stu-id="6736c-334">Never</span></span>|  
|<span data-ttu-id="6736c-335">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span><span class="sxs-lookup"><span data-stu-id="6736c-335">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span></span>|<span data-ttu-id="6736c-336">**Ref Object**  *o*</span><span class="sxs-lookup"><span data-stu-id="6736c-336">**Ref Object**  *o*</span></span>|<span data-ttu-id="6736c-337">Uniquement si le type n’a pas changé.</span><span class="sxs-lookup"><span data-stu-id="6736c-337">Only if the type has not changed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6736c-338">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6736c-338">See Also</span></span>  
 [<span data-ttu-id="6736c-339">Comportement de marshaling par défaut</span><span class="sxs-lookup"><span data-stu-id="6736c-339">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)  
 [<span data-ttu-id="6736c-340">Types blittable et non blittable</span><span class="sxs-lookup"><span data-stu-id="6736c-340">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)  
 <span data-ttu-id="6736c-341">[Attributs directionnels](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6736c-341">[Directional Attributes](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))</span></span>  
 [<span data-ttu-id="6736c-342">Copie et épinglage</span><span class="sxs-lookup"><span data-stu-id="6736c-342">Copying and Pinning</span></span>](copying-and-pinning.md)
