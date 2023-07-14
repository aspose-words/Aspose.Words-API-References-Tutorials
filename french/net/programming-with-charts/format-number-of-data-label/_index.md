---
title: Formater le nombre d'étiquettes de données dans un graphique
linktitle: Formater le nombre d'étiquettes de données dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Apprenez à formater le nombre d'étiquettes de données dans un graphique à l'aide de Aspose.Words pour .NET. Personnalisez facilement les formats de nombres pour les étiquettes de données.
type: docs
weight: 10
url: /fr/net/programming-with-charts/format-number-of-data-label/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour formater le nombre d'étiquettes de données dans un graphique. Le code source fourni montre comment créer un graphique, ajouter des données de série et personnaliser le format numérique des étiquettes de données.

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

 Ensuite, insérez un graphique dans le document à l'aide de la`InsertChart` méthode de la`DocumentBuilder`. Dans cet exemple, nous allons insérer un graphique en courbes.

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
	//Chemin d'accès à votre répertoire de documents
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

## Conclusion

Dans ce didacticiel, vous avez appris à formater le nombre d'étiquettes de données dans un graphique à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un graphique, ajouter des données de série et personnaliser le format numérique des étiquettes de données en fonction de vos besoins.

 Aspose.Words pour .NET fournit une API complète pour le traitement de mots avec des graphiques dans des documents Word, vous permettant de manipuler divers aspects du graphique, y compris les étiquettes de données. En accédant au`DataLabels` collection associée à une série, vous pouvez personnaliser le format numérique des étiquettes de données individuelles.

L'API vous permet de contrôler l'affichage des valeurs, de définir différents formats de nombre pour chaque étiquette de données et de lier le format de nombre à une cellule source. Cette flexibilité vous permet de présenter des données numériques dans des graphiques avec la mise en forme souhaitée, comme les symboles monétaires, les formats de date et les valeurs en pourcentage.

En utilisant Aspose.Words pour .NET, vous pouvez incorporer de puissantes fonctionnalités de création de graphiques dans vos applications .NET et générer des documents d'aspect professionnel avec des graphiques et des étiquettes de données entièrement formatés.

### FAQ

#### Q1. Qu'est-ce qu'Aspose.Words pour .NET ?
Aspose.Words pour .NET est une bibliothèque de traitement de documents riche en fonctionnalités qui permet aux développeurs de créer, manipuler et enregistrer des documents Word par programmation dans des applications .NET. Il fournit un large éventail de fonctionnalités pour le traitement de texte avec des éléments de document, y compris des graphiques et des étiquettes de données.

#### Q2. Comment puis-je installer Aspose.Words pour .NET ?
Vous pouvez installer Aspose.Words pour .NET en le téléchargeant à l'aide du gestionnaire de packages NuGet dans Visual Studio. Recherchez simplement "Aspose.Words" dans le gestionnaire de packages NuGet et installez-le dans votre projet.

#### Q3. Puis-je formater d'autres aspects du graphique en utilisant Aspose.Words pour .NET ?
Oui, Aspose.Words pour .NET offre des fonctionnalités étendues pour le formatage de divers aspects d'un graphique. Outre les étiquettes de données, vous pouvez personnaliser le type de graphique, les données de série, les propriétés des axes, la légende, le titre, la zone de tracé et de nombreux autres éléments du graphique. L'API offre un contrôle précis sur l'apparence et la mise en forme des graphiques.

#### Q4. Puis-je appliquer différents formats de nombres à différentes étiquettes de données dans la même série ?
 Oui, Aspose.Words pour .NET vous permet d'appliquer différents formats de nombres à des étiquettes de données individuelles au sein de la même série. En accédant au`DataLabels` collection associée à une série, vous pouvez définir la`FormatCode` propriété de chaque étiquette de données pour spécifier le format numérique souhaité. Cela vous permet de présenter des valeurs numériques dans différents formats dans le même graphique.

#### Q5. Puis-je utiliser des formats numériques personnalisés pour les étiquettes de données ?
 Oui, Aspose.Words pour .NET prend en charge les formats numériques personnalisés pour les étiquettes de données. Vous pouvez spécifier le format de nombre souhaité en réglant le`FormatCode`propriété d'une étiquette de données à un code de format personnalisé. Cela vous donne la possibilité d'appliquer une large gamme de formats numériques, tels que les symboles monétaires, les formats de date, les valeurs en pourcentage, etc.

#### Q6. Puis-je enregistrer le graphique avec des étiquettes de données formatées dans différents formats ?
 Oui, Aspose.Words pour .NET vous permet d'enregistrer le document contenant le graphique avec des étiquettes de données formatées dans différents formats, tels que DOCX, PDF, HTML, etc. Vous pouvez choisir le format approprié en fonction de vos besoins et utiliser le`Save` méthode de la`Document` objet pour enregistrer le document. Les étiquettes de données formatées seront conservées dans le document enregistré.