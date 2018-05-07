---
title: Prise en charge des transactions
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: ff4d65c37e2d7f76c8c9f0de1de9717c8dca7b27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="transaction-support"></a>Prise en charge des transactions
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] prend en charge trois modèles de transaction distincts. Ces modèles sont présentés ci-dessous dans l'ordre d'exécution des contrôles.  
  
## <a name="explicit-local-transaction"></a>Transaction locale explicite  
 Lorsque vous appelez <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, si la propriété <xref:System.Data.Linq.DataContext.Transaction%2A> a pour valeur une transaction (`IDbTransaction`), l'appel de <xref:System.Data.Linq.DataContext.SubmitChanges%2A> est effectué dans le contexte de la même transaction.  
  
 Il vous appartient de valider ou de restaurer la transaction une fois qu'elle s'est correctement exécutée. La connexion qui correspond à la transaction doit être identique à celle utilisée pour construire le <xref:System.Data.Linq.DataContext>. L'utilisation d'une autre connexion lève une exception.  
  
## <a name="explicit-distributable-transaction"></a>Transaction distribuable explicite  
 Vous pouvez appeler [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API (y compris mais non limité à <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) dans la portée d’un actif <xref:System.Transactions.Transaction>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] détecte que l’appel est dans l’étendue d’une transaction et qu’il ne crée pas une nouvelle transaction. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] évite également dans ce cas la fermeture de la connexion. Vous pouvez effectuer une requête et exécuter <xref:System.Data.Linq.DataContext.SubmitChanges%2A> dans le contexte de ce type de transaction.  
  
## <a name="implicit-transaction"></a>Transaction implicite  
 Lorsque vous appelez <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vérifie si l’appel est dans la portée d’un <xref:System.Transactions.Transaction> ou si le `Transaction` propriété (`IDbTransaction`) est définie sur une transaction locale démarrée par l’utilisateur. Si elle ne détecte aucune transaction, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] démarre une transaction locale (`IDbTransaction`) et l’utilise pour exécuter les commandes SQL générées. Lorsque toutes les commandes SQL ont été exécutées avec succès, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] valide la transaction locale et le retourne.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations générales](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [Guide pratique pour mettre entre parenthèses des soumissions de données à l’aide de transactions](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)
