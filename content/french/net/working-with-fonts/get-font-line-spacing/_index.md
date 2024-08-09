---
title: Obtenir l'espacement des lignes de police
linktitle: Obtenir l'espacement des lignes de police
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment obtenir l'espacement des lignes de police à l'aide d'Aspose.Words pour .NET avec ce didacticiel étape par étape. Parfait pour les développeurs.
type: docs
weight: 10
url: /fr/net/working-with-fonts/get-font-line-spacing/
---
## Introduction

Aspose.Words for .NET est une bibliothèque puissante qui vous permet de créer, manipuler et convertir des documents Word par programme. Une tâche courante que vous devrez peut-être effectuer consiste à récupérer l’espacement des lignes d’une police spécifique dans un document. Dans ce didacticiel, nous vous guiderons pas à pas tout au long du processus, en vous assurant que vous pouvez facilement obtenir l'espacement des lignes de police à l'aide d'Aspose.Words pour .NET. 

## Conditions préalables

Avant de plonger dans le code, assurez-vous que les conditions préalables suivantes sont en place :

1.  Aspose.Words for .NET Library : téléchargez et installez la dernière version à partir de[ici](https://releases.aspose.com/words/net/).
2. Environnement de développement : assurez-vous d'avoir configuré un IDE tel que Visual Studio.
3. Connaissance de base de C# : ce didacticiel suppose que vous possédez une compréhension de base de la programmation C#.

## Importer des espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires dans votre projet C#. Ces espaces de noms vous permettront d'accéder aux fonctionnalités Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Décomposons le processus d'obtention de l'espacement des lignes de police en étapes simples et gérables.

## Étape 1 : Créer un nouveau document

La première étape consiste à créer une nouvelle instance de document Word à l'aide d'Aspose.Words pour .NET.

```csharp
Document doc = new Document();
```

## Étape 2 : initialiser DocumentBuilder

Ensuite, nous devons initialiser le`DocumentBuilder` objet. Cet objet nous aidera à construire et manipuler le contenu du document.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : définir les propriétés de la police

Maintenant, nous définissons les propriétés de police du texte que nous voulons insérer. Pour cet exemple, nous utiliserons la police "Calibri".

```csharp
builder.Font.Name = "Calibri";
```

## Étape 4 : Écrire du texte dans le document

 En utilisant le`DocumentBuilder` objet, écrivez du texte dans le document. Ce texte utilisera les propriétés de police que nous avons définies à l'étape précédente.

```csharp
builder.Writeln("Sample Text");
```

## Étape 5 : Récupérer l'objet Police

Pour obtenir l'interligne, nous devons accéder à l'objet fonte du texte que nous venons d'ajouter. Cela peut être fait en naviguant dans la structure du document jusqu'au premier paragraphe.

```csharp
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
```

## Étape 6 : Obtenez l'espacement des lignes

Enfin, nous récupérons l’interligne de l’objet police et l’imprimons sur la console.

```csharp
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Conclusion

Et voilà ! La récupération de l'espacement des lignes de police à l'aide d'Aspose.Words pour .NET est simple lorsque vous la décomposez en ces étapes simples. Que vous créiez un nouveau document ou travailliez avec un document existant, Aspose.Words fournit tous les outils dont vous avez besoin pour gérer efficacement les propriétés des polices.

## FAQ

### Qu’est-ce qu’Aspose.Words pour .NET ?
Aspose.Words for .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et convertir des documents Word par programme à l'aide de C#.

### Puis-je utiliser Aspose.Words pour .NET dans d’autres langages .NET ?
Oui, vous pouvez utiliser Aspose.Words pour .NET avec n'importe quel langage .NET, y compris VB.NET et F#.

### Comment puis-je télécharger Aspose.Words pour .NET ?
 Vous pouvez télécharger la dernière version d’Aspose.Words pour .NET à partir de[ici](https://releases.aspose.com/words/net/).

### Existe-t-il un essai gratuit disponible pour Aspose.Words pour .NET ?
 Oui, vous pouvez bénéficier d'un essai gratuit auprès de[ici](https://releases.aspose.com/).

### Où puis-je trouver la documentation d’Aspose.Words pour .NET ?
 La documentation d'Aspose.Words pour .NET est disponible[ici](https://reference.aspose.com/words/net/).