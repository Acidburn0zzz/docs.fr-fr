---
title: SignTool.exe (outil Sign Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- Sign tool
- SignTool.exe
ms.assetid: 0c25ff6c-bff3-422e-b017-146a3ee86cb9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6fddc6142341630e96088323d0c23a2eba1e879
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479153"
---
# <a name="signtoolexe-sign-tool"></a>SignTool.exe (outil Sign Tool)
L'outil Signature est un outil en ligne de commande qui signe numériquement les fichiers, vérifie les signatures dans les fichiers et horodate les fichiers.  
  
 Cet outil est installé automatiquement avec Visual Studio. Pour exécuter l’outil, utilisez l’invite de commandes développeur pour Visual Studio (ou l’invite de commandes Visual Studio dans Windows 7). Pour plus d'informations, consultez [Invites de commandes](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 À l'invite de commandes, tapez le texte suivant :  
  
## <a name="syntax"></a>Syntaxe  
  
```  
signtool [command] [options] [file_name | ...]  
```  
  
## <a name="parameters"></a>Paramètres  
  
|Argument|Description|  
|--------------|-----------------|  
|`command`|L'une des quatre commandes (`catdb`, `sign`, `Timestamp` ou `Verify`) qui spécifie une opération à exécuter sur un fichier. Pour obtenir une description de chaque commande, consultez le tableau suivant.|  
|`options`|Une option qui modifie une commande. En plus des options globales `/q` et `/v`, chaque commande prend en charge un seul ensemble d'options.|  
|`file_name`|Le chemin d’accès à un fichier à signer.|  
  
 Les commandes suivantes sont prises en charge par l'outil Signature. Chaque commande est utilisée avec un ensemble distinct d'options, qui sont affichées dans leurs sections respectives.  
  
|Commande|Description|  
|-------------|-----------------|  
|`catdb`|Ajoute ou supprime un fichier catalogue dans une base de données de catalogue. Les bases de données de catalogue sont utilisées pour la récupération automatique des fichiers catalogue et sont identifiées par un GUID. Pour obtenir la liste des options prises en charge par la commande `catdb`, consultez [Options de commande catdb](../../../docs/framework/tools/signtool-exe.md#catdb).|  
|`sign`|Signe numériquement les fichiers. Les signatures numériques protègent les fichiers contre la falsification et permettent aux utilisateurs de vérifier le signataire selon un certificat de signature. Pour obtenir la liste des options prises en charge par la commande `sign`, consultez [Options de commande sign](../../../docs/framework/tools/signtool-exe.md#sign).|  
|`Timestamp`|Horodate les fichiers. Pour obtenir la liste des options prises en charge par la commande `TimeStamp`, consultez [Options de commande TimeStamp](../../../docs/framework/tools/signtool-exe.md#TimeStamp).|  
|`Verify`|Vérifie la signature numérique des fichiers en déterminant si le certificat de signature a été publié par une autorité de confiance, si le certificat de signature a été révoqué et, éventuellement, si le certificat de signature est valide pour une stratégie spécifique. Pour obtenir la liste des options prises en charge par la commande `Verify`, consultez [Options de commande Verify](../../../docs/framework/tools/signtool-exe.md#Verify).|  
  
 Les options suivantes s'appliquent à toutes les commandes de l'outil Signature.  
  
|Option globale|Description|  
|-------------------|-----------------|  
|**/q**|N'affiche aucune sortie si la commande fonctionne correctement, et affiche la sortie minimale si la commande échoue.|  
|**/v**|Affiche la sortie des commentaires que la commande s'exécute correctement ou échoue, et affiche des messages d'avertissement.|  
|**/debug**|Affiche les informations de débogage.|  
  
<a name="catdb"></a>   
## <a name="catdb-command-options"></a>Options de commande catdb  
 Le tableau suivant répertorie les options qui peuvent être utilisées avec la commande `catdb`.  
  
|Option Catdb|Description|  
|------------------|-----------------|  
|`/d`|Spécifie que la base de données de catalogue par défaut est mise à jour. Si les options `/d` et `/g` ne sont pas utilisées, l'outil Signature met à jour le composant système et la base de données des pilotes.|  
|`/g` *GUID*|Spécifie que la base de données de catalogue identifiée par l’identificateur global unique *GUID* est mise à jour.|  
|`/r`|Supprime les catalogues spécifiés de la base de données de catalogue. Si cette option n'est pas spécifiée, l'outil Signature ajoute les catalogues spécifiés à la base de données de catalogue.|  
|`/u`|Spécifie qu'un nom unique est généré automatiquement pour les fichiers catalogue ajoutés. Si nécessaire, les fichiers catalogue seront renommés pour empêcher des conflits entre les noms des fichiers catalogue existants. Si cette option n'est pas spécifiée, l'outil Signature remplace tout catalogue existant dont le nom est le même que celui du catalogue ajouté.|  
  
<a name="sign"></a>   
## <a name="sign-command-options"></a>Options de la commande sign  
 Le tableau suivant répertorie les options qui peuvent être utilisées avec la commande `sign`.  
  
|Options de la commande Sign|Description|  
|-------------------------|-----------------|  
|`/a`|Sélectionne automatiquement le meilleur certificat de signature. L'outil Signature recherche tous les certificats valides qui répondent à toutes les conditions spécifiées et sélectionne celui qui est valide le plus longtemps. Si cette option n'est pas présente, l'outil Signature pense trouver un seul certificat de signature valide.|  
|`/ac`  *file*|Ajoute un certificat supplémentaire à partir de *file* au bloc de signature.|  
|`/as`|Ajoute cette signature. Si aucune signature principale n'est présente, cette signature est effectuée à la signature principale à la place.|  
|`/c`  *CertTemplateName*|Spécifie le nom du modèle de certificat (une extension Microsoft) pour le certificat de signature.|  
|`/csp`  *CSPName*|Spécifie le fournisseur de services de chiffrement (CSP) qui contient le conteneur de clés privées.|  
|`/d`  *Desc*|Spécifie une description du contenu signé.|  
|`/du`  *URL*|Spécifie une URL pour la description développée du contenu signé.|  
|`/f`  *SignCertFile*|Spécifie le certificat de signature dans un fichier. Si le fichier est au format PFX (Personal Information Exchange) et protégé par un mot de passe, utilisez l'option `/p` pour spécifier le mot de passe. Si le fichier ne contient aucune clé privée, utilisez les options `/csp` et `/kc` pour spécifier le nom du conteneur CSP et de clés privées.|  
|`/fd`|Spécifie l’algorithme de condensat de fichiers à utiliser pour créer des signatures de fichiers. La valeur par défaut est SHA1.|  
|`/i`  *IssuerName*|Spécifie le nom de l'émetteur du certificat de signature. Cette valeur peut être une sous-chaîne du nom d'émetteur entier.|  
|`/kc`  *PrivKeyContainerName*|Spécifie le nom du conteneur de clés privées.|  
|`/n`  *SubjectName*|Spécifie le nom de l'objet du certificat de signature. Cette valeur peut être une sous-chaîne du nom de l'objet entier.|  
|`/nph`|En cas de prise en charge, supprime les hachages de pages pour les fichiers exécutables. La valeur par défaut est déterminée par la variable d'environnement SIGNTOOL_PAGE_HASHES et par la version de wintrust.dll. Cette option est ignorée pour les fichiers non PE.|  
|`/p`  *Password*|Spécifie le mot de passe à utiliser lors de l'ouverture d'un fichier PFX. (Utilisez l'option `/f` pour spécifier un fichier PFX.)|  
|`/p7` *Path*|Spécifie qu'un fichier PKCS (Public Key Cryptography Standards) #7 est produit pour chaque fichier de contenu spécifié. Les fichiers PKCS #7 sont nommés *path*\\*filename*.p7.|  
|`/p7ce` *Value*|Spécifie des options pour le contenu PKCS #7 signé. Remplacez *Value* par « Embedded » pour incorporer le contenu signé dans le fichier PKCS #7 ou par « DetachedSignedData » pour produire la partie signée des données d’un fichier PKCS #7 détaché. Si l'option `/p7ce` n'est pas utilisée, le contenu signé est incorporé par défaut.|  
|`/p7co` *\<OID>*|Spécifie l'identificateur d'objet (OID) qui identifie le contenu PKCS #7 signé.|  
|`/ph`|En cas de prise en charge, génère les hachages de pages pour les fichiers exécutables.|  
|`/r`  *RootSubjectName*|Spécifie le nom de l'objet du certificat racine auquel le certificat de signature doit être lié. Cette valeur peut être une sous-chaîne du nom de l'objet entier du certificat racine.|  
|`/s`  *StoreName*|Spécifie le magasin à ouvrir lors de la recherche du certificat. Si cette option n'est pas spécifiée, le magasin `My` est ouvert.|  
|`/sha1`  *Hash*|Spécifie le hachage SHA1 du certificat de signature. Le hachage SHA1 est souvent spécifié lorsque plusieurs certificats répondent aux critères spécifiés par les commutateurs restants.|  
|`/sm`|Spécifie qu'un magasin d'ordinateur, au lieu d'un magasin d'utilisateur, est utilisé.|  
|`/t`  *URL*|Spécifie l'URL du serveur d'horodatage. Si cette option (ou `/tr`) n'est pas présente, le fichier signé ne sera pas horodaté. Un avertissement est généré si l'horodatage échoue. Cette option ne peut pas être utilisée avec l'option `/tr`.|  
|`/td`  *alg*|Utilisé avec l'option `/tr` pour demander un algorithme Digest utilisé par le serveur d'horodatage RFC 3161.|  
|`/tr`  *URL*|Spécifie l'URL du serveur d'horodatage RFC 3161. Si cette option (ou `/t`) n'est pas présente, le fichier signé ne sera pas horodaté. Un avertissement est généré si l'horodatage échoue. Cette option ne peut pas être utilisée avec l'option `/t`.|  
|`/u`  *Usage*|Spécifie l'utilisation améliorée de la clé (EKU) qui doit être présente dans le certificat de signature. La valeur de l'utilisation peut être spécifiée par un OID ou une chaîne. L'utilisation par défaut est « Signature du code » (1.3.6.1.5.5.7.3.3).|  
|`/uw`|Spécifie l'utilisation « Windows System Component Verification » (1.3.6.1.4.1.311.10.3.6).|  
  
 Pour obtenir des exemples, consultez [Utilisation de SignTool pour signer un fichier](/windows/desktop/SecCrypto/using-signtool-to-sign-a-file).  
  
<a name="TimeStamp"></a>   
## <a name="timestamp-command-options"></a>Options de commande TimeStamp  
 Le tableau suivant répertorie les options qui peuvent être utilisées avec la commande `TimeStamp`.  
  
|Option TimeStamp|Description|  
|----------------------|-----------------|  
|`/p7`|Horodate les fichiers PKCS #7.|  
|`/t`  *URL*|Spécifie l'URL du serveur d'horodatage. Le fichier en cours d'horodatage doit avoir été signé au préalable. L'option `/t` ou `/tr` est obligatoire.|  
|`/td`  *alg*|Demande un algorithme de condensat utilisé par le serveur d’horodatage RFC 3161. `/td` est utilisé avec l'option `/tr`.|  
|`/tp` *index*|Horodate la signature à l’*index*.|  
|`/tr`  *URL*|Spécifie l'URL du serveur d'horodatage RFC 3161. Le fichier en cours d'horodatage doit avoir été signé au préalable. L'option `/tr` ou `/t` est obligatoire.|  
  
 Pour obtenir un exemple, consultez [Ajout d’horodatages à des fichiers précédemment signés](/windows/desktop/SecCrypto/adding-time-stamps-to-previously-signed-files).  
  
<a name="Verify"></a>   
## <a name="verify-command-options"></a>Options de commande Verify  
  
|Option Verify|Description|  
|-------------------|-----------------|  
|`/a`|Spécifie que toutes les méthodes peuvent être utilisées pour vérifier le fichier. En premier lieu, une recherche est effectuée dans les bases de données de catalogue pour déterminer si le fichier est signé dans un catalogue. Si le fichier n'est signé dans aucun catalogue, l'outil Signature tente de vérifier la signature incorporée du fichier. Cette option est recommandée lors de la vérification de fichiers qui peuvent être ou non signés dans un catalogue. Les exemples de ces fichiers incluent des fichiers ou des pilotes Windows.|  
|`/ad`|Recherche le catalogue à l'aide de la base de données de catalogue par défaut.|  
|`/ag` *CatDBGUID*|Recherche le catalogue dans la base de données de catalogue qui est identifiée par *CatDBGUID*.|  
|`/all`|Vérifie toutes les signatures dans un fichier contenant plusieurs signatures.|  
|`/as`|Recherche le catalogue à l'aide de la base de données de catalogue du composant système (pilote).|  
|`/c` *CatFile*|Spécifie le fichier catalogue par nom.|  
|`/d`|Spécifie que l'outil Signature doit imprimer la description et l'URL de description.|  
|`/ds`  *Index*|Vérifie la signature à un emplacement spécifié.|  
|`/hash` (`SHA1`&#124;`SHA256`)|Spécifie un algorithme de hachage facultatif à utiliser lors de la recherche d'un fichier dans un catalogue.|  
|`/kp`|Spécifie que la vérification doit être effectuée avec la stratégie de signature de pilotes en mode noyau.|  
|`/ms`|Utilise plusieurs sémantiques de vérification. Il s’agit du comportement par défaut d’un appel [WinVerifyTrust](/windows/desktop/api/wintrust/nf-wintrust-winverifytrust) sur [!INCLUDE[win8](../../../includes/win8-md.md)] et ultérieur.|  
|`/o` *Version*|Vérifie le fichier par version du système d'exploitation. *Version* a le format suivant : *PlatformID*:*VerMajor*.*VerMinor*.*BuildNumber*. *PlatformID* représente la valeur sous-jacente d’un membre de l’énumération <xref:System.PlatformID>. **Important :**  Il est recommandé d’utiliser le commutateur `/o`. Si `/o` n'est pas spécifié, SignTool.exe peut retourner des résultats inattendus. Par exemple, si vous n'incluez pas le commutateur `/o`, les catalogues système qui valident correctement sur un système d'exploitation plus ancien peuvent ne pas valider correctement sur un système d'exploitation plus récent.|  
|`/p7`|Vérifie les fichiers PKCS #7. Aucune stratégie existante n'est utilisée pour la validation PKCS #7. La signature est vérifiée et une chaîne est générée pour le certificat de signature.|  
|`/pa`|Spécifie que la stratégie de vérification Authenticode par défaut doit être utilisée. Si l'option `/pa` n'est pas spécifiée, l'outil Signature utilise la stratégie de vérification des pilotes Windows. Cette option ne peut pas être utilisée avec les options `catdb`.|  
|`/pg` *PolicyGUID*|Spécifie une stratégie de vérification par GUID. *PolicyGUID* correspond à la valeur ActionID de la stratégie de vérification. Cette option ne peut pas être utilisée avec les options `catdb`.|  
|`/ph`|Spécifie que l'outil Signature doit imprimer et vérifier les valeurs de hachage des pages.|  
|`/r` *RootSubjectName*|Spécifie le nom de l'objet du certificat racine auquel le certificat de signature doit être lié. Cette valeur peut être une sous-chaîne du nom de l'objet entier du certificat racine.|  
|`/tw`|Spécifie qu'un avertissement doit être généré si la signature n'est pas horodatée.|  
  
 Pour obtenir des exemples, consultez [Utilisation de SignTool pour vérifier la signature d’un fichier](/windows/desktop/SecCrypto/using-signtool-to-verify-a-file-signature).  
  
## <a name="return-value"></a>Valeur de retour  
 L'outil Signature retourne l'un des codes de sortie suivants lorsqu'il se termine.  
  
|Code de sortie|Description|  
|---------------|-----------------|  
|0|L'exécution a été correctement effectuée.|  
|1|L'exécution a échoué.|  
|2|L'exécution a été effectuée avec des avertissements.|  
  
## <a name="examples"></a>Exemples  
 La commande suivante ajoute le fichier catalogue MyCatalogFileName.cat au composant système et à la base de données de pilotes. L'option `/u` génère un nom unique si nécessaire pour éviter de remplacer un fichier catalogue existant nommé `MyCatalogFileName.cat`.  
  
```  
signtool catdb /v /u MyCatalogFileName.cat  
```  
  
 La commande suivante signe un fichier automatiquement à l'aide du meilleur certificat.  
  
```  
signtool sign /a MyFile.exe  
```  
  
 La commande suivante signe numériquement un fichier à l'aide d'un certificat stocké dans un fichier PFX protégé par un mot de passe.  
  
```  
signtool sign /f MyCert.pfx /p MyPassword MyFile.exe  
```  
  
 La commande suivante signe numériquement et horodate un fichier. Le certificat utilisé pour signer le fichier est stocké dans un fichier PFX.  
  
```  
signtool sign /f MyCert.pfx /t http://timestamp.verisign.com/scripts/timstamp.dll MyFile.exe  
```  
  
 La commande suivante signe un fichier à l'aide d'un certificat situé dans le magasin `My` qui a un nom d'objet `My Company Certificate`.  
  
```  
signtool sign /n "My Company Certificate" MyFile.exe  
```  
  
 La commande suivante signe un contrôle ActiveX et fournit des informations qui sont affichées par Internet Explorer lorsque l'utilisateur est invité à installer le contrôle.  
  
```  
Signtool sign /f MyCert.pfx /d: "MyControl" /du http://www.example.com/MyControl/info.html MyControl.exe  
```  
  
 La commande suivante horodate à un fichier qui a déjà été signé numériquement.  
  
```  
signtool timestamp /t http://timestamp.verisign.com/scripts/timstamp.dll MyFile.exe  
```  
  
 La commande suivante vérifie qu'un fichier a été signé.  
  
```  
signtool verify MyFile.exe  
```  
  
 La commande suivante vérifie un fichier système qui a peut-être été signé dans un catalogue.  
  
```  
signtool verify /a SystemFile.dll  
```  
  
 La commande suivante vérifie un fichier système qui est signé dans un catalogue nommé `MyCatalog.cat`.  
  
```  
signtool verify /c MyCatalog.cat SystemFile.dll  
```  
  
## <a name="see-also"></a>Voir aussi
- [Outils](../../../docs/framework/tools/index.md)
- [Invites de commandes](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
