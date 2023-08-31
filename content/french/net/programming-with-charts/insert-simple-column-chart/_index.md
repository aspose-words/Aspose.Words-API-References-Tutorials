---
title: Insérer un histogramme simple dans un document Word
linktitle: Insérer un histogramme simple dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer un histogramme simple dans un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/insert-simple-column-chart/
---

Ce tutoriel explique comment utiliser Aspose.Words pour .NET pour insérer un histogramme simple dans un document. Le code source fourni montre comment créer un graphique, ajouter des données de série et enregistrer le document.

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

 Ensuite, utilisez le`InsertChart` méthode de la`DocumentBuilder` pour insérer un histogramme dans le document. Vous pouvez spécifier différents types et tailles de graphique selon vos besoins.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous allons ajouter plusieurs séries avec deux catégories chacune.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Ceci termine l'implémentation de l'insertion d'un histogramme simple à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Insérer un histogramme simple à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Vous pouvez spécifier différents types et tailles de graphique.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Supprimer la série générée par défaut.
	seriesColl.Clear();
	// Créer un tableau de noms de catégories, dans ce tutoriel, nous avons deux catégories.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Veuillez noter que les tableaux de données ne doivent pas être vides et que les tableaux doivent avoir la même taille.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Conclusion

Dans ce didacticiel, vous avez appris à insérer un histogramme simple dans un document Word à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un nouveau document, insérer un histogramme, ajouter plusieurs séries avec des catégories et des valeurs correspondantes, et enregistrer le document avec le graphique.

Aspose.Words pour .NET fournit une API puissante et flexible pour le traitement de mots avec des graphiques dans des documents Word. Le graphique à colonnes simple est un moyen efficace de représenter et de comparer des données dans différentes catégories. Avec Aspose.Words pour .NET, vous pouvez facilement créer des histogrammes avec des données personnalisées, ajouter plusieurs séries pour une comparaison visuelle et personnaliser l'apparence du graphique en fonction de vos besoins.

En utilisant Aspose.Words pour .NET, vous pouvez automatiser le processus de génération de documents avec des histogrammes, ce qui vous permet d'économiser du temps et des efforts lors de la création manuelle de documents. La bibliothèque propose une large gamme de types de graphiques, y compris des graphiques à colonnes simples, et fournit diverses options de personnalisation pour adapter l'apparence du graphique à vos besoins.

### FAQ

#### Q1. Qu'est-ce qu'un histogramme ?
Un histogramme est un type de graphique qui affiche des données à l'aide de barres verticales de différentes hauteurs. Chaque colonne représente une catégorie et la hauteur de la colonne correspond à la valeur de cette catégorie. Les graphiques à colonnes sont couramment utilisés pour comparer les données de différentes catégories ou pour suivre les changements dans le temps.

#### Q2. Puis-je ajouter plusieurs séries au graphique à colonnes ?
Oui, en utilisant Aspose.Words pour .NET, vous pouvez ajouter plusieurs séries au graphique à colonnes. Chaque série représente un ensemble de points de données avec leurs catégories et valeurs respectives. En ajoutant plusieurs séries, vous pouvez comparer et analyser différents ensembles de données dans le même histogramme, offrant ainsi une vue complète de vos données.

#### Q3. Puis-je personnaliser l'apparence de l'histogramme ?
Oui, Aspose.Words pour .NET vous permet de personnaliser divers aspects de l'apparence du graphique à colonnes. Vous pouvez modifier des propriétés telles que la couleur des séries, les étiquettes d'axe, les étiquettes de données et le formatage de la zone de graphique. La bibliothèque fournit un riche ensemble d'API pour contrôler les éléments visuels du graphique et créer un aspect personnalisé qui répond à vos besoins.

#### Q4. Puis-je enregistrer le document avec l'histogramme inséré dans différents formats ?
 Oui, Aspose.Words pour .NET vous permet d'enregistrer le document avec l'histogramme inséré dans différents formats, tels que DOCX, PDF, HTML, etc. Vous pouvez choisir le format de sortie souhaité en fonction de vos besoins et utiliser le`Save` méthode de la`Document` objet pour enregistrer le document. L'histogramme inséré sera conservé dans le document enregistré.

#### Q5. Puis-je modifier les données et l'apparence de l'histogramme après l'avoir inséré ?
Oui, après avoir inséré l'histogramme dans le document, vous pouvez modifier ses données et son apparence à l'aide des API fournies par Aspose.Words pour .NET. Vous pouvez mettre à jour les données de la série avec de nouvelles catégories et valeurs, modifier les couleurs et la mise en forme des colonnes, personnaliser les propriétés des axes et appliquer diverses options de mise en forme pour créer des graphiques dynamiques et visuellement attrayants dans vos documents Word.