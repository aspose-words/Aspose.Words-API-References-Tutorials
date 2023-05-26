---
title: Options par défaut pour les étiquettes de données
linktitle: Options par défaut pour les étiquettes de données
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment définir des options par défaut pour les étiquettes de données dans un graphique à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/default-options-for-data-labels/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour définir les options par défaut des étiquettes de données dans un graphique. Le code fourni montre comment créer un graphique, ajouter des séries de données et personnaliser les étiquettes de données à l'aide de Aspose.Words.

## Étape 1 : Configurer le projet

Avant de commencer, assurez-vous que les exigences suivantes sont en place :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser le gestionnaire de packages NuGet pour l'installer.
- Un chemin d'accès au répertoire de documents où le document de sortie sera enregistré.

## Étape 2 : Créer un nouveau document et insérer un graphique

 Commençons par créer un nouveau`Document` objet et un`DocumentBuilder` pour construire le document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ensuite, nous insérons un graphique dans le document à l'aide de la`InsertChart` méthode de la`DocumentBuilder`. Dans cet exemple, nous allons insérer un graphique à secteurs.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des séries de données au graphique

Ajoutons maintenant une série de données au graphique. Dans cet exemple, nous allons ajouter trois catégories et leurs valeurs correspondantes.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Étape 4 : Personnalisez les étiquettes de données

 Pour personnaliser les étiquettes de données dans le graphique, nous devons accéder au`ChartDataLabelCollection` objet associé à la série.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 On peut alors modifier diverses propriétés du`labels` objet pour définir les options souhaitées pour les étiquettes de données. Dans cet exemple, nous allons activer l'affichage du pourcentage et de la valeur, désactiver les lignes de repère et définir un séparateur personnalisé.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Étape 5 : Enregistrez le document

 Enfin, nous enregistrons le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Ceci termine l'implémentation de la définition des options par défaut pour les étiquettes de données dans un graphique à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour les options par défaut pour les étiquettes de données à l'aide de Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```