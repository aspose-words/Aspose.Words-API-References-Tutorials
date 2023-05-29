---
title: Barré
linktitle: Barré
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à appliquer le style de texte barré avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/strikethrough/
---


Dans cet exemple, nous vous expliquerons comment appliquer le style de texte barré à l'aide de Aspose.Words pour .NET. Le texte barré est utilisé pour indiquer que le texte est supprimé ou n'est plus valide.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Appliquer le style de texte barré

 Nous allons activer le style de texte barré en définissant le`StrikeThrough` propriété de la`Font` s'opposer à`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Étape 3 : Ajoutez du texte barré

 Nous pouvons maintenant ajouter du texte barré en utilisant le générateur de document`Writeln` méthode.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Exemple de code source pour le texte barré avec Aspose.Words pour .NET

```csharp
// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Faites le texte Barré.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Félicitation ! Vous avez maintenant appris à appliquer le style de texte barré avec Aspose.Words pour .NET.
