---
title: Format Nombre d'étiquettes de données
linktitle: Format Nombre d'étiquettes de données
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à formater le nombre d'étiquettes de données dans un graphique à l'aide de Aspose.Words pour .NET. Personnalisez facilement les formats de nombres pour les étiquettes de données.
type: docs
weight: 10
url: /fr/net/programming-with-charts/format-number-of-data-label/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour formater le nombre d'étiquettes de données dans un graphique. Le code source fourni montre comment créer un graphique, ajouter des données de série et personnaliser le format numérique des étiquettes de données.

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

 Ensuite, insérez un graphique dans le document à l'aide de la`InsertChart` méthode de la`DocumentBuilder`Dans cet exemple, nous allons insérer un graphique en courbes.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous allons ajouter trois catégories et leurs valeurs correspondantes.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Étape 4 : Personnaliser le format numérique des étiquettes de données

 Pour formater le nombre d'étiquettes de données, accédez à la`DataLabels` collection associée à la série.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

Dans cet exemple, nous définissons différents formats de nombres pour chaque étiquette de données. La première étiquette de données est formatée en devise, la seconde en date et la troisième en pourcentage.

## Étape 5 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Ceci termine l'implémentation du formatage du nombre d'étiquettes de données dans un graphique à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Format Number Of Data Label en utilisant Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Supprimer la série générée par défaut.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Ou vous pouvez définir le code de format pour qu'il soit lié à une cellule source,
	// dans ce cas, NumberFormat sera réinitialisé sur général et hérité d'une cellule source.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```