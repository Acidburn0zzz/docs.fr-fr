---
ms.openlocfilehash: 12ba683655319e42368f9f2a6cf7bf70e1dbd77d
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760207"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a>Valeur par défaut des algorithmes SignedXML et SignedXMS remplacée par SHA256

|   |   |
|---|---|
|Détails|Dans .NET Framework 4.7 et les versions antérieures, SignedXML et SignedCMS utilisent par défaut SHA1 pour certaines opérations. À compter de .NET Framework 4.7.1, SHA256 est activé par défaut pour ces opérations. Ce changement est nécessaire car SHA1 n’est plus considérée comme sécurisé.|
|Suggestion|Deux nouvelles valeurs de commutateur de contexte permettent de contrôler si SHA1 (non sécurisé) ou SHA256 est utilisé par défaut :<ul><li>Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</li><li>Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms</li></ul>Pour les applications que ciblent .NET Framework 4.7.1 et les versions ultérieures, si l’utilisation de SHA256 n’est pas souhaitable, vous pouvez restaurer SHA1 comme valeur par défaut en ajoutant le commutateur de configuration suivant à la section [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) de votre fichier de configuration d’application :<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true&quot; /&gt;&#13;&#10;</code></pre>Pour les applications que ciblent .NET Framework 4.7 et les versions antérieures, vous pouvez accepter ce changement en ajoutant le commutateur de configuration suivant à la section [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) de votre fichier de configuration d’application :<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false&quot; /&gt;&#13;&#10;</code></pre>|
|Portée|Mineur|
|Version|4.7.1|
|Type|Reciblage|
|API affectées|<ul><li><xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType></li></ul>|

