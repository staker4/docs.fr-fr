---
title: 'Procédure : Rechercher un élément enfant (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: adb46c98-a650-42e2-b62d-835920fe8421
ms.openlocfilehash: 8472a3d9e90aa117c936c4314204f70d2ab33487
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495810"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-visual-basic"></a>Procédure : Rechercher un élément enfant (XPath-LINQ to XML) (Visual Basic)
Cette rubrique compare l’axe des éléments enfants XPath à la méthode <xref:System.Xml.Linq.XContainer.Element%2A> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 L'expression XPath est `DeliveryNotes`.  
  
## <a name="example"></a>Exemple  
 Cet exemple recherche l'élément enfant `DeliveryNotes`.  
  
 Cet exemple utilise le document XML suivant : [Exemple de fichier XML : Plusieurs commandes fournisseur (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```vb  
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")  
Dim po As XElement = cpo.Root.<PurchaseOrder>.FirstOrDefault  
  
'LINQ to XML query  
Dim el1 As XElement = po.<DeliveryNotes>.FirstOrDefault  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("DeliveryNotes")  
' same as "child::DeliveryNotes"  
' same as "./DeliveryNotes"  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
```  
  
 Cet exemple génère la sortie suivante :  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="see-also"></a>Voir aussi
- [LINQ to XML pour les utilisateurs de XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
