---
title: Afficher Masquer les signets
linktitle: Afficher Masquer les signets
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment afficher ou masquer un signet spécifique dans un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/show-hide-bookmarks/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Afficher les signets masqués dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet d'afficher ou de masquer un signet spécifique dans un document.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Chargement du document

 Nous utilisons le`Document` class pour charger le document existant à partir d'un fichier :

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Étape 2 : Afficher ou masquer un signet spécifique

 Nous utilisons le`ShowHideBookmarkedContent` fonction pour afficher ou masquer un signet spécifique dans le document. Cette fonction prend en paramètre le document, le nom du signet et un booléen pour indiquer s'il faut afficher ou masquer le signet :

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Étape 3 : Enregistrer le document modifié

 Nous utilisons le`Save` méthode pour enregistrer le document modifié dans un fichier :

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Exemple de code source pour Afficher les signets masqués à l'aide de Aspose.Words pour .NET

Voici l'exemple de code source complet pour démontrer l'affichage ou le masquage d'un signet spécifique à l'aide de Aspose.Words pour .NET :

```csharp

	// Chemin d'accès au répertoire des documents.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonctionnalité Afficher les signets masqués d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour afficher ou masquer un signet spécifique dans un document.