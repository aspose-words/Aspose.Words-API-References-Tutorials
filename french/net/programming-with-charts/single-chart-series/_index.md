---
title: Série de graphiques uniques
linktitle: Série de graphiques uniques
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à personnaliser une seule série de graphiques dans un graphique à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/single-chart-series/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour personnaliser une seule série de graphiques dans un graphique. Le code source fourni montre comment créer un graphique, accéder à des séries spécifiques et modifier leurs propriétés.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des prérequis suivants :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser le gestionnaire de packages NuGet pour l'installer.
- Un chemin d'accès au répertoire de documents où le document de sortie sera enregistré.

## Étape 2 : Créer un nouveau document et insérer un graphique

 Créer un nouveau`Document` objet et un`DocumentBuilder` pour construire le document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ensuite, utilisez le`InsertChart` méthode de la`DocumentBuilder` pour insérer un graphique en courbes dans le document.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Accédez aux séries de graphiques et personnalisez-les

 Pour modifier une seule série de graphiques, vous devez accéder au`ChartSeries` objets du graphique.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Ceci termine l'implémentation de la personnalisation d'une seule série de graphiques à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour une série de graphiques uniques utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// Vous pouvez également spécifier si la ligne reliant les points sur le graphique doit être lissée à l'aide de splines Catmull-Rom.
	series0.Smooth = true;
	series1.Smooth = true;
	// Spécifie si par défaut l'élément parent doit inverser ses couleurs si la valeur est négative.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```