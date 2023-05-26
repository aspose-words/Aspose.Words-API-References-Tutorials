---
title: Cochez l'alignement des étiquettes multi-lignes
linktitle: Cochez l'alignement des étiquettes multi-lignes
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à aligner les étiquettes multilignes dans un axe de graphique à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/tick-multi-line-label-alignment/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour définir l'alignement des étiquettes multilignes dans un axe de graphique. Le code source fourni montre comment créer un graphique, accéder à l'axe et modifier l'alignement de l'étiquette de graduation.

## Étape 1 : Configurer le projet

Assurez-vous que vous disposez des prérequis suivants :

- Bibliothèque Aspose.Words pour .NET installée. Vous pouvez le télécharger à partir du site Web officiel d'Aspose ou utiliser le gestionnaire de packages NuGet pour l'installer.
- Un chemin d'accès au répertoire de documents où le document de sortie sera enregistré.

## Étape 2 : Créer un nouveau document et insérer un graphique

 Créer un nouveau`Document` objet et un`DocumentBuilder` pour construire le document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ensuite, utilisez le`InsertChart` méthode de la`DocumentBuilder` pour insérer un nuage de points dans le document.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Étape 3 : Définir l'alignement des étiquettes de coche

 Pour définir l'alignement des libellés multilignes des coches, accédez à la`AxisX` propriété du graphique et définissez la`TickLabelAlignment` propriété à l'alignement souhaité. Dans cet exemple, nous définissons l'alignement sur`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Ceci termine l'implémentation de la définition de l'alignement des étiquettes multi-lignes à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour l'alignement d'étiquettes multi-lignes Tick à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Cette propriété n'a d'effet que pour les étiquettes multilignes.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```