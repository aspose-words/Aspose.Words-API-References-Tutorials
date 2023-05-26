---
title: Masquer l'axe du graphique
linktitle: Masquer l'axe du graphique
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à masquer l'axe du graphique dans un document à l'aide de Aspose.Words pour .NET. Masquez l'axe pour un affichage graphique plus net et plus ciblé.
type: docs
weight: 10
url: /fr/net/programming-with-charts/hide-chart-axis/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour masquer l'axe du graphique dans un document. Le code source fourni montre comment créer un graphique, ajouter des données de série et masquer l'axe du graphique.

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

 Ensuite, insérez un graphique dans le document à l'aide de la`InsertChart` méthode de la`DocumentBuilder`. Dans cet exemple, nous allons insérer un histogramme.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous allons ajouter cinq éléments et leurs valeurs correspondantes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Étape 4 : Masquer l'axe du graphique

 Pour masquer l'axe du graphique, accédez à la`AxisY` propriété du graphique et définissez la`Hidden` propriété à`true`.

```csharp
chart.AxisY.Hidden = true;
```

Dans cet exemple, nous masquons l'axe Y du graphique.

## Étape 5 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Ceci termine l'implémentation du masquage de l'axe du graphique à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Hide Chart Axis en utilisant Aspose.Words pour .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```