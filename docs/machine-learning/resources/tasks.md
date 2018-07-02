---
title: Tâches d’apprentissage automatique
description: Explorez les différentes tâches d’apprentissage automatique prises en charge dans ML.NET.
ms.date: 06/04/2018
author: aditidugar
ms.author: johalex
ms.openlocfilehash: 875006a9cddb87b5f9436b78773420858fd842dd
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207718"
---
# <a name="machine-learning-tasks"></a><span data-ttu-id="b714e-103">Tâches d’apprentissage automatique</span><span class="sxs-lookup"><span data-stu-id="b714e-103">Machine learning tasks</span></span>

<span data-ttu-id="b714e-104">Lorsque vous créez un modèle d’apprentissage automatique, vous devez tout d’abord définir ce que vous souhaitez obtenir avec vos données.</span><span class="sxs-lookup"><span data-stu-id="b714e-104">When building a machine learning model, you first need to define what you are hoping to achieve with your data.</span></span> <span data-ttu-id="b714e-105">Ensuite, vous pouvez choisir la tâche d’apprentissage automatique adaptée à votre situation.</span><span class="sxs-lookup"><span data-stu-id="b714e-105">After, you can pick the right machine learning task for your situation.</span></span> <span data-ttu-id="b714e-106">La liste suivante décrit les différentes tâches d’apprentissage automatique disponibles et présente certains cas d’usage courants.</span><span class="sxs-lookup"><span data-stu-id="b714e-106">The following list describes the different machine learning tasks that you can choose from and some common use cases.</span></span> 

