---
title: Crea segnalibro
linktitle: Crea segnalibro
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare segnalibri in un documento e specificare i livelli di anteprima dei segnalibri in un PDF utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/create-bookmark/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Crea segnalibro nella libreria Aspose.Words per .NET. Questa funzione consente di creare segnalibri in un documento e specificare i livelli di anteprima dei segnalibri in un file PDF di output.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione del documento e del generatore

 Prima di creare segnalibri, dobbiamo creare un documento e un generatore di documenti utilizzando il file`Document` E`DocumentBuilder` oggetti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: creazione del segnalibro principale

 Noi usiamo il`StartBookmark` metodo per avviare un segnalibro principale e il`EndBookmark` metodo per farla finita. Nel mezzo, possiamo aggiungere testo e altri segnalibri:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Aggiungi altri segnalibri o testo qui.

builder. EndBookmark("My Bookmark");
```

## Passaggio 3: creazione di segnalibri nidificati

 Possiamo anche creare segnalibri nidificati all'interno di un segnalibro principale. Usiamo lo stesso`StartBookmark` E`EndBookmark` metodi per creare e terminare i segnalibri nidificati:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Passaggio 4: specificare i livelli di anteprima dei segnalibri nel file PDF di output

 Noi usiamo il`PdfSaveOptions` oggetto per specificare i livelli di anteprima dei segnalibri nel file PDF di output. Noi usiamo il`BookmarksOutlineLevels` proprietà

  per aggiungere segnalibri principali e segnalibri nidificati con i rispettivi livelli:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Esempio di codice sorgente per Crea segnalibro utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare la creazione di segnalibri utilizzando Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
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

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Crea segnalibro di Aspose.Words per .NET. Abbiamo seguito una guida dettagliata per creare segnalibri in un documento e specificare i livelli di anteprima dei segnalibri in un file PDF di output.