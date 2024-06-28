---
title: Rubrique Setex
linktitle: Rubrique Setex
second_title: API de traitement de documents Aspose.Words
description: Apprenez à utiliser les en-têtes Setext pour formater vos documents avec le guide étape par étape d'Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/setext-heading/
---

Dans ce didacticiel, nous vous expliquerons comment utiliser la fonctionnalité Setext Heading avec Aspose.Words pour .NET. Les titres Setext sont une méthode alternative de formatage des titres dans les documents Markdown.

## Étape 1 : Utiliser un générateur de documents

Tout d’abord, nous utiliserons un générateur de documents pour ajouter du contenu à notre document.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Étape 2 : Utiliser le style de titre Setext

Nous allons utiliser le style de paragraphe par défaut « Titre 1 » pour créer un titre de niveau 1 dans notre document.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Étape 3 : Réinitialisation des styles

Nous réinitialisons les styles de police précédemment appliqués pour éviter toute combinaison indésirable de styles entre les paragraphes.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Étape 4 : Personnalisation des niveaux de titre Setext

Nous pouvons personnaliser les niveaux de titre Setext en ajoutant de nouveaux styles de paragraphe basés sur les styles de titre existants. Dans cet exemple, nous créons un style « SetextHeading1 » basé sur le style « Heading 1 » pour représenter un titre de niveau 1 au format Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Étape 5 : Sauvegarde du document

Enfin, nous pouvons enregistrer le document au format souhaité.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Exemple de code source pour les titres Setext avec Aspose.Words pour .NET

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Utilisez un générateur de documents pour ajouter du contenu au document.
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

### FAQ

#### Q : Qu'est-ce qu'un en-tête Setext Markdown ?

R : Un en-tête Setext Markdown est un moyen alternatif de créer des titres dans un document Markdown. Il utilise des caractères de soulignement (= ou -) pour indiquer différents niveaux de titres.

#### Q : Comment utiliser les en-têtes Setext Markdown ?

R : Pour utiliser les titres Setext Markdown, placez des traits de soulignement sous le texte du titre. Utilisez des signes égal (=) pour un en-tête de niveau 1 et des traits d’union (-) pour un en-tête de niveau 2.

#### Q : Y a-t-il des limites à l'utilisation des en-têtes Setext Markdown ?

R : Les titres Setext Markdown ont des limites en termes de hiérarchie des titres et ne sont pas aussi visuellement distincts que les titres Markdown standard.

#### Q : Puis-je personnaliser l'apparence des en-têtes Setext Markdown ?

R : Dans Markdown standard, il n'est pas possible de personnaliser l'apparence des en-têtes Setext Markdown. Ils ont une apparence prédéfinie en fonction des caractères de soulignement utilisés.

#### Q : Les en-têtes Setext Markdown sont-ils pris en charge par tous les éditeurs Markdown ?

R : La prise en charge des en-têtes Setext Markdown peut varier selon les éditeurs Markdown. Vérifiez la documentation spécifique de votre éditeur pour en être sûr.