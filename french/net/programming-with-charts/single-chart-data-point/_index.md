---
title: Personnaliser un seul point de données de graphique dans un graphique
linktitle: Personnaliser un seul point de données de graphique dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Apprenez à personnaliser un seul point de données dans un graphique à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/single-chart-data-point/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour personnaliser un seul point de données dans un graphique. Le code source fourni montre comment créer un graphique, accéder à des points de données spécifiques et modifier leurs propriétés.

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

 Ensuite, utilisez le`InsertChart` méthode de la`DocumentBuilder` pour insérer un graphique en courbes dans le document.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Accéder aux points de données et les personnaliser

 Pour modifier des points de données individuels, vous devez accéder au`ChartDataPointCollection` de la série et sélectionnez le point de données souhaité à l'aide de l'index.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

Ceci termine l'implémentation de la personnalisation d'un seul point de données dans un graphique à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour un point de données de graphique unique utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Conclusion

Dans ce didacticiel, vous avez appris à personnaliser un seul point de données dans un graphique à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un nouveau document, insérer un graphique linéaire, accéder à des points de données spécifiques dans la série de graphiques et modifier leurs propriétés pour obtenir la personnalisation souhaitée.

Aspose.Words pour .NET fournit des fonctionnalités puissantes pour manipuler des graphiques dans des documents Word. En accédant à des points de données individuels dans une série de graphiques, vous pouvez appliquer des modifications spécifiques pour personnaliser leur apparence et leur comportement. Cela vous permet de mettre en évidence des points de données spécifiques, de modifier les symboles de marqueur, d'ajuster la taille des marqueurs, etc., pour améliorer la représentation visuelle de votre graphique.

La personnalisation de points de données individuels vous donne la possibilité de mettre en évidence des données importantes ou de mettre en évidence des tendances spécifiques dans votre graphique. Avec Aspose.Words pour .NET, vous pouvez facilement accéder et modifier des points de données dans différents types de graphiques, ce qui vous permet de créer des graphiques visuellement attrayants et informatifs dans vos documents Word.

### FAQ

#### Q1. Puis-je personnaliser plusieurs points de données dans un graphique ?
 Oui, vous pouvez personnaliser plusieurs points de données dans un graphique à l'aide d'Aspose.Words pour .NET. En accédant au`ChartDataPointCollection`d'une série, vous pouvez sélectionner et modifier plusieurs points de données en fonction de leurs indices. Utilisez une boucle ou des affectations individuelles pour modifier les propriétés souhaitées pour chaque point de données. De cette façon, vous pouvez appliquer différentes personnalisations à plusieurs points de données dans le même graphique.

#### Q2. Comment puis-je changer le symbole marqueur d'un point de données ?
 Pour modifier le symbole de marqueur d'un point de données dans un graphique à l'aide d'Aspose.Words pour .NET, vous devez accéder au`Marker` propriété de la`ChartDataPoint` objet et définissez le`Symbol` propriété au symbole ponctuel souhaité. Les symboles ponctuels représentent la forme ou l'icône utilisée pour représenter chaque point de données sur le graphique. Vous pouvez choisir parmi une variété de symboles marqueurs intégrés tels que cercle, carré, losange, triangle, étoile, etc.

#### Q3. Puis-je ajuster la taille d'un marqueur de point de données ?
 Oui, vous pouvez ajuster la taille d'un marqueur de point de données dans un graphique à l'aide de Aspose.Words pour .NET. Accéder au`Marker` propriété de la`ChartDataPoint` objet et définissez le`Size`propriété à la taille de marqueur souhaitée. La taille du marqueur est généralement spécifiée en points, où une valeur plus grande représente une taille de marqueur plus grande. Le réglage de la taille du marqueur vous permet de mettre en évidence des points de données spécifiques ou de les différencier en fonction de leur importance.

#### Q4. Quelles autres propriétés puis-je modifier pour un point de données ?
Aspose.Words pour .NET fournit une gamme de propriétés que vous pouvez modifier pour un point de données dans un graphique. Certaines des propriétés couramment modifiées incluent le symbole de marqueur, la taille du marqueur, la couleur du marqueur, la visibilité de l'étiquette de données, l'éclatement, l'inversion si négatif, etc. Ces propriétés vous permettent de personnaliser l'apparence, le comportement et l'interactivité des points de données individuels, ce qui vous permet de créer des graphiques adaptés à vos besoins spécifiques.

#### Q5. Puis-je personnaliser les points de données dans d'autres types de graphiques ?
Oui, vous pouvez personnaliser les points de données dans différents types de graphiques à l'aide d'Aspose.Words pour .NET. Bien que ce didacticiel illustre la personnalisation des points de données dans un graphique en courbes, vous pouvez appliquer des techniques similaires à d'autres types de graphiques tels que les graphiques à colonnes, les graphiques à barres, les graphiques à secteurs, etc. Le processus implique d'accéder aux séries et aux points de données dans le graphique et de modifier leurs propriétés en conséquence.