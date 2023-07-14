---
title: Modifier l'espacement et les retraits des paragraphes asiatiques
linktitle: Modifier l'espacement et les retraits des paragraphes asiatiques
second_title: API de traitement de documents Aspose.Words
description: Apprenez à modifier l'espacement et les retraits des paragraphes asiatiques avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---

Dans ce didacticiel, nous vous expliquerons comment modifier l'espacement et les retraits d'un paragraphe asiatique à l'aide de Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications.

## Étape 1 : Chargement du document

Pour commencer, spécifiez le répertoire de vos documents et chargez le document contenant la typographie asiatique dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Étape 2 : Modification de l'espacement des paragraphes et des retraits

Nous allons maintenant modifier l'espacement et les retraits du premier paragraphe du document asiatique. Voici comment:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Mettre à jour ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Mettre à jour ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; // Mettre à jour ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Mettre à jour ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Mettre à jour ParagraphFormat.SpaceAfter
```

## Étape 3 : Enregistrer le document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide de la`Save` méthode. Assurez-vous de fournir le chemin d'accès au fichier approprié :

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Exemple de code source pour modifier l'espacement des paragraphes asiatiques et les retraits à l'aide de Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Modifier l'espacement des paragraphes asiatiques et les retraits avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent sera mis à jour
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent sera mis à jour
	format.CharacterUnitFirstLineIndent = 20;  //ParagraphFormat.FirstLineIndent sera mis à jour
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore sera mis à jour
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter sera mis à jour

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Avec ce code, vous pourrez modifier l'espacement et les retraits d'un paragraphe asiatique en utilisant Aspose.Words pour .NET.

