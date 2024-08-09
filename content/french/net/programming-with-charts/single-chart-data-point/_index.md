---
title: Personnaliser un seul point de données de graphique dans un graphique
linktitle: Personnaliser un seul point de données de graphique dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment personnaliser des points de données de graphique unique à l'aide d'Aspose.Words for .NET dans un guide détaillé étape par étape. Améliorez vos graphiques avec des marqueurs et des tailles uniques.
type: docs
weight: 10
url: /fr/net/programming-with-charts/single-chart-data-point/
---
## Introduction

Vous êtes-vous déjà demandé comment faire ressortir vos graphiques avec des points de données uniques ? Eh bien, aujourd'hui, c'est votre jour de chance ! Nous nous penchons sur la personnalisation d'un seul point de données de graphique à l'aide d'Aspose.Words pour .NET. Attachez votre ceinture et parcourez un didacticiel étape par étape non seulement informatif, mais également amusant et facile à suivre.

## Conditions préalables

Avant de commencer, assurons-nous que vous disposez de tous les éléments essentiels :

-  Aspose.Words pour la bibliothèque .NET : assurez-vous de disposer de la dernière version.[Téléchargez-le ici](https://releases.aspose.com/words/net/).
- .NET Framework : assurez-vous que .NET Framework est installé sur votre ordinateur.
- Compréhension de base de C# : Une compréhension de base de la programmation C# sera utile.
- Environnement de développement intégré (IDE) : Visual Studio est recommandé.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires pour lancer le processus :

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Étape 1 : initialiser le document et DocumentBuilder

Très bien, commençons par initialiser un nouveau document et un DocumentBuilder. Ce sera la toile de fond de notre graphique.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ici,`dataDir` est le chemin du répertoire dans lequel vous enregistrerez votre document. Le`DocumentBuilder` la classe aide à construire le document.

## Étape 2 : Insérer un graphique

Ensuite, insérons un graphique linéaire dans le document. Ce sera notre terrain de jeu pour personnaliser les points de données.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

 Le`InsertChart` La méthode prend le type, la largeur et la hauteur du graphique comme paramètres. Dans ce cas, nous insérons un graphique linéaire d'une largeur de 432 et d'une hauteur de 252.

## Étape 3 : Accéder à la série de graphiques

Il est maintenant temps d'accéder aux séries dans notre graphique. Un graphique peut comporter plusieurs séries et chaque série contient des points de données.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];
```

Ici, nous accédons aux deux premières séries de notre graphique. 

## Étape 4 : Personnaliser les points de données

C'est ici que la magie opère ! Personnalisons des points de données spécifiques au sein de notre série.

```csharp
ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];
```

Nous récupérons les points de données de la première série. Maintenant, personnalisons ces points.

### Personnaliser le point de données 00

```csharp
dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;
```

 Pour`dataPoint00`, nous définissons une explosion (utile pour les diagrammes circulaires), changeons le symbole du marqueur en cercle et définissons la taille du marqueur sur 15.

### Personnaliser le point de données 01

```csharp
dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;
```

 Pour`dataPoint01`, nous remplaçons le symbole du marqueur par un losange et définissons la taille du marqueur sur 20.

### Personnaliser le point de données dans la série 1

```csharp
ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

 Pour le troisième point de données dans`series1`, nous le paramétrons pour qu'il s'inverse si la valeur est négative, en changeant le symbole du marqueur en étoile et en définissant la taille du marqueur sur 20.

## Étape 5 : Enregistrez le document

Enfin, sauvons notre document avec toutes les personnalisations.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

 Cette ligne enregistre le document dans le répertoire spécifié sous le nom`WorkingWithCharts.SingleChartDataPoint.docx`.

## Conclusion

Et voilà ! Vous avez personnalisé avec succès des points de données individuels dans un graphique à l'aide d'Aspose.Words pour .NET. En modifiant quelques propriétés, vous pouvez rendre vos graphiques beaucoup plus informatifs et visuellement attrayants. Alors, allez-y et expérimentez différents marqueurs et tailles pour voir ce qui fonctionne le mieux pour vos données.

## FAQ

### Puis-je personnaliser les points de données dans d’autres types de graphiques ?

Absolument! Vous pouvez personnaliser les points de données dans différents types de graphiques, notamment les graphiques à barres, les diagrammes circulaires, etc. Le processus est similaire dans différents types de graphiques.

### Est-il possible d'ajouter des étiquettes personnalisées aux points de données ?

 Oui, vous pouvez ajouter des étiquettes personnalisées aux points de données à l'aide de l'outil`ChartDataPoint.Label` propriété. Cela vous permet de fournir plus de contexte pour chaque point de données.

### Comment puis-je supprimer un point de données d’une série ?

 Vous pouvez supprimer un point de données en définissant sa visibilité sur false en utilisant`dataPoint.IsVisible = false`.

### Puis-je utiliser des images comme marqueurs pour les points de données ?

Bien qu'Aspose.Words ne prenne pas en charge l'utilisation directe d'images comme marqueurs, vous pouvez créer des formes personnalisées et les utiliser comme marqueurs.

### Est-il possible d'animer des points de données dans le graphique ?

Aspose.Words for .NET ne prend pas en charge l'animation des points de données du graphique. Cependant, vous pouvez créer des graphiques animés à l'aide d'autres outils et les intégrer dans vos documents Word.