---
title: Copier le texte marqué d'un signet
linktitle: Copier le texte marqué d'un signet
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à copier le texte d'un signet d'un document source vers un autre document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/copy-bookmarked-text/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Copier le texte mis en signet dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet de copier le contenu d'un signet spécifique d'un document source vers un autre document.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Chargement du document source

 Avant de copier le texte du signet, nous devons charger le document source dans un`Document` objet en utilisant le chemin du fichier :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Étape 2 : Obtenir le signet source

 Nous utilisons le`Bookmarks` propriété de la plage de documents source pour obtenir le signet spécifique que nous voulons copier :

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Étape 3 : Création du document de destination

Nous créons un nouveau document qui servira de document de destination pour copier le contenu du signet :

```csharp
Document dstDoc = new Document();
```

## Étape 4 : Spécification de l'emplacement de la copie

Nous spécifions l'emplacement où nous voulons ajouter le texte copié. Dans notre exemple, nous ajoutons le texte à la fin du corps de la dernière section du document de destination :

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Étape 5 : Importer et copier le texte du signet

 Nous utilisons un`NodeImporter`objet pour importer et copier le texte du signet d'un document source vers le document de destination :

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Exemple de code source pour Copier le texte mis en signet à l'aide de Aspose.Words pour .NET

Voici l'exemple de code source complet pour illustrer la copie de texte à partir d'un signet à l'aide d'Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Il s'agit du signet dont nous voulons copier le contenu.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Nous compléterons ce document.
	Document dstDoc = new Document();

	// Disons que nous serons ajoutés à la fin du corps de la dernière section.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Si vous importez plusieurs fois sans un seul contexte, de nombreux styles seront créés.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Copier le texte mis en signet depuis Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour copier le contenu d'un signet d'un document source vers un autre document.