---
title: Configuration de classes de chiffrement
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b12d5d95a17439308d79d094e8c22206778f3128
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="configuring-cryptography-classes"></a>Configuration de classes de chiffrement
Le [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] permet aux administrateurs d’ordinateur configurer les algorithmes de chiffrement par défaut et les implémentations d’algorithme par le .NET Framework et les applications écrites de façon adéquate.  Par exemple, une entreprise qui utilise sa propre implémentation d’un algorithme de chiffrement faire que l’implémentation par défaut au lieu de l’implémentation fournie dans le [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]. Bien que les applications managées qui utilisent le chiffrement peuvent toujours choisir de lier explicitement à une implémentation particulière, il est recommandé qu’ils créent un objet de chiffrement en utilisant le système de configuration de chiffrement.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Mappage de noms d'algorithmes à des classes de chiffrement](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 Décrit comment mapper un nom d’algorithme à une classe de chiffrement.  
  
 [Mappage d'identificateurs d'objet à des algorithmes de chiffrement](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 Décrit comment mapper un identificateur d’objet à un algorithme de chiffrement.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)  
 Fournit une vue d’ensemble des services de chiffrement fournis par le [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].  
  
 [Schéma des paramètres de chiffrement](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 Décrit des éléments qui mappent des noms d'algorithmes conviviaux à des classes implémentant des algorithmes de chiffrement.
