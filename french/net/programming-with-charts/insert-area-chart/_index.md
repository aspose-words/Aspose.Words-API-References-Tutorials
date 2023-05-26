---
title: Insérer un graphique en aires
linktitle: Insérer un graphique en aires
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un graphique en aires dans un document à l'aide d'Aspose.Words pour .NET. Ajoutez des données de série et enregistrez le document avec le graphique.
type: docs
weight: 10
url: /fr/net/programming-with-charts/insert-area-chart/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour insérer un graphique en aires dans un document. Le code source fourni montre comment créer un graphique, ajouter des données de série et enregistrer le document.

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

 Ensuite, utilisez le`InsertChart` méthode de la`DocumentBuilder` pour insérer un graphique en aires dans le document.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous ajouterons cinq points de données avec les dates et les valeurs correspondantes.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Ceci termine l'implémentation de l'insertion d'un graphique en aires à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Insérer un graphique en aires à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```