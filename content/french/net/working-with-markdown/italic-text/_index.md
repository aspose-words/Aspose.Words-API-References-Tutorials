---
title: Texte en italique
linktitle: Texte en italique
second_title: API de traitement de documents Aspose.Words
description: Apprenez à mettre du texte en italique avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/italic-text/
---

Dans cet exemple, nous vous expliquerons comment utiliser la fonctionnalité de texte en italique avec Aspose.Words pour .NET. Le texte en italique est utilisé pour souligner certaines parties d'un document.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Mettre le texte en italique

 Nous pouvons mettre le texte en italique en définissant la police`Italic` propriété à`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Exemple de code source pour le texte en italique avec Aspose.Words pour .NET


```csharp
// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Mettez le texte en italique.
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité de texte en italique avec Aspose.Words pour .NET.


### FAQ

#### Q : Comment puis-je mettre du texte en italique dans Aspose.Words ?

 : Pour mettre en italique du texte dans Aspose.Words, vous pouvez utiliser le`Font.Italic` propriété de la`Run`objet. Vous pouvez définir cette propriété sur`true` pour mettre en italique un texte spécifique. Par exemple, vous pouvez utiliser`run.Font.Italic=true` mettre en italique le texte contenu dans le`Run` objet.

#### Q : Est-il possible de mettre en italique plusieurs parties de texte dans le même paragraphe ?

 R : Oui, vous pouvez mettre en italique plusieurs parties de texte dans un même paragraphe en utilisant plusieurs`Run` objets. Vous pouvez créer plusieurs`Run` objets et définissez les`Font.Italic` propriété à`true` pour chaque objet pour mettre en italique les parties de texte souhaitées. Ensuite, vous pouvez les ajouter au paragraphe en utilisant le`Paragraph.AppendChild(run)` méthode.

#### Q : Puis-je mettre en italique du texte qui se trouve dans un tableau ou une cellule dans Aspose.Words ?

 R : Oui, vous pouvez mettre en italique le texte qui se trouve dans un tableau ou une cellule dans Aspose.Words. Vous pouvez accéder à la cellule ou au paragraphe de votre choix à l'aide des méthodes appropriées, puis appliquer la mise en forme en italique à l'aide de la`Font.Italic` propriété de la`Run` ou`Paragraph` objet.