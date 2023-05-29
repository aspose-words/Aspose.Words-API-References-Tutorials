---
title: Colonne della tabella dei segnalibri
linktitle: Colonne della tabella dei segnalibri
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come contrassegnare una colonna della tabella in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/bookmark-table-columns/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come usare la funzione Bookmark Table Columns nella libreria Aspose.Words per .NET. Questa funzione consente di aggiungere un segnalibro a una colonna specifica di una tabella in un documento di Word e accedere al contenuto di quella colonna.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione della tabella

 Prima di creare un segnalibro su una colonna della tabella, dobbiamo prima creare la tabella utilizzando a`DocumentBuilder` oggetto. Nel nostro esempio, creiamo una tabella con due righe e due colonne:

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

## Passaggio 2: creazione del segnalibro della colonna

 Noi usiamo il`StartBookmark`metodo per creare un segnalibro su una colonna specifica della tabella. Nel nostro esempio, usiamo il nome "MyBookmark" per il segnalibro:

```csharp
builder. StartBookmark("MyBookmark");
```

## Passaggio 3: accedi al contenuto della colonna

 Esaminiamo tutti i segnalibri nel documento e mostriamo i loro nomi. Se un segnalibro è una colonna, accediamo al contenuto di quella colonna utilizzando l'indice della colonna e il`GetText` metodo:

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

### Codice sorgente di esempio per le colonne della tabella dei segnalibri utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare la creazione di un segnalibro su una colonna della tabella utilizzando Aspose.Words per .NET:

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

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come usare la funzione Bookmark Table Columns di Aspose.Words per .NET. Abbiamo seguito una guida dettagliata per aggiungere ai segnalibri una colonna specifica di una tabella in un documento di Word e passare al contenuto di quella colonna.