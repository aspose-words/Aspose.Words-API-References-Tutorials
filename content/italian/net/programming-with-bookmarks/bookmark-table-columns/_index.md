---
title: Colonne della tabella dei segnalibri nel documento di Word
linktitle: Colonne della tabella dei segnalibri nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere ai segnalibri una colonna di tabella in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/bookmark-table-columns/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Colonne della tabella dei segnalibri nella libreria Aspose.Words per .NET. Questa funzionalità consente di aggiungere ai segnalibri una colonna specifica di una tabella in un documento di Word e accedere al contenuto di quella colonna.

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

 Noi usiamo il`StartBookmark` metodo per creare un segnalibro su una colonna specifica della tabella. Nel nostro esempio, utilizziamo il nome "MyBookmark" per il segnalibro:

```csharp
builder. StartBookmark("MyBookmark");
```

## Passaggio 3: accedi al contenuto della colonna

 Esaminiamo tutti i segnalibri nel documento e visualizziamo i loro nomi. Se un segnalibro è una colonna, accediamo al contenuto di quella colonna utilizzando l'indice della colonna e il file`GetText` metodo:

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

Ecco il codice sorgente di esempio completo per dimostrare la creazione di un segnalibro su una colonna di tabella utilizzando Aspose.Words per .NET:

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

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Colonne della tabella dei segnalibri di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per aggiungere ai segnalibri una colonna specifica di una tabella in un documento di Word e passare al contenuto di quella colonna.

### Domande frequenti sulle colonne della tabella dei segnalibri nel documento Word

#### D: Quali sono i prerequisiti per utilizzare la funzionalità "Segnalibri per colonne di tabella" in Aspose.Words per .NET?

R: Per utilizzare la funzionalità "Segnalibri per colonne di tabella" in Aspose.Words per .NET, è necessario avere una conoscenza di base del linguaggio C#. È inoltre necessario un ambiente di sviluppo .NET con la libreria Aspose.Words installata.

#### D: Come creare una tabella con colonne in un documento Word utilizzando Aspose.Words per .NET?

 R: Per creare una tabella con colonne in un documento Word utilizzando Aspose.Words per .NET, puoi utilizzare a`DocumentBuilder`oggetto per inserire celle e contenuto nella tabella. Ecco un codice di esempio:

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

#### D: Come aggiungere ai segnalibri una colonna di tabella utilizzando Aspose.Words per .NET?

 R: Per creare un segnalibro su una colonna di tabella utilizzando Aspose.Words per .NET, puoi utilizzare il file`StartBookmark` metodo del`DocumentBuilder` oggetto per avviare il segnalibro su una colonna di tabella specifica. Ecco un codice di esempio:

```csharp
builder.StartBookmark("MyBookmark");
```

#### D: Come accedere al contenuto della colonna della tabella dal segnalibro utilizzando Aspose.Words per .NET?

A: Per accedere al contenuto di una colonna di tabella da un segnalibro utilizzando Aspose.Words per .NET, è possibile scorrere tutti i segnalibri nel documento, verificare se un segnalibro è una colonna e utilizzare l'indice della colonna per accedere al contenuto di quella colonna. Ecco un codice di esempio:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Fai qualcosa con il contenuto della colonna...
         }
     }
}
```

#### D: Esiste un limite al numero di colonne che posso creare in una tabella con segnalibri di colonna?

R: Non esiste un limite specifico al numero di colonne che puoi creare in una tabella con segnalibri di colonna utilizzando Aspose.Words per .NET. Il limite dipende principalmente dalle risorse disponibili sul tuo sistema e dalle specifiche del formato di file Word che stai utilizzando. Si consiglia tuttavia di non creare un numero di colonne eccessivamente elevato, poiché ciò potrebbe compromettere la resa e la leggibilità del documento finale.