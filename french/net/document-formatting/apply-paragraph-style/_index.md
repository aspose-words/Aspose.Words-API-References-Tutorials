---
title: Appliquer le style de paragraphe
linktitle: Appliquer le style de paragraphe
second_title: API de traitement de documents Aspose.Words
description: Apprenez à appliquer un style de paragraphe à l'aide de Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/document-formatting/apply-paragraph-style/
---

Dans ce didacticiel, nous vous expliquerons comment appliquer un style de paragraphe à l'aide de Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et appliquer le style de paragraphe.

## Étape 1 : Création et configuration du document

Pour commencer, créez un nouveau document et un objet DocumentBuilder associé. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Configurer le style de paragraphe

Nous allons maintenant configurer le style de paragraphe à l'aide de l'identificateur de style intégré. Voici comment:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## Étape 3 : Ajouter du contenu

Nous allons ajouter du contenu au paragraphe. Voici comment:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### Exemple de code source pour Appliquer le style de paragraphe à l'aide de Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité Appliquer le style de paragraphe avec Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

Avec ce code, vous pourrez appliquer un style de paragraphe en utilisant Aspose.Words pour .NET.

