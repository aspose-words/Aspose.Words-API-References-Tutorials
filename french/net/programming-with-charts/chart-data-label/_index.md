---
title: Libellé des données du graphique
linktitle: Libellé des données du graphique
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment ajouter et personnaliser des étiquettes de données dans un graphique à l'aide d'Aspose.Words pour .NET afin de fournir des informations supplémentaires sur les points de données.
type: docs
weight: 10
url: /fr/net/programming-with-charts/chart-data-label/
---

Ce didacticiel explique comment ajouter et personnaliser des étiquettes de données dans un graphique à l'aide de Aspose.Words pour .NET. Les étiquettes de données fournissent des informations supplémentaires sur les points de données d'un graphique.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et travail avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"`avec le chemin d'accès réel au répertoire où vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document et DocumentBuilder
 Créez une nouvelle instance de`Document` classe et une`DocumentBuilder` objet de travailler avec le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer et configurer un graphique
 Insérez un graphique dans le document à l'aide de la`InsertChart` méthode de la`DocumentBuilder` objet. Définissez le type et les dimensions de graphique souhaités.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Étape 4 : Personnaliser les étiquettes de données
Accédez à la collection d'étiquettes de données de la série de graphiques et modifiez diverses propriétés pour personnaliser l'apparence des étiquettes de données.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Étape 5 : Enregistrer le document
 Enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Exemple de code source pour Chart Data Label utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	//Par défaut, lorsque vous ajoutez des étiquettes de données aux points de données d'un graphique à secteurs, des lignes de repère s'affichent pour les étiquettes de données qui sont
	// positionné loin à l'extérieur de la fin des points de données. Les lignes de repère créent une connexion visuelle entre une étiquette de données et son
	// point de données correspondant.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

C'est ça! Vous avez ajouté et personnalisé avec succès des étiquettes de données dans un graphique à l'aide d'Aspose.Words pour .NET.