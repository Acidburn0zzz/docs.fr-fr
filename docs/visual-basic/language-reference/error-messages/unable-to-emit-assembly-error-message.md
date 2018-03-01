---
title: "Impossible de créer l’assembly : &lt;message d’erreur&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b19b6439d85822c69adac0b3e0e04b2f31299836
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a>Impossible de créer l’assembly : &lt;message d’erreur&gt;
Le [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilateur appelle l’utilitaire Assembly Linker (Al.exe, également appelé Alink) pour générer un assembly avec un manifeste, et l’éditeur de liens signale une erreur lors de l’étape d’émission de création de l’assembly.  
  
 **ID d’erreur :** BC30145  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
1.  Examinez le message d’erreur entre guillemets et consultez la rubrique [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). Pour obtenir davantage d’explications et de conseils.  
  
2.  Essayez de signer l’assembly manuellement, soit à l’aide de la [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) ou le [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
3.  Si l'erreur persiste, rassemblez des informations sur ses circonstances et avertissez les services de support technique Microsoft.  
  
### <a name="to-sign-the-assembly-manually"></a>Pour signer manuellement l'assembly  
  
1.  Utilisez le [Sn.exe (outil Strong Name)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) pour créer un fichier de paire de clés publique/privée.  
  
     Ce fichier porte l’extension .snk.  
  
2.  Supprimez la référence COM qui génère l'erreur de votre projet.  
  
3.  À partir des fenêtres **Démarrer** menu, pointez sur **programmes**, pointez sur **Microsoft Visual Studio 2008**, pointez sur **Visual Studio Tools**, et puis cliquez sur **invite de commandes de Visual Studio 2008**.  
  
4.  Accédez au répertoire dans lequel vous voulez placer le wrapper d'assembly.  
  
5.  Tapez le code suivant.  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     Voici un exemple du code que vous pouvez entrer.  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     Utilisez des guillemets doubles (") si un chemin ou un fichier contient des espaces.  
  
6.  Dans [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], ajoutez une référence à un assembly .NET dans le fichier que vous venez de créer.  
  
## <a name="see-also"></a>Voir aussi  
 
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).  
 [Sn.exe (outil Strong Name)] [Sn.exe (outil Strong Name)](../../../framework/tools/sn-exe-strong-name-tool.md))  
 [Guide pratique pour créer une paire de clés publique/privée](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [Nous contacter](/visualstudio/ide/talk-to-us)
