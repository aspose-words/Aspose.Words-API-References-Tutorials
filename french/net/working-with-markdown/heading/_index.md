---
title: Titre
linktitle: Titre
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser le titre avec Aspose.Words pour .NET Guide étape par étape.
type: docs
weight: 10
url: /fr/net/working-with-markdown/heading/
---

Dans cet exemple, nous allons vous montrer comment utiliser la fonction de titres avec Aspose.Words pour .NET. Les titres sont utilisés pour structurer et hiérarchiser le contenu d'un document.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Personnaliser les styles de titre

Par défaut, les styles de titre dans Word peuvent avoir une mise en forme en gras et en italique. Si nous ne voulons pas que ces propriétés soient appliquées, nous devons les définir explicitement sur "false".

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Étape 3 : Ajouter un titre de niveau 1

 Nous pouvons ajouter un titre de niveau 1 en spécifiant le nom du style de paragraphe approprié et en utilisant le`Writeln` méthode pour écrire le contenu du titre.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

### Exemple de code source pour le titre avec Aspose.Words pour .NET


```csharp
// Utilisez un générateur de document pour ajouter du contenu au document.
DocumentBuilder builder = new DocumentBuilder();

// Par défaut, les styles de titre dans Word peuvent avoir une mise en forme Gras et Italique.
//Si nous ne voulons pas être soulignés, définissez explicitement ces propriétés sur false.
builder.Font.Bold = false;
builder.Font.Italic = false;

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

Félicitation ! Vous avez maintenant appris à utiliser la fonctionnalité des en-têtes avec Aspose.Words pour .NET.


