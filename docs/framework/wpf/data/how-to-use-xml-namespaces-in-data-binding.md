---
title: 'Procédure : Utiliser des espaces de noms XML dans la liaison de données'
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: bd2a156920057dc197fabbaa46e3a2d886a1b322
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600347"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Procédure : Utiliser des espaces de noms XML dans la liaison de données
## <a name="example"></a>Exemple  
 Cet exemple montre comment gérer les espaces de noms spécifiés dans votre source de liaison [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)].  
  
 Si vos données [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] contiennent la définition d’espace de noms [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] suivante :  
  
 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`  
  
 Vous pouvez utiliser la <xref:System.Windows.Data.XmlNamespaceMapping> élément pour mapper l’espace de noms à un <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, comme dans l’exemple suivant. Vous pouvez ensuite utiliser le <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> pour faire référence à la [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] espace de noms. Le <xref:System.Windows.Controls.ListBox> dans cet exemple affiche le *titre* et *DC : date* de chacun d’eux *élément*.  
  
 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]  
  
 Notez que le <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> vous spécifiez ne doit pas correspondre à celui utilisé dans le [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source ; si le préfixe change dans le [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] source votre mappage continuera de fonctionner.  
  
 Dans cet exemple particulier, le [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] données proviennent d’un service web, mais la <xref:System.Windows.Data.XmlNamespaceMapping> élément fonctionne également avec inline [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ou [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] les données dans un fichier incorporé.  
  
## <a name="see-also"></a>Voir aussi
- [Effectuer une liaison à des données XML à l’aide d’un XMLDataProvider et de requêtes XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Vue d’ensemble de la liaison de données](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Rubriques de guide pratique](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
