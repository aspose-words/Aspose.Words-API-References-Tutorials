---
title: Définir les options par défaut pour les étiquettes de données dans un graphique
linktitle: Définir les options par défaut pour les étiquettes de données dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir des options par défaut pour les étiquettes de données dans un graphique à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/default-options-for-data-labels/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour définir les options par défaut des étiquettes de données dans un graphique. Le code fourni montre comment créer un graphique, ajouter des séries de données et personnaliser les étiquettes de données à l'aide de Aspose.Words.

## Étape 1 : Configurer le projet

Avant de commencer, assurez-vous que les exigences suivantes sont en place :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger à l'aide du gestionnaire de packages NuGet pour l'installer.
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

 On peut alors modifier diverses propriétés du`labels`objet pour définir les options souhaitées pour les étiquettes de données. Dans cet exemple, nous allons activer l'affichage du pourcentage et de la valeur, désactiver les lignes de repère et définir un séparateur personnalisé.

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
	//Chemin d'accès à votre répertoire de documents
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

Dans ce didacticiel, vous avez appris à définir les options par défaut des étiquettes de données dans un graphique à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape, vous pouvez créer un graphique, ajouter des séries de données et personnaliser les étiquettes de données pour répondre à vos besoins spécifiques. Aspose.Words pour .NET fournit une API puissante pour le traitement de mots avec des graphiques dans des documents Word, vous permettant de manipuler divers éléments de graphique et d'obtenir l'apparence et les fonctionnalités souhaitées.

 En définissant les propriétés du`ChartDataLabelCollection`objet associé à la série de graphiques, vous pouvez contrôler l'affichage des étiquettes de données, y compris des options telles que l'affichage des pourcentages, des valeurs, des lignes de repère et des séparateurs personnalisés. Cette flexibilité vous permet de présenter efficacement les données et d'améliorer la représentation visuelle de vos graphiques.

### FAQ

#### Q1. Qu'est-ce qu'Aspose.Words pour .NET ?
Aspose.Words pour .NET est une bibliothèque qui permet aux développeurs de créer, manipuler et enregistrer des documents Word par programmation à l'aide d'applications .NET. Il fournit un large éventail de fonctionnalités pour le traitement de texte avec des éléments de document, y compris des graphiques.

#### Q2. Comment puis-je installer Aspose.Words pour .NET ?
Vous pouvez installer Aspose.Words pour .NET en le téléchargeant à l'aide du gestionnaire de packages NuGet dans Visual Studio. Recherchez simplement "Aspose.Words" dans le gestionnaire de packages NuGet et installez-le dans votre projet.

#### Q3. Puis-je personnaliser d'autres aspects du graphique à l'aide d'Aspose.Words pour .NET ?
Oui, Aspose.Words pour .NET vous permet de personnaliser divers aspects d'un graphique, tels que le type de graphique, les étiquettes d'axe, la légende, la zone de tracé, etc. Vous pouvez accéder à différentes propriétés de l'objet graphique et les modifier pour obtenir l'apparence et le comportement souhaités.

#### Q4. Puis-je enregistrer le graphique dans différents formats ?
 Oui, Aspose.Words pour .NET prend en charge l'enregistrement du document contenant le graphique dans différents formats, notamment DOCX, PDF, HTML, etc. Vous pouvez choisir le format approprié en fonction de vos besoins et utiliser le`Save` méthode de la`Document` objet pour enregistrer le document.

#### Q5. Puis-je appliquer ces techniques à d'autres types de graphiques ?
Oui, les techniques décrites dans ce didacticiel peuvent être appliquées à d'autres types de graphiques pris en charge par Aspose.Words pour .NET. La clé est d'accéder aux objets et propriétés pertinents spécifiques au type de graphique avec lequel vous effectuez le traitement de texte.