---
title: Traitement de données XML en mémoire
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8e6e89cafeb4cc580edb9630ba7415a669ea750c
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904412"
---
# <a name="processing-xml-data-in-memory"></a>Traitement de données XML en mémoire
Microsoft .NET Framework comprend trois modèles pour le traitement des données XML : la classe <xref:System.Xml.XmlDocument>, la classe <xref:System.Xml.XPath.XPathDocument> et [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).  
  
 La classe <xref:System.Xml.XmlDocument> implémente les recommandations du W3C relatives aux modèles objet de document (DOM), niveaux 1 et 2 (noyau). Le DOM est une représentation sous la forme d'une arborescence (cache) en mémoire d'un document XML. L'objet <xref:System.Xml.XmlDocument> et les classes y afférentes permettent de construire des documents XML, de charger et d'accéder à des données, de modifier des données et d'enregistrer des modifications.  
  
 La classe <xref:System.Xml.XPath.XPathDocument> est un magasin de données en mémoire en lecture seule basé sur le modèle de données XPath. La classe <xref:System.Xml.XPath.XPathNavigator> propose plusieurs options de modification et fonctionnalités de navigation à l'aide d'un modèle de curseur entre des documents XML contenus dans la classe <xref:System.Xml.XPath.XPathDocument> en lecture seule ainsi que dans la classe <xref:System.Xml.XmlDocument>.  
  
 [LINQ to XML](../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) est un modèle introduit dans .NET Framework version 3.5 pour le traitement des données XML. Il s’agit d’un modèle en mémoire qui tire parti de [LINQ (Language-Integrated Query)](../../../csharp/programming-guide/concepts/linq/index.md). LINQ étend la syntaxe des langages C# et Visual Basic pour fournir de nouvelles capacités de requête.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Traitement de données XML à l’aide du modèle DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 Explique l'utilisation de l'objet <xref:System.Xml.XmlDocument> et des classes y afférentes pour le traitement de données XML.  
  
 [Traitement des données XML à l’aide du modèle de données XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 Explique l'utilisation des classes <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> et <xref:System.Xml.XPath.XPathNavigator> pour le traitement de données XML.  
  
 [Traitement des données XML à l’aide de LINQ to XML](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 Fournit une brève vue d'ensemble de LINQ to XML et indique des liens vers la documentation LINQ to XML.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Documents et données XML](../../../../docs/standard/data/xml/index.md)
