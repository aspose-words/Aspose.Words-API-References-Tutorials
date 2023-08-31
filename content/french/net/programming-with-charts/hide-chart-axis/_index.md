---
title: Masquer l'axe du graphique dans un document Word
linktitle: Masquer l'axe du graphique dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment masquer l'axe du graphique dans un document à l'aide d'Aspose.Words for .NET. Masquez l’axe pour un affichage graphique plus propre et plus ciblé.
type: docs
weight: 10
url: /fr/net/programming-with-charts/hide-chart-axis/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour masquer l'axe du graphique dans un document. Le code source fourni montre comment créer un graphique, ajouter des données de série et masquer l'axe du graphique.

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

 Ensuite, insérez un graphique dans le document à l'aide du`InsertChart` méthode du`DocumentBuilder`Dans cet exemple, nous allons insérer un histogramme.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous ajouterons cinq éléments et leurs valeurs correspondantes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Étape 4 : Masquer l'axe du graphique

 Pour masquer l'axe du graphique, accédez à l'onglet`AxisY` propriété du graphique et définissez la`Hidden` propriété à`true`.

```csharp
chart.AxisY.Hidden = true;
```

Dans cet exemple, nous masquons l'axe Y du graphique.

## Étape 5 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide du`Save` méthode du`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Ceci termine la mise en œuvre du masquage de l’axe du graphique à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour masquer l'axe du graphique à l'aide d'Aspose.Words pour .NET 

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
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Conclusion

Dans ce didacticiel, vous avez appris à masquer l'axe du graphique dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un graphique, ajouter des données de série et masquer l'axe du graphique pour obtenir l'effet visuel souhaité.

 Aspose.Words for .NET fournit une API complète pour le traitement de mots avec des graphiques dans des documents Word, vous permettant de manipuler divers aspects du graphique, y compris les propriétés des axes. En accédant au`AxisY`propriété du graphique, vous pouvez masquer l’axe Y pour le supprimer de la visualisation du graphique.

Masquer l’axe du graphique peut être utile lorsque vous souhaitez vous concentrer sur les données du graphique sans être distrait par les lignes et les étiquettes des axes. Il donne une apparence plus propre et minimaliste au graphique.

En utilisant Aspose.Words pour .NET, vous pouvez facilement intégrer des fonctionnalités de création de graphiques dans vos applications .NET et générer des documents d'aspect professionnel avec des graphiques personnalisés et des axes de graphique masqués.

### FAQ

#### T1. Qu’est-ce qu’Aspose.Words pour .NET ?
Aspose.Words for .NET est une puissante bibliothèque de traitement de documents qui permet aux développeurs de créer, manipuler et enregistrer des documents Word par programme dans des applications .NET. Il fournit un large éventail de fonctionnalités pour le traitement de texte avec des éléments de document, notamment des graphiques et des axes de graphique.

#### Q2. Comment puis-je installer Aspose.Words pour .NET ?
Vous pouvez installer Aspose.Words pour .NET en le téléchargeant à l'aide du gestionnaire de packages NuGet dans Visual Studio. Recherchez simplement « Aspose.Words » dans le gestionnaire de packages NuGet et installez-le dans votre projet.

#### Q3. Puis-je masquer à la fois l’axe X et l’axe Y d’un graphique ?
 Oui, vous pouvez masquer à la fois l'axe X et l'axe Y d'un graphique à l'aide d'Aspose.Words pour .NET. Pour masquer l'axe X, vous pouvez accéder au`AxisX` propriété du graphique et définissez la`Hidden` propriété à`true` De même, pour masquer l'axe Y, vous pouvez accéder au`AxisY` propriété et définir la`Hidden` propriété à`true`. Cela vous permet de supprimer les deux axes de la visualisation graphique.

#### Q4. Puis-je afficher à nouveau l’axe après l’avoir masqué ?
 Oui, vous pouvez afficher à nouveau l'axe du graphique après l'avoir masqué à l'aide d'Aspose.Words for .NET. Pour afficher un axe caché, définissez simplement le`Hidden` propriété du correspondant`AxisX` ou`AxisY` s'opposer à`false`. Cela rendra l'axe à nouveau visible dans le graphique.

#### Q5. Puis-je personnaliser d’autres propriétés de l’axe du graphique ?
 Oui, Aspose.Words for .NET vous permet de personnaliser diverses propriétés de l'axe du graphique, telles que le titre de l'axe, les étiquettes, la couleur des lignes, etc. En accédant au`AxisX` et`AxisY` propriétés du graphique, vous pouvez modifier les propriétés telles que`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, et plein d'autres. Cela vous donne un contrôle précis sur l’apparence et le comportement des axes du graphique.

#### Q6. Puis-je enregistrer le graphique avec l’axe caché dans différents formats de fichier ?
Oui, Aspose.Words for .NET vous permet d'enregistrer le document contenant le graphique avec un axe masqué dans différents formats de fichiers, tels que DOCX, PDF, HTML, etc. Vous pouvez choisir le format de sortie souhaité en fonction de vos besoins et utiliser le`Save` méthode du`Document` objet pour enregistrer le document. L'axe caché sera conservé dans le document enregistré.