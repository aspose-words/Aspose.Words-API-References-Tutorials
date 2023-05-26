---
title: Groupe de saut de ligne de typographie asiatique
linktitle: Groupe de saut de ligne de typographie asiatique
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser le groupe de saut de ligne Asian Typography avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/asian-typography-line-break-group/
---

Dans ce didacticiel, nous allons vous montrer comment utiliser la fonctionnalité de groupe de saut de ligne de typographie asiatique avec Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications de mise en forme.

## Étape 1 : Chargement du document

Pour commencer, spécifiez le répertoire de vos documents et chargez le document contenant la typographie asiatique dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Étape 2 : configuration de la typographie asiatique

Nous allons maintenant configurer les paramètres de typographie asiatique pour le premier paragraphe du document. Voici comment:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Étape 3 : Enregistrer le document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide de la`Save` méthode. Assurez-vous de fournir le chemin d'accès au fichier approprié :

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Exemple de code source pour le groupe de sauts de ligne de typographie asiatique utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Asian Typography Line Break Group avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Avec ce code, vous pourrez appliquer un groupe de sauts de ligne de typographie asiatique en utilisant Aspose.Words pour .NET.

