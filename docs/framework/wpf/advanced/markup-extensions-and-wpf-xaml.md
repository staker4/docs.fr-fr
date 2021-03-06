---
title: Extensions de balisage et XAML WPF
ms.date: 03/30/2017
helpviewer_keywords:
- brace character [WPF]
- Binding markup extensions [WPF]
- RelativeSource markup extensions [WPF]
- XAML [WPF], markup extensions
- markup extensions [WPF]
- nesting extension syntax [WPF]
- curly brace characters ({})
- TemplateBinding markup extensions [WPF]
- StaticResource markup extensions [WPF]
- literal curly brace characters ({})
- characters [WPF], curly brace
- DynamicResource markup extensions [WPF]
ms.assetid: 618dc745-8b14-4886-833f-486d2254bb78
ms.openlocfilehash: 1726ce0798f2511ee2e7d910ee5f6a0f30f9a282
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585641"
---
# <a name="markup-extensions-and-wpf-xaml"></a>Extensions de balisage et XAML WPF
Cette rubrique introduit le concept d’extensions de balisage pour XAML, notamment leurs règles de syntaxe, leur finalité et le modèle d’objet de classe sous-jacent. Les extensions de balisage sont une fonctionnalité générale du langage XAML et de l’implémentation .NET des services XAML. Cette rubrique détaille spécifiquement des extensions de balisage pour une utilisation dans le langage XAML de WPF.  
  
  
<a name="XAML_Processors_and_Markup_Extensions"></a>   
## <a name="xaml-processors-and-markup-extensions"></a>Processeurs XAML et extensions de balisage  
 En général, un analyseur XAML peut interpréter une valeur d’attribut en tant que chaîne littérale convertible en primitive ou la convertir en objet par un moyen ou par un autre. L’un d’eux consiste à référencer un convertisseur de type ; cette méthode est documentée dans la rubrique [TypeConverters et XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md). Cependant, certains scénarios peuvent nécessiter un comportement différent. Par exemple, un processeur XAML peut être informé du fait qu’une valeur d’attribut ne doit pas générer un nouvel objet dans le graphique d’objet. L’attribut doit en revanche générer un graphique d’objet qui fait référence à un objet déjà construit dans une autre partie du graphique, c’est-à-dire un objet statique. Autre scénario : un processeur XAML peut être chargé d’utiliser une syntaxe qui fournit des arguments non définis par défaut au constructeur d’un objet. Dans ces types de scénario, une extension de balisage peut être la solution.  
  
<a name="Basic_Markup_Extension_Syntax"></a>   
## <a name="basic-markup-extension-syntax"></a>Syntaxe d’extension de balisage de base  
 Une extension de balisage peut être implémentée pour fournir des valeurs de propriétés dans une utilisation d’attribut ou d’un élément de propriété, ou les deux à la fois.  
  
 Quand elle est utilisée pour fournir une valeur d’attribut, la syntaxe qui distingue une séquence d’extension de balisage d’un processeur XAML est la présence d’accolades ouvrantes et fermantes ({ et }). Le type d’extension de balisage est alors identifié par le jeton de chaîne qui suit immédiatement l’accolade ouvrante.  
  
 Quand elle est utilisée dans la syntaxe des éléments de propriété, une extension de balisage ressemble visuellement à n’importe quel autre élément utilisé pour fournir une valeur d’élément de propriété, c’est-à-dire à une déclaration d’élément XAML qui fait référence à la classe d’extension de balisage en tant qu’élément, comprise entre les signes « inférieur à » et « supérieur à » (< >).  
  
