---
title: FTP
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e491754b1c6c96e6afa9b172200cfb564307a8a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395071"
---
# <a name="ftp"></a><span data-ttu-id="f8f50-102">FTP</span><span class="sxs-lookup"><span data-stu-id="f8f50-102">FTP</span></span>
<span data-ttu-id="f8f50-103">Le.NET Framework fournit une prise en charge complète du protocole FTP avec les classes <xref:System.Net.FtpWebRequest> et <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="f8f50-103">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="f8f50-104">Ces classes sont dérivées de <xref:System.Net.WebRequest> et <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="f8f50-104">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="f8f50-105">Dans la plupart des cas, les classes <xref:System.Net.WebRequest> et <xref:System.Net.WebResponse> fournissent tout ce qui est nécessaire pour effectuer la demande mais, si vous avez besoin d’un accès aux fonctionnalités spécifiques à FTP exposées comme propriétés, vous pouvez convertir ces classes en <xref:System.Net.FtpWebRequest> ou <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="f8f50-105">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="f8f50-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="f8f50-106">Examples</span></span>  
 <span data-ttu-id="f8f50-107">Pour plus d’informations, consultez les rubriques suivantes : [Guide pratique pour télécharger des fichiers avec FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [Guide pratique pour charger des fichiers avec FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md) et [Guide pratique pour répertorier le contenu d’un répertoire avec FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).</span><span class="sxs-lookup"><span data-stu-id="f8f50-107">For more information, see the following topics: [How to: Download Files with FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).</span></span>  
  
## <a name="ftp-and-proxies"></a><span data-ttu-id="f8f50-108">FTP et proxies</span><span class="sxs-lookup"><span data-stu-id="f8f50-108">FTP and proxies</span></span>  
 <span data-ttu-id="f8f50-109">Si un proxy (spécifié par la propriété <xref:System.Net.FtpWebRequest.Proxy%2A>) est un proxy HTTP, seules les commandes <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> et <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="f8f50-109">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f50-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8f50-110">See Also</span></span>  
 [<span data-ttu-id="f8f50-111">Accès à Internet via un proxy</span><span class="sxs-lookup"><span data-stu-id="f8f50-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="f8f50-112">Exemples de programmation réseau</span><span class="sxs-lookup"><span data-stu-id="f8f50-112">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 [<span data-ttu-id="f8f50-113">Exemple de technologie cliente FTP</span><span class="sxs-lookup"><span data-stu-id="f8f50-113">FTP Client Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179557)  
 [<span data-ttu-id="f8f50-114">Exemple de technologie de l’explorateur FTP</span><span class="sxs-lookup"><span data-stu-id="f8f50-114">FTP Explorer Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179569)  
 [<span data-ttu-id="f8f50-115">Utilisation de protocoles d’application</span><span class="sxs-lookup"><span data-stu-id="f8f50-115">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
