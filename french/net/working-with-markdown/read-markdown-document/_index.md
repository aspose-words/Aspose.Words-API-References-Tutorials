---
title: Lire le document Markdown
linktitle: Lire le document Markdown
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à lire un document Markdown avec le guide étape par étape Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/read-markdown-document/
---

Dans cet exemple, nous vous expliquerons comment lire un document Markdown à l'aide d'Aspose.Words pour .NET Markdown est un langage de balisage léger utilisé pour formater du texte brut.

## Étape 1 : Lecture du document Markdown

 Dans un premier temps, nous utiliserons le`Document` class pour lire le document Markdown. Nous devons spécifier le chemin du fichier Markdown à lire.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Quotes.md");
```

## Étape 2 : Supprimer la mise en forme de l'en-tête

Nous pouvons supprimer la mise en forme de l'en-tête dans le dernier paragraphe du document. Dans cet exemple, nous attribuons le style "Citation" au paragraphe.

```csharp
Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
paragraph.ParagraphFormat.Style = doc.Styles["Quote"];
```

## Étape 3 : Enregistrer le document

Enfin, nous pouvons enregistrer le document dans le format souhaité.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
```

### Exemple de code source pour lire un document Markdown avec Aspose.Words pour .NET


```csharp
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Quotes.md");

	// Supprimons la mise en forme du titre d'un devis dans le tout dernier paragraphe.
	Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
	paragraph.ParagraphFormat.Style = doc.Styles["Quote"];

	doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
            
```

Félicitation ! Vous avez maintenant appris à lire un document Markdown avec Aspose.Words pour .NET.

