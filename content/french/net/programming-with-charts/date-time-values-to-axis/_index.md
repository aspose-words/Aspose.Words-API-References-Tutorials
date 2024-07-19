---
title: Ajouter des valeurs de date et d'heure à l'axe d'un graphique
linktitle: Ajouter des valeurs de date et d'heure à l'axe d'un graphique
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment ajouter des valeurs de date et d'heure à l'axe d'un graphique à l'aide d'Aspose.Words for .NET dans ce guide complet étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-charts/date-time-values-to-axis/
---
## Introduction

La création de graphiques dans des documents peut être un moyen puissant de visualiser des données. Lorsqu'il s'agit de données de séries chronologiques, l'ajout de valeurs de date et d'heure à l'axe d'un graphique est crucial pour plus de clarté. Dans ce didacticiel, nous vous guiderons tout au long du processus d'ajout de valeurs de date et d'heure à l'axe d'un graphique à l'aide d'Aspose.Words for .NET. Ce guide étape par étape vous aidera à configurer votre environnement, à écrire le code et à comprendre chaque partie du processus. Allons-y !

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. Visual Studio ou n'importe quel IDE .NET : vous avez besoin d'un environnement de développement pour écrire et exécuter votre code .NET.
2.  Aspose.Words pour .NET : la bibliothèque Aspose.Words pour .NET doit être installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/words/net/).
3. Connaissance de base de C# : ce didacticiel suppose que vous possédez une compréhension de base de la programmation C#.
4.  Une licence Aspose valide : Vous pouvez obtenir une licence temporaire auprès de[ici](https://purchase.aspose.com/temporary-license/).

## Importer des espaces de noms

Pour commencer, assurez-vous d'avoir importé les espaces de noms nécessaires dans votre projet. Cette étape est cruciale pour accéder aux classes et méthodes Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Étape 1 : Configurez votre répertoire de documents

Tout d'abord, vous devez définir le répertoire dans lequel votre document sera enregistré. Ceci est important pour organiser vos fichiers et garantir que votre code s'exécute correctement.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Étape 2 : Créer un nouveau document et DocumentBuilder

 Ensuite, créez une nouvelle instance du`Document` classe et un`DocumentBuilder` objet. Ces objets vous aideront à créer et à manipuler votre document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Insérer un graphique dans le document

 Maintenant, insérez un graphique dans votre document à l'aide du`DocumentBuilder` objet. Dans cet exemple, nous utilisons un histogramme, mais vous pouvez également choisir d'autres types.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Étape 4 : Effacer les séries existantes

Effacez toutes les séries existantes dans le graphique pour vous assurer de commencer avec une table vierge. Cette étape est essentielle pour les données personnalisées.

```csharp
chart.Series.Clear();
```

## Étape 5 : ajouter des valeurs de date et d'heure à la série

Ajoutez vos valeurs de date et d'heure à la série de graphiques. Cette étape implique la création de tableaux pour les dates et les valeurs correspondantes.

```csharp
chart.Series.Add("Aspose Series 1",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Étape 6 : Configurer l'axe X

Définissez la mise à l'échelle et les graduations pour l'axe X. Cela garantit que vos dates sont affichées correctement et à intervalles appropriés.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Étape 7 : Enregistrez le document

Enfin, enregistrez votre document dans le répertoire spécifié. Cette étape conclut le processus et votre document doit maintenant contenir un graphique avec les valeurs de date et d'heure sur l'axe X.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

## Conclusion

L'ajout de valeurs de date et d'heure à l'axe d'un graphique dans un document est un processus simple avec Aspose.Words pour .NET. En suivant les étapes décrites dans ce didacticiel, vous pouvez créer des graphiques clairs et informatifs qui visualisent efficacement les données de séries chronologiques. Que vous prépariez des rapports, des présentations ou tout autre document nécessitant une représentation détaillée des données, Aspose.Words fournit les outils dont vous avez besoin pour réussir.

## FAQ

### Puis-je utiliser d’autres types de graphiques avec Aspose.Words pour .NET ?

Oui, Aspose.Words prend en charge différents types de graphiques, notamment les courbes, les barres, les secteurs, etc.

### Comment puis-je personnaliser l'apparence de mon graphique ?

Vous pouvez personnaliser l'apparence en accédant aux propriétés du graphique et en définissant les styles, les couleurs, etc.

### Est-il possible d'ajouter plusieurs séries à un graphique ?

 Absolument! Vous pouvez ajouter plusieurs séries à votre graphique en appelant le`Series.Add` méthode plusieurs fois avec des données différentes.

### Que se passe-t-il si je dois mettre à jour les données du graphique de manière dynamique ?

Vous pouvez mettre à jour les données du graphique de manière dynamique en manipulant les propriétés des séries et des axes par programme en fonction de vos besoins.

### Où puis-je trouver une documentation plus détaillée pour Aspose.Words pour .NET ?

 Vous pouvez trouver une documentation plus détaillée[ici](https://reference.aspose.com/words/net/).