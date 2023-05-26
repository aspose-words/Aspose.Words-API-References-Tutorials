---
title: Insérer un histogramme
linktitle: Insérer un histogramme
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un histogramme dans un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/insert-column-chart/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour insérer un histogramme dans un document. Le code source fourni montre comment créer un graphique, ajouter des données de série et enregistrer le document.

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

Ajoutez des données de série au graphique. Dans cet exemple, nous allons ajouter deux catégories et leurs valeurs correspondantes.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Ceci termine l'implémentation de l'insertion d'un histogramme à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Insérer un graphique à colonnes à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```