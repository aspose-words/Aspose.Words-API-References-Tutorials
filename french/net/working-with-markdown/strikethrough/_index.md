---
title: Barré
linktitle: Barré
second_title: API de traitement de documents Aspose.Words
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

 Nous allons activer le style de texte barré en définissant le`StrikeThrough`propriété de la`Font` s'opposer à`true`.

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

### FAQ

#### Q : Comment puis-je ajouter le texte barré dans Aspose.Words ?

 R : Pour ajouter le texte barré dans Aspose.Words, vous pouvez utiliser le`Font.StrikeThrough`propriété de la`Run`objet. Vous pouvez définir cette propriété sur`true` pour ajouter du texte barré à un texte spécifique. Par exemple, vous pouvez utiliser`run.Font.StrikeThrough=true` pour ajouter le texte barré dans le`Run` objet.

#### Q : Est-il possible d'ajouter le texte barré à plusieurs parties de texte dans le même paragraphe ?

 R : Oui, vous pouvez ajouter du texte barré à plusieurs parties de texte dans un même paragraphe en utilisant plusieurs`Run` objets. Vous pouvez créer plusieurs`Run` objets et définissez les`Font.StrikeThrough` propriété à`true`pour chaque objet pour ajouter le texte barré aux parties de texte souhaitées. Ensuite, vous pouvez les ajouter au paragraphe en utilisant le`Paragraph.AppendChild(run)` méthode.

#### Q : Puis-je ajouter du texte barré au texte qui se trouve dans un tableau ou une cellule dans Aspose.Words ?

 R : Oui, vous pouvez ajouter du texte barré au texte qui se trouve dans un tableau ou une cellule dans Aspose.Words. Vous pouvez accéder directement à la cellule ou au paragraphe de votre choix à l'aide des méthodes appropriées, puis appliquer la mise en forme du texte barré à l'aide de la`Font.StrikeThrough`propriété de la`Run` ou`Paragraph` objet.