---
title: Organiser des projets pour .NET Framework et .NET Core
description: Aide destinée aux propriétaires de projet qui souhaitent compiler leur solution côte à côte pour le .NET Framework et .NET Core.
author: conniey
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 57bb766f1d91c502a508b6362dc642310009c8c4
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904021"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a>Organiser votre projet pour prendre en charge à la fois le .NET Framework et .NET Core

Découvrez comment créer une solution qui se compile parallèlement pour .NET Framework et .NET Core. Découvrez plusieurs options pour organiser les projets de façon à vous aider à atteindre cet objectif. Voici quelques scénarios classiques à prendre en compte quand vous devez décider comment configurer la disposition de votre projet avec .NET Core. La liste peut ne pas couvrir tout ce que vous souhaitez : établissez vos priorités en fonction des besoins de votre projet.

* [**Combiner des projets existants et des projets .NET Core pour en faire des projets uniques**](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  *En voici les avantages :*
  * Simplification de votre processus de génération : compilation d’un seul projet au lieu de plusieurs, chacun ciblant une version du .NET Framework ou une plateforme différente.
  * Simplification de la gestion des fichiers sources pour les projets multiciblés car vous devez gérez un seul fichier projet. Lors de l’ajout/suppression de fichiers sources, les alternatives vous obligent à synchroniser manuellement ces fichiers avec vos autres projets.
  * Génération facile d’un package NuGet à consommer.
  * Vous permet d’écrire du code pour une version spécifique du .NET Framework dans vos bibliothèques via l’utilisation de directives de compilation.

  *Scénarios non pris en charge :*
  * Demander aux développeurs d’utiliser Visual Studio 2017 pour ouvrir des projets existants. Pour prendre en charge les versions antérieures de Visual Studio, [conserver vos fichiers projet dans des dossiers différents](#support-vs) est une meilleure option.

* <a name="support-vs"></a>[**Séparer les projets existants des nouveaux projets .NET Core**](#keep-existing-projects-and-create-a-net-core-project)

  *En voici les avantages :*
  * Continuation de la prise en charge du développement de projets existants sans devoir mettre à niveau pour les développeurs/contributeurs qui n’ont pas Visual Studio 2017.
  * Réduction du risque de création de bogues dans des projets existants car aucune évolution du code n’est nécessaire dans ces projets.

## <a name="example"></a>Exemple

Considérez le dépôt ci-dessous :

![Projet existant](media/project-structure/project.png)

[**Code source**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

La section suivante décrit plusieurs méthodes pour ajouter la prise en charge de .NET Core pour ce dépôt en fonction des contraintes et de la complexité des projets existants.

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a>Remplacer les projets existants par un projet .NET Core multiciblé

Réorganisez le dépôt de sorte que tous les fichiers *\*.csproj* existants soient supprimés et qu’un seul fichier *\*.csproj* ciblant plusieurs frameworks soit créé. Il s’agit d’une option intéressante car un même projet peut être compilé pour différents frameworks. Elle permet également de gérer différentes options de compilation et dépendances par framework ciblé.

![Créer un csproj qui cible plusieurs frameworks](media/project-structure/project.csproj.png)

[**Code source**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

Les modifications à noter sont :

* Remplacement de *packages.config* et de *\*.csproj* par un nouveau [.csproj *\*.NET Core*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj). Les packages NuGet sont spécifiés avec `<PackageReference> ItemGroup`.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Conserver les projets existants et créer un projet .NET Core

Si des projets existants ciblent des frameworks plus anciens, vous pouvez laisser ces projets inchangés et utiliser un projet .NET Core pour cibler les futurs frameworks.

![Projet .NET Core avec un projet existant dans un dossier différent](media/project-structure/project.csproj.different.png)

[**Code source**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

Les modifications à noter sont :

* Le projet .NET Core et les projets existants sont conservés dans des dossiers distincts.
  * Le fait de conserver les projets dans des dossiers distincts vous évite de devoir installer Visual Studio 2017. Vous pouvez créer une solution distincte qui ouvre seulement les anciens projets.

## <a name="see-also"></a>Voir aussi

Consultez la [documentation relative au portage vers .NET Core](index.md) pour obtenir des informations supplémentaires sur la migration vers .NET Core.
