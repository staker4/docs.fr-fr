---
title: Contrôles constitutifs
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 28ae15165327a1bd72e1099460a2a1e3d337ca48
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739152"
---
# <a name="constituent-controls"></a>Contrôles constitutifs
Les contrôles qui composent un contrôle utilisateur, appelés *contrôles constitutifs*, sont relativement peu flexibles en matière de rendu graphique personnalisé. Tous les contrôles Windows Forms gèrent leur propre rendu par l’intermédiaire de leurs propres <xref:System.Windows.Forms.Control.OnPaint%2A> (méthode). Comme cette méthode est protégée, elle n’est pas accessible au développeur et il n’est pas possible d’empêcher son exécution quand le contrôle est dessiné. Cela ne signifie pas pour autant que vous ne pouvez pas ajouter du code pour modifier l’apparence des contrôles constitutifs. Un rendu supplémentaire est possible en ajoutant un gestionnaire d’événements. Par exemple, supposons que vous créez un <xref:System.Windows.Forms.UserControl> avec un bouton nommé `MyButton`. Si vous voulez obtenir un rendu supplémentaires au-delà de ce qui a été fourni par le <xref:System.Web.UI.WebControls.Button>, vous devez ajouter le code à votre contrôle utilisateur similaire à ce qui suit :  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
>  Contrôles de certaines formes de Windows, tels que <xref:System.Windows.Forms.TextBox>, sont dessinés directement par Windows. Dans ce cas, le <xref:System.Windows.Forms.Control.OnPaint%2A> méthode n’est jamais appelée, et par conséquent, l’exemple ci-dessus ne sera jamais appelée.  
  
 Ceci crée une méthode qui s’exécute chaque fois que l’événement `MyButton.Paint` s’exécute, ce qui ajoute une représentation graphique supplémentaire à votre contrôle. Notez que ceci n’empêche pas l’exécution de `MyButton.OnPaint`, et tout le dessin généralement effectué par un bouton est donc exécuté en plus de votre dessin personnalisé. Pour plus d’informations sur la technologie GDI+ et le rendu personnalisé, consultez [Création d’images graphiques avec GDI+](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md). Si vous voulez avoir une représentation unique de votre contrôle, le mieux est de créer un contrôle hérité et d’écrire pour celui-ci du code de rendu personnalisé. Pour plus d’informations, consultez [Contrôles dessinés par l’utilisateur](../../../../docs/framework/winforms/controls/user-drawn-controls.md).  
  
## <a name="see-also"></a>Voir aussi
- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Contrôles dessinés par l’utilisateur](../../../../docs/framework/winforms/controls/user-drawn-controls.md)
- [Guide pratique pour Créer des objets graphiques pour le dessin](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)
- [Variétés de contrôles personnalisés](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
