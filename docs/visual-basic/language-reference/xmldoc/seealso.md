---
title: '&lt;seealso&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: a792bbea108bcdf33d430c47773466ef3dccdb0c
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46539990"
---
# <a name="ltseealsogt-visual-basic"></a><span data-ttu-id="0e68f-102">&lt;seealso&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e68f-102">&lt;seealso&gt; (Visual Basic)</span></span>
<span data-ttu-id="0e68f-103">Spécifie un lien qui apparaît dans la section Voir aussi.</span><span class="sxs-lookup"><span data-stu-id="0e68f-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e68f-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0e68f-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e68f-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="0e68f-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="0e68f-106">Référence à un membre ou un champ qu’il est possible d’appeler à partir de l’environnement de compilation actuel.</span><span class="sxs-lookup"><span data-stu-id="0e68f-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="0e68f-107">Le compilateur vérifie que l’élément de code donné existe et qu’il passe `member` au nom d’élément dans la sortie XML.</span><span class="sxs-lookup"><span data-stu-id="0e68f-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="0e68f-108">`member` doit apparaître entre guillemets doubles (" ").</span><span class="sxs-lookup"><span data-stu-id="0e68f-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e68f-109">Notes</span><span class="sxs-lookup"><span data-stu-id="0e68f-109">Remarks</span></span>  
 <span data-ttu-id="0e68f-110">Utilisez le `<seealso>` balise pour spécifier le texte que vous souhaitez voir apparaître dans une section Voir aussi.</span><span class="sxs-lookup"><span data-stu-id="0e68f-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="0e68f-111">Utilisez [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) pour spécifier un lien à partir de l’intérieur du texte.</span><span class="sxs-lookup"><span data-stu-id="0e68f-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="0e68f-112">Compilez avec [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) pour placer les commentaires de documentation dans un fichier en vue de les traiter.</span><span class="sxs-lookup"><span data-stu-id="0e68f-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e68f-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="0e68f-113">Example</span></span>  
 <span data-ttu-id="0e68f-114">Cet exemple utilise le `<seealso>` balise dans le `DoesRecordExist` section pour faire référence à la section Notes le `UpdateRecord` (méthode).</span><span class="sxs-lookup"><span data-stu-id="0e68f-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0e68f-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e68f-115">See Also</span></span>  
 [<span data-ttu-id="0e68f-116">Étiquettes XML pour les commentaires</span><span class="sxs-lookup"><span data-stu-id="0e68f-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
