---
title: Par Rubriques Html
linktitle: Par Rubriques Html
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour expliquer le code source C# de la fonctionnalité HTML par en-tête d'Aspose.Words pour .NET
type: docs
weight: 10
url: /fr/net/split-document/by-headings-html/
---
Dans ce didacticiel, nous vous expliquerons comment diviser un document Word en parties plus petites à l'aide de la fonctionnalité Par en-tête HTML de Aspose.Words pour .NET. Suivez les étapes ci-dessous pour comprendre le code source et générer des documents HTML distincts basés sur le titre.

## Étape 1 : Chargement du document

Pour commencer, spécifiez le répertoire de votre document et chargez le document dans un objet Document. Voici comment:

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Étape 2 : Diviser le document par Titre au format HTML

Nous allons maintenant définir les options d'enregistrement pour diviser le document en parties plus petites en fonction de l'en-tête au format HTML. Voici comment:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Divisez le document en parties plus petites, dans ce cas en le séparant par titre.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Exemple de code source pour By Headings HTML en utilisant Aspose.Words pour .NET

Voici le code source complet de la fonctionnalité By HTML Heading de Aspose.Words pour .NET :

```csharp
// Chemin d'accès au répertoire des documents.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Diviser un document en parties plus petites, dans ce cas divisé par en-tête.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Avec ce code, vous pourrez diviser un document Word en parties plus petites à l'aide d'Aspose.Words pour .NET, en fonction des en-têtes. Vous pouvez ensuite générer des documents HTML distincts pour chaque partie.

