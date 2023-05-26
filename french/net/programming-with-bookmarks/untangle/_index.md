---
title: Démêler
linktitle: Démêler
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à démêler les signets imbriqués dans les lignes de tableau adjacentes à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/untangle/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Untangle dans la bibliothèque Aspose.Words pour .NET. Cette fonction dénoue les signets imbriqués qui se trouvent dans les lignes de tableau adjacentes.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Étape 1 : Parcourir les signets du document

Nous utilisons une boucle foreach pour parcourir tous les signets présents dans le document :

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Code de gestion des signets ici
}
```

## Étape 2 : Obtenir les lignes parentes des signets

 Nous utilisons le`GetAncestor` méthodes pour récupérer les lignes parentes des nœuds de début et de fin du signet :

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Étape 3 : démêler les signets imbriqués

Si les deux lignes parentes sont trouvées et que le signet commence et se termine dans des lignes adjacentes, nous déplaçons le nœud de fin du signet à la fin du dernier paragraphe de la dernière cellule de la rangée supérieure :

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Exemple de code source pour Untangle utilisant Aspose.Words pour .NET

Voici l'exemple de code source complet pour démêler les signets imbriqués à l'aide de Aspose.Words pour .NET :

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Obtenez la ligne parent du signet et du nœud de fin de signet.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Si les deux lignes sont correctes et que le début et la fin du signet sont contenus dans des lignes adjacentes,
		// déplacer le nœud de fin de signet à la fin du dernier paragraphe de la dernière cellule de la ligne supérieure.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Untangle d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour démêler les signets imbriqués dans les lignes de tableau adjacentes.