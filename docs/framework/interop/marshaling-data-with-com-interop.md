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
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="marshaling-data-with-com-interop"></a>marshaler des données avec COM Interop
COM Interop prend en charge l'utilisation des objets COM à partir de code managé, ainsi que l'exposition des objets managés à COM. La prise en charge du marshaling des données vers et depuis COM est complète et fournit quasiment toujours le comportement de marshaling approprié.  
  
 Le [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] comprend les outils COM Interop suivants :  
  
-   [Importateur de bibliothèques de types (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), qui convertit une bibliothèque de types COM en un assembly d’interopérabilité. À partir de cet assembly, le service de marshaling d’interopérabilité génère des wrappers qui effectuent le marshaling des données entre la mémoire managée et non managée.  
  
-   [Exportateur de bibliothèques de types (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), qui produit une bibliothèque de types COM à partir d’un assembly et génère un wrapper qui effectue le marshaling lors des appels de méthode.  
  
 Les sections suivantes lien vers les rubriques qui décrivent les processus de personnalisation des wrappers d’interopérabilité lorsque vous pouvez (ou devez) fournir au marshaleur des informations de type supplémentaires.  
  
## <a name="in-this-section"></a>Dans cette section  
[Comment : créer manuellement des Wrappers](how-to-create-wrappers-manually.md)   
Décrit comment créer un wrapper COM manuellement dans du code source managé. 
 
 [Guide pratique pour migrer le modèle DCOM de code managé vers WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 Décrit comment migrer du code DCOM managé vers WCF pour la solution la plus sécurisée.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Types de données COM](https://msdn.microsoft.com/library/sak564ww(v=vs.100).aspx)  
 Fournit les types de données managés et non managés correspondants.  
  
 [Personnalisation des wrappers CCW (COM Callable Wrapper)](https://msdn.microsoft.com/library/3bwc828w(v=vs.100).aspx)  
 Décrit comment marshaler explicitement des types de données à l’aide de la <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribut au moment du design.  
  
 [Personnalisation des wrappers RCW (Runtime Callable Wrapper)](https://msdn.microsoft.com/library/e753eftz(v=vs.100).aspx)  
 Décrit comment ajuster le comportement de marshaling des types dans un assembly d’interopérabilité et comment définir des types COM manuellement.  
  
 [Interopérabilité COM avancée](https://msdn.microsoft.com/library/bd9cdfyx(v=vs.100).aspx)  
 Fournit des liens vers des informations sur l'incorporation de composants COM dans une application .NET Framework.  
  
 [Récapitulatif de la conversion d’un assembly en bibliothèque de types](https://msdn.microsoft.com/library/xk1120c3(v=vs.100).aspx)  
 Décrit le processus d'exportation et de conversion d'un assembly en une bibliothèque de types.  
  
 [Récapitulatif de la conversion d’une bibliothèque de types en assembly](https://msdn.microsoft.com/library/k83zzh38(v=vs.100).aspx)  
 Décrit le processus d'importation et de conversion d'une bibliothèque de types en un assembly.  
  
 [Interopérabilité à l’aide de types génériques](https://msdn.microsoft.com/library/ms229590(v=vs.100).aspx)  
 Décrit les actions prises en charge lors de l'utilisation de types génériques pour l'interopérabilité COM.
