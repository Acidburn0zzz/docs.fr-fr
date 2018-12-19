---
title: Expressions lambda - Guide de programmation C#
ms.custom: seodec18
ms.date: 03/03/2017
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: 0feff32f3a2264b8e6cbd4746fdeaaaad728b8e5
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241286"
---
# <a name="lambda-expressions-c-programming-guide"></a>Expressions lambda (Guide de programmation C#)

Une expression lambda est une [fonction anonyme](anonymous-methods.md) que vous pouvez utiliser pour créer des types [délégués](../delegates/using-delegates.md) ou des types d' [arborescence d'expression](../concepts/expression-trees/index.md) . En utilisant des expressions lambda, vous pouvez écrire des fonctions locales qui peuvent être passées comme des arguments ou retournées comme la valeur d'appels de fonction. Les expressions lambda sont particulièrement utiles pour écrire des expressions de requête LINQ.
  
Pour créer une expression lambda, vous spécifiez des paramètres d'entrée (le cas échéant) à gauche de l'opérateur lambda [=>](../../../csharp/language-reference/operators/lambda-operator.md), et vous placez l'expression ou le bloc d'instructions de l'autre côté. Par exemple, l'expression lambda `x => x * x` spécifie un paramètre nommé `x` et retourne la valeur `x` élevée au carré. Vous pouvez assigner cette expression à un type délégué, comme dans l'exemple suivant :  
  
```csharp  
delegate int del(int i);  
static void Main(string[] args)  
{  
    del myDelegate = x => x * x;  
    int j = myDelegate(5); //j = 25  
}  
```  
  
 Pour créer un type d'arborescence d'expression :  
  
