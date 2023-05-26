---
title: Accents
linktitle: Accents
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à utiliser les accents (gras et italique) avec Aspose.Words pour le guide étape par étape .NET.
type: docs
weight: 10
url: /fr/net/working-with-markdown/emphases/
---

Dans cet exemple, nous expliquerons comment utiliser les emphases avec Aspose.Words pour .NET. emphases est utilisé pour souligner certaines parties du texte, comme le gras et l'italique.

## Étape 1 : Initialisation du document

 Tout d'abord, nous allons initialiser le document en créant une instance de`Document` classe.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Étape 2 : Utiliser un générateur de documents

Ensuite, nous utiliserons un générateur de document pour ajouter du contenu à notre document.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 3 : Ajouter du texte avec Emphases

Nous pouvons ajouter du texte d'emphase en modifiant les propriétés de police du générateur de documents. Dans cet exemple, nous utilisons le gras et l'italique pour souligner différentes parties du texte.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Étape 4 : Enregistrer le document

 Enfin, nous pouvons enregistrer le document dans le format souhaité. Dans cet exemple, nous utilisons le`.md` extension pour un format Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Félicitation ! Vous avez maintenant appris à utiliser les emphases avec Aspose.Words pour .NET.

### Exemple de code source pour Emphases utilisant Aspose.Words pour .NET


```csharp
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
	builder.Write("You can write ");

	builder.Font.Bold = true;
	builder.Write("bold");

	builder.Font.Bold = false;
	builder.Write(" or ");

	builder.Font.Italic = true;
	builder.Write("italic");

	builder.Font.Italic = false;
	builder.Writeln(" text. ");

	builder.Write("You can also write ");
	builder.Font.Bold = true;

	builder.Font.Italic = true;
	builder.Write("BoldItalic");

	builder.Font.Bold = false;
	builder.Font.Italic = false;
	builder.Write("text.");

	builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
            
```
