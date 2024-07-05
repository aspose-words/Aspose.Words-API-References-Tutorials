---
title: Insérer un graphique à nuages de points dans un document Word
linktitle: Insérer un graphique à nuages de points dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un nuage de points dans un document à l'aide d'Aspose.Words pour .NET. Ajoutez des données de série avec les coordonnées X et Y.
type: docs
weight: 10
url: /fr/net/programming-with-charts/insert-scatter-chart/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour insérer un nuage de points dans un document. Le code source fourni montre comment créer un graphique, ajouter des données de série et enregistrer le document.

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

 Ensuite, utilisez le`InsertChart` méthode du`DocumentBuilder` pour insérer un nuage de points dans le document.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous ajouterons deux ensembles de coordonnées X et Y.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide du`Save` méthode du`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Ceci termine la mise en œuvre de l’insertion d’un diagramme à nuages de points à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour insérer un graphique à nuages de points à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Conclusion

Dans ce didacticiel, vous avez appris à insérer un nuage de points dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un nouveau document, insérer un nuage de points, ajouter des données de série avec les coordonnées X et Y et enregistrer le document avec le graphique.

Aspose.Words for .NET fournit une API complète pour le traitement de mots avec des graphiques dans les documents Word. Les diagrammes à nuages de points sont utiles pour visualiser et analyser des données avec deux variables numériques. Avec Aspose.Words pour .NET, vous pouvez facilement créer des nuages de points qui représentent la relation entre les valeurs X et Y et identifier des modèles ou des tendances dans les données.

En utilisant Aspose.Words pour .NET, vous pouvez automatiser le processus de génération de documents avec des nuages de points, économisant ainsi du temps et des efforts dans la création manuelle de documents. La bibliothèque propose une large gamme de types de graphiques, notamment des nuages de points, et propose diverses options de personnalisation pour adapter l'apparence du graphique en fonction de vos besoins.

### FAQ

#### T1. Qu'est-ce qu'un nuage de points ?
Un nuage de points est un type de graphique qui affiche la relation entre deux variables numériques. Il se compose d'une série de points tracés sur une grille de coordonnées, avec une variable représentée sur l'axe X et l'autre variable représentée sur l'axe Y. Les diagrammes à nuages de points sont utilisés pour identifier des modèles, des corrélations ou des tendances entre deux ensembles de points de données.

#### Q2. Puis-je ajouter plusieurs séries au nuage de points ?
Oui, vous pouvez ajouter plusieurs séries au nuage de points à l'aide d'Aspose.Words for .NET. Chaque série représente un ensemble de points de données avec leurs coordonnées X et Y respectives. En ajoutant plusieurs séries, vous pouvez comparer et analyser différents ensembles de données au sein du même nuage de points, offrant ainsi une vue complète de vos données.

#### Q3. Puis-je personnaliser l’apparence du nuage de points ?
Oui, en utilisant Aspose.Words pour .NET, vous pouvez personnaliser divers aspects de l'apparence du nuage de points. Vous pouvez modifier des propriétés telles que la couleur de la série, la forme du marqueur, les étiquettes des axes et le formatage de la zone du graphique. La bibliothèque fournit un riche ensemble d'API pour contrôler les éléments visuels du graphique et créer une apparence personnalisée adaptée à vos besoins.

#### Q4. Puis-je enregistrer le document avec le nuage de points inséré dans différents formats ?
Oui, Aspose.Words for .NET vous permet d'enregistrer le document avec le nuage de points inséré dans différents formats, tels que DOCX, PDF, HTML, etc. Vous pouvez choisir le format de sortie souhaité en fonction de vos besoins et utiliser le`Save` méthode du`Document` objet pour enregistrer le document. Le diagramme de nuages de points inséré sera conservé dans le document enregistré.

#### Q5. Puis-je modifier les données et l’apparence du nuage de points après l’avoir inséré ?
Oui, après avoir inséré le nuage de points dans le document, vous pouvez modifier ses données et son apparence à l'aide des API fournies par Aspose.Words for .NET. Vous pouvez mettre à jour les données de la série avec de nouvelles coordonnées X et Y, modifier les formes et les couleurs des marqueurs, personnaliser les propriétés des axes et appliquer des options de formatage pour créer des graphiques dynamiques et interactifs dans vos documents Word.