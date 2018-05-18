---
title: Guide pratique pour lire des fichiers binaires en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- binary files [Visual Basic], reading from
- I/O [Visual Basic], reading from binary files
- ReadAllBytes method [Visual Basic], reading from binary files
- My.Computer.FileSystem object, reading from binary files
ms.assetid: d2b1269e-24b6-42e0-9414-ae708db282d8
ms.openlocfilehash: 979e70d21a3af6a7df1aed2886cdb308ee0faee7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-from-binary-files-in-visual-basic"></a>Guide pratique pour lire des fichiers binaires en Visual Basic
L’objet `My.Computer.FileSystem` fournit la méthode `ReadAllBytes` pour la lecture de fichiers binaires.  
  
### <a name="to-read-from-a-binary-file"></a>Pour lire un fichier binaire  
  
-   Utilisez la méthode `ReadAllBytes`, qui retourne le contenu d’un fichier en tant que tableau d’octets. Cet exemple lit le fichier `C:/Documents and Settings/selfportrait.jpg`.  
  
     [!code-vb[VbVbcnMyFileSystem#78](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_1.vb)]  
  
-   Pour les fichiers binaires volumineux, vous pouvez utiliser la méthode <xref:System.IO.FileStream.Read%2A> de l’objet <xref:System.IO.FileStream> pour lire le fichier bloc par bloc. Vous pouvez alors limiter la quantité de données du fichier chargées en mémoire pour chaque opération de lecture. L’exemple de code suivant copie un fichier et permet à l’appelant de spécifier la quantité de données lues en mémoire pour chaque opération de lecture.  
  
     [!code-vb[VbVbcnMyFileSystem#91](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-binary-files_2.vb)]  
  
## <a name="robust-programming"></a>Programmation fiable  
 Les conditions ci-dessous peuvent générer une exception :  
  
-   Le chemin d'accès n'est pas valide pour une des raisons suivantes : il s'agit d'une chaîne de longueur nulle ; il ne contient que des espaces blancs ; il contient des caractères non valides ou il s'agit d'un chemin d'accès de périphérique (<xref:System.ArgumentException>).  
  
-   Le chemin n’est pas valide, car il a la valeur `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Le fichier n'existe pas (<xref:System.IO.FileNotFoundException>).  
  
-   Le fichier est utilisé par un autre processus, ou une erreur E/S se produit (<xref:System.IO.IOException>).  
  
-   Le chemin dépasse la longueur maximale définie par le système (<xref:System.IO.PathTooLongException>).  
  
-   Un nom de fichier ou de répertoire du chemin d'accès contient un signe deux-points (:) ou n'a pas un format correct (<xref:System.NotSupportedException>).  
  
-   Il n'y a pas assez de mémoire pour écrire la chaîne dans la mémoire tampon (<xref:System.OutOfMemoryException>).  
  
-   L'utilisateur n'a pas les autorisations nécessaires pour afficher le chemin d'accès (<xref:System.Security.SecurityException>).  
  
 Ne vous basez pas sur le nom d'un fichier pour en déterminer le contenu. Par exemple, le fichier Form1.vb peut ne pas être un fichier source Visual Basic.  
  
 Vérifiez toutes les entrées avant d'utiliser les données dans votre application. Le fichier n'a peut-être pas le contenu attendu, et les méthodes utilisées pour lire le fichier peuvent échouer.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>  
 [Lecture à partir de fichiers](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [Guide pratique : lire des fichiers texte avec plusieurs formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)  
 [Stockage de données dans le Presse-papiers et lecture du Presse-papiers](../../../../visual-basic/developing-apps/programming/computer-resources/storing-data-to-and-reading-from-the-clipboard.md)
