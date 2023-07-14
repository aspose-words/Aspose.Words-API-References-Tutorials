---
title: Personnaliser une série de graphiques dans un graphique
linktitle: Personnaliser une série de graphiques dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Apprenez à personnaliser une seule série de graphiques dans un graphique à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/single-chart-series/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour personnaliser une seule série de graphiques dans un graphique. Le code source fourni montre comment créer un graphique, accéder à des séries spécifiques et modifier leurs propriétés.

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
	//Chemin d'accès à votre répertoire de documents
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

## Conclusion

Dans ce didacticiel, vous avez appris à personnaliser une seule série de graphiques dans un graphique à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un nouveau document, insérer un graphique linéaire, accéder à des séries de graphiques spécifiques et modifier leurs propriétés pour obtenir la personnalisation souhaitée.

Aspose.Words pour .NET fournit des fonctionnalités puissantes pour manipuler des graphiques dans des documents Word. En accédant à des séries de graphiques individuelles, vous pouvez appliquer des modifications spécifiques pour personnaliser leur apparence et leur comportement. Cela vous permet de modifier le nom de la série, d'activer le lissage de la ligne du graphique, de personnaliser les marqueurs pour les points de données, d'inverser les couleurs pour les valeurs négatives, etc., afin d'améliorer la représentation visuelle de votre graphique.

La personnalisation d'une seule série de graphiques vous offre la possibilité de mettre en évidence des données spécifiques ou de souligner des tendances particulières dans votre graphique. Avec Aspose.Words pour .NET, vous pouvez facilement accéder et modifier les propriétés des séries de graphiques, ce qui vous permet de créer des graphiques visuellement attrayants et informatifs dans vos documents Word.

### FAQ

#### Q1. Puis-je personnaliser plusieurs séries de graphiques dans un graphique ?
 Oui, vous pouvez personnaliser plusieurs séries de graphiques dans un graphique à l'aide d'Aspose.Words pour .NET. En accédant au`ChartSeries`objets dans le graphique, vous pouvez sélectionner et modifier plusieurs séries en fonction de leurs indices ou de critères spécifiques. Utilisez une boucle ou des affectations individuelles pour modifier les propriétés souhaitées pour chaque série de graphiques. De cette façon, vous pouvez appliquer différentes personnalisations à plusieurs séries dans le même graphique.

#### Q2. Comment puis-je changer le nom d'une série de graphiques ?
 Pour modifier le nom d'une série de graphiques dans un graphique à l'aide d'Aspose.Words pour .NET, vous devez accéder au`Name`propriété de la`ChartSeries` objet et attribuez-lui le nom souhaité. Le nom de la série est généralement affiché dans la légende du graphique ou les étiquettes de données, fournissant une étiquette descriptive pour la série. En modifiant le nom de la série, vous pouvez fournir des noms significatifs qui reflètent les données représentées par chaque série.

#### Q3. Qu'est-ce que le lissage des séries de graphiques ?
Le lissage de séries de graphiques est une technique d'amélioration visuelle qui vous permet de créer une ligne lisse reliant les points du graphique. Il applique un algorithme de lissage, tel que les splines Catmull-Rom, pour interpoler entre les points de données et créer une courbe visuellement agréable. Pour activer le lissage des séries dans un graphique à l'aide d'Aspose.Words pour .NET, accédez au`Smooth`propriété de la`ChartSeries` objet et réglez-le sur`true`. Le lissage peut être utile pour afficher des tendances ou des modèles dans des données présentant des fluctuations irrégulières.

#### Q4. Comment puis-je personnaliser les marqueurs pour les points de données dans une série de graphiques ?
 Pour personnaliser les marqueurs des points de données dans une série de graphiques à l'aide d'Aspose.Words pour .NET, vous devez accéder au`Marker`propriété de la`ChartSeries` objet et modifier ses propriétés telles que`Symbol` et`Size`. Les marqueurs sont des indicateurs visuels placés sur le graphique pour représenter des points de données individuels. Vous pouvez choisir parmi une variété de symboles marqueurs intégrés et ajuster leur taille pour mettre en évidence ou différencier des points de données spécifiques au sein de la série.

#### Q5. Puis-je inverser les couleurs des valeurs négatives dans une série de graphiques ?
 Oui, vous pouvez inverser les couleurs des valeurs négatives dans une série de graphiques à l'aide de Aspose.Words pour .NET. En réglant le`InvertIfNegative`propriété de la`ChartSeries` s'opposer à`true`, les couleurs des points de données avec des valeurs négatives seront inversées, ce qui les distinguera visuellement des valeurs positives. Cette fonctionnalité peut être utile lors de la comparaison de valeurs positives et négatives dans une série de graphiques, en fournissant une différenciation claire entre les deux.