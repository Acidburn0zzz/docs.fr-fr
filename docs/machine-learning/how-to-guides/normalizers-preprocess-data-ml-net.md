---
title: Prétraiter les données d’entraînement avec des normaliseurs pour les utiliser dans le traitement des données - ML.NET
description: Découvrez comment utiliser des normaliseurs pour prétraiter les données d’entraînement à utiliser dans la création, l’entraînement et le scoring de modèles Machine Learning avec ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 2d18f7c19a51fd929ac6efb7f600cb1ac2733de8
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676601"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a>Prétraiter les données d’entraînement avec des normaliseurs pour les utiliser dans le traitement des données - ML.NET

> [!NOTE]
> Cette rubrique fait référence à ML.NET, actuellement en préversion, et les ressources sont susceptibles d’être modifiées. Pour plus d’informations, consultez [l’introduction à ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Ce guide pratique et l’exemple associé utilisent actuellement **ML.NET version 0.10**. Pour plus d’informations, voir les notes de publication dans le référentiel GitHub [dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

ML.NET expose plusieurs [algorithmes paramétriques et non paramétriques](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/).

Le choix du normaliseur que vous choisissez d’utiliser est **moins** important que celui d’**utiliser** un normaliseur lors de l’entraînement de modèles linéaires ou d’autres modèles paramétriques.

Ajoutez toujours le normaliseur directement dans le pipeline d’entraînement de ML.NET, pour :

- L’entraîner seulement sur les données d’entraînement et non pas sur vos données de test
- L’appliquer correctement à toutes les nouvelles données entrantes, sans nécessiter de prétraitement supplémentaire au moment de la prédiction.

Voici un extrait de code qui montre la normalisation dans les pipelines d’apprentissage. Il suppose l’existence du jeu de données Iris :

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features",DataKind.R4,0,3),
        // Label: kind of iris.
        new TextLoader.Column("Label",DataKind.TX,4)
    },
    // Default separator is tab, but the dataset has comma.
    separatorChar: ',',
    // First line of the file is a header, not a data row.
    hasHeader: true
);

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
            new NormalizingEstimator.MinMaxColumn(inputColumnName:"Features", outputColumnName:"MinMaxNormalized", fixZero: true),
            new NormalizingEstimator.MeanVarColumn(inputColumnName: "Features", outputColumnName: "MeanVarNormalized", fixZero: true),
            new NormalizingEstimator.BinningColumn(inputColumnName: "Features", outputColumnName: "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
