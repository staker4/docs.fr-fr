---
title: Publier des applications .NET Core avec l’interface CLI
description: Découvrez comment publier une application .NET Core avec les outils de l’interface de ligne de commande (CLI) du kit SDK .NET Core.
author: thraka
ms.author: adegeo
ms.date: 01/16/2019
dev_langs:
- csharp
- vb
ms.custom: seodec18
ms.openlocfilehash: cac6215afb34b5b2864284763eea59b33feb35fe
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826458"
---
# <a name="publish-net-core-apps-with-the-cli"></a>Publier des applications .NET Core avec l’interface CLI

Cet article montre comment vous pouvez publier votre application .NET Core à partir de la ligne de commande. .NET Core offre trois manières de publier des applications. Le déploiement dépendant du framework génère un fichier .dll multiplateforme qui utilise le runtime .NET Core installé localement. L’exécutable dépendant du framework génère un exécutable propre à la plateforme qui utilise le runtime .NET Core installé localement. L’exécutable autonome génère un exécutable propre à la plateforme et inclut une copie locale du runtime .NET Core.

Pour obtenir une vue d’ensemble de ces modes de publication, consultez [Déploiement d’applications .NET Core](index.md). 

Vous recherchez une aide rapide sur l’utilisation de l’interface CLI ? Le tableau suivant présente quelques exemples illustrant comment publier votre application. Vous pouvez spécifier le framework cible avec le paramètre `-f <TFM>` ou en modifiant le fichier projet. Pour plus d’informations, consultez [Principes de base de la publication](#publishing-basics).

| Mode de publication | Version du kit SDK | Commande |
| ------------ | ----------- | ------- |
| Déploiement dépendant du framework | 2.x | `dotnet publish -c Release` |
| Exécutable dépendant du framework | 2.2 | `dotnet publish -c Release -r <RID> --self-contained false` |
|                                | 3.0 | `dotnet publish -c Release -r <RID> --self-contained false` |
|                                | 3.0* | `dotnet publish -c Release` |
| Déploiement autonome      | 2.1 | `dotnet publish -c Release -r <RID> --self-contained true` |
|                                | 2.2 | `dotnet publish -c Release -r <RID> --self-contained true` |
|                                | 3.0 | `dotnet publish -c Release -r <RID> --self-contained true` |

>[!IMPORTANT]
>\*Quand vous utilisez un déploiement dépendant du framework avec la version 3.0 du SDK, il s’agit du mode de publication par défaut lors de l’exécution de la commande `dotnet publish` de base. Cela s’applique uniquement aux projets qui ciblent **.NET Core 2.1** ou **.NET Core 3.0**.

## <a name="publishing-basics"></a>Principes de base de la publication

Le paramètre `<TargetFramework>` du fichier projet spécifie le framework cible par défaut quand vous publiez votre application. Vous pouvez choisir comme framework cible n’importe quel [TFM (Target Framework Moniker)](../../standard/frameworks.md) valide. Par exemple, si votre projet utilise `<TargetFramework>netcoreapp2.2</TargetFramework>`, un binaire qui cible .NET Core 2.2 est créé. Le TFM spécifié dans ce paramètre est la cible par défaut utilisée par la commande [`dotnet publish`](../tools/dotnet-publish.md).

Si vous souhaitez cibler plusieurs frameworks, vous pouvez affecter au paramètre `<TargetFrameworks>` plusieurs valeurs de TFM séparées par un point-virgule. Vous pouvez publier l’un des frameworks avec la commande `dotnet publish -f <TFM>`. Par exemple, si vous avez `<TargetFrameworks>netcoreapp2.1;netcoreapp2.2</TargetFrameworks>` et que vous exécutez `dotnet publish -f netcoreapp2.1`, un binaire qui cible .NET Core 2.1 est créé.

Le répertoire de sortie de la commande [`dotnet publish`](../tools/dotnet-publish.md) est `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/`, sauf s’il est défini autrement. Le mode **BUILD-CONFIGURATION** par défaut est **Debug**, sauf si vous le modifiez avec le paramètre `-c`. Par exemple, `dotnet publish -c Release -f netcoreapp2.1` publie dans `myfolder/bin/Release/netcoreapp2.1/publish/`. 

Si vous utilisez le kit SDK .NET Core 3.0, le mode de publication par défaut pour les applications qui ciblent .NET Core version 2.1, 2.2 ou 3.0 est « Exécutable dépendant du framework ».

Si vous utilisez le kit SDK .NET Core 2.1, le mode de publication par défaut pour les applications qui ciblent .NET Core version 2.1 ou 2.2 est « Déploiement dépendant du framework ».

### <a name="native-dependencies"></a>Dépendances natives

Si votre application a des dépendances natives, elle risque de ne pas fonctionner sur un autre système d’exploitation. Par exemple, si votre application utilise l’API Win32 native, elle ne s’exécutera pas sur macOS ou Linux. Vous devrez fournir du code propre à la plateforme et compiler un exécutable pour chaque plateforme. 

Sachez également que si une bibliothèque que vous avez référencée a une dépendance native, votre application risque de ne pas fonctionner sur toutes les plateformes. Toutefois, il est possible qu’un package NuGet que vous référencez ait inclus des versions propres à la plateforme afin de gérer pour vous les dépendances natives requises.

Lors de la distribution d’une application avec des dépendances natives, vous devrez peut-être utiliser le commutateur `dotnet publish -r <RID>` afin de spécifier la plateforme cible pour laquelle vous souhaitez publier. Pour obtenir une liste des identificateurs de runtime, consultez [Catalogue d’identificateurs de runtime (RID)](../rid-catalog.md).

Vous trouverez davantage d’informations sur les binaires propres à la plateforme dans les sections [Exécutable dépendant du framework](#framework-dependent-executable) et [Déploiement autonome](#self-contained-deployment).

## <a name="sample-app"></a>Exemple d’application

Vous pouvez utiliser l’application ci-dessous pour explorer les commandes de publication. L’application est créée en exécutant les commandes suivantes dans votre terminal :

```dotnetcli
mkdir apptest1
cd apptest1
dotnet new console
dotnet add package Figgle
```

Le fichier `Program.cs` ou `Program.vb` généré par le modèle de console doit être modifié comme suit :

```csharp
using System;

namespace apptest1
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"));
        }
    }
}
```
```vb
Imports System

Module Program
    Sub Main(args As String())
        Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"))
    End Sub
End Module
```

Quand vous exécutez l’application ([`dotnet run`](../tools/dotnet-run.md)), la sortie suivante s’affiche :

```terminal
  _   _      _ _         __        __         _     _ _
 | | | | ___| | | ___    \ \      / /__  _ __| | __| | |
 | |_| |/ _ \ | |/ _ \    \ \ /\ / / _ \| '__| |/ _` | |
 |  _  |  __/ | | (_) |    \ V  V / (_) | |  | | (_| |_|
 |_| |_|\___|_|_|\___( )    \_/\_/ \___/|_|  |_|\__,_(_)
                     |/
```

## <a name="framework-dependent-deployment"></a>Déploiement dépendant du framework

Pour l’interface CLI du kit SDK .NET Core 2.x, le déploiement dépendant du framework est le mode par défaut pour la commande `dotnet publish` de base.

Quand vous publiez votre application en tant que déploiement dépendant du framework, un fichier `<PROJECT-NAME>.dll` est créé dans le dossier `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/`. Pour exécuter votre application, accédez au dossier de sortie et utilisez la commande `dotnet <PROJECT-NAME>.dll`.

Votre application est configurée pour cibler une version spécifique de .NET Core. Ce runtime .NET Core cible doit se trouver sur l’ordinateur où vous souhaitez exécuter votre application. Par exemple, si votre application cible .NET Core 2.2, le runtime .NET Core 2.2 doit être installé sur tout ordinateur sur lequel votre application s’exécute. Comme indiqué dans la section [Principes de base de la publication](#publishing-basics), vous pouvez modifier votre fichier projet afin de changer le framework cible par défaut ou de cibler plusieurs frameworks.

La publication d’un déploiement dépendant du framework crée une application qui extrapole automatiquement vers le dernier correctif de sécurité .NET Core disponible sur le système qui exécute l’application. Pour plus d’informations sur la liaison de version au moment de la compilation, consultez [Sélectionner la version .NET Core à utiliser](../versions/selection.md#framework-dependent-apps-roll-forward).

## <a name="framework-dependent-executable"></a>Exécutable dépendant du framework

Pour l’interface CLI du kit SDK .NET Core 3.x, l’exécutable dépendant du framework est le mode par défaut pour la commande `dotnet publish` de base. Vous n’avez pas besoin de spécifier d’autres paramètres tant que vous souhaitez cibler le système d’exploitation actuel.

Dans ce mode, un hôte d’exécutable propre à la plateforme est créé pour héberger votre application multiplateforme. Ce mode est semblable au déploiement dépendant du framework, étant donné que celui-ci nécessite un ordinateur hôte sous la forme de la commande `dotnet`. Le nom de fichier de l’exécutable hôte varie en fonction de la plateforme, et ressemble à `<PROJECT-FILE>.exe`. Vous pouvez exécuter cet exécutable directement au lieu d’appeler `dotnet <PROJECT-FILE>.dll`, qui constitue tout de même une manière acceptable d’exécuter l’application.

Votre application est configurée pour cibler une version spécifique de .NET Core. Ce runtime .NET Core cible doit se trouver sur l’ordinateur où vous souhaitez exécuter votre application. Par exemple, si votre application cible .NET Core 2.2, le runtime .NET Core 2.2 doit être installé sur tout ordinateur sur lequel votre application s’exécute. Comme indiqué dans la section [Principes de base de la publication](#publishing-basics), vous pouvez modifier votre fichier projet afin de changer le framework cible par défaut ou de cibler plusieurs frameworks.

La publication d’un exécutable dépendant du framework crée une application qui extrapole automatiquement vers le dernier correctif de sécurité .NET Core disponible sur le système qui exécute l’application. Pour plus d’informations sur la liaison de version au moment de la compilation, consultez [Sélectionner la version .NET Core à utiliser](../versions/selection.md#framework-dependent-apps-roll-forward).

Vous devez utiliser les commutateurs suivants avec la commande `dotnet publish` pour publier un exécutable dépendant du framework (sauf pour .NET Core 3.x quand vous ciblez la plateforme actuelle) :

- `-r <RID>`  
  Ce commutateur utilise un identificateur (RID) pour spécifier la plateforme cible. Pour obtenir une liste des identificateurs de runtime, consultez [Catalogue d’identificateurs de runtime (RID)](../rid-catalog.md).

- `--self-contained false`  
  Ce commutateur indique au kit SDK .NET Core qu’il faut créer un fichier exécutable dépendant du framework.

Quand vous utilisez le commutateur `-r`, le chemin du dossier de sortie devient : `./bin/<BUILD-CONFIGURATION>/<TFM>/<RID>/publish/`

Si vous utilisez l’[exemple d’application](#sample-app), exécutez `dotnet publish -f netcoreapp2.2 -r win10-x64 --self-contained false`. Cette commande crée l’exécutable suivant : `./bin/Debug/netcoreapp2.2/win10-x64/publish/apptest1.exe`

> [!Note]
> Vous pouvez réduire la taille totale de votre déploiement en activant le **mode invariant de globalisation**. Ce mode est utile pour les applications qui ne sont pas globalement compatibles et qui peuvent utiliser les conventions de mise en forme, les conventions de casse et la comparaison de chaînes, ainsi que l’ordre de tri de la [culture invariante](xref:System.Globalization.CultureInfo.InvariantCulture). Pour plus d’informations sur le **mode invariant de globalisation** et sur la façon de l’activer, consultez [.NET Core Globalization Invariant Mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).

## <a name="self-contained-deployment"></a>Déploiement autonome

Quand vous publiez un déploiement autonome, le kit SDK .NET Core crée un exécutable propre à la plateforme. La publication d’un déploiement autonome comprend tous les fichiers .NET Core nécessaires pour exécuter votre application, mais n’inclut pas les [dépendances natives de .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md). Ces dépendances doivent être présentes sur le système avant l’exécution de l’application. 

La publication d’un déploiement autonome crée une application qui n’extrapole pas vers la dernière version de correctif de sécurité .NET Core disponible. Pour plus d’informations sur la liaison de version au moment de la compilation, consultez [Sélectionner la version .NET Core à utiliser](../versions/selection.md#self-contained-deployments-include-the-selected-runtime).

Vous devez utiliser les commutateurs suivants avec la commande `dotnet publish` pour publier un déploiement autonome :

- `-r <RID>`  
  Ce commutateur utilise un identificateur (RID) pour spécifier la plateforme cible. Pour obtenir une liste des identificateurs de runtime, consultez [Catalogue d’identificateurs de runtime (RID)](../rid-catalog.md).

- `--self-contained true`  
  Ce commutateur indique au kit SDK .NET Core qu’il faut créer un exécutable en tant que déploiement autonome.

> [!Note]
> Vous pouvez réduire la taille totale de votre déploiement en activant le **mode invariant de globalisation**. Ce mode est utile pour les applications qui ne sont pas globalement compatibles et qui peuvent utiliser les conventions de mise en forme, les conventions de casse et la comparaison de chaînes, ainsi que l’ordre de tri de la [culture invariante](xref:System.Globalization.CultureInfo.InvariantCulture). Pour plus d’informations sur le **mode invariant de globalisation** et sur la façon de l’activer, consultez [.NET Core Globalization Invariant Mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).


## <a name="see-also"></a>Voir aussi

- [Déploiement d’applications .NET Core](index.md)
- [Catalogue d’identificateurs de runtime (RID) .NET Core](../rid-catalog.md)
