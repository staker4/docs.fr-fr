---
title: 'Procédure : inscrire un protocole personnalisé à l’aide de WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: d2056bee6c8847989556799511dfaea326dcdac1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669040"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a>Procédure : inscrire un protocole personnalisé à l’aide de WebRequest
Cet exemple montre comment inscrire une classe spécifique à un protocole qui est définie ailleurs dans du code. Dans cet exemple, `CustomWebRequestCreator` est l’objet implémenté par l’utilisateur qui implémente la méthode **Create** utilisée pour retourner l’objet `CustomWebRequest`. L’exemple de code suppose que vous avez écrit le code `CustomWebRequest` qui implémente le protocole personnalisé.  
  
## <a name="example"></a>Exemple  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Cet exemple nécessite :  
  
 Références à l’espace de noms <xref:System.Net>.  
  
## <a name="see-also"></a>Voir aussi
- [Programmation de protocoles enfichables](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
