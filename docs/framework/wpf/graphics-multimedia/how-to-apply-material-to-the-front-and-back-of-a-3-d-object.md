---
title: "Procédure : Appliquer un matériau à l'avant et à l'arrière d'un objet 3D"
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 16f30e3a880d7dcc943a9583ba0f04c4bd682827
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652031"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a>Procédure : Appliquer un matériau à l'avant et à l'arrière d'un objet 3D
L’exemple suivant montre comment appliquer un <xref:System.Windows.Media.Media3D.Material> de l’objet à l’avant et arrière 3D et animer l’objet pour afficher les deux côtés de l’objet. Le <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> propriété d’un <xref:System.Windows.Media.Media3D.GeometryModel3D> est utilisé pour appliquer une croix rouge <xref:System.Windows.Media.Brush> à la face avant de l’objet et le <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> propriété du <xref:System.Windows.Media.Media3D.GeometryModel3D> est utilisé pour appliquer un bleu <xref:System.Windows.Media.Brush> à l’arrière de l’objet. Le code ci-dessous montre l’application des matériaux à l’objet :  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>Exemple  
 Le code suivant montre l’exemple complet.  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>Voir aussi
- [Créer une scène 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [Vue d’ensemble des graphiques 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [Animer les propriétés de matériel dans une scène 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)
- [Appliquer un matériau émissif à un objet 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
