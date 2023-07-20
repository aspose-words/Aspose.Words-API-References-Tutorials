---
title: Cochez l'alignement des étiquettes multi-lignes dans un graphique
linktitle: Cochez l'alignement des étiquettes multi-lignes dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Apprenez à aligner les étiquettes multilignes dans un axe de graphique à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/tick-multi-line-label-alignment/
---

Ce didacticiel explique comment utiliser Aspose.Words pour .NET pour définir l'alignement des étiquettes multilignes dans un axe de graphique. Le code source fourni montre comment créer un graphique, accéder à l'axe et modifier l'alignement de l'étiquette de graduation.

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
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Cette propriété n'a d'effet que pour les étiquettes multilignes.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Conclusion

Dans ce didacticiel, vous avez appris à définir l'alignement des étiquettes multilignes dans un axe de graphique à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un nouveau document, insérer un nuage de points, accéder à l'axe du graphique et modifier l'alignement des étiquettes de graduation.

Aspose.Words pour .NET fournit des fonctionnalités puissantes pour manipuler des graphiques dans des documents Word. Les étiquettes multilignes de coche sont utiles lorsque les étiquettes d'axe contiennent du texte long qui nécessite un habillage ou un fractionnement sur plusieurs lignes. En définissant l'alignement des étiquettes de graduation, vous pouvez contrôler l'alignement horizontal des étiquettes multilignes dans l'axe du graphique, garantissant une présentation et une lisibilité optimales.

La personnalisation de l'alignement des étiquettes multi-lignes vous permet d'affiner l'apparence de votre graphique, en particulier lorsqu'il s'agit d'étiquettes longues ou complexes. En alignant les étiquettes à droite, à gauche, au centre ou justifiées, vous pouvez obtenir une disposition équilibrée et visuellement attrayante des étiquettes de graduation le long de l'axe.

Avec Aspose.Words pour .NET, vous pouvez facilement accéder et modifier la propriété d'alignement des étiquettes de graduation d'un axe de graphique, vous offrant un contrôle total sur l'apparence et la disposition des étiquettes de graduation dans vos tableaux de documents Word.

### FAQ

#### Q1. Qu'est-ce que les étiquettes multi-lignes de coche dans un axe de graphique ?
Les étiquettes de coche multilignes dans un axe de graphique font référence aux étiquettes d'axe qui s'étendent sur plusieurs lignes lorsque le texte de l'étiquette est long ou nécessite un retour à la ligne pour tenir dans l'espace disponible. Au lieu de tronquer le texte de l'étiquette ou de créer un encombrement visuel, l'axe du graphique divise automatiquement les étiquettes en plusieurs lignes pour garantir la lisibilité. Les étiquettes multilignes à cocher sont particulièrement utiles lorsqu'il s'agit de longues étiquettes de catégorie ou de valeur dans les graphiques.

#### Q2. Puis-je personnaliser l'alignement des étiquettes de graduation dans un axe de graphique ?
 Oui, vous pouvez personnaliser l'alignement des étiquettes de graduation dans un axe de graphique à l'aide de Aspose.Words pour .NET. En accédant au`TickLabelAlignment` propriété de la`ChartAxis` objet, vous pouvez définir l'alignement souhaité pour les étiquettes de graduation. Les options d'alignement incluent l'alignement à gauche, à droite, centré ou justifié. Le réglage de l'alignement vous permet de contrôler le positionnement horizontal des étiquettes de graduation le long de l'axe du graphique, garantissant une bonne lisibilité et une présentation visuelle.

#### Q3. Quand dois-je envisager de modifier l'alignement des étiquettes de graduation dans un axe de graphique ?
La modification de l'alignement des étiquettes de graduation dans un axe de graphique est bénéfique lorsque vous avez des étiquettes longues ou multilignes qui nécessitent une présentation et une lisibilité optimales. En ajustant l'alignement, vous pouvez vous assurer que les étiquettes sont correctement alignées et espacées, en évitant les chevauchements ou les troncatures. Envisagez de modifier l'alignement des étiquettes de graduation lorsque vous traitez des graphiques qui ont de longs noms de catégories, des étiquettes de valeurs détaillées ou tout autre scénario où l'alignement par défaut ne fournit pas l'apparence visuelle souhaitée.

#### Q4. L'alignement des étiquettes de graduation affecte-t-il les étiquettes à une seule ligne dans un axe de graphique ?
Non, la propriété d'alignement des étiquettes de graduation n'affecte pas les étiquettes à une seule ligne dans un axe de graphique. Il est spécialement conçu pour les étiquettes multilignes qui nécessitent un emballage ou un fractionnement. Les étiquettes à une seule ligne sont alignées en fonction des paramètres d'alignement par défaut de l'axe du graphique. La propriété d'alignement des étiquettes de graduation s'applique uniquement aux étiquettes qui s'étendent sur plusieurs lignes, ce qui vous permet de contrôler l'alignement de chaque ligne dans l'étiquette multiligne.

#### Q5. Puis-je aligner les étiquettes de graduation différemment pour l'axe X et l'axe Y dans un graphique ?
 Oui, vous pouvez aligner les étiquettes de graduation différemment pour l'axe X et l'axe Y dans un graphique à l'aide de Aspose.Words pour .NET. La propriété d'alignement des étiquettes de graduation est spécifique à chaque axe du graphique. En accédant au correspondant`ChartAxis` objet pour l'axe X ou l'axe Y, vous pouvez définir indépendamment l'alignement de l'étiquette de graduation sur différentes valeurs. Cela vous offre la possibilité d'aligner les étiquettes de graduation différemment en fonction de vos besoins spécifiques pour chaque axe du graphique.