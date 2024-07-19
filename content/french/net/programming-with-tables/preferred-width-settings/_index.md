---
title: Paramètres de largeur préférés
linktitle: Paramètres de largeur préférés
second_title: API de traitement de documents Aspose.Words
description: Apprenez à créer des tableaux avec des paramètres de largeur absolus, relatifs et automatiques dans Aspose.Words for .NET avec ce guide étape par étape.
type: docs
weight: 10
url: /fr/net/programming-with-tables/preferred-width-settings/
---
## Introduction

Les tableaux constituent un moyen puissant d’organiser et de présenter des informations dans vos documents Word. Lorsque vous travaillez avec des tableaux dans Aspose.Words for .NET, vous disposez de plusieurs options pour définir la largeur des cellules du tableau afin de garantir qu'elles s'adaptent parfaitement à la mise en page de votre document. Ce guide vous guidera tout au long du processus de création de tableaux avec des paramètres de largeur préférés à l'aide d'Aspose.Words pour .NET, en se concentrant sur les options de dimensionnement absolu, relatif et automatique. 

## Conditions préalables

Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :

1.  Aspose.Words for .NET : assurez-vous que Aspose.Words for .NET est installé dans votre environnement de développement. Vous pouvez le télécharger[ici](https://releases.aspose.com/words/net/).

2. Environnement de développement .NET : disposez d'un environnement de développement .NET, tel que Visual Studio.

3. Connaissance de base de C# : la familiarité avec la programmation C# vous aidera à mieux comprendre les extraits de code et les exemples.

4.  Documentation Aspose.Words : reportez-vous à la[Documentation Aspose.Words](https://reference.aspose.com/words/net/) pour des informations détaillées sur l'API et des lectures complémentaires.

## Importer des espaces de noms

Avant de commencer à coder, vous devez importer les espaces de noms nécessaires dans votre projet C# :

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Ces espaces de noms donnent accès aux fonctionnalités de base d'Aspose.Words et de l'objet Table, vous permettant de manipuler des tableaux de documents.

Décomposons le processus de création d'un tableau avec différents paramètres de largeur préférés en étapes claires et gérables.

## Étape 1 : initialiser le document et DocumentBuilder

Titre : Création d'un nouveau document et DocumentBuilder

 Explication : Commencez par créer un nouveau document Word et un`DocumentBuilder` exemple. Le`DocumentBuilder` La classe fournit un moyen simple d’ajouter du contenu à votre document.

```csharp
// Définissez le chemin pour enregistrer le document.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Créez un nouveau document.
Document doc = new Document();

// Créez un DocumentBuilder pour ce document.
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ici, vous spécifiez le répertoire dans lequel le document sera enregistré et initialisez le`Document`et`DocumentBuilder` objets.

## Étape 2 : Insérez la première cellule du tableau avec une largeur absolue

Insérez la première cellule dans le tableau avec une largeur fixe de 40 points. Cela garantira que cette cellule conserve toujours une largeur de 40 points quelle que soit la taille du tableau.

```csharp

// Insérez une cellule de taille absolue.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell at 40 points width");
```

Dans cette étape, vous commencez à créer le tableau et insérez une cellule avec une largeur absolue. Le`PreferredWidth.FromPoints(40)` La méthode définit la largeur de la cellule à 40 points, et`Shading.BackgroundPatternColor` applique une couleur de fond jaune clair.

## Étape 3 : Insérer une cellule de taille relative

Insérez une autre cellule d'une largeur correspondant à 20 % de la largeur totale du tableau. Ce dimensionnement relatif garantit que la cellule s'ajuste proportionnellement à la largeur du tableau.

```csharp
// Insérez une cellule de taille relative (pourcentage).
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell at 20% width");
```

La largeur de cette cellule représentera 20 % de la largeur totale du tableau, ce qui la rendra adaptable à différentes tailles d'écran ou mises en page de documents.

### Étape 4 : Insérer une cellule de taille automatique

Enfin, insérez une cellule qui se redimensionne automatiquement en fonction de l'espace disponible restant dans le tableau.

```csharp
// Insérez une cellule de taille automatique.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Cell automatically sized. The size of this cell is calculated from the table preferred width.");
builder.Writeln("In this case the cell will fill up the rest of the available space.");
```

 Le`PreferredWidth.Auto` Le paramètre permet à cette cellule de s'étendre ou de se contracter en fonction de l'espace restant une fois les autres cellules prises en compte. Cela garantit que la disposition de la table semble équilibrée et professionnelle.

## Étape 5 : finaliser et enregistrer le document

Une fois que vous avez inséré toutes vos cellules, complétez le tableau et enregistrez le document dans le chemin spécifié.

```csharp
// Enregistrez le document.
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Cette étape finalise le tableau et enregistre le document sous le nom de fichier « WorkingWithTables.PreferredWidthSettings.docx » dans votre répertoire désigné.

## Conclusion

La création de tableaux avec des paramètres de largeur préférés dans Aspose.Words pour .NET est simple une fois que vous comprenez les différentes options de dimensionnement disponibles. Que vous ayez besoin de largeurs de cellules fixes, relatives ou automatiques, Aspose.Words offre la flexibilité nécessaire pour gérer efficacement divers scénarios de disposition de tableau. En suivant les étapes décrites dans ce guide, vous pouvez vous assurer que vos tableaux sont bien structurés et visuellement attrayants dans vos documents Word.

## FAQ

### Quelle est la différence entre les largeurs de cellule absolues et relatives ?
Les largeurs absolues des cellules sont fixes et ne changent pas, tandis que les largeurs relatives s'ajustent en fonction de la largeur totale du tableau.

### Puis-je utiliser des pourcentages négatifs pour les largeurs relatives ?
Non, les pourcentages négatifs ne sont pas valables pour les largeurs de cellules. Seuls les pourcentages positifs sont autorisés.

### Comment fonctionne la fonctionnalité de dimensionnement automatique ?
Le dimensionnement automatique ajuste la largeur de la cellule pour remplir tout espace restant dans le tableau une fois que les autres cellules ont été redimensionnées.

### Puis-je appliquer différents styles à des cellules avec des paramètres de largeur différents ?
Oui, vous pouvez appliquer différents styles et mises en forme aux cellules quels que soient leurs paramètres de largeur.

### Que se passe-t-il si la largeur totale du tableau est inférieure à la somme de toutes les largeurs de cellules ?
Le tableau ajustera automatiquement la largeur des cellules pour les adapter à l'espace disponible, ce qui peut entraîner un rétrécissement de certaines cellules.