<a name="XAML_Defined_Markup_Extensions"></a>   
## <a name="xaml-defined-markup-extensions"></a>Extensions de balisage définies en XAML  
 Il existe plusieurs extensions de balisage qui ne sont pas spécifiques à l’implémentation WPF de XAML, mais qui sont plutôt des implémentations d’intrinsèques ou de fonctionnalités du langage XAML. Ces extensions de balisage sont implémentées dans l’assembly System.Xaml en tant que partie intégrante des services généraux XAML du .NET Framework et se trouvent dans l’espace de noms XAML du langage XAML. Dans le cadre d’une utilisation de balisage courante, ces extensions de balisage sont en général identifiables par le préfixe `x:`. Le <xref:System.Windows.Markup.MarkupExtension> classe de base (également définie dans System.Xaml) fournit le modèle que toutes les extensions de balisage doivent utiliser pour être prises en charge dans les lecteurs XAML et les writers XAML, notamment dans WPF XAML.  
  
-   `x:Type` fournit l'objet <xref:System.Type> pour le type nommé. Cette fonctionnalité est généralement utilisée dans les styles et les modèles. Pour plus d’informations, consultez [x:Type, extension de balisage](../../../../docs/framework/xaml-services/x-type-markup-extension.md).  
  
-   `x:Static` génère des valeurs statiques. Les valeurs proviennent des entités de code de type de valeur qui ne désignent pas directement le type de la valeur d’une propriété cible, mais qui peuvent être évaluées comme étant de ce type. Pour plus d’informations, consultez [x:Static, extension de balisage](../../../../docs/framework/xaml-services/x-static-markup-extension.md).  
  
-   `x:Null` spécifie `null` en tant que valeur d’une propriété et peut être utilisé pour les attributs ou les valeurs d’élément de propriété. Pour plus d’informations, consultez [x:Null, extension de balisage](../../../../docs/framework/xaml-services/x-null-markup-extension.md).  
  
-   `x:Array` offre une prise en charge pour la création de tableaux généraux dans la syntaxe XAML, dans les cas où la prise en charge des collections assurée par les éléments de base et les modèles de contrôle WPF n’est délibérément pas utilisée. Pour plus d’informations, consultez [x:Array, extension de balisage](../../../../docs/framework/xaml-services/x-array-markup-extension.md).  
  
> [!NOTE]
>  Le préfixe `x:` est utilisé pour le mappage d’espace de noms XAML standard des intrinsèques du langage XAML, dans l’élément racine d’un fichier ou d’une production XAML. Par exemple, les modèles Visual Studio pour les applications WPF lancer un fichier XAML à l’aide de ce `x:` mappage. Vous pouvez choisir un autre jeton de préfixe pour votre propre mappage d’espace de noms XAML. Cependant, dans cette documentation, le mappage `x:` par défaut est considéré comme un moyen d’identifier les entités qui représentent une partie définie de l’espace de noms XAML du langage XAML, par opposition à l’espace de noms XAML par défaut ou à d’autres espaces de noms XAML non liés à un framework spécifique.  
  
<a name="WPF_Specific_Markup_Extensions"></a>   
## <a name="wpf-specific-markup-extensions"></a>Extensions de balisage spécifiques à WPF  
 Les extensions de balisage les plus courantes utilisées en programmation WPF sont celles qui prennent en charge les références de ressources (`StaticResource` et `DynamicResource`) et celles qui prennent en charge la liaison de données (`Binding`).  
  
