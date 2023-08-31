---
title: Créer et personnaliser un graphique à l'aide de la forme
linktitle: Créer et personnaliser un graphique à l'aide de la forme
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment créer et personnaliser un graphique à l'aide d'une forme dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/create-chart-using-shape/
---

Ce didacticiel explique comment créer un graphique à l'aide d'une forme dans un document Word à l'aide de Aspose.Words pour .NET.

## Conditions préalables
Pour suivre ce tutoriel, vous devez disposer des éléments suivants :

- Bibliothèque Aspose.Words pour .NET installée.
- Connaissance de base de C# et du traitement de texte avec des documents Word.

## Étape 1 : Configurer le répertoire de documents
 Commencez par configurer le chemin d'accès à votre répertoire de documents. Remplacer`"YOUR DOCUMENT DIRECTORY"` avec le chemin d'accès réel au répertoire où vous souhaitez enregistrer le document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document et DocumentBuilder
 Créez une nouvelle instance de`Document` classe et une`DocumentBuilder` objet de travailler avec le document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer et configurer une forme de graphique
 Insérez une forme de graphique dans le document à l'aide de la`InsertChart` méthode de la`DocumentBuilder` objet. Définissez le type et les dimensions de graphique souhaités.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Étape 4 : Personnalisez le graphique
Personnalisez le graphique en modifiant diverses propriétés telles que le titre et la légende du graphique.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Étape 5 : Enregistrer le document
 Enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode. Indiquez le nom de fichier souhaité avec l'extension de fichier appropriée. Dans cet exemple, nous enregistrons le document sous "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Exemple de code source pour Créer un graphique à l'aide de la forme à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Veuillez noter que si une valeur nulle ou vide est spécifiée comme texte de titre, le titre généré automatiquement sera affiché.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

C'est ça! Vous avez créé avec succès un graphique à l'aide d'une forme dans un document Word à l'aide de Aspose.Words pour .NET.

## Conclusion
Dans ce didacticiel, vous avez appris à créer un graphique à l'aide d'une forme dans un document Word à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape, vous pouvez insérer et configurer une forme de graphique, personnaliser son apparence et enregistrer le document. Aspose.Words pour .NET fournit un ensemble complet de fonctionnalités pour le traitement de mots avec des documents et des graphiques Word, vous permettant de créer des graphiques d'aspect professionnel et visuellement attrayants directement dans vos applications .NET.

### FAQ

#### Q1. Puis-je créer des graphiques dans un document Word à l'aide d'Aspose.Words pour .NET ?
Oui, avec Aspose.Words pour .NET, vous pouvez créer des graphiques dans un document Word par programmation. Aspose.Words fournit des API et des fonctionnalités pour insérer différents types de graphiques, personnaliser leur apparence et manipuler les données des graphiques.

#### Q2. Quels types de graphiques sont pris en charge par Aspose.Words pour .NET ?
Aspose.Words pour .NET prend en charge un large éventail de types de graphiques, y compris les graphiques linéaires, les graphiques à barres, les graphiques circulaires, les graphiques en aires, les graphiques en nuage de points, etc. Vous pouvez choisir le type de graphique approprié en fonction de vos exigences en matière de données et de visualisation.

#### Q3. Puis-je personnaliser l'apparence du graphique créé ?
Oui, vous pouvez personnaliser l'apparence du graphique créé à l'aide de Aspose.Words pour .NET. Vous pouvez modifier des propriétés telles que le titre du graphique, la position de la légende, les étiquettes de données, les étiquettes d'axe, les couleurs et d'autres éléments visuels pour répondre à vos besoins spécifiques en matière de conception et de formatage.
