---
title: Charger des données avec de nombreuses colonnes à partir d’un fichier CSV pour le traitement Machine Learning ML.NET
description: Découvrez comment charger des données à partir de plusieurs colonnes d’un fichier CSV pour les utiliser lors de la création, l’entraînement et le scoring de modèles Machine Learning avec ML.NET.
ms.date: 01/29/2019
ms.custom: mvc,how-to
ms.openlocfilehash: a06d7edfb4746a39377116b15903b68f8723cb02
ms.sourcegitcommit: dcc8feeff4718664087747529638ec9b47e65234
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/31/2019
ms.locfileid: "55479709"
---
# <a name="load-data-with-many-columns-from-a-csv-file-for-machine-learning-processing---mlnet"></a>Charger des données avec de nombreuses colonnes à partir d’un fichier CSV pour le traitement Machine Learning ML.NET

`TextLoader` sert à charger des données à partir de fichiers texte. Vous devez spécifier les colonnes de données, leurs types et leur emplacement dans le fichier texte.

Lorsque le fichier d’entrée contient plusieurs colonnes du même type et toujours utilisées ensemble, lisez-les comme une *colonne du vecteur*. Cette stratégie génère un schéma de données sain et évite les coûts qu’entraînent des performances inutiles, comme indiqué dans l’exemple suivant :

[Exemple de fichier](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv) :

```console
-2.75;0.77;-0.61;0.14;1.39;0.38;-0.53;-0.50;-2.13;-0.39;0.46;140.66
-0.61;-0.37;-0.12;0.55;-1.00;0.84;-0.02;1.30;-0.24;-0.50;-2.12;148.12
-0.85;-0.91;1.81;0.02;-0.78;-1.41;-1.09;-0.65;0.90;-0.37;-0.22;402.20
0.28;1.05;-0.24;0.30;-0.99;0.19;0.32;-0.95;-1.19;-0.63;0.75;443.51
```

Lecture de ce fichier à l’aide de `TextLoader`:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextReader(
    columns: new TextLoader.Column[]
    {
    // We read the first 10 values as a single float vector.
        new TextLoader.Column("FeatureVector",DataKind.R4,0,9),
        // Separately, read the target variable.
        new TextLoader.Column("Target",DataKind.R4,10)
    },
    // Default separator is tab, but we need a semicolon.
    separatorChar: ';',
    hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(dataPath);
```    