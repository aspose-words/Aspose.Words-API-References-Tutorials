---
title: Signet des colonnes de tableau dans un document Word
linktitle: Signet des colonnes de tableau dans un document Word
second_title: API de traitement de documents Aspose.Words
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

 Nous utilisons le`StartBookmark` méthode pour créer un signet sur une colonne spécifique de la table. Dans notre exemple, nous utilisons le nom "MyBookmark" pour le signet :

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

### FAQ pour les colonnes de tableau de signets dans un document Word

#### Q : Quels sont les prérequis pour utiliser la fonctionnalité "Signets pour les colonnes de tableau" dans Aspose.Words pour .NET ?

R : Pour utiliser la fonctionnalité "Signets pour les colonnes de tableau" dans Aspose.Words pour .NET, vous devez avoir une connaissance de base du langage C#. Vous avez également besoin d'un environnement de développement .NET avec la bibliothèque Aspose.Words installée.

#### Q : Comment créer un tableau avec des colonnes dans un document Word à l'aide d'Aspose.Words pour .NET ?

 R : Pour créer un tableau avec des colonnes dans un document Word à l'aide d'Aspose.Words pour .NET, vous pouvez utiliser un`DocumentBuilder`objet pour insérer des cellules et du contenu dans le tableau. Voici un exemple de code :

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### Q : Comment ajouter un signet à une colonne de tableau à l'aide d'Aspose.Words pour .NET ?

 R : Pour créer un signet sur une colonne de tableau à l'aide d'Aspose.Words pour .NET, vous pouvez utiliser le`StartBookmark` méthode de la`DocumentBuilder` objet pour démarrer le signet sur une colonne de tableau spécifique. Voici un exemple de code :

```csharp
builder.StartBookmark("MyBookmark");
```

#### Q : Comment accéder au contenu des colonnes de table à partir d'un signet à l'aide d'Aspose.Words pour .NET ?

R : Pour accéder au contenu d'une colonne de table à partir d'un signet à l'aide d'Aspose.Words pour .NET, vous pouvez parcourir tous les signets du document, vérifier si un signet est une colonne et utiliser l'index de la colonne pour accéder au contenu de cette colonne. Voici un exemple de code :

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Faites quelque chose avec le contenu de la colonne...
         }
     }
}
```

#### Q : Y a-t-il une limite au nombre de colonnes que je peux créer dans un tableau avec des signets de colonne ?

R : Il n'y a pas de limite spécifique au nombre de colonnes que vous pouvez créer dans une table avec des signets de colonne à l'aide d'Aspose.Words pour .NET. La limite dépend principalement des ressources disponibles sur votre système et des spécifications du format de fichier Word que vous utilisez. Cependant, il est recommandé de ne pas créer un trop grand nombre de colonnes, car cela peut affecter les performances et la lisibilité du document final.