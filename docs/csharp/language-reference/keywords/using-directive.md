---
title: using, directive (référence C#)
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 180c038987e7de6b39a8eae0e86871eea41a40bb
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960038"
---
# <a name="using-directive-c-reference"></a>using, directive (référence C#)
La directive `using` a trois utilisations :  
  
-   Pour autoriser l'utilisation de types dans un espace de noms pour ne pas avoir à qualifier l'utilisation d'un type dans cet espace de noms :  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   Pour vous permettre d’accéder aux membres statiques d’un type sans devoir qualifier l’accès avec le nom du type. 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    Pour plus d’informations, consultez la [directive using static](using-static.md).

-   Pour créer un alias pour un espace de noms ou un type. Cela s’appelle une *directive using alias*.  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 Le mot clé `using` est également utilisé pour créer des *instructions using<xref:System.IDisposable>, qui garantissent que les objets*  tels que les fichiers et les polices sont gérés correctement. Pour plus d’informations, consultez [Instruction using](../../../csharp/language-reference/keywords/using-statement.md).  
  
## <a name="using-static-type"></a>Utilisation du type static  
 Vous pouvez accéder aux membres statiques d'un type sans devoir qualifier l'accès avec le nom du type :  
  
```csharp  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
```  
  
## <a name="remarks"></a>Notes  
 La portée d'une directive `using` se limite au fichier dans lequel elle apparaît.  
  
 Créez un alias `using` pour faciliter la qualification d'un identificateur pour un espace de noms ou un type. Le côté droit d'une directive d'alias using doit toujours être un type complet quelles que soient les directives using placées avant.  
  
 Créez une directive `using` pour utiliser les types dans un espace de noms sans avoir à spécifier l'espace de noms. Une directive `using` ne vous donne pas accès à des espaces de noms imbriqués dans l'espace de noms que vous spécifiez.  
  
 Les espaces de noms sont organisés en deux catégories : définis par l'utilisateur et définis par le système. Les espaces de noms définis par l'utilisateur sont des espaces de noms définis dans votre code. Pour obtenir la liste des espaces de noms définis par le système, consultez [Vue d’ensemble de la bibliothèque de classes .NET Framework](../../../standard/class-library-overview.md).  
  
 Pour obtenir des exemples de référencement de méthodes dans d’autres assemblys, consultez [Créer et utiliser des assemblys avec la ligne de commande](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).  
  
## <a name="example-1"></a>Exemple 1  
  
 L'exemple suivant montre comment définir et utiliser un alias `using` pour un espace de noms :  
  
 [!code-csharp[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 Une directive d'alias using ne peut pas avoir un type générique ouvert sur le côté droit. Par exemple, vous ne pouvez pas créer un alias using pour un List\<T>, mais vous pouvez en créer un pour un List\<int>.  
  
## <a name="example-2"></a>Exemple 2  
  
 L'exemple suivant montre comment définir une directive `using` et un alias `using` pour une classe :  
  
 [!code-csharp[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a>Spécification du langage C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Référence C#](../../../csharp/language-reference/index.md)  
 [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
 [Utilisation d’espaces de noms](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
 [Mots clés C#](../../../csharp/language-reference/keywords/index.md)  
 [Mots clés d’espaces de noms](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [Espaces de noms](../../../csharp/programming-guide/namespaces/index.md)  
 [using, instruction](../../../csharp/language-reference/keywords/using-statement.md)