-   `StaticResource` fournit une valeur de propriété en remplaçant la valeur d’une ressource déjà définie. Une évaluation `StaticResource` est finalement effectuée au moment du chargement XAML et n’a pas accès au graphique d’objet au moment de l’exécution. Pour plus d’informations, consultez [StaticResource, extension de balisage](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  
  
-   `DynamicResource` fournit une valeur de propriété en différant le moment où cette valeur devient une référence à une ressource au moment de l’exécution. Une référence de ressource dynamique force une nouvelle recherche chaque fois qu’un accès à ladite ressource a lieu et que cette dernière a accès au graphique d’objet au moment de l’exécution. Pour obtenir cet accès, le concept `DynamicResource` est pris en charge par les propriétés de dépendance dans le système de propriétés WPF et les expressions évaluées. Par conséquent, vous pouvez uniquement utiliser `DynamicResource` pour une cible de propriété de dépendance. Pour plus d’informations, consultez [DynamicResource, extension de balisage](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  
  
-   `Binding` fournit une valeur liée aux données pour une propriété, en utilisant le contexte de données qui s’applique à l’objet parent au moment de l’exécution. Cette extension de balisage est relativement complexe, car elle active une syntaxe inline substantielle pour spécifier une liaison de données. Pour plus d’informations, consultez [Binding, extension de balisage](../../../../docs/framework/wpf/advanced/binding-markup-extension.md).  
  
-   `RelativeSource` Fournit des informations sources pour un <xref:System.Windows.Data.Binding> qui peut naviguer entre plusieurs relations possibles dans l’arborescence de l’objet d’exécution. Cela fournit une source d’approvisionnement spécialisée pour les liaisons créées dans des modèles multiusage ou dans du code sans avoir pleine connaissance de l’arborescence d’objets environnante. Pour plus d’informations, consultez [RelativeSource, extension de balisage](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md).  
  
-   `TemplateBinding` permet à un modèle de contrôle d’utiliser des valeurs pour des propriétés basées sur un modèle provenant de propriétés définies par un modèle objet de la classe destinée à utiliser le modèle. En d’autres termes, la propriété au sein de la définition du modèle peut accéder à un contexte qui existe uniquement une fois que le modèle est appliqué. Pour plus d’informations, consultez [TemplateBinding, extension de balisage](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md). Pour plus d’informations sur l’utilisation pratique de `TemplateBinding`, consultez [Style avec ControlTemplates, exemple](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
-   `ColorConvertedBitmap` prend en charge un scénario d’acquisition d’images relativement avancé. Pour plus d’informations, consultez [ColorConvertedBitmap, extension de balisage](../../../../docs/framework/wpf/advanced/colorconvertedbitmap-markup-extension.md).  
  
-   `ComponentResourceKey` et `ThemeDictionary` prennent en charge les aspects de la recherche de ressources, en particulier pour les ressources et les thèmes empaquetés avec des contrôles personnalisés. Pour plus d’informations, consultez [ComponentResourceKey, extension de balisage](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md), [ThemeDictionary, extension de balisage](../../../../docs/framework/wpf/advanced/themedictionary-markup-extension.md) ou [Vue d’ensemble de la création de contrôles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
<a name="StarExtension"></a>   
## <a name="extension-classes"></a>*Classes d’extension  
 Pour le langage XAML général et extensions de balisage spécifiques à WPF, le comportement de chaque extension de balisage est identifié à un processeur XAML via un `*Extension` classe qui dérive de <xref:System.Windows.Markup.MarkupExtension>et fournit une implémentation de la <xref:System.Windows.Markup.StaticExtension.ProvideValue%2A> méthode. Cette méthode au niveau de chaque extension fournit l’objet qui est retourné au moment où l’extension de balisage est évaluée. L’objet retourné est généralement évalué en fonction des différents jetons de chaîne passés à l’extension de balisage.  
  
 Par exemple, le <xref:System.Windows.StaticResourceExtension> classe fournit l’implémentation de surface de recherche de ressource réelle afin que son <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> implémentation retourne l’objet qui est demandé, l’entrée de cette implémentation particulière étant une chaîne qui est utilisée pour rechercher la ressource par son `x:Key`. L’essentiel de cette implémentation n’a pas d’importance si vous utilisez une extension de balisage existante.  
  
 Certaines extensions de balisage n’utilisent pas d’arguments de jeton de chaîne. Cela s’explique soit par le fait qu’ils retournent une valeur statique ou cohérente, soit par le fait que le contexte de la valeur devant être retournée est disponible via l’un des services transmis par le paramètre `serviceProvider`.  
  
 Le modèle de nommage `*Extension` est fourni par souci pratique et de cohérence. Il n’est pas nécessaire à un processeur XAML pour identifier cette classe comme étant une prise en charge d’une extension de balisage. Tant que votre base de code comprend System.Xaml et utilise les implémentations de Services XAML du .NET Framework, tout ce qui est nécessaire pour être reconnu comme une extension de balisage XAML doit dériver de <xref:System.Windows.Markup.MarkupExtension> et pour prendre en charge une syntaxe de construction. WPF définit les classes d’activation de l’extension de balisage qui ne suivent pas le `*Extension` d’affectation de noms de modèle, par exemple <xref:System.Windows.Data.Binding>. En général, la raison à cela est que la classe prend en charge des scénarios qui dépassent la prise en charge pure de l’extension de balisage. Dans le cas de <xref:System.Windows.Data.Binding>, que classe prend en charge l’accès d’exécution aux méthodes et propriétés de l’objet pour les scénarios qui n’ont rien à faire avec XAML.  
  
### <a name="extension-class-interpretation-of-initialization-text"></a>Interprétation du texte d’initialisation par la classe d’extension  
 Les jetons de chaîne situés à la suite du nom d’extension de balisage et se trouvant toujours entre accolades sont interprétés par un processeur XAML de l’une des manières suivantes :  
  
-   Une virgule représente toujours le séparateur ou délimiteur de jetons individuels.  
  
-   Si des jetons distincts ne contiennent pas de signes égal, chaque jeton est considéré comme un argument de constructeur. Chaque paramètre de constructeur doit être fourni dans le type et l’ordre correct attendus par cette signature.  
  
    > [!NOTE]
    >  Un processeur XAML doit appeler le constructeur qui correspond au nombre d’arguments du nombre de paires. Pour cette raison, si vous implémentez une extension de balisage personnalisée, ne fournissez pas plusieurs constructeurs avec le même nombre d’arguments. Bien que le comportement d’un processeur XAML en présence de plusieurs chemins d’accès de constructeur d’extension de balisage ayant le même nombre de paramètres ne soit pas défini, il est probable que le processeur XAML soit autorisé à lever une exception d’utilisation si ce cas se présente dans les définitions de type d’extension de balisage.  
  
-   Si les différents jetons contiennent des signes égal, le processeur XAML appelle d’abord le constructeur par défaut pour l’extension de balisage. Ensuite, chaque paire nom=valeur est interprétée comme un nom de propriété existant au niveau de l’extension de balisage et une valeur à assigner à cette propriété.  
  
-   S’il existe un résultat parallèle entre le comportement du constructeur et le comportement de définition de la propriété dans une extension de balisage, peu importe le comportement que vous utilisez. Il est plus courant d’utiliser les paires *propriété*`=`*valeur* pour les extensions de balisage qui ont plusieurs propriétés définissables, ne serait-ce que parce qu’elles donnent à votre balisage un caractère plus intentionnel et vous avez moins de chances d’inverser par erreur les paramètres du constructeur. (Quand vous spécifiez des paires propriété=valeur, ces propriétés peuvent être fournies dans n’importe quel ordre.) De plus, rien de garantit qu’une extension de balisage fournisse un paramètre de constructeur qui définit chacune de ses propriétés définissables. Par exemple, <xref:System.Windows.Data.Binding> est une extension de balisage, avec de nombreuses propriétés qui peuvent être définies via l’extension dans *propriété*`=`*valeur* formulaire, mais <xref:System.Windows.Data.Binding> prend uniquement en charge les deux constructeurs : un constructeur par défaut et un autre qui définit un chemin d’accès initial.  
  
-   Une virgule littérale ne peut pas être passée à une extension de balisage sans échappement.  
  
<a name="EscapeSequences"></a>   
## <a name="escape-sequences-and-markup-extensions"></a>Séquences d’échappement et extensions de balisage  
 La gestion des attributs dans un processeur XAML utilise les accolades comme indicateurs d’une séquence d’extension de balisage. Il est possible aussi de générer une valeur d’attribut de caractère d’accolade littérale, si nécessaire, en entrant une séquence d’échappement avec une paire d’accolades vides, suivie de l’accolade littérale. Consultez [ {} séquence - Extension de balisage d’échappement](../../xaml-services/escape-sequence-markup-extension.md).  
  
<a name="Nesting"></a>   
## <a name="nesting-markup-extensions-in-xaml-usage"></a>Imbrication d’extensions de balisage dans l’utilisation de XAML  
 L’imbrication de plusieurs extensions de balisage est prise en charge, et chaque extension de balisage est d’abord évaluée au plus profond. Penchons-nous, par exemple, sur l’utilisation suivante :  
  
```  
<Setter Property="Background"  
  Value="{DynamicResource {x:Static SystemColors.ControlBrushKey}}" />  
```  
  
 Dans ce cas, l’instruction `x:Static` est évaluée en premier et retourne une chaîne. Cette chaîne est ensuite utilisée comme argument pour `DynamicResource`.  
  
## <a name="markup-extensions-and-property-element-syntax"></a>Extensions de balisage et syntaxe des éléments de propriété  
 Quand elle est utilisée comme un élément objet qui fournit une valeur d’élément de propriété, une classe d’extension de balisage ne se distingue pas visuellement d’un élément objet associé à un type ordinaire qui peut être utilisé en XAML. D’un point de vue pratique, la différence entre un élément objet ordinaire et une extension de balisage vient du fait que l’extension de balisage est soit évaluée en valeur typée, soit différée en tant qu’expression. Par conséquent, les mécanismes qui interviennent en cas d’erreur de type pour les valeurs de propriété de l’extension de balisage sont différents, à l’instar de la façon dont une propriété à liaison tardive est traitée dans d’autres modèles de programmation. Un élément objet ordinaire fera l’objet d’une évaluation de la correspondance de type par rapport à la propriété cible qu’il définit pendant l’analyse du code XAML.  
  
 La plupart des extensions de balisage, quand elles sont utilisées dans une syntaxe d’éléments objet pour remplir un élément de propriété, ne doit pas comporter de contenu ni toute autre syntaxe d’éléments de propriété. Par conséquent, vous devez fermer la balise de l’élément objet et ne fournir aucun élément enfant. Chaque fois qu’un processeur XAML rencontre un élément objet, le constructeur de cette classe est appelé, ce qui instancie l’objet créé à partir de l’élément analysé. Une classe d’extension de balisage n’est aucunement différente : si vous souhaitez que votre extension de balisage soit utilisable dans la syntaxe de l’élément objet, vous devez indiquer un constructeur par défaut. Certaines extensions de balisage existantes ont au moins une valeur de propriété requise qui doit être spécifiée pour une initialisation efficace. Si tel est le cas, cette valeur de propriété est généralement fournie en tant qu’attribut de propriété au niveau de l’élément objet. Dans le [XAML Namespace (x :)) Fonctionnalités de langage](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md) et [les Extensions XAML WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md) markup extensions qui ont des propriétés requises (et les noms des propriétés requises) sont notées pages de référence. Ces pages indiquent aussi si la syntaxe des éléments objet ou des attributs est rejetée pour des extensions de balisage particulières. Il convient d’attirer l’attention sur le cas de l’[extension de balisage x:Array](../../../../docs/framework/xaml-services/x-array-markup-extension.md), qui ne peut pas prendre en charge la syntaxe d’attribut, car le contenu de ce tableau doit être spécifié dans le balisage en tant contenu. Le contenu du tableau étant géré en tant qu’objets généraux, aucun convertisseur de type par défaut ne peut être exécuté pour l’attribut. De plus, l’[extension de balisage x:Array](../../../../docs/framework/xaml-services/x-array-markup-extension.md) nécessite un paramètre `type`.  
  
## <a name="see-also"></a>Voir aussi
- [Vue d’ensemble du langage XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [XAML Namespace (x :)) Fonctionnalités de langage](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)
- [Extensions XAML WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)
- [StaticResource, extension de balisage](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)
- [Binding, extension de balisage](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)
- [Extension de balisage DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
- [x:Type, extension de balisage](../../../../docs/framework/xaml-services/x-type-markup-extension.md)
