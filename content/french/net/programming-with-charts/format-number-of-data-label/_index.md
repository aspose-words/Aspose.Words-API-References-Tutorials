---
title: Formater le nombre d'étiquettes de données dans un graphique
linktitle: Formater le nombre d'étiquettes de données dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment formater le nombre d'étiquettes de données dans un graphique à l'aide d'Aspose.Words pour .NET. Personnalisez facilement les formats numériques pour les étiquettes de données.
type: docs
weight: 10
url: /fr/net/programming-with-charts/format-number-of-data-label/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour formater le nombre d'étiquettes de données dans un graphique. Le code source fourni montre comment créer un graphique, ajouter des données de série et personnaliser le format numérique des étiquettes de données.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des conditions préalables suivantes :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger en utilisant le gestionnaire de packages NuGet pour l'installer.
- Un chemin de répertoire de document où le document de sortie sera enregistré.

## Étape 2 : Créez un nouveau document et insérez un graphique

 Créer un nouveau`Document` objet et un`DocumentBuilder` pour construire le document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ensuite, insérez un graphique dans le document à l'aide du`InsertChart` méthode du`DocumentBuilder`. Dans cet exemple, nous allons insérer un graphique linéaire.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous ajouterons trois catégories et leurs valeurs correspondantes.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Étape 4 : Personnalisez le format numérique des étiquettes de données

 Pour formater le nombre d'étiquettes de données, accédez au`DataLabels` collection associée à la série.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

Dans cet exemple, nous définissons différents formats de nombres pour chaque étiquette de données. La première étiquette de données est formatée sous forme de devise, la seconde sous forme de date et la troisième sous forme de pourcentage.

## Étape 5 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide du`Save` méthode du`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Ceci termine la mise en œuvre du formatage du nombre d’étiquettes de données dans un graphique à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour le format du numéro d'étiquette de données à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Supprimez la série générée par défaut.
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

Dans ce didacticiel, vous avez appris à formater le nombre d'étiquettes de données dans un graphique à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un graphique, ajouter des données de série et personnaliser le format numérique des étiquettes de données en fonction de vos besoins.

 Aspose.Words for .NET fournit une API complète pour le traitement de mots avec des graphiques dans des documents Word, vous permettant de manipuler divers aspects du graphique, y compris les étiquettes de données. En accédant au`DataLabels` collection associée à une série, vous pouvez personnaliser le format numérique des étiquettes de données individuelles.

L'API vous permet de contrôler l'affichage des valeurs, de définir différents formats numériques pour chaque étiquette de données et de lier le format numérique à une cellule source. Cette flexibilité vous permet de présenter des données numériques dans des graphiques avec le formatage souhaité, tel que des symboles monétaires, des formats de date et des valeurs en pourcentage.

En utilisant Aspose.Words pour .NET, vous pouvez intégrer de puissantes fonctionnalités de création de graphiques dans vos applications .NET et générer des documents d'aspect professionnel avec des graphiques et des étiquettes de données entièrement formatés.

### FAQ

#### T1. Qu’est-ce qu’Aspose.Words pour .NET ?
Aspose.Words for .NET est une bibliothèque de traitement de documents riche en fonctionnalités qui permet aux développeurs de créer, manipuler et enregistrer des documents Word par programme dans des applications .NET. Il offre un large éventail de fonctionnalités pour le traitement de texte avec des éléments de document, notamment des graphiques et des étiquettes de données.

#### Q2. Comment puis-je installer Aspose.Words pour .NET ?
Vous pouvez installer Aspose.Words pour .NET en le téléchargeant à l'aide du gestionnaire de packages NuGet dans Visual Studio. Recherchez simplement « Aspose.Words » dans le gestionnaire de packages NuGet et installez-le dans votre projet.

#### Q3. Puis-je formater d’autres aspects du graphique à l’aide d’Aspose.Words for .NET ?
Oui, Aspose.Words for .NET offre des fonctionnalités étendues pour formater divers aspects d'un graphique. En plus des étiquettes de données, vous pouvez personnaliser le type de graphique, les données de série, les propriétés des axes, la légende, le titre, la zone de tracé et de nombreux autres éléments du graphique. L'API offre un contrôle précis sur l'apparence et le formatage des graphiques.

#### Q4. Puis-je appliquer différents formats de nombres à différentes étiquettes de données dans la même série ?
 Oui, Aspose.Words for .NET vous permet d'appliquer différents formats de nombres à des étiquettes de données individuelles au sein de la même série. En accédant au`DataLabels` collection associée à une série, vous pouvez définir la`FormatCode` propriété de chaque étiquette de données pour spécifier le format numérique souhaité. Cela vous permet de présenter des valeurs numériques dans différents formats au sein du même graphique.

#### Q5. Puis-je utiliser des formats numériques personnalisés pour les étiquettes de données ?
 Oui, Aspose.Words for .NET prend en charge les formats numériques personnalisés pour les étiquettes de données. Vous pouvez spécifier le format numérique souhaité en réglant le`FormatCode`propriété d'une étiquette de données en un code de format personnalisé. Cela vous donne la possibilité d'appliquer une large gamme de formats numériques, tels que des symboles monétaires, des formats de date, des valeurs en pourcentage, etc.

#### Q6. Puis-je enregistrer le graphique avec des étiquettes de données formatées dans différents formats ?
 Oui, Aspose.Words for .NET vous permet d'enregistrer le document contenant le graphique avec des étiquettes de données formatées dans différents formats, tels que DOCX, PDF, HTML, etc. Vous pouvez choisir le format approprié en fonction de vos besoins et utiliser le`Save` méthode du`Document` objet pour enregistrer le document. Les étiquettes de données formatées seront conservées dans le document enregistré.