> [!NOTE]
> <span data-ttu-id="b714e-107">ML.NET est actuellement en préversion.</span><span class="sxs-lookup"><span data-stu-id="b714e-107">ML.NET is currently in Preview.</span></span> <span data-ttu-id="b714e-108">Actuellement, les tâches d’apprentissage automatique ne sont pas toutes prises en charge.</span><span class="sxs-lookup"><span data-stu-id="b714e-108">Not all machine learning tasks are currently supported.</span></span> <span data-ttu-id="b714e-109">Pour envoyer une requête pour une tâche particulière, signalez un problème dans le [référentiel dotnet/machinelearning](https://github.com/dotnet/machinelearning/issues).</span><span class="sxs-lookup"><span data-stu-id="b714e-109">To submit a request for a certain task, open an issue in the [dotnet/machinelearning repository](https://github.com/dotnet/machinelearning/issues).</span></span>

> [!NOTE]
> <span data-ttu-id="b714e-110">Actuellement, ML.NET ne prend pas en charge les tâches d’apprentissage automatique avec des images.</span><span class="sxs-lookup"><span data-stu-id="b714e-110">Currently, ML.NET does not support machine learning tasks with images.</span></span> <span data-ttu-id="b714e-111">Cette prise en charge sera ajoutée aux prochaines versions.</span><span class="sxs-lookup"><span data-stu-id="b714e-111">Support will be added in future releases.</span></span> 

## <a name="binary-classification"></a><span data-ttu-id="b714e-112">Classification binaire</span><span class="sxs-lookup"><span data-stu-id="b714e-112">Binary classification</span></span>

<span data-ttu-id="b714e-113">Une tâche [Apprentissage automatique supervisé](glossary.md#supervised-machine-learning) utilisée pour prédire à laquelle des deux classes (catégories) appartient une instance de données.</span><span class="sxs-lookup"><span data-stu-id="b714e-113">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict which of two classes (categories) an instance of data belongs to.</span></span> <span data-ttu-id="b714e-114">L’entrée d’un algorithme de classification est un ensemble d’exemples étiquetés, où chaque étiquette est un entier ayant pour valeur 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="b714e-114">The input of a classification algorithm is a set of labeled examples, where each label is an integer of either 0 or 1.</span></span> <span data-ttu-id="b714e-115">La sortie d’un algorithme de classification binaire est un classifieur, que vous pouvez utiliser pour prédire la classe de nouvelles instances sans étiquette.</span><span class="sxs-lookup"><span data-stu-id="b714e-115">The output of a binary classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="b714e-116">Voici quelques exemples de scénarios de classification binaire :</span><span class="sxs-lookup"><span data-stu-id="b714e-116">Examples of binary classification scenarios include:</span></span>

* <span data-ttu-id="b714e-117">[Déterminer si des commentaires Twitter](../tutorials/sentiment-analysis.md) sont « positifs » ou « négatifs ».</span><span class="sxs-lookup"><span data-stu-id="b714e-117">[Understanding sentiment of Twitter comments](../tutorials/sentiment-analysis.md) as either "positive" or "negative".</span></span>
* <span data-ttu-id="b714e-118">Diagnostiquer si un patient est atteint ou non d’une certaine maladie.</span><span class="sxs-lookup"><span data-stu-id="b714e-118">Diagnosing whether a patient has a certain disease or not.</span></span>
* <span data-ttu-id="b714e-119">Décider si un e-mail doit être considéré comme « spam » ou non.</span><span class="sxs-lookup"><span data-stu-id="b714e-119">Making a decision to mark an email as "spam" or not.</span></span>

<span data-ttu-id="b714e-120">Pour plus d’informations, consultez l’article Wikipédia [Classification binaire](https://en.wikipedia.org/wiki/Binary_classification).</span><span class="sxs-lookup"><span data-stu-id="b714e-120">For more information, see the [Binary classification](https://en.wikipedia.org/wiki/Binary_classification) article on Wikipedia.</span></span>

## <a name="multiclass-classification"></a><span data-ttu-id="b714e-121">Classification multiclasse</span><span class="sxs-lookup"><span data-stu-id="b714e-121">Multiclass classification</span></span>

<span data-ttu-id="b714e-122">Une tâche [Apprentissage automatique supervisé](glossary.md#supervised-machine-learning) utilisée pour prédire la classe (catégorie) d’une instance de données.</span><span class="sxs-lookup"><span data-stu-id="b714e-122">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the class (category) of an instance of data.</span></span> <span data-ttu-id="b714e-123">L’entrée d’un algorithme de classification est un ensemble d’exemples étiquetés.</span><span class="sxs-lookup"><span data-stu-id="b714e-123">The input of a classification algorithm is a set of labeled examples.</span></span> <span data-ttu-id="b714e-124">Chaque étiquette est un entier compris entre 0 et k-1, où k est le nombre de classes.</span><span class="sxs-lookup"><span data-stu-id="b714e-124">Each label is an integer between 0 and k-1, where k is the number of classes.</span></span> <span data-ttu-id="b714e-125">La sortie d’un algorithme de classification est un classifieur, que vous pouvez utiliser pour prédire la classe de nouvelles instances sans étiquette.</span><span class="sxs-lookup"><span data-stu-id="b714e-125">The output of a classification algorithm is a classifier, which you can use to predict the class of new unlabeled instances.</span></span> <span data-ttu-id="b714e-126">Voici quelques exemples de scénarios de classification multiclasse :</span><span class="sxs-lookup"><span data-stu-id="b714e-126">Examples of multi-class classification scenarios include:</span></span>

* <span data-ttu-id="b714e-127">Déterminer la race d’un chien, par exemple « Husky de Sibérie », « Golden Retriever », « Caniche », etc.</span><span class="sxs-lookup"><span data-stu-id="b714e-127">Determining the breed of a dog as a "Siberian Husky", "Golden Retriever", "Poodle", etc.</span></span>
* <span data-ttu-id="b714e-128">Déterminer si des critiques d’un film sont « positives », « neutres » ou « négatives ».</span><span class="sxs-lookup"><span data-stu-id="b714e-128">Understanding movie reviews as "positive", "neutral", or "negative".</span></span>
* <span data-ttu-id="b714e-129">Classer les évaluations d’un hôtel par « situation géographique », « prix », « propreté », etc.</span><span class="sxs-lookup"><span data-stu-id="b714e-129">Categorizing hotel reviews as "location", "price", "cleanliness", etc.</span></span>

<span data-ttu-id="b714e-130">Pour plus d’informations, consultez l’article Wikipédia [Classification multiclasse](https://en.wikipedia.org/wiki/Multiclass_classification).</span><span class="sxs-lookup"><span data-stu-id="b714e-130">For more information, see the [Multiclass classification](https://en.wikipedia.org/wiki/Multiclass_classification) article on Wikipedia.</span></span>

## <a name="regression"></a><span data-ttu-id="b714e-131">Régression</span><span class="sxs-lookup"><span data-stu-id="b714e-131">Regression</span></span>

<span data-ttu-id="b714e-132">Une tâche [Apprentissage automatique supervisée](glossary.md#supervised-machine-learning) utilisée pour prédire la valeur de l’étiquette d’un ensemble de fonctionnalités connexes.</span><span class="sxs-lookup"><span data-stu-id="b714e-132">A [supervised machine learning](glossary.md#supervised-machine-learning) task that is used to predict the value of the label from a set of related features.</span></span> <span data-ttu-id="b714e-133">L’étiquette peut avoir n’importe quelle valeur réelle et ne provient pas d’un ensemble fini de valeurs comme dans les tâches de classification.</span><span class="sxs-lookup"><span data-stu-id="b714e-133">The label can be of any real value and is not from a finite set of values as in classification tasks.</span></span> <span data-ttu-id="b714e-134">Les algorithmes de régression modèlent la dépendance de l’étiquette sur ses fonctionnalités connexes pour déterminer la façon dont l’étiquette change avec des valeurs de fonctionnalités différentes.</span><span class="sxs-lookup"><span data-stu-id="b714e-134">Regression algorithms model the dependency of the label on its related features to determine how the label will change as the values of the features are varied.</span></span> <span data-ttu-id="b714e-135">L’entrée d’un algorithme de régression est un ensemble d’exemples avec des étiquettes de valeurs connues.</span><span class="sxs-lookup"><span data-stu-id="b714e-135">The input of a regression algorithm is a set of examples with labels of known values.</span></span> <span data-ttu-id="b714e-136">La sortie d’un algorithme de régression est une fonction, que vous pouvez utiliser pour prédire la valeur de l’étiquette pour tout nouvel ensemble de fonctionnalités d’entrée.</span><span class="sxs-lookup"><span data-stu-id="b714e-136">The output of a regression algorithm is a function, which you can use to predict the label value for any new set of input features.</span></span> <span data-ttu-id="b714e-137">Voici quelques exemples de scénarios de régression :</span><span class="sxs-lookup"><span data-stu-id="b714e-137">Examples of regression scenarios include:</span></span>

* <span data-ttu-id="b714e-138">Prédire le prix d’une maison selon ses attributs, par exemple le nombre de chambres, l’emplacement ou la taille.</span><span class="sxs-lookup"><span data-stu-id="b714e-138">Predicting house prices based on house attributes such as number of bedrooms, location, or size.</span></span>
* <span data-ttu-id="b714e-139">Prédire le cours d’actions en fonction de données historiques et des tendances du marché actuel.</span><span class="sxs-lookup"><span data-stu-id="b714e-139">Predicting future stock prices based on historical data and current market trends.</span></span>
* <span data-ttu-id="b714e-140">Prédire les ventes d’un produit en fonction d’un budget publicitaire.</span><span class="sxs-lookup"><span data-stu-id="b714e-140">Predicting sales of a product based on advertising budgets.</span></span>

> [!NOTE]
> <span data-ttu-id="b714e-141">ML.NET prépare actuellement la prise en charge des tâches de régression qui impliquent des séries chronologiques.</span><span class="sxs-lookup"><span data-stu-id="b714e-141">Currently, ML.NET is still building support for regression tasks that involve time series.</span></span>

## <a name="clustering"></a><span data-ttu-id="b714e-142">Clustering</span><span class="sxs-lookup"><span data-stu-id="b714e-142">Clustering</span></span>

<span data-ttu-id="b714e-143">Une tâche [Apprentissage automatique non supervisé](glossary.md#unsupervised-machine-learning) utilisée pour regrouper des instances de données dans des clusters contenant des caractéristiques similaires.</span><span class="sxs-lookup"><span data-stu-id="b714e-143">An [unsupervised machine learning](glossary.md#unsupervised-machine-learning) task that is used to group instances of data into clusters that contain similar characteristics.</span></span> <span data-ttu-id="b714e-144">Le clustering permet également d’identifier, dans un jeu de données, les relations qui peuvent ne pas être logiquement dérivées par navigation ou simple observation.</span><span class="sxs-lookup"><span data-stu-id="b714e-144">Clustering can also be used to identify relationships in a dataset that you might not logically derive by browsing or simple observation.</span></span> <span data-ttu-id="b714e-145">Les entrées et sorties d’un algorithme de clustering dépendent de la méthode choisie.</span><span class="sxs-lookup"><span data-stu-id="b714e-145">The inputs and outputs of a clustering algorithm depends on the methodology chosen.</span></span> <span data-ttu-id="b714e-146">Vous pouvez adopter une approche de type distribution, centroïde, connectivité ou basée sur la densité.</span><span class="sxs-lookup"><span data-stu-id="b714e-146">You can take a distribution, centroid, connectivity, or density-based approach.</span></span> <span data-ttu-id="b714e-147">ML.NET prend actuellement en charge une approche de type centroïde à l’aide du clustering K-Means.</span><span class="sxs-lookup"><span data-stu-id="b714e-147">ML.NET currently supports a centroid-based approach using K-Means clustering.</span></span> <span data-ttu-id="b714e-148">Voici quelques exemples de scénarios de clustering :</span><span class="sxs-lookup"><span data-stu-id="b714e-148">Examples of clustering scenarios include:</span></span>

* <span data-ttu-id="b714e-149">Évaluer les segments d’une clientèle d’hôtel en fonction de leurs habitudes et des caractéristiques de l’hôtel.</span><span class="sxs-lookup"><span data-stu-id="b714e-149">Understanding segments of hotel guests based on habits and characteristics of hotel choices.</span></span>
* <span data-ttu-id="b714e-150">Identifier les segments d’une clientèle et les données démographiques pour faciliter la mise en œuvre de campagnes publicitaires ciblées.</span><span class="sxs-lookup"><span data-stu-id="b714e-150">Identifying customer segments and demographics to help build targeted advertising campaigns.</span></span>
* <span data-ttu-id="b714e-151">Classer un inventaire en fonction de métriques de fabrication.</span><span class="sxs-lookup"><span data-stu-id="b714e-151">Categorizing inventory based on manufacturing metrics.</span></span>

## <a name="anomaly-detection-coming-soon"></a><span data-ttu-id="b714e-152">Détection d’anomalie (*bientôt disponible*)</span><span class="sxs-lookup"><span data-stu-id="b714e-152">Anomaly detection (*coming soon*)</span></span>

## <a name="ranking-coming-soon"></a><span data-ttu-id="b714e-153">Classement (*bientôt disponible*)</span><span class="sxs-lookup"><span data-stu-id="b714e-153">Ranking (*coming soon*)</span></span>

## <a name="recommendation-coming-soon"></a><span data-ttu-id="b714e-154">Suggestion (*bientôt disponible*)</span><span class="sxs-lookup"><span data-stu-id="b714e-154">Recommendation (*coming soon*)</span></span>
