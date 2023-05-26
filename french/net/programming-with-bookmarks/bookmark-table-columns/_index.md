---
title: Colonnes du tableau des signets
linktitle: Colonnes du tableau des signets
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à ajouter un signet à une colonne de tableau dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-bookmarks/bookmark-table-columns/
---

Dans cet article, nous allons explorer le code source C# ci-dessus pour comprendre comment utiliser la fonction Bookmark Table Columns dans la bibliothèque Aspose.Words pour .NET. Cette fonctionnalité vous permet de mettre en signet une colonne spécifique d'un tableau dans un document Word et d'accéder au contenu de cette colonne.

## Conditions préalables

- Connaissance de base du langage C#.
- Environnement de développement .NET avec la bibliothèque Aspose.Words installée.

## Etape 1 : Création du tableau

 Avant de créer un signet sur une colonne de tableau, il faut d'abord créer le tableau à l'aide d'un`DocumentBuilder` objet. Dans notre exemple, nous créons un tableau avec deux lignes et deux colonnes :

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## Étape 2 : Création du signet de la colonne

 Nous utilisons le`StartBookmark`méthode pour créer un signet sur une colonne spécifique de la table. Dans notre exemple, nous utilisons le nom "MyBookmark" pour le signet :

```csharp
builder. StartBookmark("MyBookmark");
```

## Étape 3 : Accéder au contenu de la colonne

 Nous parcourons tous les signets du document et affichons leurs noms. Si un signet est une colonne, nous accédons au contenu de cette colonne en utilisant l'index de colonne et le`GetText` méthode:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Exemple de code source pour les colonnes de table de signets à l'aide de Aspose.Words pour .NET

Voici l'exemple de code source complet pour illustrer la création d'un signet sur une colonne de table à l'aide d'Aspose.Words pour .NET :

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## Conclusion

Dans cet article, nous avons exploré le code source C# pour comprendre comment utiliser la fonction Bookmark Table Columns d'Aspose.Words pour .NET. Nous avons suivi un guide étape par étape pour mettre en signet une colonne spécifique d'un tableau dans un document Word et accéder au contenu de cette colonne.