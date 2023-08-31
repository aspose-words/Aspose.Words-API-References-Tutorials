---
title: Définir les propriétés de l'axe XY dans un graphique
linktitle: Définir les propriétés de l'axe XY dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Apprenez à définir les propriétés de l'axe XY dans un graphique à l'aide de Aspose.Words pour .NET. Les options de personnalisation pour les axes X et Y sont démontrées.
type: docs
weight: 10
url: /fr/net/programming-with-charts/define-xyaxis-properties/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour définir les propriétés des axes X et Y dans un graphique. Le code source fourni montre comment créer un graphique, ajouter des données de série et personnaliser les propriétés de l'axe.

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

 Ensuite, insérez un graphique dans le document à l'aide de la`InsertChart` méthode de la`DocumentBuilder`. Dans cet exemple, nous allons insérer un graphique en aires.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous ajouterons cinq points de données avec les dates et les valeurs correspondantes.

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

## Étape 4 : Personnalisez les propriétés des axes X et Y

 Pour personnaliser les propriétés des axes X et Y, accédez au`ChartAxis` objets associés au graphique.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Modifier les propriétés du`xAxis` et`yAxis`objets pour définir les options souhaitées pour les axes X et Y. Dans cet exemple, nous allons démontrer certaines propriétés communes qui peuvent être personnalisées.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Étape 5 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Ceci termine l'implémentation de la définition des propriétés de l'axe XY dans un graphique à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour définir les propriétés de l'axe XYAxis à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Insérer un graphique
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Modifiez l'axe X pour qu'il soit catégorie au lieu de date, de sorte que tous les points seront placés avec un intervalle égal sur l'axe X.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; // Mesuré en unités d'affichage de l'axe Y (centaines).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Conclusion

Dans ce didacticiel, vous avez appris à définir les propriétés des axes X et Y dans un graphique à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape, vous pouvez créer un graphique, ajouter des données de série et personnaliser les propriétés de l'axe pour répondre à vos besoins spécifiques. Aspose.Words pour .NET fournit une API complète pour le traitement de mots avec des graphiques dans des documents Word, vous permettant de manipuler divers aspects du graphique, y compris les axes.

 En accédant au`ChartAxis` objets associés au graphique, vous pouvez modifier des propriétés telles que le type de catégorie, les croix d'axe, les graduations, les positions des étiquettes, la mise à l'échelle, etc. Cette flexibilité vous permet de personnaliser l'apparence et le comportement des axes du graphique pour présenter efficacement vos données.

En utilisant Aspose.Words pour .NET, vous pouvez intégrer de manière transparente des fonctionnalités de création et de personnalisation de graphiques dans vos applications .NET et automatiser la génération de documents d'aspect professionnel avec des visualisations riches.

### FAQ

#### Q1. Qu'est-ce qu'Aspose.Words pour .NET ?
Aspose.Words pour .NET est une puissante bibliothèque de traitement de documents qui permet aux développeurs de créer, manipuler et enregistrer des documents Word par programme dans des applications .NET. Il fournit un large éventail de fonctionnalités pour le traitement de texte avec des éléments de document, y compris des graphiques.

#### Q2. Comment puis-je installer Aspose.Words pour .NET ?
Vous pouvez installer Aspose.Words pour .NET en le téléchargeant à l'aide du gestionnaire de packages NuGet dans Visual Studio. Recherchez simplement "Aspose.Words" dans le gestionnaire de packages NuGet et installez-le dans votre projet.

#### Q3. Puis-je personnaliser d'autres aspects du graphique à l'aide d'Aspose.Words pour .NET ?
Oui, Aspose.Words pour .NET fournit des fonctionnalités étendues pour personnaliser divers aspects d'un graphique. En plus de définir les propriétés des axes, vous pouvez modifier le type de graphique, les séries de données, la légende, le titre, la zone de tracé, les étiquettes de données et de nombreux autres éléments du graphique. L'API offre un contrôle précis sur l'apparence et le comportement des graphiques.

#### Q4. Puis-je créer différents types de graphiques en utilisant Aspose.Words pour .NET ?
Oui, Aspose.Words pour .NET prend en charge un large éventail de types de graphiques, notamment les aires, les barres, les lignes, les secteurs, les nuages de points, etc. Vous pouvez utiliser le`ChartType` énumération pour spécifier le type de graphique souhaité lors de l'insertion d'une forme de graphique dans un document Word.

#### Q5. Puis-je enregistrer le graphique dans différents formats ?
 Oui, Aspose.Words pour .NET vous permet d'enregistrer le document contenant le graphique dans différents formats, tels que DOCX, PDF, HTML, etc. Vous pouvez choisir le format approprié en fonction de vos besoins et utiliser le`Save` méthode de la`Document` objet pour enregistrer le document.

#### Q6. Puis-je appliquer ces techniques à plusieurs graphiques dans un document ?
 Oui, vous pouvez appliquer ces techniques à plusieurs graphiques dans un document en répétant les étapes nécessaires pour chaque graphique. Vous pouvez créer séparément`Chart` et`ChartAxis` objets pour chaque graphique et personnalisez leurs propriétés en conséquence. Aspose.Words pour .NET offre une prise en charge complète du traitement de mots avec plusieurs graphiques dans un seul document.