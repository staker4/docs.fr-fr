---
title: 'Procédure : Prennent en charge COM Interop en affichant chaque formulaire Windows sur son propre Thread'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
ms.openlocfilehash: 5df3b4868a514fb520a66aa89ae7795d68eaffd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672069"
---
# <a name="how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread"></a>Procédure : Prennent en charge COM Interop en affichant chaque formulaire Windows sur son propre Thread
Vous pouvez résoudre les problèmes d'interopérabilité COM en affichant votre formulaire sur une boucle de message [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , que vous pouvez créer à l'aide de la méthode <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> .  
  
 Pour qu'un Windows Form fonctionne correctement à partir d'une application cliente COM, vous devez l'exécuter sur une boucle de message Windows Forms. Pour cela, utilisez l'une des approches suivantes :  
  
-   Utilisez la méthode <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> pour afficher le Windows Form. Pour plus d'informations, voir [Procédure : Prise en charge COM Interop en affichant un formulaire Windows avec la méthode ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md).  
  
-   Affichez chaque Windows Form sur un thread séparé.  
  
 Il existe une prise en charge étendue pour cette fonctionnalité dans Visual Studio.  
  
 Consultez également [procédure pas à pas : Prise en charge COM Interop en affichant chaque formulaire Windows sur son propre Thread](https://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## <a name="example"></a>Exemple  
 L'exemple de code suivant montre comment afficher le formulaire sur un thread distinct et appeler la méthode <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> pour démarrer une pompe de messages Windows Forms sur ce thread. Pour utiliser cette approche, vous devez marshaler tous les appels au formulaire à partir de l'application non managée à l'aide de la méthode <xref:System.Windows.Forms.Control.Invoke%2A> .  
  
 Cette approche exige que chaque instance d'un formulaire s'exécute sur son propre thread à l'aide de sa propre boucle de message. Une seule boucle de message peut s'exécuter par thread. Ainsi, vous ne pouvez pas modifier la boucle de message de l'application cliente. En revanche, vous pouvez modifier le composant [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] pour démarrer un nouveau thread qui utilise sa propre boucle de message.  
  
 [!code-vb[System.Windows.Forms.ComInterop#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
  
-   Compilez le types `COMForm`, `Form1`et `FormManager` dans un assembly nommé `COMWinform.dll`. Inscrivez l’assembly pour COM Interop en utilisant l’une des méthodes décrites dans [Packaging an Assembly for COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md). Vous pouvez maintenant utiliser l'assembly et son fichier de bibliothèque de types (.tlb) correspondant dans des applications non managées. Par exemple, vous pouvez utiliser la bibliothèque de types comme référence dans un projet exécutable Visual Basic 6.0.  
  
## <a name="see-also"></a>Voir aussi
- [Exposition de composants .NET Framework à COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)
- [Empaquetage d'un assembly pour COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md)
- [Inscription d’assemblys dans COM](../../../../docs/framework/interop/registering-assemblies-with-com.md)
- [Guide pratique pour Prennent en charge COM Interop en affichant un formulaire Windows avec la méthode ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)
- [Vue d'ensemble des applications Windows Forms et non managées](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)
