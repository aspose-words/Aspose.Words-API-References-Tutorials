---
title: Créer un signet dans un document Word
linktitle: Créer un signet dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment créer des signets dans un document Word et spécifier les niveaux d'aperçu des signets dans un PDF à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/create-bookmark/
---

Dans cet article, nous explorerons le code source C# ci-dessus pour comprendre comment utiliser la fonction Créer un signet dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet de créer des signets dans un document et de spécifier des niveaux d'aperçu des signets dans un fichier PDF de sortie.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Création du document et du générateur

 Avant de créer des signets, nous devons créer un document et un générateur de documents à l'aide du`Document` et`DocumentBuilder` objets:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Création du signet principal

 Nous utilisons le`StartBookmark` méthode pour démarrer un signet principal et le`EndBookmark` méthode pour y mettre fin. Entre les deux, nous pouvons ajouter du texte et d'autres signets :

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Ajoutez plus de signets ou de texte ici.

builder. EndBookmark("My Bookmark");
```

## Étape 3 : Création de signets imbriqués

Nous pouvons également créer des signets imbriqués dans un signet principal. Nous utilisons le même`StartBookmark` et`EndBookmark` méthodes pour créer et mettre fin aux signets imbriqués :

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Étape 4 : Spécification des niveaux d'aperçu des signets dans le fichier PDF de sortie

 Nous utilisons le`PdfSaveOptions` objet pour spécifier les niveaux d’aperçu des signets dans le fichier PDF de sortie. Nous utilisons le`BookmarksOutlineLevels` propriété

  pour ajouter des signets principaux et des signets imbriqués avec leurs niveaux respectifs :

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Exemple de code source pour créer un signet à l'aide d'Aspose.Words pour .NET

Voici l'exemple complet de code source pour démontrer la création de signets à l'aide d'Aspose.Words pour .NET :

```csharp

	// Le chemin d'accès au répertoire des documents.
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

### FAQ

#### Q : Quelles sont les conditions préalables pour utiliser la fonction « Créer des favoris » dans Aspose.Words pour .NET ?

: Pour utiliser la fonction « Créer des favoris » dans Aspose.Words for .NET, vous devez avoir des connaissances de base du langage C#. Vous avez également besoin d'un environnement de développement .NET avec la bibliothèque Aspose.Words installée.

#### Q : Comment créer un document dans Aspose.Words pour .NET ?

 R : Pour créer un document dans Aspose.Words for .NET, vous pouvez utiliser le`Document` classe. Voici un exemple de code :

```csharp
Document doc = new Document();
```

#### Q : Comment créer un signet principal dans un document à l'aide d'Aspose.Words pour .NET ?

 R : Pour créer un signet principal dans un document à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`StartBookmark` méthode pour démarrer le signet, ajouter du texte ou d'autres signets à l'intérieur, puis utiliser la` EndBookmark` pour y mettre fin. Voici un exemple de code :

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Q : Comment créer un signet imbriqué dans un signet principal à l'aide d'Aspose.Words pour .NET ?

 R : Pour créer un signet imbriqué dans un signet principal à l'aide d'Aspose.Words for .NET, vous pouvez utiliser le même`StartBookmark` et`EndBookmark` méthodes pour démarrer et terminer le signet imbriqué. Voici un exemple de code :

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### Q : Comment spécifier les niveaux d'aperçu des signets dans un PDF de sortie à l'aide d'Aspose.Words pour .NET ?

 R : Pour spécifier les niveaux d'aperçu des signets dans un PDF de sortie à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`PdfSaveOptions` la classe et le`BookmarksOutlineLevels` propriété. Vous pouvez ajouter des signets principaux et des signets imbriqués avec leurs niveaux respectifs. Voici un exemple de code :

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### Q : Comment enregistrer un document après avoir créé des signets à l'aide d'Aspose.Words for .NET ?

 R : Pour enregistrer un document après avoir créé des signets à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`Save` méthode du`Document` objet spécifiant le chemin du fichier de destination. Voici un exemple de code :

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### Q : Comment spécifier les niveaux d'aperçu des signets dans un PDF de sortie à l'aide d'Aspose.Words pour .NET ?

 R : Pour spécifier les niveaux d'aperçu des signets dans un PDF de sortie à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`PdfSaveOptions` la classe et le`BookmarksOutlineLevels` propriété. Vous pouvez ajouter des signets principaux et des signets imbriqués avec leurs niveaux respectifs. Voici un exemple de code :

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### Q : Comment créer des signets imbriqués dans un signet principal à l'aide d'Aspose.Words pour .NET ?

 R : Pour créer des signets imbriqués dans un signet principal à l'aide d'Aspose.Words for .NET, vous pouvez utiliser le même`StartBookmark` et`EndBookmark` méthodes pour démarrer et terminer les signets imbriqués. Assurez-vous de spécifier le signet parent comme paramètre lors de l'appel du`StartBookmark` méthode. Voici un exemple de code :

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### Q : Comment ajouter du texte dans un signet à l'aide d'Aspose.Words pour .NET ?

 R : Pour ajouter du texte dans un signet à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`Write` méthode du`DocumentBuilder`objet spécifiant le texte à ajouter. Voici un exemple de code :

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Q : Comment créer un signet principal dans un document à l'aide d'Aspose.Words pour .NET ?

 R : Pour créer un signet principal dans un document à l'aide d'Aspose.Words for .NET, vous pouvez utiliser l'outil`StartBookmark` méthode pour démarrer le signet et le`EndBookmark` méthode pour y mettre fin. Voici un exemple de code :

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```