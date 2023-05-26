---
title: Créer un signet
linktitle: Créer un signet
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à créer des signets dans un document et à spécifier les niveaux d'aperçu des signets dans un PDF à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/create-bookmark/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Créer un signet dans la bibliothèque Aspose.Words pour .NET. Cette fonction vous permet de créer des signets dans un document et de spécifier les niveaux d'aperçu des signets dans un fichier PDF de sortie.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Création du document et du générateur

 Avant de créer des signets, nous devons créer un document et un générateur de document à l'aide de l'outil`Document` et`DocumentBuilder` objets:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Création du signet principal

 Nous utilisons le`StartBookmark` méthode pour démarrer un signet principal et la`EndBookmark` méthode pour y mettre fin. Entre les deux, nous pouvons ajouter du texte et d'autres signets :

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Ajoutez plus de signets ou de texte ici.

builder. EndBookmark("My Bookmark");
```

## Étape 3 : Créer des signets imbriqués

 Nous pouvons également créer des signets imbriqués dans un signet principal. Nous utilisons le même`StartBookmark` et`EndBookmark` méthodes pour créer et terminer des signets imbriqués :

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Étape 4 : Spécification des niveaux d'aperçu des signets dans le fichier PDF de sortie

 Nous utilisons le`PdfSaveOptions` objet pour spécifier les niveaux d'aperçu des signets dans le fichier PDF de sortie. Nous utilisons le`BookmarksOutlineLevels` propriété

  pour ajouter des signets principaux et des signets imbriqués avec leurs niveaux respectifs :

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Exemple de code source pour Créer un signet à l'aide d'Aspose.Words pour .NET

Voici l'exemple de code source complet pour illustrer la création de signets à l'aide d'Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Créer un signet d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour créer des signets dans un document et spécifier les niveaux d'aperçu des signets dans un fichier PDF de sortie.