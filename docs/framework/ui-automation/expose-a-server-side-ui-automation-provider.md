---
title: Exposer un fournisseur UI Automation côté serveur
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- expose a server-side UI Automation provider
- UI Automation, server-side provider, exposing
- server-side UI Automation provider, exposing
ms.assetid: 55d419c0-2201-4101-90c9-2888df4dbb47
ms.openlocfilehash: 61515c4c87638d7e2bde63f0ca9faac58128f2e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225025"
---
# <a name="expose-a-server-side-ui-automation-provider"></a>Exposer un fournisseur UI Automation côté serveur
> [!NOTE]
>  Cette documentation s'adresse aux développeurs .NET Framework qui souhaitent utiliser les classes [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] managées définies dans l'espace de noms <xref:System.Windows.Automation>. Pour plus d’informations sur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consultez [Windows Automation API : UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Cette rubrique contient un exemple de code qui montre comment exposer un fournisseur UI Automation côté serveur, qui est hébergé dans une fenêtre <xref:System.Windows.Forms.Control?displayProperty=nameWithType> .  
  
 Cet exemple substitue la procédure de fenêtre pour intercepter WM_GETOBJECT, qui est le message envoyé par le service principal [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] lorsqu’une application cliente demande des informations sur la fenêtre.  
  
## <a name="example"></a>Exemple  
 [!code-csharp[UIAFragmentProvider_snip#116](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#116)]
 [!code-vb[UIAFragmentProvider_snip#116](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#116)]  
  
## <a name="see-also"></a>Voir aussi

- [Vue d'ensemble des fournisseurs UI Automation](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [Implémentation de fournisseur UI Automation côté serveur](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
