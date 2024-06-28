---
title: Cochez l'alignement des étiquettes sur plusieurs lignes dans un graphique
linktitle: Cochez l'alignement des étiquettes sur plusieurs lignes dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment aligner les étiquettes multilignes de coches dans un axe de graphique à l’aide d’Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-charts/tick-multi-line-label-alignment/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour définir l'alignement des étiquettes multilignes de graduation dans un axe de graphique. Le code source fourni montre comment créer un graphique, accéder à l'axe et modifier l'alignement des étiquettes de graduation.

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

 Ensuite, utilisez le`InsertChart` méthode du`DocumentBuilder` pour insérer un nuage de points dans le document.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Étape 3 : Définir l'alignement des étiquettes de coche

 Pour définir l'alignement des étiquettes multilignes de graduation, accédez à la`AxisX` propriété du graphique et définissez la`TickLabelAlignment` propriété à l’alignement souhaité. Dans cet exemple, nous définissons l'alignement sur`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide du`Save` méthode du`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Ceci termine la mise en œuvre de la définition de l’alignement des étiquettes multilignes à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour l'alignement des étiquettes sur plusieurs lignes à l'aide d'Aspose.Words pour .NET 

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

## Conclusion

Dans ce didacticiel, vous avez appris à définir l'alignement des étiquettes multilignes de graduation dans un axe de graphique à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un nouveau document, insérer un nuage de points, accéder à l'axe du graphique et modifier l'alignement des étiquettes de graduation.

Aspose.Words for .NET fournit des fonctionnalités puissantes pour manipuler des graphiques dans des documents Word. Les étiquettes multilignes à cocher sont utiles lorsque les étiquettes d'axe contiennent du texte long qui nécessite un retour à la ligne ou une division sur plusieurs lignes. En définissant l'alignement des étiquettes de graduation, vous pouvez contrôler l'alignement horizontal des étiquettes multilignes dans l'axe du graphique, garantissant ainsi une présentation et une lisibilité optimales.

La personnalisation de l'alignement des étiquettes multilignes vous permet d'affiner l'apparence de votre graphique, en particulier lorsqu'il s'agit d'étiquettes longues ou complexes. En alignant les étiquettes à droite, à gauche, au centre ou justifiées, vous pouvez obtenir une disposition équilibrée et visuellement attrayante des étiquettes de graduation le long de l'axe.

Avec Aspose.Words pour .NET, vous pouvez facilement accéder et modifier la propriété d'alignement des étiquettes de graduation d'un axe de graphique, vous offrant ainsi un contrôle total sur l'apparence et la disposition des étiquettes de graduation dans vos graphiques de documents Word.

### FAQ

#### T1. Que sont les étiquettes multilignes dans un axe de graphique ?
Cocher les étiquettes multilignes dans un axe de graphique fait référence aux étiquettes d'axe qui s'étendent sur plusieurs lignes lorsque le texte de l'étiquette est long ou nécessite un retour à la ligne pour s'adapter à l'espace disponible. Au lieu de tronquer le texte de l'étiquette ou de provoquer un encombrement visuel, l'axe du graphique divise automatiquement les étiquettes en plusieurs lignes pour garantir la lisibilité. Les étiquettes multilignes à cocher sont particulièrement utiles lorsqu'il s'agit de longues étiquettes de catégorie ou de valeur dans les graphiques.

#### Q2. Puis-je personnaliser l’alignement des étiquettes de graduation dans un axe de graphique ?
 Oui, vous pouvez personnaliser l'alignement des étiquettes de graduation dans un axe de graphique à l'aide d'Aspose.Words pour .NET. En accédant au`TickLabelAlignment` propriété du`ChartAxis` objet, vous pouvez définir l’alignement souhaité pour les étiquettes de graduation. Les options d'alignement incluent l'alignement à gauche, à droite, au centre ou justifié. L'ajustement de l'alignement vous permet de contrôler le positionnement horizontal des étiquettes de graduation le long de l'axe du graphique, garantissant ainsi une lisibilité et une présentation visuelle appropriées.

#### Q3. Quand dois-je envisager de modifier l’alignement des étiquettes de graduation dans un axe du graphique ?
La modification de l'alignement des étiquettes de graduation dans un axe du graphique est utile lorsque vous avez des étiquettes longues ou multilignes qui nécessitent une présentation et une lisibilité optimales. En ajustant l'alignement, vous pouvez vous assurer que les étiquettes sont correctement alignées et espacées, évitant ainsi les chevauchements ou les troncatures. Envisagez de modifier l'alignement des étiquettes de graduation lorsque vous traitez des graphiques comportant des noms de catégorie longs, des étiquettes de valeurs détaillées ou tout autre scénario dans lequel l'alignement par défaut ne fournit pas l'apparence visuelle souhaitée.

#### Q4. L’alignement des étiquettes de graduation affecte-t-il les étiquettes sur une seule ligne dans un axe de graphique ?
Non, la propriété d'alignement des étiquettes de coche n'affecte pas les étiquettes sur une seule ligne dans un axe de graphique. Il est spécialement conçu pour les étiquettes multilignes nécessitant un emballage ou un fractionnement. Les étiquettes sur une seule ligne sont alignées en fonction des paramètres d’alignement par défaut de l’axe du graphique. La propriété d'alignement des étiquettes de coche s'applique uniquement aux étiquettes qui s'étendent sur plusieurs lignes, vous permettant de contrôler l'alignement de chaque ligne dans l'étiquette multiligne.

#### Q5. Puis-je aligner différemment les étiquettes de graduation pour les axes X et Y dans un graphique ?
 Oui, vous pouvez aligner différemment les étiquettes de graduation pour les axes X et Y dans un graphique à l'aide d'Aspose.Words pour .NET. La propriété d’alignement des étiquettes de graduation est spécifique à chaque axe du graphique. En accédant au correspondant`ChartAxis` objet pour l'axe X ou l'axe Y, vous pouvez définir indépendamment l'alignement de l'étiquette de graduation sur différentes valeurs. Cela vous offre la possibilité d'aligner les étiquettes de graduation différemment en fonction de vos besoins spécifiques pour chaque axe du graphique.