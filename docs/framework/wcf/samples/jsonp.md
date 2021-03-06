---
title: JSONP
ms.date: 03/30/2017
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
ms.openlocfilehash: 37da57a000376f972cd6da9e04be46ddec1b7144
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329659"
---
# <a name="jsonp"></a>JSONP
Cet exemple montre comment prendre en charge JSON with Padding (JSONP) dans les services WCF REST. JSONP est une convention servant à appeler des scripts entre domaines en générant des balises de script dans le document actif. Le résultat est retourné dans une fonction de rappel spécifiée. JSONP repose sur l’idée que les balises telles que `<script src="http://..." >` peuvent évaluer des scripts à partir de n’importe quel domaine et le script récupéré par ces balises est évalué dans une étendue dans laquelle d’autres fonctions peuvent déjà être définies.

## <a name="demonstrates"></a>Démonstrations
 Script entre domaines avec JSONP.

## <a name="discussion"></a>Discussion
 L'exemple inclut une page Web qui ajoute dynamiquement un bloc de script après que la page a été rendue dans le navigateur. Ce bloc de script appelle un service WCF REST qui a une seule opération, `GetCustomer`. Le service WCF REST retourne le nom et l'adresse d'un client encapsulés dans un nom de fonction de rappel. Lorsque le service WCF REST répond, la fonction de rappel de la page web est appelée avec les données client et la fonction de rappel affiche les données dans la page web. L'injection de la balise de script et l'exécution de la fonction de rappel sont gérées automatiquement par le contrôle ASP.NET AJAX ScriptManager. Le modèle d’utilisation est le même qu’avec tous les proxys ASP.NET AJAX, mais comprend une ligne supplémentaire pour activer JSONP, comme le montre le code suivant :

```csharp
var proxy = new JsonpAjaxService.CustomerService();
proxy.set_enableJsonp(true);
proxy.GetCustomer(onSuccess, onFail, null);
```

 La page web peut appeler le service WCF REST, car le service utilise le <xref:System.ServiceModel.Description.WebScriptEndpoint> avec `crossDomainScriptAccessEnabled` ayant la valeur `true`. Deux de ces configurations s’effectuent dans le fichier Web.config sous la \<system.serviceModel > élément.

```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

 ScriptManager gère l'interaction avec le service et cache la complexité de l'implémentation manuelle de l'accès JSONP. Lorsque `crossDomainScriptAccessEnabled` a la valeur `true` et le format de réponse pour une opération est JSON, l’infrastructure WCF inspecte l’URI de la demande pour un paramètre de chaîne de requête de rappel et encapsule la réponse JSON avec la valeur de la chaîne de requête de rappel paramètre. Dans l'exemple, la page Web appelle le service WCF REST avec l'URI suivant.

```
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0
```

 Étant donné que le paramètre de chaîne de requête de rappel a la valeur `JsonPCallback`, le service WCF retourne une réponse JSONP représentée dans l'exemple suivant.

```
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});
```

 Cette réponse JSONP inclut les données client mises au format JSON et encapsulées avec le nom de la fonction de rappel que la page web a demandée. ScriptManager exécute ce rappel à l'aide d'une balise de script pour effectuer la demande entre domaines, puis passe le résultat au gestionnaire onSuccess qui a été passé à l'opération GetCustomer du proxy ASP.NET AJAX.

 L’exemple se compose de deux applications web ASP.NET : un contient seulement un service WCF, et une autre la page Web .aspx, qui appelle le service. Lorsque vous exécutez la solution, Visual Studio 2012 hébergera les deux sites Web sur des ports différents, ce qui crée un environnement où le service et le client résident dans des domaines différents.

> [!IMPORTANT]
>  Les exemples peuvent déjà être installés sur votre ordinateur. Recherchez le répertoire (par défaut) suivant avant de continuer.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si ce répertoire n’existe pas, accédez à [Windows Communication Foundation (WCF) et des exemples de Windows Workflow Foundation (WF) pour .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) pour télécharger tous les Windows Communication Foundation (WCF) et [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemples. Cet exemple se trouve dans le répertoire suivant.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a>Pour exécuter l'exemple  
  
1. Ouvrez la solution de l'exemple JSONP.  
  
2. Appuyez sur F5 pour lancer `http://localhost:26648/JSONPClientPage.aspx` dans le navigateur.  
  
3. Notez qu’une fois la page chargée, les entrées de texte pour « Name » et « Address » sont remplies par les valeurs.  Ces valeurs ont été fournies à partir d’un appel au service WCF une fois que le navigateur a terminé le rendu de la page.
