---
title: "'<membername>' ne peut pas exposer le type '<typename>' en dehors du projet via <containertype> '<containertypename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 03767501488a395073f925e27adea439751c0de6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265062"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a>'\<nom_membre >' ne peut pas exposer le type '\<nom_type >' en dehors du projet via \<containertype > '\<containertypename >'
Une variable, un paramètre de procédure ou un retour de fonction est exposé en dehors de son conteneur, mais il est déclaré comme un type qui ne doit pas être exposé en dehors du conteneur.  
  
 Le code squelette suivant montre une situation qui génère cette erreur.  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 Un type qui est déclaré `Protected`, `Friend`, `Protected Friend`, ou `Private` est destiné à un accès en dehors de son contexte de déclaration limité. À l’utiliser en tant que les données de type d’une variable avec un accès restreint moins serait en opposition avec cet effet. Dans le code squelette précédent, `exposedVar` est `Public` et exposera `privateClass` au code que vous ne devez pas y accéder.  
  
 **ID d’erreur :** BC30909  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Changement du niveau d’accès de la variable, un paramètre de procédure ou une fonction de retour pour être au moins aussi restrictif que le niveau d’accès de son type de données.  
  
## <a name="see-also"></a>Voir aussi
- [Niveaux d’accès dans Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