```csharp  
using System.Linq.Expressions;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Expression<del> myET = x => x * x;  
        }  
    }  
}  
```  
  
 L'opérateur `=>` a la même priorité que l'assignation (`=`) et est de type [right associative](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (consultez la section « Associativité » de l'article Opérateurs).  
  
 Les lambdas sont utilisés dans les requêtes [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] fondées sur une méthode en tant qu'arguments pour les méthodes d'opérateur de requête standard telles que <xref:System.Linq.Enumerable.Where%2A>.  
  
 Lorsque vous utilisez la syntaxe fondée sur une méthode pour appeler la méthode <xref:System.Linq.Enumerable.Where%2A> dans la classe <xref:System.Linq.Enumerable> (de la même manière que dans [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects et [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]), le paramètre est un type délégué <xref:System.Func%602?displayProperty=nameWithType>. Une expression lambda est la méthode la plus commode pour créer ce délégué. Quand vous appelez la même méthode dans, par exemple, la classe <xref:System.Linq.Queryable?displayProperty=nameWithType> (comme vous le faites dans [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]), le type de paramètre est <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType><Func\>, où Func correspond à un délégué Func avec seize paramètres d'entrée maximum. Une expression lambda est simplement une méthode très concise pour construire cette arborescence de l'expression. Les lambdas font apparaître les appels `Where` comme semblables bien qu'en fait, le type d'objet créé à partir du lambda soit différent.  
  
 Dans l'exemple précédent, vous remarquez que la signature du délégué comporte un paramètre d'entrée implicitement typé `int`et retourne un `int`. L'expression lambda peut être convertie en un délégué de ce type, car elle comporte également un paramètre d'entrée (`x`) et une valeur de retour que le compilateur peut convertir implicitement en type `int`. (L'inférence de type est traitée plus en détail dans les sections suivantes.) Lorsque le délégué est appelé à l'aide d'un paramètre d'entrée de 5, il retourne un résultat de 25.  
  
 Les expressions lambda ne sont pas autorisées du côté gauche de l’opérateur [is](../../../csharp/language-reference/keywords/is.md) ou [as](../../../csharp/language-reference/keywords/as.md).  
  
 Toutes les restrictions qui s'appliquent aux méthodes anonymes s'appliquent également aux expressions lambda. Pour plus d’informations, consultez [Méthodes anonymes](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).  
  
## <a name="expression-lambdas"></a>Expressions lambda

 Une expression lambda avec une expression du côté droit de l’opérateur => est appelée *expression lambda*. Les expressions lambda sont utilisées en grand nombre dans la construction d’[arborescences d’expression](../concepts/expression-trees/index.md). Une expression lambda retourne le résultat de l'expression et prend la forme de base suivante :
  
```csharp
(input-parameters) => expression
```

 Les parenthèses sont facultatives uniquement si le lambda comporte un paramètre d'entrée ; sinon, elles sont obligatoires. Les paramètres d'entrée sont séparés par des virgules entre parenthèses :  
  
```csharp
(x, y) => x == y
```

 Il est parfois difficile, voire impossible, pour le compilateur de déduire les types d'entrée. Dans ce cas, vous pouvez spécifier les types explicitement comme indiqué dans l'exemple suivant :  
  
```csharp
(int x, string s) => s.Length > x
```
 Les types de paramètre d’entrée doivent être tous explicites ou implicites. Sinon, C# génère l’erreur de compilateur [CS0748](../../misc/cs0748.md).

 Spécifiez des paramètres d'entrée de zéro avec des parenthèses vides :  
  
```csharp
() => SomeMethod()
```

 Notez dans l'exemple précédent que le corps d'une expression lambda peut se composer d'un appel de méthode. Toutefois, si vous créez des arborescences d'expressions évaluées en dehors de .NET Framework, comme dans SQL Server, vous ne devez pas utiliser les appels de méthode dans les expressions lambda. Les méthodes n'auront aucune signification en dehors du contexte du Common Language Runtime .NET.  
  
## <a name="statement-lambdas"></a>Instructions lambda  
 Une instruction lambda ressemble à une expression lambda, mais l'instruction ou les instructions sont mises entre accolades :  
  
(paramètres d’entrée) => { instruction ; }

 Le corps d'une instruction lambda peut se composer d'un nombre illimité d'instructions ; toutefois, en pratique, leur nombre est généralement de deux ou trois.  
  
[!code-csharp[StatementLamba#1](~/samples/snippets/csharp/programming-guide/lambda-expressions/statements.cs#1)]

[!code-csharp[StatementLamba#2](~/samples/snippets/csharp/programming-guide/lambda-expressions/statements.cs#2)]

 Les instructions lambda, comme les méthodes anonymes, ne peuvent pas être utilisées pour créer des arborescences d'expression.  
  
## <a name="async-lambdas"></a>Lambdas asynchrones  
 Vous pouvez facilement créer des expressions et des instructions lambda qui incorporent le traitement asynchrone à l'aide des mots clés [async](../../../csharp/language-reference/keywords/async.md) et [await](../../../csharp/language-reference/keywords/await.md) . Par exemple, l'exemple Windows Forms suivant contient un gestionnaire d'événements qui appelle et attend une méthode async `ExampleMethodAsync`.  
  
```csharp
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
    }  
  
    private async void button1_Click(object sender, EventArgs e)  
    {  
        // ExampleMethodAsync returns a Task.  
        await ExampleMethodAsync();  
        textBox1.Text += "\r\nControl returned to Click event handler.\n";  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```

 Vous pouvez ajouter le même gestionnaire d'événements en utilisant une expression lambda asynchrone. Pour ajouter ce gestionnaire, ajoutez un modificateur `async` avant la liste des paramètres lambda, comme le montre l'exemple suivant.  
  
```csharp  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        button1.Click += async (sender, e) =>  
        {  
            // ExampleMethodAsync returns a Task.  
            await ExampleMethodAsync();  
            textBox1.Text += "\nControl returned to Click event handler.\n";  
        };  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```  

 Pour plus d’informations sur la création et l’utilisation des méthodes asyncrones, consultez [Programmation asynchrone avec async et await](../../../csharp/programming-guide/concepts/async/index.md).  
  
## <a name="lambdas-with-the-standard-query-operators"></a>Lambdas avec les opérateurs de requête standard  
 De nombreux opérateurs de requête standard comportent un paramètre d'entrée dont le type est l'un de la famille <xref:System.Func%602> de délégués génériques. Ces délégués utilisent des paramètres de type pour définir le nombre et les types de paramètres d'entrée, ainsi que le type de retour du délégué. Les délégués`Func` sont très utiles pour l'encapsulation des expressions définies par l'utilisateur appliquées à chaque élément dans un jeu de données sources. Considérons par exemple le type délégué suivant :  
  
```csharp  
public delegate TResult Func<TArg0, TResult>(TArg0 arg0)  
```  
  
 Ce délégué peut être instancié comme `Func<int,bool> myFunc` où `int` est un paramètre d'entrée et `bool` est la valeur de retour. La valeur de retour est toujours spécifiée dans le dernier paramètre de type. `Func<int, string, bool>` définit un délégué avec deux paramètres d'entrée, `int` et `string`et un type de retour de `bool`. Le délégué `Func` suivant, lorsqu'il est appelé, retourne la valeur true ou false pour indiquer si le paramètre d'entrée est égal à 5 :  
  
```csharp  
Func<int, bool> myFunc = x => x == 5;  
bool result = myFunc(4); // returns false of course  
```  
  
 Vous pouvez également fournir une expression lambda lorsque le type d'argument est `Expression<Func>`, par exemple dans les opérateurs de requête standard définis dans System.Linq.Queryable. Lorsque vous spécifiez un argument `Expression<Func>` , le lambda est compilé en une arborescence d'expression.  
  
 Opérateur de requête standard, la méthode <xref:System.Linq.Enumerable.Count%2A> , est illustré ici :  
  
```csharp  
int[] numbers = { 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };  
int oddNumbers = numbers.Count(n => n % 2 == 1);  
```  
  
 Le compilateur peut déduire le type du paramètre d'entrée, ou vous pouvez également le spécifier explicitement. Cette expression lambda particulière compte les entiers (`n`) qui, lorsqu'ils sont divisés par deux, ont un reste de 1.  
  
 La ligne de code suivante produit une séquence qui contient tous les éléments du tableau `numbers` qui apparaissent à gauche du « 9 », car c'est le premier nombre de la séquence qui ne satisfait pas la condition :  
  
```csharp  
var firstNumbersLessThan6 = numbers.TakeWhile(n => n < 6);  
```  
  
 Cet exemple indique comment spécifier plusieurs paramètres d'entrée en les mettant entre parenthèses. La méthode retourne tous les éléments du tableau de nombres, jusqu'à ce que soit rencontré un nombre dont la valeur est inférieure à cette position. Ne confondez pas l'opérateur lambda (`=>`) avec l'opérateur supérieur ou égal (`>=`).  
  
```csharp  
var firstSmallNumbers = numbers.TakeWhile((n, index) => n >= index);  
```  
  
## <a name="type-inference-in-lambdas"></a>Inférence de type dans les lambdas  
 Lorsque vous écrivez des lambdas, vous n'avez généralement pas à spécifier un type pour les paramètres d'entrée, car le compilateur peut déduire le type en fonction du corps du lambda, du type délégué du paramètre et d'autres facteurs décrits dans la spécification du langage C#. Pour la plupart des opérateurs de requête standard, la première entrée est le type des éléments dans la séquence source. Donc, si vous interrogez un `IEnumerable<Customer>`, il en est déduit que la variable d'entrée est un objet `Customer` , ce qui signifie que vous avez accès à ses méthodes et propriétés :  
  
```csharp  
customers.Where(c => c.City == "London");  
```  
  
 Les règles générales pour les lambdas sont les suivantes :  
  
-   Le lambda doit contenir le même nombre de paramètres que le type délégué.  
  
-   Chaque paramètre d'entrée dans le lambda doit être implicitement convertible en son paramètre de délégué correspondant.  
  
-   La valeur de retour du lambda (le cas échéant) doit être implicitement convertible en type de retour du délégué.  
  
 Notez que les expressions lambda en elles-mêmes n'ont pas de type, car le système de type commun (CTS, Common Type System) ne comporte aucun concept intrinsèque « d'expression lambda ». Toutefois, il est parfois commode de parler de manière informelle du « type » d'une expression lambda. Dans ce cas, le type fait référence au type délégué ou au type <xref:System.Linq.Expressions.Expression> dans lequel est convertie l'expression lambda.  
  
## <a name="variable-scope-in-lambda-expressions"></a>Portée variable dans les expressions lambda  
 Les expressions lambda peuvent faire référence à des *variables externes* (consultez [Méthodes anonymes](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)) qui se trouvent dans l’étendue de la méthode qui définit la fonction lambda, ou dans l’étendue du type qui contient l’expression lambda. Les variables capturées de cette manière sont stockées pour une utilisation dans l'expression lambda, même si les variables se trouvent en dehors de la portée et sont récupérées par le garbage collector. Une variable externe doit être assignée de manière précise pour pouvoir être utilisée dans une expression lambda. L'exemple suivant illustre ces règles :  
  
```csharp  
delegate bool D();  
delegate bool D2(int i);  
  
class Test  
{  
    D del;  
    D2 del2;  
    public void TestMethod(int input)  
    {  
        int j = 0;  
        // Initialize the delegates with lambda expressions.  
        // Note access to 2 outer variables.  
        // del will be invoked within this method.  
        del = () => { j = 10;  return j > input; };  
  
        // del2 will be invoked after TestMethod goes out of scope.  
        del2 = (x) => {return x == j; };  
  
        // Demonstrate value of j:  
        // Output: j = 0   
        // The delegate has not been invoked yet.  
        Console.WriteLine("j = {0}", j);        // Invoke the delegate.  
        bool boolResult = del();  
  
        // Output: j = 10 b = True  
        Console.WriteLine("j = {0}. b = {1}", j, boolResult);  
    }  
  
    static void Main()  
    {  
        Test test = new Test();  
        test.TestMethod(5);  
  
        // Prove that del2 still has a copy of  
        // local variable j from TestMethod.  
        bool result = test.del2(10);  
  
        // Output: True  
        Console.WriteLine(result);  
  
        Console.ReadKey();  
    }  
}  
```  
  
 Les règles suivantes s'appliquent à la portée des variables dans les expressions lambda :  
  
-   Une variable qui est capturée ne sera pas récupérée par le garbage collector avant que le délégué qui le référence soit disponible pour le garbage collection.  
  
-   Les variables introduites dans une expression lambda ne sont pas visibles dans la méthode externe.  
  
-   Une expression lambda ne peut pas capturer directement un paramètre `in`, `ref` ou `out` dans une méthode englobante.  
  
-   Une instruction return dans une expression lambda ne provoque pas le retour de la méthode englobante.  
  
-   Une expression lambda ne peut pas contenir une instruction `goto` , une instruction `break` , ou une instruction `continue` à l'intérieur de la fonction lambda si la cible de l'instruction de saut est hors du bloc. C'est également une erreur d'avoir une instruction de saut en dehors du bloc de la fonction lambda si la cible est à l'intérieur du bloc.  
  
## <a name="c-language-specification"></a>Spécification du langage C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapter"></a>Chapitre proposé  
 [Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Délégués, événements et expressions lambda) dans [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)  
  
## <a name="see-also"></a>Voir aussi

- [Guide de programmation C#](../../../csharp/programming-guide/index.md)  
- [LINQ (Language Integrated Query)](../../../csharp/programming-guide/concepts/linq/index.md)  
- [Méthodes anonymes](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
- [is](../../../csharp/language-reference/keywords/is.md)  
- [Arborescences d’expressions](../../../csharp/programming-guide/concepts/expression-trees/index.md)  
- [Exemples Visual Studio 2008 C# (voir les fichiers d’exemples de requêtes LINQ et le programme XQuery)](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)  
- [Expressions lambda récursives](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)
