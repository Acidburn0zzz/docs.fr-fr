---
title: "Comment : modifier la valeur d'un paramètre entre des sessions d'application"
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 383f72f223fb92170d16a9538c94e67825009abb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523408"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="0677c-102">Comment : modifier la valeur d'un paramètre entre des sessions d'application</span><span class="sxs-lookup"><span data-stu-id="0677c-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="0677c-103">Dans certains cas, vous pouvez modifier la valeur d’un paramètre entre des sessions d’application une fois que l’application a été compilée et déployée.</span><span class="sxs-lookup"><span data-stu-id="0677c-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="0677c-104">Par exemple, vous pouvez modifier une chaîne de connexion pour pointer vers l’emplacement de la base de données correcte.</span><span class="sxs-lookup"><span data-stu-id="0677c-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="0677c-105">Étant donné que les outils de conception ne sont pas disponibles une fois que l’application a été compilée et déployée, vous devez modifier la valeur du paramètre manuellement dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="0677c-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="0677c-106">Pour modifier la valeur d’un paramètre entre des Sessions d’Application</span><span class="sxs-lookup"><span data-stu-id="0677c-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1.  <span data-ttu-id="0677c-107">À l’aide de Microsoft Notepad ou un autre texte ou éditeur XML, ouvrez le fichier .config associé à votre application.</span><span class="sxs-lookup"><span data-stu-id="0677c-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2.  <span data-ttu-id="0677c-108">Recherchez l’entrée pour le paramètre que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="0677c-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="0677c-109">Il doit ressembler à l’exemple présenté ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="0677c-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  <span data-ttu-id="0677c-110">Tapez une nouvelle valeur pour votre paramètre et enregistrez le fichier.</span><span class="sxs-lookup"><span data-stu-id="0677c-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0677c-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0677c-111">See Also</span></span>  
 [<span data-ttu-id="0677c-112">Utilisation de paramètres d'application et de paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="0677c-112">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="0677c-113">Vue d'ensemble des paramètres d'application</span><span class="sxs-lookup"><span data-stu-id="0677c-113">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
