---
title: System.Object, méthodes
ms.date: 03/30/2017
ms.assetid: 5397fca0-689e-443e-802f-e1cbdc866427
ms.openlocfilehash: bd4b30a65e7ad9391d9b867884d1c909491344bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="systemobject-methods"></a>System.Object, méthodes
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] prend en charge les éléments suivants <xref:System.Object> méthodes.  
  
|||  
|-|-|  
|<xref:System.Object.Equals%28System.Object%29?displayProperty=nameWithType>|<xref:System.Object.Equals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType>||  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ne prend pas en charge les méthodes <xref:System.Object> suivantes.  
  
|||  
|-|-|  
|<xref:System.Object.GetHashCode?displayProperty=nameWithType>|<xref:System.Object.ReferenceEquals%28System.Object%2CSystem.Object%29?displayProperty=nameWithType>|  
|<xref:System.Object.MemberwiseClone?displayProperty=nameWithType>|<xref:System.Object.GetType?displayProperty=nameWithType>|  
|<xref:System.Object.ToString?displayProperty=nameWithType> pour les types binaires tels que `BINARY`, `VARBINARY`, `IMAGE` et `TIMESTAMP`.||  
  
## <a name="differences-from-net"></a>Différences par rapport à .NET  
 La sortie de <xref:System.Object.ToString?displayProperty=nameWithType> pour les doubles utilise SQL `CONVERT`(nvarchar (30), @x, 2) sur SQL. SQL utilise toujours 16 chiffres et une notation scientifique dans ce cas (par exemple, "0.000000000000000e+000" pour 0). Par conséquent, la conversion <xref:System.Object.ToString?displayProperty=nameWithType> ne génère pas la même chaîne que <xref:System.Convert.ToString%2A?displayProperty=nameWithType> dans le .NET Framework.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions et types de données](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
