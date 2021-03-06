---
title: 'Procédure : Demander des informations'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 9476144d84454aedc331214a55c77547697c378f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608412"
---
# <a name="how-to-query-for-information"></a>Procédure : Demander des informations
Les requêtes effectuées dans [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utilisent la même syntaxe que les requêtes effectuées dans [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. La seule différence est que les objets référencés dans [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requêtes sont mappés aux éléments d’une base de données. Pour plus d’informations, consultez [Introduction aux requêtes LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] traduit les requêtes que vous écrivez en requêtes SQL équivalentes et les envoie au serveur pour traitement.  
  
 Certaines fonctionnalités de requêtes [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] peuvent nécessiter une attention particulière dans les applications [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Pour plus d’informations, consultez [concepts relatifs aux requêtes](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).  
  
## <a name="example"></a>Exemple  
 La requête suivante demande une liste de clients de Londres. Dans cet exemple, `Customers` est une table de l'exemple de base de données Northwind.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Voir aussi
- [Création du modèle objet](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [Téléchargement d’exemples de base de données](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Interrogation de la base de données](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
