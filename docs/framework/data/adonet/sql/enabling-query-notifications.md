---
title: Activation de notifications de requête
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: be9cae6f702b72306875246e874b99e7c79eb113
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743034"
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="68d6e-102">Activation de notifications de requête</span><span class="sxs-lookup"><span data-stu-id="68d6e-102">Enabling Query Notifications</span></span>
<span data-ttu-id="68d6e-103">Les applications qui utilisent des notifications de requête ont un ensemble commun d’exigences.</span><span class="sxs-lookup"><span data-stu-id="68d6e-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="68d6e-104">Votre source de données doit être correctement configurée pour prendre en charge les notifications de requête SQL et l'utilisateur doit disposer des autorisations appropriées côté client et côté serveur.</span><span class="sxs-lookup"><span data-stu-id="68d6e-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="68d6e-105">Pour utiliser des notifications de requête, vous devez :</span><span class="sxs-lookup"><span data-stu-id="68d6e-105">To use query notifications you must:</span></span>  
  
-   <span data-ttu-id="68d6e-106">Activer les notifications de requête pour votre base de données.</span><span class="sxs-lookup"><span data-stu-id="68d6e-106">Enable query notifications for your database.</span></span>  
  
-   <span data-ttu-id="68d6e-107">Veiller à ce que l'ID utilisateur utilisé pour se connecter à la base de données dispose des autorisations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="68d6e-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
-   <span data-ttu-id="68d6e-108">Utiliser un objet <xref:System.Data.SqlClient.SqlCommand> pour exécuter une instruction SELECT valide avec un objet notification associé — <xref:System.Data.SqlClient.SqlDependency> ou <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="68d6e-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
-   <span data-ttu-id="68d6e-109">Fournir le code permettant de traiter la notification en cas de modification des données surveillées.</span><span class="sxs-lookup"><span data-stu-id="68d6e-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="68d6e-110">Spécifications des notifications de requête</span><span class="sxs-lookup"><span data-stu-id="68d6e-110">Query Notifications Requirements</span></span>  
 <span data-ttu-id="68d6e-111">Les notifications de requête ne sont prises en charge que pour les instructions SELECT qui répondent à une liste de spécifications précises.</span><span class="sxs-lookup"><span data-stu-id="68d6e-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="68d6e-112">Le tableau suivant présente des liens vers la documentation consacrée à Service Broker et aux notifications de requête dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="68d6e-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="68d6e-113">**Documentation en ligne de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="68d6e-113">**SQL Server Books Online**</span></span>  
  
