---
title: Définir les options par défaut pour les étiquettes de données dans un graphique
linktitle: Définir les options par défaut pour les étiquettes de données dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir les options par défaut pour les étiquettes de données dans un graphique à l'aide d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/default-options-for-data-labels/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour définir les options par défaut pour les étiquettes de données dans un graphique. Le code fourni montre comment créer un graphique, ajouter des séries de données et personnaliser les étiquettes de données à l'aide d'Aspose.Words.

## Étape 1 : Configurer le projet

Avant de commencer, assurez-vous que les conditions suivantes sont remplies :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger à l'aide du gestionnaire de packages NuGet pour l'installer.
- Un chemin de répertoire de document où le document de sortie sera enregistré.

## Étape 2 : Créez un nouveau document et insérez un graphique.

 Tout d'abord, créons un nouveau`Document` objet et un`DocumentBuilder` pour construire le document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ensuite, nous insérons un graphique dans le document en utilisant le`InsertChart` méthode du`DocumentBuilder`. Dans cet exemple, nous allons insérer un diagramme circulaire.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des séries de données au graphique

Maintenant, ajoutons une série de données au graphique. Dans cet exemple, nous ajouterons trois catégories et leurs valeurs correspondantes.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Étape 4 : Personnaliser les étiquettes de données

 Pour personnaliser les étiquettes de données dans le graphique, nous devons accéder au`ChartDataLabelCollection` objet associé à la série.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 On peut alors modifier diverses propriétés du`labels`objet pour définir les options souhaitées pour les étiquettes de données. Dans cet exemple, nous allons activer l'affichage du pourcentage et de la valeur, désactiver les lignes de repère et définir un séparateur personnalisé.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Étape 5 : Enregistrez le document

 Enfin, nous enregistrons le document dans le répertoire spécifié en utilisant le`Save` méthode du`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Ceci termine la mise en œuvre de la définition des options par défaut pour les étiquettes de données dans un graphique à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour les options par défaut pour les étiquettes de données utilisant Aspose.Words pour .NET 

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

## Conclusion

Dans ce didacticiel, vous avez appris à définir les options par défaut pour les étiquettes de données dans un graphique à l'aide d'Aspose.Words for .NET. En suivant le guide étape par étape, vous pouvez créer un graphique, ajouter des séries de données et personnaliser les étiquettes de données pour répondre à vos besoins spécifiques. Aspose.Words for .NET fournit une API puissante pour le traitement de mots avec des graphiques dans des documents Word, vous permettant de manipuler divers éléments de graphique et d'obtenir l'apparence et les fonctionnalités souhaitées.

 En définissant les propriétés du`ChartDataLabelCollection`objet associé à la série de graphiques, vous pouvez contrôler l'affichage des étiquettes de données, y compris des options telles que l'affichage des pourcentages, des valeurs, des lignes de repère et des séparateurs personnalisés. Cette flexibilité vous permet de présenter les données de manière efficace et d'améliorer la représentation visuelle de vos graphiques.

### FAQ

#### T1. Qu’est-ce qu’Aspose.Words pour .NET ?
Aspose.Words for .NET est une bibliothèque qui permet aux développeurs de créer, manipuler et enregistrer des documents Word par programme à l'aide d'applications .NET. Il offre un large éventail de fonctionnalités pour le traitement de texte avec des éléments de document, notamment des graphiques.

#### Q2. Comment puis-je installer Aspose.Words pour .NET ?
Vous pouvez installer Aspose.Words pour .NET en le téléchargeant à l'aide du gestionnaire de packages NuGet dans Visual Studio. Recherchez simplement « Apose.Words » dans le gestionnaire de packages NuGet et installez-le dans votre projet.

#### Q3. Puis-je personnaliser d’autres aspects du graphique à l’aide d’Aspose.Words for .NET ?
Oui, Aspose.Words for .NET vous permet de personnaliser divers aspects d'un graphique, tels que le type de graphique, les étiquettes des axes, la légende, la zone de tracé, etc. Vous pouvez accéder et modifier différentes propriétés de l'objet graphique pour obtenir l'apparence et le comportement souhaités.

#### Q4. Puis-je enregistrer le graphique dans différents formats ?
 Oui, Aspose.Words for .NET prend en charge l'enregistrement du document contenant le graphique dans différents formats, notamment DOCX, PDF, HTML, etc. Vous pouvez choisir le format approprié en fonction de vos besoins et utiliser le`Save` méthode du`Document` objet pour enregistrer le document.

#### Q5. Puis-je appliquer ces techniques à d’autres types de graphiques ?
Oui, les techniques décrites dans ce didacticiel peuvent être appliquées à d'autres types de graphiques pris en charge par Aspose.Words for .NET. La clé est d'accéder aux objets et propriétés pertinents spécifiques au type de graphique avec lequel vous utilisez le traitement de texte.