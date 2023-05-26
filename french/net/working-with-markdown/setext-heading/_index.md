---
title: En-tête de texte
linktitle: En-tête de texte
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser les en-têtes Setext pour formater vos documents avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/setext-heading/
---

Dans ce didacticiel, nous vous expliquerons comment utiliser la fonctionnalité Setext Heading avec Aspose.Words pour .NET. Setext Heading est une méthode alternative de formatage des titres dans les documents Markdown.

## Étape 1 : Utiliser un générateur de documents

Tout d'abord, nous allons utiliser un générateur de document pour ajouter du contenu à notre document.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Utiliser le style de titre Setext

Nous allons utiliser le style de paragraphe par défaut "Titre 1" pour créer un titre de niveau 1 dans notre document.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Étape 3 : Réinitialiser les styles

Nous réinitialisons les styles de police précédemment appliqués pour éviter toute combinaison indésirable de styles entre les paragraphes.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Étape 4 : Personnalisation des niveaux d'en-tête Setext

Nous pouvons personnaliser les niveaux de titre Setext en ajoutant de nouveaux styles de paragraphe basés sur les styles de titre existants. Dans cet exemple, nous créons un style "SetextHeading1" basé sur le style "Heading 1" pour représenter un titre de niveau 1 au format Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Étape 5 : Enregistrer le document

Enfin, nous pouvons enregistrer le document dans le format souhaité.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Exemple de code source pour les titres Setext avec Aspose.Words pour .NET

```csharp
	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Utilisez un générateur de document pour ajouter du contenu au document.
	DocumentBuilder builder = new DocumentBuilder();

	builder.ParagraphFormat.StyleName = "Heading 1";
	builder.Writeln("This is an H1 tag");

	// Réinitialisez les styles du paragraphe précédent pour ne pas combiner les styles entre les paragraphes.
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
	builder.ParagraphFormat.Style = setexHeading1;
	builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
	builder.Writeln("Setext Heading level 1");

	builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
	builder.Writeln("This is an H3 tag");

	// Réinitialisez les styles du paragraphe précédent pour ne pas combiner les styles entre les paragraphes.
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
	builder.ParagraphFormat.Style = setexHeading2;
	builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

	// Le niveau de titre Setex sera réinitialisé à 2 si le paragraphe de base a un niveau de titre supérieur à 2.
	builder.Writeln("Setext Heading level 2");
	

	builder.Document.Save(dataDir + "Test.md");
```



