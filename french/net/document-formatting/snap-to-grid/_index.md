---
title: Aligner sur la grille
linktitle: Aligner sur la grille
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour expliquer le code source C # de la fonctionnalité Snap to Grid avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/snap-to-grid/
---

Dans ce didacticiel, nous vous expliquerons comment utiliser la fonction Aligner sur la grille avec Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications.

## Étape 1 : Création et configuration du document

Pour commencer, créez un nouveau document et un objet DocumentBuilder associé. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Alignement de la grille

Nous allons maintenant appliquer l'alignement de la grille à un paragraphe spécifique et à la police utilisée dans le paragraphe. Voici comment:

```csharp
// Activer l'alignement sur la grille pour le paragraphe
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// Écrivez le texte dans le paragraphe
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// Activer l'alignement sur la grille pour la police utilisée dans le paragraphe
par.Runs[0].Font.SnapToGrid = true;
```

## Étape 3 : Enregistrer le document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide de la`Save` méthode. Assurez-vous de fournir le chemin d'accès au fichier approprié :

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### Exemple de code source pour Snap To Grid en utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Snap to Grid avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Optimisez la mise en page lors de la saisie de caractères asiatiques.
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

Avec ce code, vous pourrez aligner votre texte sur la grille et optimiser l'apparence de votre document en utilisant Aspose.Words pour .NET.

