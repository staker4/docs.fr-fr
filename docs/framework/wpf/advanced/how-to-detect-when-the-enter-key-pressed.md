---
title: 'Procédure : Détecter quand la touche enfoncée'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Enter key [WPF], detecting
- keys [WPF], Enter
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
ms.openlocfilehash: fbb9b1b9cbb56a49aba018f122a7e903bd4f677d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592245"
---
# <a name="how-to-detect-when-the-enter-key-pressed"></a>Procédure : Détecter quand la touche enfoncée
Cet exemple montre comment détecter lorsque le <xref:System.Windows.Input.Key.Enter> touche du clavier.  
  
 Cet exemple se compose d’un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] fichier et un fichier code-behind.  
  
## <a name="example"></a>Exemple  
 Lorsque l’utilisateur appuie sur la touche <xref:System.Windows.Input.Key.Enter> dans la <xref:System.Windows.Controls.TextBox>, le texte entré s’affiche dans une autre zone de la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].    
  
 Ce qui suit [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crée l’interface utilisateur, qui se compose d’un <xref:System.Windows.Controls.StackPanel>, un <xref:System.Windows.Controls.TextBlock>et un <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keydown#KeyDownUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Le code-behind suivant crée le <xref:System.Windows.UIElement.KeyDown> Gestionnaire d’événements.  Si la touche enfoncée est la touche <xref:System.Windows.Input.Key.Enter>, un message s’affiche dans le <xref:System.Windows.Controls.TextBlock>.   
  
 [!code-csharp[keydown#KeyDownSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## <a name="see-also"></a>Voir aussi
- [Vue d’ensemble des entrées](../../../../docs/framework/wpf/advanced/input-overview.md)
- [Vue d’ensemble des événements routés](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
