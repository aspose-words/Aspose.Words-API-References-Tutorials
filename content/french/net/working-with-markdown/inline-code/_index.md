---
title: Code en ligne
linktitle: Code en ligne
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment appliquer des styles de code en ligne dans des documents Word à l'aide d'Aspose.Words pour .NET. Ce didacticiel couvre les backticks simples et multiples pour le formatage du code.
type: docs
weight: 10
url: /fr/net/working-with-markdown/inline-code/
---
## Introduction

Si vous travaillez sur la génération ou la manipulation de documents Word par programmation, vous devrez peut-être formater le texte pour qu'il ressemble à du code. Qu'il s'agisse de documentation ou d'extraits de code dans un rapport, Aspose.Words for .NET fournit un moyen robuste de gérer le style du texte. Dans ce didacticiel, nous nous concentrerons sur la façon d'appliquer des styles de code en ligne au texte à l'aide d'Aspose.Words. Nous explorerons comment définir et utiliser des styles personnalisés pour des backticks simples ou multiples, afin que vos segments de code ressortent clairement dans vos documents.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

1.  Aspose.Words pour la bibliothèque .NET : assurez-vous que Aspose.Words est installé dans votre environnement .NET. Vous pouvez le télécharger depuis le[Page des versions d'Aspose.Words pour .NET](https://releases.aspose.com/words/net/).

2. Connaissance de base de la programmation .NET : ce guide suppose que vous possédez une compréhension fondamentale de la programmation C# et .NET.

3. Environnement de développement : vous devez disposer d'un environnement de développement .NET, tel que Visual Studio, dans lequel vous pouvez écrire et exécuter du code C#.

## Importer des espaces de noms

Pour commencer à utiliser Aspose.Words dans votre projet, vous devrez importer les espaces de noms nécessaires. Voici comment procéder :

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Décomposons le processus en étapes claires :

## Étape 1 : initialiser le document et DocumentBuilder

 Tout d'abord, vous devez créer un nouveau document et un`DocumentBuilder` exemple. Le`DocumentBuilder`La classe vous aide à ajouter du contenu et à le formater dans un document Word.

```csharp
// Initialisez DocumentBuilder avec le nouveau document.
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : ajouter un style de code en ligne avec un seul backtick

Dans cette étape, nous définirons un style pour le code en ligne avec un seul backtick. Ce style formatera le texte pour qu'il ressemble à du code en ligne.

### Définir le style

```csharp
// Définissez un nouveau style de caractère pour le code en ligne avec un backtick.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
inlineCode1BackTicks.Font.Name = "Courier New"; // Une police typique pour le code.
inlineCode1BackTicks.Font.Size = 10.5; // Taille de police pour le code en ligne.
inlineCode1BackTicks.Font.Color = System.Drawing.Color.Blue; // Couleur du texte du code.
inlineCode1BackTicks.Font.Bold = true; // Mettez le texte du code en gras.
```

### Appliquer le style

Vous pouvez désormais appliquer ce style au texte de votre document.

```csharp
// Utilisez DocumentBuilder pour insérer du texte avec le style de code en ligne.
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");
```

## Étape 3 : ajouter un style de code en ligne avec trois backticks

Ensuite, nous définirons un style pour le code en ligne avec trois backticks, qui est généralement utilisé pour les blocs de code multilignes.

### Définir le style

```csharp
// Définissez un nouveau style de caractère pour le code en ligne avec trois backticks.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
inlineCode3BackTicks.Font.Name = "Courier New"; // Police cohérente pour le code.
inlineCode3BackTicks.Font.Size = 10.5; // Taille de police pour le bloc de code.
inlineCode3BackTicks.Font.Color = System.Drawing.Color.Green; //Couleur différente pour la visibilité.
inlineCode3BackTicks.Font.Bold = true; // Gardez-le en gras pour mettre l’accent.
```

### Appliquer le style

Appliquez ce style au texte pour le formater sous forme de bloc de code multiligne.

```csharp
// Appliquez le style au bloc de code.
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```

## Conclusion

Le formatage du texte sous forme de code en ligne dans des documents Word à l'aide d'Aspose.Words pour .NET est simple une fois que vous connaissez les étapes. En définissant et en appliquant des styles personnalisés avec un ou plusieurs backticks, vous pouvez faire ressortir clairement vos extraits de code. Cette méthode est particulièrement utile pour la documentation technique ou tout document où la lisibilité du code est essentielle.

N'hésitez pas à expérimenter différents styles et options de formatage pour répondre au mieux à vos besoins. Aspose.Words offre une grande flexibilité, vous permettant de personnaliser dans une large mesure l'apparence de votre document.

## FAQ

### Puis-je utiliser différentes polices pour les styles de code en ligne ?
Oui, vous pouvez utiliser n’importe quelle police adaptée à vos besoins. Les polices telles que « Courier New » sont généralement utilisées pour le code en raison de leur nature à espacement fixe.

### Comment changer la couleur du texte du code en ligne ?
 Vous pouvez changer la couleur en réglant le`Font.Color` propriété du style à tout`System.Drawing.Color`.

### Puis-je appliquer plusieurs styles au même texte ?
Dans Aspose.Words, vous ne pouvez appliquer qu’un seul style à la fois. Si vous devez combiner des styles, envisagez de créer un nouveau style intégrant toutes les mises en forme souhaitées.

### Comment appliquer des styles au texte existant dans un document ?
 Pour appliquer des styles à un texte existant, vous devez d'abord sélectionner le texte, puis appliquer le style souhaité à l'aide du bouton`Font.Style` propriété.

### Puis-je utiliser Aspose.Words pour d’autres formats de documents ?
Aspose.Words est conçu spécifiquement pour les documents Word. Pour d'autres formats, vous devrez peut-être utiliser différentes bibliothèques ou convertir les documents dans un format compatible.