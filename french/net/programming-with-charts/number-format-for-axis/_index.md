---
title: Format de nombre pour l'axe dans un graphique
linktitle: Format de nombre pour l'axe dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Apprenez à définir le format numérique d'un axe dans un graphique à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/number-format-for-axis/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour définir le format numérique d'un axe dans un graphique. Le code source fourni montre comment créer un graphique, ajouter des données de série et formater les étiquettes des axes.

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

 Ensuite, utilisez le`InsertChart` méthode de la`DocumentBuilder` pour insérer un histogramme dans le document.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous allons ajouter cinq éléments avec leurs valeurs correspondantes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Étape 4 : formater les étiquettes des axes

 Pour définir le format numérique des étiquettes de l'axe Y, accédez à la`AxisY` propriété du graphique et définissez la`NumberFormat.FormatCode` propriété au format souhaité. Dans cet exemple, nous définissons le format sur "#,##0" pour afficher les nombres avec des séparateurs de milliers.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Étape 5 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Ceci termine l'implémentation de la définition du format de nombre pour l'axe à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour le format de nombre pour l'axe en utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Conclusion

Dans ce didacticiel, vous avez appris à définir le format numérique d'un axe dans un graphique à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un nouveau document, insérer un histogramme, ajouter des données de série et formater les étiquettes d'axe pour afficher les nombres dans un format spécifique.

Aspose.Words pour .NET fournit des fonctionnalités puissantes pour personnaliser l'apparence des graphiques dans les documents Word. En définissant le format numérique des étiquettes d'axe, vous pouvez contrôler la façon dont les nombres sont affichés, y compris des options telles que les décimales, les séparateurs de milliers, les symboles monétaires, etc. Cela vous permet de présenter des données numériques de manière claire et significative.

Avec Aspose.Words pour .NET, vous avez la possibilité de formater divers aspects du graphique, y compris les étiquettes des axes. En définissant le format numérique de l'axe, vous pouvez assurer la cohérence et améliorer la lisibilité du graphique, ce qui facilite l'interprétation des valeurs représentées par les utilisateurs.

### FAQ

#### Q1. Quel est le format numérique d'un axe dans un graphique ?
Le format numérique d'un axe dans un graphique fait référence au formatage appliqué aux valeurs numériques affichées sur l'axe. Il vous permet de contrôler la présentation des nombres, y compris des options telles que les décimales, les séparateurs de milliers, les symboles monétaires, les signes de pourcentage, etc. En définissant le format numérique, vous pouvez personnaliser l'apparence des données numériques dans le graphique en fonction de vos besoins spécifiques.

#### Q2. Comment puis-je définir le format numérique des étiquettes d'axe ?
 Pour définir le format numérique des étiquettes d'axe dans un graphique à l'aide d'Aspose.Words pour .NET, vous pouvez accéder au`AxisY` propriété du graphique et définissez la`NumberFormat.FormatCode`propriété au code de format souhaité. Le code de format suit la syntaxe des modèles de formatage numérique standard et détermine la façon dont les nombres sont affichés. Par exemple, vous pouvez utiliser "#,##0.00" pour afficher des nombres avec deux décimales et des séparateurs de milliers.

#### Q3. Puis-je définir des formats de nombre différents pour les étiquettes de l'axe X et de l'axe Y ?
Oui, vous pouvez définir différents formats de nombres pour les étiquettes des axes X et Y à l'aide de Aspose.Words pour .NET. Accéder à l'axe respectif (`AxisX` pour l'axe X ou`AxisY` pour l'axe Y) du graphique et modifier le`NumberFormat.FormatCode` propriété individuellement pour chaque axe. Cela vous permet d'appliquer différents formats de nombres aux étiquettes sur chaque axe en fonction de vos besoins spécifiques.

#### Q4. Quels sont les codes de format numérique courants que je peux utiliser ?
Aspose.Words pour .NET prend en charge une large gamme de codes de format numérique que vous pouvez utiliser pour formater les étiquettes d'axe dans un graphique. Certains codes de format courants incluent :

- `0` ou`#` - Affiche le nombre sans décimales.
- `0.00` ou`#.00` - Affiche le nombre avec deux décimales.
- `#,##0` Affiche le nombre avec des séparateurs de milliers.
- `"€"0.00` - Affiche le nombre avec le symbole monétaire de l'euro et deux décimales.
- `"%"0` - Affiche le nombre en pourcentage.

 Vous pouvez trouver plus d'informations sur le numéro[codes de format](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) dans la référence API de Aspose.Words pour .NET.

#### Q5. Puis-je personnaliser d'autres propriétés des étiquettes d'axe ?
Oui, Aspose.Words pour .NET fournit un large éventail de propriétés pour personnaliser l'apparence et le comportement des étiquettes d'axe. Outre le format numérique, vous pouvez modifier des propriétés telles que la police, la taille, la couleur, l'orientation, l'alignement, etc. Cela vous permet de personnaliser entièrement les étiquettes des axes en fonction du style et des exigences de présentation souhaités.