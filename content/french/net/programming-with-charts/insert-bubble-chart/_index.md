---
title: Insérer un graphique à bulles dans un document Word
linktitle: Insérer un graphique à bulles dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer un graphique à bulles dans un document à l'aide d'Aspose.Words pour .NET. Ajoutez des données de série avec des valeurs X, Y et de taille de bulle.
type: docs
weight: 10
url: /fr/net/programming-with-charts/insert-bubble-chart/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour insérer un graphique à bulles dans un document. Le code source fourni montre comment créer un graphique, ajouter des données de série et enregistrer le document.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des prérequis suivants :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger en utilisant le gestionnaire de packages NuGet pour l'installer.
- Un chemin d'accès au répertoire de documents où le document de sortie sera enregistré.

## Étape 2 : Créer un nouveau document et insérer un graphique

 Créer un nouveau`Document` objet et un`DocumentBuilder` pour construire le document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ensuite, utilisez le`InsertChart` méthode de la`DocumentBuilder` pour insérer un graphique à bulles dans le document.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous allons ajouter trois points de données avec les valeurs X, Y et de taille de bulle correspondantes.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

Ceci termine l'implémentation de l'insertion d'un graphique à bulles à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Insérer un graphique à bulles en utilisant Aspose.Words pour .NET 

```csharp
//Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## Conclusion

Dans ce didacticiel, vous avez appris à insérer un graphique à bulles dans un document Word à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un nouveau document, insérer un graphique à bulles, ajouter des données de série et enregistrer le document avec le graphique.

Aspose.Words pour .NET fournit une API puissante pour le traitement de mots avec des graphiques dans des documents Word. Les graphiques à bulles sont idéaux pour visualiser des données en trois dimensions, où chaque point de données est représenté par une bulle avec des coordonnées X et Y et une valeur de taille. Avec Aspose.Words pour .NET, vous pouvez créer des graphiques à bulles dynamiques et informatifs qui améliorent la représentation visuelle de vos données.

En utilisant Aspose.Words pour .NET, vous pouvez automatiser le processus de génération de documents avec des graphiques à bulles, ce qui vous permet d'économiser du temps et des efforts lors de la création manuelle de documents. La bibliothèque offre une large gamme de types de graphiques et d'options de personnalisation, vous permettant de créer des graphiques visuellement attrayants et riches en données dans vos documents Word.

### FAQ

#### Q1. Qu'est-ce qu'un graphique à bulles ?
Un graphique à bulles est un type de graphique qui affiche des données tridimensionnelles à l'aide de bulles ou de sphères. Chaque point de données est représenté par une bulle, où les coordonnées X et Y déterminent la position de la bulle sur le graphique, et la taille de la bulle représente la troisième dimension des données. Les graphiques à bulles sont utiles pour visualiser les relations et les modèles entre plusieurs variables.

#### Q2. Puis-je ajouter plusieurs séries au graphique à bulles ?
Oui, vous pouvez ajouter plusieurs séries au graphique à bulles en utilisant Aspose.Words pour .NET. Chaque série représente un ensemble de points de données avec leurs valeurs X, Y et de taille de bulle respectives. En ajoutant plusieurs séries, vous pouvez comparer et analyser différents ensembles de données dans le même graphique, offrant ainsi une vue complète de vos données.

#### Q3. Puis-je personnaliser l'apparence du graphique à bulles ?
Oui, en utilisant Aspose.Words pour .NET, vous pouvez personnaliser divers aspects de l'apparence du graphique à bulles. Vous pouvez modifier des propriétés telles que la couleur des séries, la taille des bulles, les étiquettes des axes et la mise en forme de la zone du graphique. La bibliothèque fournit un riche ensemble d'API pour contrôler les éléments visuels du graphique et créer un aspect personnalisé qui répond à vos besoins.

#### Q4. Puis-je enregistrer le document avec le graphique à bulles inséré dans différents formats ?
Oui, Aspose.Words pour .NET vous permet d'enregistrer le document avec le graphique à bulles inséré dans différents formats, tels que DOCX, PDF, HTML, etc. Vous pouvez choisir le format de sortie souhaité en fonction de vos besoins et utiliser le`Save` méthode de la`Document` objet pour enregistrer le document. Le graphique à bulles inséré sera conservé dans le document enregistré.

#### Q5. Puis-je modifier les données et l'apparence du graphique à bulles après l'avoir inséré ?
Oui, après avoir inséré le graphique à bulles dans le document, vous pouvez modifier ses données et son apparence à l'aide des API fournies par Aspose.Words pour .NET. Vous pouvez mettre à jour les données de la série, modifier la taille des bulles, personnaliser les propriétés des axes et appliquer des options de mise en forme pour créer des graphiques dynamiques et interactifs dans vos documents Word.