---
title: Emprunt et restauration d'identité
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsIdentity objects, impersonating
- security [.NET Framework], impersonating Windows accounts
- impersonating Windows accounts
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3bc5b4a9bef51ac1591bdeb21651cee624d552b2
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44339368"
---
# <a name="impersonating-and-reverting"></a>Emprunt et restauration d'identité
Parfois, vous devez obtenir un jeton de compte Windows pour emprunter l’identité d’un compte Windows. Par exemple, votre application ASP.NET peut devoir agir pour le compte de plusieurs utilisateurs à des moments différents. Votre application peut accepter un jeton représentant un administrateur à partir d’Internet Information Services (IIS), emprunter l’identité de cet utilisateur, effectuer une opération et revenir à l’identité précédente. Ensuite, elle peut accepter un jeton d’IIS représentant un utilisateur disposant de droits inférieurs, effectuer une opération et revenir à nouveau à l’identité précédente.  
  
 Dans les situations où votre application doit emprunter l’identité d’un compte Windows qui n’a pas été attaché au thread actuel par IIS, vous devez extraire le jeton du compte et l’utiliser pour activer le compte. Pour cela, procédez comme suit :  
  
1.  Récupérez le jeton de compte pour un utilisateur particulier en appelant la méthode **LogonUser** non managée. Cette méthode ne figure pas dans la bibliothèque de classes de base du .NET Framework, mais dans le fichier **advapi32.dll** non managé. L’accès aux méthodes dans du code non managé est une opération complexe qui dépasse le cadre de cette discussion. Pour plus d’informations, consultez [Interopération avec du code non managé](../../../docs/framework/interop/index.md). Pour plus d’informations sur la méthode **LogonUser** et **advapi32.dll**, consultez la documentation du SDK de la plateforme.  
  
2.  Créez une nouvelle instance de la classe **WindowsIdentity**, qui passe le jeton. Le code suivant illustre cet appel, où `hToken` désigne un jeton Windows.  
  
    ```csharp  
    WindowsIdentity ImpersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim ImpersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3.  Commencez l’emprunt d’identité en créant une nouvelle instance de la <xref:System.Security.Principal.WindowsImpersonationContext> classe et en l’initialisant avec la <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> méthode de la classe initialisée, comme indiqué dans le code suivant.  
  
    ```csharp  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate()  
    ```  
  
4.  Lorsque vous n’avez plus besoin d’emprunter l’identité, appelez le <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> méthode pour rétablir l’emprunt d’identité, comme indiqué dans le code suivant.  
  
    ```csharp  
    MyImpersonation.Undo();  
    ```  
  
    ```vb  
    MyImpersonation.Undo()  
    ```  
  
 Si le code approuvé a déjà attaché un <xref:System.Security.Principal.WindowsPrincipal> de l’objet au thread, vous pouvez appeler la méthode d’instance **Impersonate**, qui n’accepte pas de jeton de compte. Notez que cela est utile uniquement lorsque l’objet **WindowsPrincipal** sur le thread représente un utilisateur autre que celui sous lequel le processus est exécuté. Par exemple, vous pouvez rencontrer cette situation quand vous utilisez ASP.NET avec l’authentification Windows activée et l’emprunt d’identité désactivé. Dans ce cas, le processus s’exécute sous un compte configuré dans Internet Information Services (IIS), tandis que le principal actuel représente l’utilisateur Windows qui accède à la page.  
  
 Notez que ni **Impersonate** ni **Annuler** modifications le **Principal** objet (<xref:System.Security.Principal.IPrincipal>) associé au contexte d’appel en cours. Au lieu de cela, l’emprunt d’identité et le rétablissement modifient le jeton associé au processus de système d’exploitation actuel.  
  
## <a name="see-also"></a>Voir aussi

- <xref:System.Security.Principal.WindowsIdentity>  
- <xref:System.Security.Principal.WindowsImpersonationContext>  
- [Objets Principal et Identity](../../../docs/standard/security/principal-and-identity-objects.md)  
- [Interopération avec du code non managé](../../../docs/framework/interop/index.md)
