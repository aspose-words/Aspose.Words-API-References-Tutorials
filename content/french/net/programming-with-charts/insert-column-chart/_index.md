---
title: Insérer un histogramme dans un document Word
linktitle: Insérer un histogramme dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un histogramme dans un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/insert-column-chart/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour insérer un histogramme dans un document. Le code source fourni montre comment créer un graphique, ajouter des données de série et enregistrer le document.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des conditions préalables suivantes :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger en utilisant le gestionnaire de packages NuGet pour l'installer.
- Un chemin de répertoire de document où le document de sortie sera enregistré.

## Étape 2 : Créez un nouveau document et insérez un graphique.

 Créer un nouveau`Document` objet et un`DocumentBuilder` pour construire le document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ensuite, utilisez le`InsertChart` méthode du`DocumentBuilder` pour insérer un histogramme dans le document.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous ajouterons deux catégories et leurs valeurs correspondantes.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide du`Save` méthode du`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Ceci termine la mise en œuvre de l’insertion d’un histogramme à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour Insérer un diagramme à colonnes à l'aide d'Aspose.Words pour .NET 

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

## Conclusion

Dans ce didacticiel, vous avez appris à insérer un histogramme dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un nouveau document, insérer un histogramme, ajouter des données de série et enregistrer le document avec le graphique.

Aspose.Words for .NET fournit une API puissante pour le traitement de mots avec des graphiques dans les documents Word. Les graphiques à colonnes sont couramment utilisés pour afficher et comparer les données de différentes catégories ou groupes. Avec Aspose.Words pour .NET, vous pouvez facilement créer des histogrammes qui visualisent efficacement vos données et fournissent des informations précieuses.

En utilisant Aspose.Words pour .NET, vous pouvez automatiser le processus de génération de documents avec des histogrammes, économisant ainsi du temps et des efforts dans la création manuelle de documents. La bibliothèque propose une large gamme de types de graphiques et d'options de personnalisation, vous permettant de créer des graphiques visuellement attrayants et riches en données dans vos documents Word.

### FAQ

#### T1. Qu'est-ce qu'un histogramme ?
Un histogramme est un type de graphique qui représente les données sous forme de barres verticales ou de colonnes. Chaque colonne représente généralement une catégorie ou un groupe, et la hauteur ou la longueur de la colonne indique la valeur des données associées à cette catégorie. Les graphiques à colonnes sont couramment utilisés pour comparer les données de différentes catégories ou pour suivre les changements au fil du temps.

#### Q2. Puis-je ajouter plusieurs séries au graphique à colonnes ?
Oui, vous pouvez ajouter plusieurs séries au graphique à colonnes à l'aide d'Aspose.Words for .NET. Chaque série représente un ensemble de points de données avec leurs catégories et valeurs respectives. En ajoutant plusieurs séries, vous pouvez comparer et analyser différents ensembles de données au sein du même graphique, offrant ainsi une vue complète de vos données.

#### Q3. Puis-je personnaliser l’apparence du graphique à colonnes ?
Oui, en utilisant Aspose.Words pour .NET, vous pouvez personnaliser divers aspects de l’apparence du histogramme. Vous pouvez modifier des propriétés telles que la couleur des séries, les étiquettes des axes, la largeur des colonnes et le formatage de la zone du graphique. La bibliothèque fournit un riche ensemble d'API pour contrôler les éléments visuels du graphique et créer une apparence personnalisée adaptée à vos besoins.

#### Q4. Puis-je enregistrer le document avec l’histogramme inséré dans différents formats ?
 Oui, Aspose.Words for .NET vous permet d'enregistrer le document avec l'histogramme inséré dans différents formats, tels que DOCX, PDF, HTML, etc. Vous pouvez choisir le format de sortie souhaité en fonction de vos besoins et utiliser le`Save` méthode du`Document` objet pour enregistrer le document. L'histogramme inséré sera conservé dans le document enregistré.

#### Q5. Puis-je modifier les données et l’apparence de l’histogramme après l’avoir inséré ?
Oui, après avoir inséré l'histogramme dans le document, vous pouvez modifier ses données et son apparence à l'aide des API fournies par Aspose.Words for .NET. Vous pouvez mettre à jour les données de la série, modifier les couleurs des colonnes, personnaliser les propriétés des axes et appliquer des options de formatage pour créer des graphiques dynamiques et interactifs dans vos documents Word.