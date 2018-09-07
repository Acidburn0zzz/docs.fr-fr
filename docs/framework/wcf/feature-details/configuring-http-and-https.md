---
title: Configuration de HTTP et HTTPS
ms.date: 03/30/2017
helpviewer_keywords:
- configuring HTTP [WCF]
ms.assetid: b0c29a86-bc0c-41b3-bc1e-4eb5bb5714d4
ms.openlocfilehash: 36dbf725dfcd6fefe6482f7de69daea9356d3d07
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087697"
---
# <a name="configuring-http-and-https"></a>Configuration de HTTP et HTTPS
Les services et les clients WCF peuvent communiquer sur HTTP et HTTPS. Les paramètres HTTP/HTTPS sont configurés à l'aide d'IIS (Internet Information Services) ou d'un outil de ligne de commande. Lorsqu'un service WCF est hébergé sous IIS, des paramètres HTTP ou HTTPS peuvent être configurés dans IIS (avec l'outil inetmgr.exe). Si un service WCF est auto-hébergé, les paramètres HTTP ou HTTPS sont configurés à l'aide d'un outil de ligne de commande.  
  
 Au minimum, vous pouvez configurer une inscription d'URL, puis ajouter une exception de pare-feu pour l'URL que votre service utilisera.  
  
 L'outil utilisé pour configurer les paramètres HTTP dépend du système d'exploitation exécuté sur l'ordinateur.  
  
 Lors de l’exécution [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] ou [!INCLUDE[wxp](../../../../includes/wxp-md.md)], utilisez l’outil HttpCfg.exe. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] installe automatiquement cet outil. Lors de l’exécution [!INCLUDE[wxp](../../../../includes/wxp-md.md)], vous pouvez télécharger l’outil sur [outils de Support de Windows XP Service Pack 2](https://go.microsoft.com/fwlink/?LinkId=88606). Pour plus d’informations, consultez [vue d’ensemble de Httpcfg](https://go.microsoft.com/fwlink/?LinkId=88605).  
  
 Lors de l’exécution [!INCLUDE[wv](../../../../includes/wv-md.md)] ou Windows 7, vous configurez ces paramètres avec l’outil Netsh.exe.  
  
## <a name="configuring-namespace-reservations"></a>Configuration de réservations d'espace de noms  
 La réservation d'espace de noms assigne les droits d'une partie de l'espace de noms de l'URL HTTP à un groupe d'utilisateurs particulier. Une réservation leur donne le droit de créer des services qui écoutent sur cette partie de l'espace de noms. Les réservations sont des préfixes d'URL, autrement dit, la réservation couvre tous les sous-chemins d'accès du chemin d'accès de la réservation. Les réservations d'espace de noms autorisent deux façons d'utiliser des caractères génériques. La documentation de l’API du serveur HTTP décrit le [ordre de résolution entre les revendications d’espace de noms qui impliquent des caractères génériques](https://go.microsoft.com/fwlink/?LinkId=94841).  
  
 Une application exécutée peut créer une demande similaire pour ajouter des inscriptions d'espace de noms. Les inscriptions et les réservations rivalisent pour les parties de l'espace de noms. Une réservation peut avoir la priorité sur une inscription selon l’ordre indiqué dans le [ordre de résolution entre les revendications d’espace de noms qui impliquent des caractères génériques](https://go.microsoft.com/fwlink/?LinkId=94841). Dans ce cas, la réservation empêche à l'application courante de recevoir des demandes.  
  
### <a name="running-windows-xp-or-server-2003"></a>Exécution de Windows XP ou Server 2003  
 Utilisez le `httpcfg.exe set urlacl` commande pour modifier des réservations d’espace de noms. Le [documentation sur les outils de prise en charge de Windows](https://go.microsoft.com/fwlink/?LinkId=94840) explique la syntaxe de l’outil Httpcfg.exe. La modification des droits de réservation pour une partie de l'espace de noms requiert des privilèges d'administrateur ou la propriété de cette partie de l'espace de noms. Initialement, la totalité de l'espace de noms HTTP appartient à l'administrateur local.  
  
 Les éléments suivants affichent la syntaxe de la commande Httpcfg avec l'option `set urlacl`  
  
```  
httpcfg set urlacl /u {http://URL:Port/ | https://URL:Port/} /aACL  
```  
  
 Le paramètre `/u` est requis lorsqu'on utilise `set urlacl`. Il prend une chaîne qui contient une URL qualifiée complète servant de clé d'enregistrement pour la réservation effectuée.  
  
 Le paramètre `/a` est également requis en cas d'utilisation de `set urlacl`. Il prend une chaîne qui contient une liste de contrôle d'accès (ACL) sous la forme d'une chaîne SDDL (Security Descriptor Definition Language).  
  
 Le code ci-après indique comment utiliser cette commande.  
  
```  
httpcfg.exe set urlacl /u http://myhost:8000/ /a "O:AOG:DAD:(A;;RPWPCCDCLCSWRCWDWOGA;;;S-1-0-0)"  
```  
  
### <a name="running-windows-vista-windows-server-2008-r2-or-windows-7"></a>Exécution de Windows Vista, Windows Server 2008 R2 ou Windows 7  
 Si votre système d'exploitation est [!INCLUDE[wv](../../../../includes/wv-md.md)], Windows Server 2008 R2 ou Windows 7, utilisez l'outil Netsh.exe. Le code ci-après indique comment utiliser cette commande.  
  
```  
netsh http add urlacl url=http://+:80/MyUri user=DOMAIN\user  
```  
  
 Cette commande ajoute une réservation d'URL pour l'espace de nom d'URL spécifié pour le compte DOMAIN/utilisateur.  Pour plus d’informations sur l’utilisation de la commande netsh, entrez « netsh http add urlacl » dans une invite de commandes, appuyez sur entrer.  
  
## <a name="configuring-a-firewall-exception"></a>Configuration d'une exception de pare-feu  
 Lors de l'auto-hébergement d'un service WCF qui communique sur HTTP, une exception doit être ajoutée à la configuration du pare-feu pour autoriser les connexions entrantes à l'aide d'une URL particulière. Pour plus d’informations, consultez [ouvrir un port dans le pare-feu Windows (Windows 7)](https://go.microsoft.com/fwlink/?LinkId=239961)  
  
## <a name="configuring-ssl-certificates"></a>Configuration de certificats SSL  
 Le protocole SSL (Secure Sockets Layer) utilise des certificats sur le client et le serveur pour stocker les clés de chiffrement. Le serveur fournit son certificat SSL à l'établissement d'une connexion afin que le client puisse vérifier son identité. Le serveur peut également demander un certificat au client pour permettre une authentification mutuelle des deux sens de connexion.  
  
 Les certificats sont stockés dans un magasin centralisé en fonction de l'adresse IP et du numéro de port de la connexion. L'adresse IP 0.0.0.0 spéciale correspond à l'adresse IP de l'ordinateur local. Notez que le magasin de certificats ne distingue pas l'URL en fonction du chemin d'accès. Les services ayant la même combinaison d’adresse IP et de port doivent partager les mêmes certificats même si le chemin d’accès des services dans l’URL est différent.  
  
 Pour obtenir des instructions détaillées, consultez [Comment : configurer un Port avec un certificat SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
## <a name="configuring-the-ip-listen-list"></a>Configuration de la liste d'écoutes IP  
 L'API du serveur HTTP crée une liaison uniquement avec une adresse IP et un port lorsqu'un utilisateur inscrit une URL. Par défaut, l'API du serveur HTTP crée une liaison avec le port dans l'URL pour toutes les adresses IP de l'ordinateur. Un conflit survient si une application qui n'utilise pas l'API du serveur HTTP a créé précédemment une liaison avec cette combinaison d'adresse IP et de port. La liste d’écoutes IP permet aux services WCF de coexister avec les applications qui utilisent un port pour certaines des adresses IP de l’ordinateur. Si la liste d'écoutes IP contient une entrée, l'API du serveur HTTP crée seulement une liaison avec les adresses IP spécifiées dans la liste. La modification de la liste d'écoutes IP requiert des privilèges d'administrateur.  
  
### <a name="running-windows-xp-or-server-2003"></a>Exécution de Windows XP ou Server 2003  
 Utilisez l'outil httpcfg pour modifier la liste d'écoute IP, comme illustré dans l'exemple suivant. Le [documentation sur les outils de prise en charge de Windows](https://go.microsoft.com/fwlink/?LinkId=94840) explique la syntaxe de l’outil httpcfg.exe.  
  
```  
httpcfg.exe set iplisten -i 0.0.0.0:8000  
```  
  
### <a name="running-windows-vista-or-windows-7"></a>Exécution de Windows Vista ou Windows 7  
 Utilisez l'outil netsh pour modifier la liste d'écoute IP, comme illustré dans l'exemple suivant.  
  
```  
netsh http add iplisten ipaddress=0.0.0.0:8000  
```  
  
## <a name="other-configuration-settings"></a>Autres paramètres de configuration  
 Lors de l'utilisation de <xref:System.ServiceModel.WSDualHttpBinding>, la connexion cliente utilise des valeurs par défaut qui sont compatibles avec les réservations d'espace de noms et le pare-feu de Windows. Si vous choisissez de personnaliser l'adresse cliente de base d'une connexion double, vous devez également configurer ces paramètres HTTP sur le client pour qu'ils correspondent à la nouvelle adresse.  
  
 L'API du serveur HTTP inclut un certain nombre de paramètres de configuration avancés qui ne sont pas disponibles via HttpCfg. Ces paramètres sont maintenus dans le registre et s'appliquent à toutes les applications exécutées sur les systèmes utilisant les API de serveur HTTP. Pour plus d’informations sur ces paramètres, consultez [les paramètres de Registre Http.sys pour IIS](https://go.microsoft.com/fwlink/?LinkId=94843). La plupart des utilisateurs n'ont pas besoin de modifier ces paramètres.  
  
## <a name="issues-specific-to-windows-xp"></a>Problèmes spécifiques à Windows XP  
 IIS ne prend pas en charge le partage de ports sur [!INCLUDE[wxp](../../../../includes/wxp-md.md)]. Si IIS est en cours d’exécution et un service WCF tente d’utiliser un espace de noms avec le même port, le service WCF ne parvient pas à démarrer. IIS et WCF par défaut la valeur à l’aide du port 80. Modifier l’affectation de port pour un des services ou la liste d’écoutes IP permet d’affecter le service WCF à une carte réseau non utilisée par IIS. IIS 6.0 et ses versions ultérieures ont été redessinés pour utiliser les API du serveur HTTP.  
  
## <a name="see-also"></a>Voir aussi  
 <xref:System.ServiceModel.WSDualHttpBinding>  
 [Guide pratique pour configurer un port avec un certificat SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
