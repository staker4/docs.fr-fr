---
title: "'<elementname>' est obsolète (avertissement Visual Basic)"
ms.date: 07/20/2015
f1_keywords:
- vbc40008
- bc40008
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
ms.openlocfilehash: c6d927ef6681838d8a77a0c6018eb6bbe30913e8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255859"
---
# <a name="elementname-is-obsolete-visual-basic-warning"></a>'\<nom_élément >' est obsolète (avertissement Visual Basic)
Une instruction tente d’accéder à un élément de programmation qui a été marqué avec l’attribut <xref:System.ObsoleteAttribute> et la directive pour le traiter comme un avertissement.  
  
 Vous pouvez marquer un élément de programmation comme n’étant plus utilisé en lui appliquant <xref:System.ObsoleteAttribute> . Dans ce cas, vous pouvez affecter à la propriété <xref:System.ObsoleteAttribute.IsError%2A> de l’attribut la valeur `True` ou `False`. Si vous lui affectez la valeur `True`, le compilateur traite une tentative d’utilisation de l’élément comme une erreur. Si vous lui affectez la valeur `False`ou si vous laissez la valeur par défaut `False`, le compilateur émet un avertissement en cas de tentative d’utilisation de l’élément.  
  
 Par défaut, ce message est un avertissement, car la propriété <xref:System.ObsoleteAttribute.IsError%2A> de <xref:System.ObsoleteAttribute> a la valeur `False`. Pour plus d’informations sur le masquage des avertissements ou le traitement des avertissements en tant qu’erreurs, consultez [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID d’erreur :** BC40008  
  
## <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Vérifiez que le nom de l’élément est orthographié correctement dans la référence du code source.  
  
## <a name="see-also"></a>Voir aussi
- [Vue d’ensemble des attributs](../../../visual-basic/programming-guide/concepts/attributes/index.md)
