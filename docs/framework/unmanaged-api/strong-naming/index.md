---
title: Nom fort (Informations de référence sur les API non managées)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32e74a76b6b1bedee4efc5715d0710c8efce2455
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120755"
---
# <a name="strong-naming-unmanaged-api-reference"></a>Nom fort (Informations de référence sur les API non managées)
L’API de nommage fort permet à un client d’administrer la signature avec noms forts pour les assemblys.  
  
 La signature d'un assembly avec un nom fort ajoute un chiffrement à clé publique au fichier contenant le manifeste d'assembly. La signature avec un nom fort permet de vérifier l’unicité du nom, empêche l’usurpation de noms et fournit aux appelants une identité unique quand une référence est résolue. Aucun niveau de confiance n’est toutefois associé à un nom fort.  
  
## <a name="in-this-section"></a>Dans cette section  
  
> [!NOTE]
>  Toutes ces fonctions sont dépréciées à compter de [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Pour obtenir des suggestions d’alternatives, consultez l’interface [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md).  
  
 [GetHashFromAssemblyFile, fonction](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 Obtient un hachage du fichier d’assembly spécifié, à l’aide de l’algorithme de hachage spécifié. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromAssemblyFileW, fonction](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 Obtient un hachage du fichier d’assembly spécifié sous forme de chaîne Unicode, à l’aide de l’algorithme de hachage spécifié. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromBlob, fonction](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 Obtient un hachage de l’assembly à l’adresse mémoire spécifiée, à l’aide de l’algorithme de hachage spécifié. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromFile, fonction](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 Génère un hachage sur le contenu du fichier spécifié.  Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromFileW, fonction](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 Génère un hachage sur le contenu du fichier spécifié par une chaîne Unicode. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [GetHashFromHandle, fonction](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 Génère un hachage sur le contenu du fichier avec le handle de fichier spécifié, à l’aide de l’algorithme de hachage spécifié.  Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameCompareAssemblies, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 Détermine si deux assemblys diffèrent uniquement par leurs signatures avec nom fort. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameErrorInfo, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 Obtient le dernier code d’erreur déclenché par l’une des fonctions de nom fort.  
  
 [StrongNameFreeBuffer, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 Libère la mémoire qui a été alloué avec un appel précédent à une fonction de nom fort comme [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) ou [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).   Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetBlob, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 Remplit la mémoire tampon spécifiée avec la représentation binaire du fichier exécutable à l’adresse spécifiée. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetBlobFromImage, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 Obtient une représentation binaire de l’image de l’assembly à l’adresse mémoire spécifiée. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameGetPublicKey, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 Obtient la clé publique à partir d’une paire de clés publique/privée. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameHashSize, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 Obtient la taille de mémoire tampon requise pour un hachage, à l’aide de l’algorithme de hachage spécifié.  Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyDelete, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 Supprime le conteneur de clé spécifié. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyGen, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 Crée une nouvelle paire de clés publique/privée pour une utilisation de nom fort.  Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyGenEx, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 Génère une nouvelle paire de clés publique/privée avec la taille de clé spécifiée pour une utilisation de nom fort. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameKeyInstall, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 Importe une paire de clés publique/privée dans un conteneur.  Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureGeneration, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 Génère une signature de nom fort pour l’assembly spécifié.   Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureGenerationEx, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 Génère une signature de nom fort pour l’assembly spécifié, en fonction des indicateurs spécifiés.    Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureSize, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 Retourne la taille de la signature de nom fort. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerification, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 Obtient une valeur indiquant si le manifeste d’assembly au chemin fourni contient une signature de nom fort, qui est vérifiée en fonction des indicateurs spécifiés. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerificationEx, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 Obtient une valeur indiquant si le manifeste d’assembly au chemin fourni contient une signature de nom fort.  Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameSignatureVerificationFromImage, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 Vérifie qu’un assembly qui a déjà été mappé en mémoire est valide pour la clé publique associée. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromAssembly, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 Crée un jeton de nom fort à partir du fichier d’assembly spécifié.  Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromAssemblyEx, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 Crée un jeton de nom fort à partir du fichier d’assembly spécifié et retourne la clé publique. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [StrongNameTokenFromPublicKey, fonction](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 Obtient un jeton représentant une clé publique. Déprécié à compter de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].  
  
 [PublicKeyBlob, structure](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 Représente la clé publique d’une paire de clés publique/privée au format binaire.  
  
## <a name="see-also"></a>Voir aussi

- [ICLRStrongName, interface](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [Informations de référence sur les API non managées](../../../../docs/framework/unmanaged-api/index.md)
