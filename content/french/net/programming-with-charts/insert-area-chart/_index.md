---
title: Insérer un graphique en aires dans un document Word
linktitle: Insérer un graphique en aires dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un graphique en aires dans un document à l'aide d'Aspose.Words pour .NET. Ajoutez des données de série et enregistrez le document avec le graphique.
type: docs
weight: 10
url: /fr/net/programming-with-charts/insert-area-chart/
---

Ce didacticiel explique comment utiliser Aspose.Words for .NET pour insérer un graphique en aires dans un document. Le code source fourni montre comment créer un graphique, ajouter des données de série et enregistrer le document.

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

 Ensuite, utilisez le`InsertChart` méthode du`DocumentBuilder` pour insérer un graphique en aires dans le document.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Étape 3 : Ajouter des données de série au graphique

Ajoutez des données de série au graphique. Dans cet exemple, nous ajouterons cinq points de données avec les dates et valeurs correspondantes.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## Étape 4 : Enregistrez le document

 Enfin, enregistrez le document dans le répertoire spécifié à l'aide du`Save` méthode du`Document` objet.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Ceci termine la mise en œuvre de l’insertion d’un graphique en aires à l’aide d’Aspose.Words pour .NET.

### Exemple de code source pour Insérer un graphique en aires à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Conclusion

Dans ce didacticiel, vous avez appris à insérer un graphique en aires dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez créer un nouveau document, insérer un graphique en aires, ajouter des données de série et enregistrer le document avec le graphique.

Aspose.Words for .NET fournit une API puissante pour le traitement de mots avec des graphiques dans les documents Word. Avec seulement quelques lignes de code, vous pouvez créer des graphiques en aires d'aspect professionnel et les personnaliser en fonction de vos besoins. Les graphiques en aires sont couramment utilisés pour afficher l'ampleur et les tendances des données au fil du temps ou par catégories.

En utilisant Aspose.Words pour .NET, vous pouvez automatiser le processus de génération de documents avec des graphiques en aires, économisant ainsi du temps et des efforts dans la création manuelle de documents. La bibliothèque propose une large gamme de types de graphiques et d'options de personnalisation, vous permettant de créer des graphiques visuellement attrayants et informatifs dans vos documents Word.

### FAQ

#### T1. Qu’est-ce qu’Aspose.Words pour .NET ?
Aspose.Words for .NET est une puissante bibliothèque de traitement de documents qui permet aux développeurs de créer, modifier et convertir des documents Word par programme dans des applications .NET. Il fournit un ensemble complet d'API pour le traitement de texte avec des éléments de document, notamment des graphiques, des paragraphes, des tableaux, etc.

#### Q2. Comment installer Aspose.Words pour .NET ?
Pour installer Aspose.Words pour .NET, vous pouvez utiliser le gestionnaire de packages NuGet dans Visual Studio pour installer la bibliothèque directement dans votre projet. Recherchez simplement « Apose.Words » dans le gestionnaire de packages NuGet et installez le package.

#### Q3. Puis-je personnaliser l’apparence du graphique en aires ?
Oui, en utilisant Aspose.Words pour .NET, vous pouvez personnaliser divers aspects de l’apparence du graphique en aires. Vous pouvez modifier les propriétés telles que le titre du graphique, la couleur de la série, les étiquettes des axes et le formatage de la zone du graphique. La bibliothèque fournit un riche ensemble d'API pour contrôler les éléments visuels du graphique et créer une apparence personnalisée adaptée à vos besoins.

#### Q4. Puis-je ajouter plusieurs séries au graphique en aires ?
Oui, vous pouvez ajouter plusieurs séries au graphique en aires à l'aide d'Aspose.Words for .NET. Chaque série représente un ensemble de points de données tracés sur le graphique. Vous pouvez ajouter des séries avec différents ensembles de données et personnaliser chaque série individuellement, notamment son nom, ses points de données et son apparence.

#### Q5. Puis-je enregistrer le document avec le graphique en aires inséré dans différents formats ?
 Oui, Aspose.Words for .NET vous permet d'enregistrer le document avec le graphique en aires inséré dans différents formats, tels que DOCX, PDF, HTML, etc. Vous pouvez choisir le format de sortie souhaité en fonction de vos besoins et utiliser le`Save` méthode du`Document` objet pour enregistrer le document. Le graphique en aires inséré sera conservé dans le document enregistré.

#### Q6. Puis-je modifier les données et l’apparence du graphique en aires après l’avoir inséré ?
Oui, après avoir inséré le graphique en aires dans le document, vous pouvez modifier ses données et son apparence à l'aide des API fournies par Aspose.Words for .NET. Vous pouvez mettre à jour les données de la série, modifier le type de graphique, personnaliser les propriétés des axes et appliquer des options de formatage pour créer des graphiques dynamiques et interactifs dans vos documents Word.