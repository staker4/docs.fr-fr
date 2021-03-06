---
title: 'Procédure : Récupérer une sélection de texte'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: 3e2a4d9938f73cb306e8fd8b0e6b25b5abfa3b4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517771"
---
# <a name="how-to-retrieve-a-text-selection"></a>Procédure : Récupérer une sélection de texte
Cet exemple montre une manière d’utiliser le <xref:System.Windows.Controls.TextBox.SelectedText%2A> propriété à récupérer le texte que l’utilisateur a sélectionné dans un <xref:System.Windows.Controls.TextBox> contrôle.  
  
## <a name="example"></a>Exemple  
 Ce qui suit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] exemple illustre la définition d’un <xref:System.Windows.Controls.TextBox> contrôle contenant du texte à sélectionner, et un <xref:System.Windows.Controls.Button> contrôle avec un <xref:System.Windows.Controls.Button.OnClick%2A> (méthode).  
  
 Dans cet exemple, un bouton avec associé à un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Gestionnaire d’événements est utilisé pour récupérer la sélection de texte. Lorsque l’utilisateur clique sur le bouton, le <xref:System.Windows.Controls.Button.OnClick%2A> méthode copie le texte sélectionné dans la zone de texte dans une chaîne. Circonstances particulières auxquelles la sélection de texte est récupérée (en cliquant sur un bouton), ainsi que l’action effectuée avec cette sélection (copie la sélection de texte vers une chaîne), peut facilement être modifié pour prendre en charge un large éventail de scénarios.  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a>Exemple  
 Ce qui suit C# exemple illustre un <xref:System.Windows.Controls.Button.OnClick%2A> Gestionnaire d’événements pour le bouton défini dans le [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pour cet exemple.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a>Voir aussi
- [Vue d’ensemble de TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [Vue d’ensemble de RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
