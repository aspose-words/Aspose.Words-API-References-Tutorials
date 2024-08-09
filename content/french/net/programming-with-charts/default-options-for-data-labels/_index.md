---
title: Définir les options par défaut pour les étiquettes de données dans un graphique
linktitle: Définir les options par défaut pour les étiquettes de données dans un graphique
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir les options par défaut pour les étiquettes de données dans un graphique à l'aide d'Aspose.Words for .NET. Suivez notre guide étape par étape pour créer et personnaliser des graphiques sans effort.
type: docs
weight: 10
url: /fr/net/programming-with-charts/default-options-for-data-labels/
---
## Introduction

Salut! Êtes-vous impatient de plonger dans le monde de l’automatisation des documents ? Aujourd'hui, nous allons explorer comment utiliser Aspose.Words for .NET pour créer de superbes documents par programmation. Aspose.Words est une bibliothèque puissante qui vous permet de manipuler facilement des documents Word. Dans ce didacticiel, nous nous concentrerons sur la définition des options par défaut pour les étiquettes de données dans un graphique. Que vous soyez un développeur chevronné ou un débutant, ce guide vous guidera à travers chaque étape pour vous permettre d'être opérationnel en un rien de temps.

## Conditions préalables

Avant de commencer, assurons-nous que vous disposez de tout ce dont vous avez besoin pour suivre ce didacticiel. Voici une liste de contrôle rapide :

- Visual Studio ou tout autre IDE compatible .NET : c'est ici que vous écrirez et exécuterez votre code.
-  Aspose.Words pour .NET : vous pouvez[télécharger la dernière version](https://releases.aspose.com/words/net/) et installez-le dans votre projet.
- Connaissance de base de la programmation C# : bien que ce guide soit adapté aux débutants, une petite familiarité avec C# sera utile.
- .NET Framework installé : assurez-vous que .NET Framework est configuré sur votre ordinateur.
-  Une licence temporaire pour Aspose.Words : obtenez-en une[ici](https://purchase.aspose.com/temporary-license/) pour débloquer toutes les fonctionnalités.

Une fois que vous avez réglé ces prérequis, nous sommes prêts à démarrer !

## Importer des espaces de noms

Tout d’abord, configurons notre projet et importons les espaces de noms nécessaires. Ces espaces de noms sont cruciaux pour accéder à la fonctionnalité Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.ReportingServices;
```

## Étape 1 : Créer un nouveau document


 Le voyage commence par la création d'un nouveau document et l'initialisation d'un`DocumentBuilder` . Le`DocumentBuilder` La classe fournit un ensemble de méthodes pour manipuler facilement le contenu du document.

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créer un nouveau document
Document doc = new Document();

// Initialiser DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Explication

 Dans cette étape, nous avons configuré le document et le générateur que nous utiliserons pour insérer et formater notre contenu. Le`dataDir` La variable contient le chemin où nous enregistrerons notre document final.

## Étape 2 : Insérer un graphique

 Ensuite, nous ajouterons un diagramme circulaire à notre document. Le`InsertChart` méthode du`DocumentBuilder` la classe rend cela super facile.

```csharp
// Insérer un diagramme circulaire
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);

// Accéder à l'objet graphique
Chart chart = shape.Chart;
```

### Explication

Ici, nous insérons un diagramme circulaire dans notre document. Le`InsertChart` La méthode nécessite le type, la largeur et la hauteur du graphique comme paramètres. Après avoir inséré le graphique, nous accédons à l’objet graphique pour le manipuler davantage.

## Étape 3 : Personnaliser la série de graphiques

Maintenant, nous allons effacer toutes les séries existantes dans le graphique et ajouter notre série personnalisée. Cette série représentera nos points de données.

```csharp
// Effacer les séries de graphiques existantes
chart.Series.Clear();

// Ajouter une nouvelle série au graphique
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

### Explication

Dans cette étape, nous nous assurons que notre graphique est vide en effaçant toute série préexistante. Ensuite, nous ajoutons une nouvelle série avec des catégories et des valeurs personnalisées, qui seront affichées dans notre diagramme circulaire.

## Étape 4 : Définir les options par défaut pour les étiquettes de données

Les étiquettes de données sont cruciales pour rendre votre graphique informatif. Nous définirons les options pour afficher le pourcentage, la valeur et personnaliserons le séparateur.

```csharp
// Accéder à la collection d'étiquettes de données
ChartDataLabelCollection labels = series.DataLabels;

// Définir les options d'étiquette de données
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

### Explication

 Ici, nous accédons au`DataLabels`propriété de notre série pour personnaliser l'apparence et les informations affichées sur chaque étiquette de données. Nous avons choisi d'afficher à la fois le pourcentage et la valeur, de masquer les lignes de repère et de définir un séparateur personnalisé.

## Étape 5 : Enregistrez le document

Enfin, nous enregistrerons notre document dans le répertoire spécifié. Cette étape garantit que toutes nos modifications sont écrites dans un fichier.

```csharp
// Enregistrez le document
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

### Explication

 Dans cette dernière étape, nous sauvegardons notre document en utilisant le`Save` méthode. Le document sera enregistré dans le répertoire spécifié par`dataDir`, avec le nom « WorkingWithCharts.DefaultOptionsForDataLabels.docx ».

## Conclusion

Et voilà ! Vous avez créé avec succès un document Word avec un diagramme circulaire personnalisé à l'aide d'Aspose.Words pour .NET. Cette puissante bibliothèque facilite l'automatisation de la création et de la manipulation de documents, vous permettant ainsi d'économiser du temps et des efforts. Que vous génériez des rapports, des factures ou tout autre type de document, Aspose.Words est là pour vous.

 N'hésitez pas à explorer le[Documentation Aspose.Words](https://reference.aspose.com/words/net/) pour plus de fonctionnalités et d’exemples. Bon codage !

## FAQ

### Puis-je utiliser Aspose.Words gratuitement ?
Vous pouvez utiliser Aspose.Words gratuitement avec un[permis temporaire](https://purchase.aspose.com/temporary-license/) ou explorez ses fonctionnalités à l'aide du[essai gratuit](https://releases.aspose.com/).

### Comment puis-je obtenir de l'aide pour Aspose.Words ?
 Vous pouvez obtenir de l'aide via le[Forum d'assistance Aspose.Words](https://forum.aspose.com/c/words/8).

### Puis-je ajouter d’autres types de graphiques ?
 Oui, Aspose.Words prend en charge différents types de graphiques tels que les graphiques à barres, en courbes et en colonnes. Vérifiez le[documentation](https://reference.aspose.com/words/net/) pour plus de détails.

### Aspose.Words est-il compatible avec .NET Core ?
 Oui, Aspose.Words est compatible avec .NET Core. Vous pouvez trouver plus d'informations dans le[documentation](https://reference.aspose.com/words/net/).

### Comment puis-je acheter une licence pour Aspose.Words ?
 Vous pouvez acheter une licence auprès du[Magasin Aspose](https://purchase.aspose.com/buy).

