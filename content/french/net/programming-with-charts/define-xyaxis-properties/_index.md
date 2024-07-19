---
title: Définir les propriétés de l'axe XY dans un graphique
linktitle: Définir les propriétés de l'axe XY dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir les propriétés de l'axe XY dans un graphique à l'aide d'Aspose.Words for .NET avec ce guide étape par étape. Parfait pour les développeurs .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/define-xyaxis-properties/
---
## Introduction

Les graphiques sont un outil puissant pour visualiser les données. Lorsque vous devez créer des documents professionnels avec des graphiques dynamiques, Aspose.Words for .NET est une bibliothèque inestimable. Cet article vous guidera tout au long du processus de définition des propriétés de l'axe XY dans un graphique à l'aide d'Aspose.Words for .NET, en décomposant chaque étape pour garantir la clarté et la facilité de compréhension.

## Conditions préalables

Avant de vous lancer dans le codage, vous devez mettre en place quelques prérequis :

1. Aspose.Words for .NET : assurez-vous de disposer de la bibliothèque Aspose.Words for .NET. Tu peux[Télécharger les ici](https://releases.aspose.com/words/net/).
2. Environnement de développement : vous avez besoin d'un environnement de développement intégré (IDE) comme Visual Studio.
3. .NET Framework : assurez-vous que votre environnement de développement est configuré pour le développement .NET.
4. Connaissance de base de C# : ce guide suppose que vous possédez une compréhension de base de la programmation C#.

## Importer des espaces de noms

Pour commencer, vous devez importer les espaces de noms nécessaires dans votre projet. Cela garantit que vous avez accès à toutes les classes et méthodes requises pour créer et manipuler des documents et des graphiques.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

Nous décomposerons le processus en étapes simples, chacune se concentrant sur une partie spécifique de la définition des propriétés de l'axe XY dans un graphique.

## Étape 1 : initialiser le document et DocumentBuilder

 Tout d'abord, vous devez initialiser un nouveau document et un`DocumentBuilder` objet. Le`DocumentBuilder` aide à insérer du contenu dans le document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Insérer un graphique

Ensuite, vous allez insérer un graphique dans le document. Dans cet exemple, nous utiliserons un graphique en aires. Vous pouvez personnaliser les dimensions du graphique selon vos besoins.

```csharp
// Insérer un graphique
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Effacer la série par défaut et ajouter des données personnalisées

Par défaut, le graphique aura des séries prédéfinies. Nous allons les effacer et ajouter notre série de données personnalisées.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
	new DateTime[]
	{
		new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
		new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
	},
	new double[] { 640, 320, 280, 120, 150 });
```

## Étape 4 : Définir les propriétés de l'axe X

Il est maintenant temps de définir les propriétés de l'axe X. Cela inclut la définition du type de catégorie, la personnalisation du croisement des axes et l’ajustement des graduations et des étiquettes.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3; //Mesuré en unités d'affichage de l'axe Y (centaines).
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;
```

## Étape 5 : Définir les propriétés de l'axe Y

De même, vous définirez les propriétés de l’axe Y. Cela inclut la définition de la position de l'étiquette de graduation, des unités majeures et mineures, de l'unité d'affichage et de la mise à l'échelle.

```csharp
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Étape 6 : Enregistrez le document

Enfin, enregistrez le document dans le répertoire spécifié. Cela générera le document Word avec le graphique personnalisé.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Conclusion

La création et la personnalisation de graphiques dans des documents Word à l'aide d'Aspose.Words pour .NET sont simples une fois que vous avez compris les étapes à suivre. Ce guide vous a accompagné tout au long du processus de définition des propriétés de l'axe XY dans un graphique, depuis l'initialisation du document jusqu'à l'enregistrement du produit final. Grâce à ces compétences, vous pouvez créer des graphiques détaillés d’aspect professionnel qui améliorent vos documents.

## FAQ

### Quels types de graphiques puis-je créer avec Aspose.Words pour .NET ?
Vous pouvez créer différents types de graphiques, notamment à aires, à barres, à courbes, à secteurs, etc.

### Comment installer Aspose.Words pour .NET ?
 Vous pouvez télécharger Aspose.Words pour .NET à partir de[ici](https://releases.aspose.com/words/net/) et suivez les instructions d'installation fournies.

### Puis-je personnaliser l'apparence de mes graphiques ?
Oui, Aspose.Words for .NET permet une personnalisation étendue des graphiques, notamment les couleurs, les polices et les propriétés des axes.

### Existe-t-il un essai gratuit disponible pour Aspose.Words pour .NET ?
 Oui, vous pouvez bénéficier d'un essai gratuit[ici](https://releases.aspose.com/).

### Où puis-je trouver plus de tutoriels et de documentation ?
 Vous pouvez trouver plus de tutoriels et une documentation détaillée sur le[Page de documentation Aspose.Words pour .NET](https://reference.aspose.com/words/net/).
