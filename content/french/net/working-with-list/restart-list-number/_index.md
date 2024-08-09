---
title: Numéro de liste de redémarrage
linktitle: Numéro de liste de redémarrage
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment redémarrer les numéros de liste dans les documents Word à l'aide d'Aspose.Words pour .NET. Ce guide détaillé de 2 000 mots couvre tout ce que vous devez savoir, de la configuration à la personnalisation avancée.
type: docs
weight: 10
url: /fr/net/working-with-list/restart-list-number/
---
## Introduction

Cherchez-vous à maîtriser l’art de la manipulation de listes dans vos documents Word à l’aide d’Aspose.Words pour .NET ? Eh bien, vous êtes au bon endroit ! Dans ce didacticiel, nous allons approfondir le redémarrage des numéros de liste, une fonctionnalité intéressante qui fera passer vos compétences en automatisation de documents au niveau supérieur. Attachez votre ceinture et commençons !

## Conditions préalables

Avant de passer au code, assurons-nous que vous disposez de tout ce dont vous avez besoin :

1.  Aspose.Words pour .NET : vous devez avoir installé Aspose.Words pour .NET. Si vous ne l'avez pas encore installé, vous pouvez[téléchargez-le ici](https://releases.aspose.com/words/net/).
2. Environnement de développement : assurez-vous de disposer d'un environnement de développement approprié tel que Visual Studio.
3. Connaissance de base de C# : Une compréhension de base de C# vous aidera à suivre le didacticiel.

## Importer des espaces de noms

Tout d’abord, importons les espaces de noms nécessaires. Ceux-ci sont cruciaux pour accéder aux fonctionnalités Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
using System.Drawing;
```

Maintenant, décomposons le processus en étapes faciles à suivre. Nous couvrirons tout, de la création d'une liste à la reprise de sa numérotation.

## Étape 1 : Configurez votre document et votre générateur

Avant de pouvoir commencer à manipuler des listes, vous avez besoin d'un document et d'un DocumentBuilder. DocumentBuilder est votre outil incontournable pour ajouter du contenu à votre document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Créez et personnalisez votre première liste

Ensuite, nous allons créer une liste basée sur un modèle et personnaliser son apparence. Dans cet exemple, nous utilisons le format de nombre arabe avec parenthèses.

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

Ici, nous avons défini la couleur de la police sur rouge et aligné le texte à droite.

## Étape 3 : ajoutez des éléments à votre première liste

 Une fois votre liste prête, il est temps d'ajouter quelques éléments. Le DocumentBuilder`ListFormat.List` La propriété aide à appliquer le format de liste au texte.

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Étape 4 : Redémarrer la numérotation des listes

Pour réutiliser la liste et relancer sa numérotation, vous devez créer une copie de la liste originale. Cela vous permet de modifier la nouvelle liste indépendamment.

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Dans cet exemple, la nouvelle liste commence au numéro 10.

## Étape 5 : ajouter des éléments à la nouvelle liste

Comme avant, ajoutez des éléments à votre nouvelle liste. Cela montre que la liste redémarre au numéro spécifié.

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Étape 6 : Enregistrez votre document

Enfin, enregistrez votre document dans le répertoire spécifié.

```csharp
builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
```

## Conclusion

Le redémarrage des numéros de liste dans les documents Word à l'aide d'Aspose.Words pour .NET est simple et incroyablement utile. Que vous génériez des rapports, créiez des documents structurés ou que vous ayez simplement besoin d'un meilleur contrôle sur vos listes, cette technique est là pour vous.

## FAQ

### Puis-je utiliser d’autres modèles de liste que NumberArabicParenthesis ?

Absolument! Aspose.Words propose divers modèles de listes tels que des puces, des lettres, des chiffres romains, etc. Vous pouvez choisir celui qui correspond le mieux à vos besoins.

### Comment changer le niveau de la liste ?

 Vous pouvez changer le niveau de liste en modifiant le`ListLevels` propriété. Par exemple,`list1.ListLevels[1]` ferait référence au deuxième niveau de la liste.

### Puis-je recommencer la numérotation à n’importe quel numéro ?

 Oui, vous pouvez définir le numéro de départ sur n'importe quelle valeur entière à l'aide de la touche`StartAt` propriété du niveau liste.

### Est-il possible d'avoir un formatage différent pour différents niveaux de liste ?

En effet! Chaque niveau de liste peut avoir ses propres paramètres de formatage, tels que la police, l'alignement et le style de numérotation.

### Que faire si je souhaite continuer la numérotation d'une liste précédente au lieu de recommencer ?

Si vous souhaitez continuer la numérotation, vous n'avez pas besoin de créer une copie de la liste. Continuez simplement à ajouter des éléments à la liste d'origine.