-   [<span data-ttu-id="68d6e-114">Création d’une requête pour Notification</span><span class="sxs-lookup"><span data-stu-id="68d6e-114">Creating a Query for Notification</span></span>](https://msdn.microsoft.com/library/ms181122.aspx)  
  
-   [<span data-ttu-id="68d6e-115">Considérations de sécurité pour Service Broker</span><span class="sxs-lookup"><span data-stu-id="68d6e-115">Security Considerations for Service Broker</span></span>](https://msdn.microsoft.com/library/ms166059.aspx)  
  
-   [<span data-ttu-id="68d6e-116">Sécurité et Protection (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="68d6e-116">Security and Protection (Service Broker)</span></span>](https://msdn.microsoft.com/library/bb522911.aspx)  
  
-   [<span data-ttu-id="68d6e-117">Considérations de sécurité pour les Services de Notifications</span><span class="sxs-lookup"><span data-stu-id="68d6e-117">Security Considerations for Notifications Services</span></span>](https://msdn.microsoft.com/library/ms172604.aspx)  
  
-   [<span data-ttu-id="68d6e-118">Autorisations de Notification de requête</span><span class="sxs-lookup"><span data-stu-id="68d6e-118">Query Notification Permissions</span></span>](https://msdn.microsoft.com/library/ms188311.aspx)  
  
-   [<span data-ttu-id="68d6e-119">Observations à caractère internationales pour Service Broker</span><span class="sxs-lookup"><span data-stu-id="68d6e-119">International Considerations for Service Broker</span></span>](https://msdn.microsoft.com/library/ms166028.aspx)  
  
-   [<span data-ttu-id="68d6e-120">Considérations de conception de solution (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="68d6e-120">Solution Design Considerations (Service Broker)</span></span>](https://msdn.microsoft.com/library/bb522899.aspx)  
  
-   [<span data-ttu-id="68d6e-121">Centre d’informations du développeur Service Broker</span><span class="sxs-lookup"><span data-stu-id="68d6e-121">Service Broker Developer InfoCenter</span></span>](https://msdn.microsoft.com/library/ms166100.aspx)  
  
-   [<span data-ttu-id="68d6e-122">Guide du développeur (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="68d6e-122">Developer's Guide (Service Broker)</span></span>](https://msdn.microsoft.com/library/bb522908.aspx)  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="68d6e-123">Activation des notifications de requête pour exécuter l'exemple de code</span><span class="sxs-lookup"><span data-stu-id="68d6e-123">Enabling Query Notifications to Run Sample Code</span></span>  
 <span data-ttu-id="68d6e-124">Pour activer Service Broker sur le **AdventureWorks** de base de données à l’aide de SQL Server Management Studio, exécutez l’instruction Transact-SQL suivante :</span><span class="sxs-lookup"><span data-stu-id="68d6e-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="68d6e-125">Pour que les exemples de notification de requête s'exécutent correctement, les instructions Transact-SQL suivantes doivent être exécutées sur le serveur de base de données.</span><span class="sxs-lookup"><span data-stu-id="68d6e-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```  
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="68d6e-126">Autorisations de notifications de requête</span><span class="sxs-lookup"><span data-stu-id="68d6e-126">Query Notifications Permissions</span></span>  
 <span data-ttu-id="68d6e-127">Les utilisateurs qui exécutent des commandes nécessitant une notification doivent disposer d'une autorisation de base de données SUBSCRIBE QUERY NOTIFICATIONS sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="68d6e-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="68d6e-128">Le code côté client exécuté dans une situation de confiance partielle requiert le <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="68d6e-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="68d6e-129">Le code suivant crée un objet <xref:System.Data.SqlClient.SqlClientPermission> en affectant la valeur <xref:System.Security.Permissions.PermissionState> à l'objet <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span><span class="sxs-lookup"><span data-stu-id="68d6e-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="68d6e-130">La méthode <xref:System.Security.CodeAccessPermission.Demand%2A> forcera un objet <xref:System.Security.SecurityException> au moment de l'exécution si l'autorisation n'a été accordée à aucun des appelants figurant plus haut dans la pile des appels.</span><span class="sxs-lookup"><span data-stu-id="68d6e-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="68d6e-131">Sélection d'un objet notification</span><span class="sxs-lookup"><span data-stu-id="68d6e-131">Choosing a Notification Object</span></span>  
 <span data-ttu-id="68d6e-132">L'API des notifications de requête fournit deux objets pour traiter les notifications :<xref:System.Data.SqlClient.SqlDependency> et <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="68d6e-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="68d6e-133">En règle générale, la plupart des applications non ASP.NET doivent utiliser l'objet <xref:System.Data.SqlClient.SqlDependency>.</span><span class="sxs-lookup"><span data-stu-id="68d6e-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="68d6e-134">Les applications ASP.NET doivent utiliser le <xref:System.Web.Caching.SqlCacheDependency> de niveau supérieur, qui enveloppe <xref:System.Data.SqlClient.SqlDependency> et fournit un cadre pour l'administration des objets notification et cache.</span><span class="sxs-lookup"><span data-stu-id="68d6e-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="68d6e-135">Utilisation de SqlDependency</span><span class="sxs-lookup"><span data-stu-id="68d6e-135">Using SqlDependency</span></span>  
 <span data-ttu-id="68d6e-136">Pour utiliser <xref:System.Data.SqlClient.SqlDependency>, Service Broker doit être activé pour la base de données SQL Server utilisée et les utilisateurs doivent disposer des autorisations nécessaires pour recevoir des notifications.</span><span class="sxs-lookup"><span data-stu-id="68d6e-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="68d6e-137">Les objets Service Broker, tels que la file d'attente des notifications, sont prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="68d6e-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="68d6e-138">De plus, l'objet <xref:System.Data.SqlClient.SqlDependency> lance automatiquement un thread de travail pour traiter les notifications à mesure qu'elles sont publiées dans la file d'attente ; il analyse également le message de Service Broker, en exposant les informations comme données d'argument d'événement.</span><span class="sxs-lookup"><span data-stu-id="68d6e-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="68d6e-139">L'objet <xref:System.Data.SqlClient.SqlDependency> doit être initialisé par l'appel à la méthode `Start` afin d'établir une dépendance par rapport à la base de données.</span><span class="sxs-lookup"><span data-stu-id="68d6e-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="68d6e-140">Il s'agit d'une méthode statique qui doit être appelée une fois durant l'initialisation de l'application pour chaque connexion requise à la base de données.</span><span class="sxs-lookup"><span data-stu-id="68d6e-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="68d6e-141">La méthode `Stop` doit être appelée à la fin de l'application pour chaque connexion de dépendance établie.</span><span class="sxs-lookup"><span data-stu-id="68d6e-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="68d6e-142">Utilisation de SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="68d6e-142">Using SqlNotificationRequest</span></span>  
 <span data-ttu-id="68d6e-143">En revanche, <xref:System.Data.Sql.SqlNotificationRequest> requiert que vous implémentiez vous-même l'infrastructure d'écoute complète.</span><span class="sxs-lookup"><span data-stu-id="68d6e-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="68d6e-144">En outre, tous les objets Service Broker tels que la file d'attente, le service et les types de message pris en charge par la file d'attente doivent être définis.</span><span class="sxs-lookup"><span data-stu-id="68d6e-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="68d6e-145">Cette approche manuelle est utile si votre application requiert des messages ou des comportements de notification spéciaux, ou si votre application fait partie d'une application Service Broker plus large.</span><span class="sxs-lookup"><span data-stu-id="68d6e-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d6e-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68d6e-146">See also</span></span>
- [<span data-ttu-id="68d6e-147">Notifications de requête dans SQL Server</span><span class="sxs-lookup"><span data-stu-id="68d6e-147">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [<span data-ttu-id="68d6e-148">Fournisseurs managés ADO.NET et centre de développement DataSet</span><span class="sxs-lookup"><span data-stu-id="68d6e-148">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
