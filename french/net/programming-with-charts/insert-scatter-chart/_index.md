---
title: Insérer un nuage de points dans un document Word
linktitle: Insérer un nuage de points dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à insérer un nuage de points dans un document à l'aide d'Aspose.Words pour .NET. Ajoutez des données de série avec les coordonnées X et Y.
type: docs
weight: 10
url: /fr/net/programming-with-charts/insert-scatter-chart/
---

Ce tutoriel explique comment utiliser Aspose.Words pour .NET pour insérer un nuage de points dans un document. Le code source fourni montre comment créer un graphique, ajouter des données de série et enregistrer le document.

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
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous allons ajouter deux ensembles de coordonnées X et Y.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide de la`Save` méthode de la`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Ceci termine l'implémentation de l'insertion d'un nuage de points à l'aide de Aspose.Words pour .NET.

### Exemple de code source pour Insert Scatter Chart en utilisant Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Conclusion

Dans ce didacticiel, vous avez appris à insérer un nuage de points dans un document Word à l'aide de Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un nouveau document, insérer un graphique en nuage de points, ajouter des données de série avec les coordonnées X et Y et enregistrer le document avec le graphique.

Aspose.Words pour .NET fournit une API complète pour le traitement de mots avec des graphiques dans des documents Word. Les diagrammes de dispersion sont utiles pour visualiser et analyser des données avec deux variables numériques. Avec Aspose.Words pour .NET, vous pouvez facilement créer des diagrammes de dispersion qui représentent la relation entre les valeurs X et Y et identifier des modèles ou des tendances dans les données.

En utilisant Aspose.Words pour .NET, vous pouvez automatiser le processus de génération de documents avec des diagrammes de dispersion, économisant ainsi du temps et des efforts dans la création manuelle de documents. La bibliothèque propose une large gamme de types de graphiques, y compris des graphiques en nuage de points, et fournit diverses options de personnalisation pour adapter l'apparence du graphique en fonction de vos besoins.

### FAQ

#### Q1. Qu'est-ce qu'un nuage de points ?
Un nuage de points est un type de graphique qui affiche la relation entre deux variables numériques. Il se compose d'une série de points tracés sur une grille de coordonnées, avec une variable représentée sur l'axe X et l'autre variable représentée sur l'axe Y. Les diagrammes de dispersion sont utilisés pour identifier des modèles, des corrélations ou des tendances entre deux ensembles de points de données.

#### Q2. Puis-je ajouter plusieurs séries au nuage de points ?
Oui, vous pouvez ajouter plusieurs séries au nuage de points en utilisant Aspose.Words pour .NET. Chaque série représente un ensemble de points de données avec leurs coordonnées X et Y respectives. En ajoutant plusieurs séries, vous pouvez comparer et analyser différents ensembles de données dans le même nuage de points, offrant ainsi une vue complète de vos données.

#### Q3. Puis-je personnaliser l'apparence du nuage de points ?
Oui, en utilisant Aspose.Words pour .NET, vous pouvez personnaliser divers aspects de l'apparence du nuage de points. Vous pouvez modifier des propriétés telles que la couleur de la série, la forme du marqueur, les étiquettes des axes et la mise en forme de la zone de graphique. La bibliothèque fournit un riche ensemble d'API pour contrôler les éléments visuels du graphique et créer un aspect personnalisé qui répond à vos besoins.

#### Q4. Puis-je enregistrer le document avec le nuage de points inséré dans différents formats ?
Oui, Aspose.Words pour .NET vous permet d'enregistrer le document avec le nuage de points inséré dans différents formats, tels que DOCX, PDF, HTML, etc. Vous pouvez choisir le format de sortie souhaité en fonction de vos besoins et utiliser le`Save` méthode de la`Document` objet pour enregistrer le document. Le nuage de points inséré sera conservé dans le document enregistré.

#### Q5. Puis-je modifier les données et l'apparence du nuage de points après l'avoir inséré ?
Oui, après avoir inséré le nuage de points dans le document, vous pouvez modifier ses données et son apparence à l'aide des API fournies par Aspose.Words pour .NET. Vous pouvez mettre à jour les données de la série avec de nouvelles coordonnées X et Y, modifier les formes et les couleurs des marqueurs, personnaliser les propriétés des axes et appliquer des options de mise en forme pour créer des graphiques dynamiques et interactifs dans vos documents Word.