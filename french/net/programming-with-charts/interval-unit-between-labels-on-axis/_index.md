---
title: Unité d'intervalle entre les étiquettes sur l'axe
linktitle: Unité d'intervalle entre les étiquettes sur l'axe
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à définir l'unité d'intervalle entre les étiquettes sur l'axe d'un graphique à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour définir l'unité d'intervalle entre les étiquettes sur l'axe d'un graphique. Le code source fourni montre comment créer un graphique, ajouter des données de série et personnaliser les étiquettes des axes.

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

 Ensuite, utilisez le`InsertChart` méthode de la`DocumentBuilder` pour insérer un histogramme dans le document.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous allons ajouter cinq éléments avec leurs valeurs correspondantes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Étape 4 : Personnalisez les libellés des axes

 Pour définir l'unité d'intervalle entre les étiquettes sur l'axe X, accédez à la`AxisX` propriété du graphique et définissez la`TickLabelSpacing` propriété à la valeur désirée. Dans cet exemple, nous avons défini l'espacement sur 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Étape 5 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Ceci termine l'implémentation de la définition de l'unité d'intervalle entre les étiquettes sur l'axe à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Interval Unit Between Labels On Axis en utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```