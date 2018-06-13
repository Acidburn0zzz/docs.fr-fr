---
title: Téléchargement du package du Gestionnaire de jetons Web JSON
ms.date: 03/30/2017
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: 5a4846a5ec92324105f41b320d0d77f8749c28f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404675"
---
# <a name="downloading-the-json-web-token-handler-package"></a>Téléchargement du package du Gestionnaire de jetons Web JSON
Cette rubrique explique comment télécharger et utiliser le Gestionnaire de jetons Web JSON dans votre projet.  
  
## <a name="downloading-the-json-web-token-handler"></a>Téléchargement du Gestionnaire de jetons Web JSON  
 L’extension du Gestionnaire de jetons Web JSON est disponible sous forme de package NuGet, qui ajoute les assemblys et les références nécessaires à votre projet. Si vous n’avez pas encore installé NuGet, accédez à [nuget.org](http://nuget.org) pour l’installer. Vous pouvez voir l’historique de gestion de version de l’extension en accédant à sa page sur NuGet : [Gestionnaire de jetons Web JSON sur NuGet](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-gui"></a>Téléchargement du Gestionnaire de jetons Web JSON à l’aide de l’interface graphique utilisateur du Gestionnaire de package  
  
1.  Dans Visual Studio, cliquez sur votre projet dans l’**Explorateur de solutions**, puis sélectionnez **Gérer les packages NuGet**.  
  
2.  Dans la fenêtre **Gérer les packages NuGet**, cliquez sur la zone de recherche et tapez `JWT Token Handler`, puis appuyez sur **Entrée**.  
  
3.  Dans le volet de résultats, cliquez sur le bouton **Installer** pour le premier résultat.  
  
4.  Le téléchargement du package commence. Avant l’ajout du package à votre projet, la boîte de dialogue d’acceptation de licence s’affiche. Si vous êtes d’accord avec les termes du contrat de licence, cliquez sur **Accepter**.  
  
5.  Les assemblys du Gestionnaire de jetons Web JSON les plus récents seront téléchargés et ajoutés à votre projet.  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-console"></a>Téléchargement du Gestionnaire de jetons Web JSON à l’aide de la console du Gestionnaire de package  
  
1.  Dans Visual Studio, cliquez sur **Outils**, **Gestionnaire de package de bibliothèque**, puis **Console du Gestionnaire de package**.  
  
2.  La **Console du Gestionnaire de package** s’affiche. Tapez le texte suivant et appuyez sur **Entrée** :  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  Les assemblys du Gestionnaire de jetons Web JSON les plus récents seront téléchargés et ajoutés à votre projet.
