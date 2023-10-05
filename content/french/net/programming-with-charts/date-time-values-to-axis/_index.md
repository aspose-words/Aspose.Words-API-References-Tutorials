---
title: Ajouter des valeurs de date et d'heure à l'axe d'un graphique
linktitle: Ajouter des valeurs de date et d'heure à l'axe d'un graphique
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter des valeurs date/heure à l’axe d’un graphique à l’aide d’Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/date-time-values-to-axis/
---

Ce didacticiel explique comment ajouter des valeurs date/heure à l'axe d'un graphique à l'aide d'Aspose.Words for .NET.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de mots avec des documents Word.

## Étape 1 : configurer le répertoire de documents
 Commencez par configurer le chemin d’accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin réel du répertoire dans lequel vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document et DocumentBuilder
 Créez une nouvelle instance du`Document` classe et un`DocumentBuilder` s'opposer à travailler avec le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer et configurer une forme de graphique
 Insérez une forme de graphique dans le document à l'aide du`InsertChart` méthode du`DocumentBuilder` objet. Définissez le type de graphique et les dimensions souhaités.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Étape 4 : Ajouter des données au graphique
Ajoutez des données à la série de graphiques, y compris les valeurs date/heure.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Étape 5 : Configurer l'axe
Configurez l'axe X du graphique pour afficher les valeurs de date et d'heure.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Étape 6 : Enregistrez le document
 Enregistrez le document dans le répertoire spécifié à l'aide du`Save` méthode. Fournissez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous le nom « WorkingWithCharts.DateTimeValuesToAxis.docx ».

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Exemple de code source pour les valeurs date-heure vers l'axe à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Réglez les unités principales sur une semaine et les unités mineures sur un jour.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Cet exemple de code crée un nouveau document Word, insère un histogramme avec des valeurs de date et d'heure sur l'axe X et enregistre le document dans le répertoire spécifié.

## Conclusion
Dans ce didacticiel, vous avez appris à ajouter des valeurs de date et d'heure à l'axe d'un graphique à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape, vous pouvez créer un graphique, ajouter des valeurs de date et d'heure à la série et configurer l'axe pour afficher les valeurs de date et d'heure avec précision. Aspose.Words for .NET fournit un ensemble puissant de fonctionnalités pour le traitement de mots avec des graphiques dans les documents Word, vous permettant de représenter et de visualiser efficacement des données avec des valeurs de date et d'heure.

### FAQ

#### T1. Puis-je ajouter des valeurs date/heure à l’axe d’un graphique à l’aide d’Aspose.Words for .NET ?
Oui, avec Aspose.Words pour .NET, vous pouvez ajouter et afficher des valeurs date/heure sur l'axe d'un graphique dans un document Word. Aspose.Words fournit des API et des fonctionnalités pour travailler avec différents types de graphiques et personnaliser leur apparence, y compris la gestion des valeurs de date et d'heure sur l'axe.

#### Q2. Comment ajouter des valeurs date/heure à la série de graphiques ?
 Pour ajouter des valeurs date/heure à la série de graphiques, vous pouvez utiliser l'outil`Add`méthode des séries du graphique. Fournissez un tableau de valeurs date/heure en tant que données de catégorie (axe X), ainsi que les valeurs de série correspondantes. Cela vous permet de tracer des points de données avec des valeurs date/heure sur le graphique.

#### Q3. Comment puis-je configurer l’axe pour afficher les valeurs date/heure ?
 Vous pouvez configurer l'axe du graphique pour afficher les valeurs de date et d'heure en définissant les propriétés appropriées. Par exemple, vous pouvez spécifier les valeurs minimale et maximale de l'axe à l'aide de l'option`Scaling.Minimum` et`Scaling.Maximum` propriétés, respectivement. De plus, vous pouvez définir les unités majeures et mineures pour définir l'intervalle et les graduations de l'axe.
