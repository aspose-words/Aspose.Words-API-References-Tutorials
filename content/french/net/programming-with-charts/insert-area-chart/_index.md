---
title: Insérer un graphique en aires dans un document Word
linktitle: Insérer un graphique en aires dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment insérer un graphique en aires dans un document à l'aide d'Aspose.Words pour .NET. Ajoutez des données de série et enregistrez le document avec le graphique.
type: docs
weight: 10
url: /fr/net/programming-with-charts/insert-area-chart/
---
## Introduction

Bienvenue dans ce guide étape par étape expliquant comment insérer un graphique en aires dans un document Word à l'aide d'Aspose.Words pour .NET. Que vous soyez un développeur chevronné ou que vous débutiez tout juste, ce didacticiel vous expliquera tout ce que vous devez savoir pour créer des graphiques en aires époustouflants et informatifs dans vos documents Word. Nous couvrirons les conditions préalables, vous montrerons comment importer les espaces de noms nécessaires et vous guiderons à travers chaque étape du processus avec des instructions claires et faciles à suivre.

## Conditions préalables

Avant de plonger dans le vif du sujet, assurons-nous que vous disposez de tout ce dont vous avez besoin pour commencer :

1.  Aspose.Words pour .NET : assurez-vous que Aspose.Words pour .NET est installé. Vous pouvez le télécharger[ici](https://releases.aspose.com/words/net/).
2. .NET Framework : assurez-vous que .NET Framework est installé sur votre ordinateur.
3. IDE : un environnement de développement intégré (IDE) comme Visual Studio pour écrire et exécuter votre code.
4. Connaissances de base en C# : Une compréhension de base de la programmation C# sera utile.

Une fois ces conditions préalables remplies, vous êtes prêt à commencer à créer de superbes graphiques en aires dans vos documents Word.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires. Ces espaces de noms fournissent les classes et méthodes requises pour utiliser des documents et des graphiques Word dans Aspose.Words for .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System;
```

Maintenant que nous avons importé les espaces de noms essentiels, passons à la création de notre document et à l'insertion d'un graphique en aires étape par étape.

## Étape 1 : Créer un nouveau document Word

Commençons par créer un nouveau document Word. Ce sera la base sur laquelle nous insérerons notre carte en aires.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 Dans cette étape, nous initialisons un nouveau`Document` objet qui représente notre document Word.

## Étape 2 : utiliser DocumentBuilder pour insérer un graphique

 Ensuite, nous utiliserons le`DocumentBuilder` classe pour insérer un graphique en aires dans notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
```

 Ici, nous créons un`DocumentBuilder` objet et utilisez-le pour insérer un graphique en aires de dimensions spécifiques (432x252) dans notre document.

## Étape 3 : accéder à l'objet graphique

 Après avoir inséré le graphique, nous devons accéder au`Chart` objet pour personnaliser notre graphique en aires.

```csharp
Chart chart = shape.Chart;
```

 Cette ligne de code récupère le`Chart` objet à partir de la forme que nous venons d’insérer.

## Étape 4 : ajouter des données de série au graphique

Il est maintenant temps d'ajouter quelques données à notre graphique. Nous ajouterons une série avec des dates et des valeurs correspondantes.

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

Dans cette étape, nous ajoutons une série nommée « Aspose Series 1 » avec un ensemble de dates et de valeurs correspondantes.

## Étape 5 : Enregistrez le document

Enfin, nous enregistrerons notre document avec le graphique en aires inséré.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Cette ligne de code enregistre le document dans le répertoire spécifié avec le nom de fichier donné.

## Conclusion

Toutes nos félicitations! Vous avez réussi à insérer un graphique en aires dans un document Word à l'aide d'Aspose.Words pour .NET. Ce guide vous a accompagné à chaque étape, depuis la configuration de votre environnement jusqu'à l'enregistrement du document final. Avec Aspose.Words pour .NET, vous pouvez créer une grande variété de graphiques et d'autres éléments complexes dans vos documents Word, rendant ainsi vos rapports et présentations plus dynamiques et informatifs.

## FAQ

### Puis-je utiliser Aspose.Words pour .NET avec d’autres langages .NET ?
Oui, Aspose.Words for .NET prend en charge d'autres langages .NET tels que VB.NET.

### Est-il possible de personnaliser l'apparence du graphique ?
Absolument! Aspose.Words for .NET fournit de nombreuses options pour personnaliser l'apparence de vos graphiques.

### Puis-je ajouter plusieurs graphiques à un seul document Word ?
Oui, vous pouvez insérer autant de graphiques que nécessaire dans un seul document Word.

### Aspose.Words for .NET prend-il en charge d’autres types de graphiques ?
Oui, Aspose.Words for .NET prend en charge différents types de graphiques, notamment à barres, à courbes, à secteurs, etc.

### Où puis-je obtenir une licence temporaire pour Aspose.Words for .NET ?
 Vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).