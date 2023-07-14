---
title: Espace entre le texte asiatique et latin
linktitle: Espace entre le texte asiatique et latin
second_title: API de traitement de documents Aspose.Words
description: Apprenez à ajuster automatiquement l'espace entre le texte asiatique et latin dans votre document avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/space-between-asian-and-latin-text/
---

Dans ce didacticiel, nous allons vous montrer comment utiliser la fonctionnalité Espace entre le texte asiatique et latin avec Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer les modifications.

## Étape 1 : Création et configuration du document

Pour commencer, créez un nouveau document et un objet DocumentBuilder associé. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Configuration de l'espace entre le texte asiatique et le texte latin

Nous allons maintenant configurer l'espace entre le texte asiatique et le texte latin à l'aide des propriétés de l'objet ParagraphFormat. Voici comment:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Étape 3 : Enregistrer le document

 Après avoir inséré le champ du formulaire de saisie de texte, enregistrez le document à l'emplacement souhaité à l'aide de la`Save` méthode. Assurez-vous de fournir le chemin d'accès au fichier approprié :

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Exemple de code source pour l'espace entre le texte asiatique et latin à l'aide de Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Space Between Asian and Latin Text avec Aspose.Words pour .NET :


```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
	paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

	builder.Writeln("Automatically adjust space between Asian and Latin text");
	builder.Writeln("Automatically adjust space between Asian text and numbers");

	doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
        
```

Avec ce code, vous pourrez ajuster automatiquement l'espace entre le texte asiatique et latin dans votre document en utilisant Aspose.Words pour .NET.



