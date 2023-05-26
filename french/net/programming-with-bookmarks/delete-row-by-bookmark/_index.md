---
title: Supprimer la ligne par signet
linktitle: Supprimer la ligne par signet
second_title: Référence de l'API Aspose.Words pour .NET
description: Découvrez comment supprimer une ligne de tableau en fonction d'un signet spécifique dans un document à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/delete-row-by-bookmark/
---

Dans cet article, nous allons explorer le code source C # ci-dessus pour comprendre comment utiliser la fonction Supprimer la ligne par signet dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet de supprimer une ligne de tableau en fonction d'un signet spécifique dans un document.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Récupérer le marque-page

 Nous utilisons le`Bookmarks`propriété de la plage de documents pour obtenir le signet spécifique que nous voulons utiliser pour supprimer la ligne du tableau :

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Étape 2 : Supprimer la ligne du tableau

 Nous utilisons le`GetAncestor` méthode pour obtenir le`Row` type élément parent du signet. Ensuite, nous utilisons le`Remove` méthode pour supprimer la ligne du tableau :

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Exemple de code source pour Supprimer la ligne par signet à l'aide de Aspose.Words pour .NET

Voici l'exemple de code source complet pour illustrer la suppression d'une ligne de tableau basée sur un signet spécifique à l'aide d'Aspose.Words pour .NET :

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Supprimer la ligne par signet d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour supprimer une ligne de tableau en fonction d'un signet spécifique dans un document.