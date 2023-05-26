---
title: Format de nombre pour l'axe
linktitle: Format de nombre pour l'axe
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à définir le format numérique d'un axe dans un graphique à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/number-format-for-axis/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour définir le format numérique d'un axe dans un graphique. Le code source fourni montre comment créer un graphique, ajouter des données de série et formater les étiquettes des axes.

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
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Étape 4 : formater les étiquettes des axes

 Pour définir le format numérique des étiquettes de l'axe Y, accédez à la`AxisY` propriété du graphique et définissez la`NumberFormat.FormatCode` propriété au format souhaité. Dans cet exemple, nous définissons le format sur "#,##0" pour afficher les nombres avec des séparateurs de milliers.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Étape 5 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Ceci termine l'implémentation de la définition du format de nombre pour l'axe à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour le format de nombre pour l'axe en utilisant Aspose.Words pour .NET 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```