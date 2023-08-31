---
title: Texte en italique
linktitle: Texte en italique
second_title: API de traitement de documents Aspose.Words
description: Apprenez à mettre du texte en italique avec le guide étape par étape d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/italic-text/
---

Dans cet exemple, nous allons vous expliquer comment utiliser la fonctionnalité de texte en italique avec Aspose.Words pour .NET. Le texte en italique est utilisé pour mettre en valeur certaines parties d'un document.

## Étape 1 : Utiliser un générateur de documents

Tout d’abord, nous utiliserons un générateur de documents pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Mettre le texte en italique

 Nous pouvons mettre le texte en italique en définissant la police`Italic` propriété à`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Exemple de code source pour du texte en italique avec Aspose.Words pour .NET


```csharp
// Utilisez un générateur de documents pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Mettez le texte en italique.
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité de texte en italique avec Aspose.Words pour .NET.


### FAQ

#### Q : Comment puis-je mettre du texte en italique dans Aspose.Words ?

R : Pour mettre du texte en italique dans Aspose.Words, vous pouvez utiliser le`Font.Italic` propriété du`Run`objet. Vous pouvez définir cette propriété sur`true` pour mettre en italique un texte spécifique. Par exemple, vous pouvez utiliser`run.Font.Italic=true` pour mettre en italique le texte contenu dans le`Run` objet.

#### Q : Est-il possible de mettre en italique plusieurs morceaux de texte dans un même paragraphe ?

 R : Oui, vous pouvez mettre en italique plusieurs morceaux de texte dans un seul paragraphe en utilisant plusieurs`Run` objets. Vous pouvez créer plusieurs`Run` objets et définir le`Font.Italic` propriété à`true` pour chaque objet pour mettre en italique les parties souhaitées du texte. Ensuite, vous pouvez les ajouter au paragraphe en utilisant le`Paragraph.AppendChild(run)` méthode.

#### Q : Puis-je mettre en italique le texte d'un tableau ou d'une cellule dans Aspose.Words ?

 R : Oui, vous pouvez mettre en italique le texte d'un tableau ou d'une cellule dans Aspose.Words. Vous pouvez accéder à la cellule ou au paragraphe souhaité à l'aide des méthodes appropriées, puis appliquer une mise en forme en italique à l'aide de l'option`Font.Italic` propriété du`Run` ou`Paragraph` objet.