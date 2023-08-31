---
title: Crea segnalibro nel documento Word
linktitle: Crea segnalibro nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come creare segnalibri in un documento Word e specificare i livelli di anteprima dei segnalibri in un PDF utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/create-bookmark/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Crea segnalibro nella libreria Aspose.Words per .NET. Questa funzionalità consente di creare segnalibri in un documento e specificare i livelli di anteprima dei segnalibri in un file PDF di output.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione del documento e del generatore

 Prima di creare i segnalibri, dobbiamo creare un documento e un generatore di documenti utilizzando il file`Document` E`DocumentBuilder` oggetti:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: creazione del segnalibro principale

 Noi usiamo il`StartBookmark` metodo per avviare un segnalibro principale e il file`EndBookmark` metodo per porvi fine. Nel mezzo, possiamo aggiungere testo e altri segnalibri:

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

### Codice sorgente di esempio per Crea segnalibro utilizzando Aspose.Words per .NET

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

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Crea segnalibro di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per creare segnalibri in un documento e specificare i livelli di anteprima dei segnalibri in un file PDF di output.

### Domande frequenti

#### D: Quali sono i prerequisiti per utilizzare la funzione "Crea segnalibri" in Aspose.Words per .NET?

R: Per utilizzare la funzione "Crea segnalibri" in Aspose.Words per .NET, è necessario avere una conoscenza di base del linguaggio C#. È inoltre necessario un ambiente di sviluppo .NET con la libreria Aspose.Words installata.

#### D: Come creare un documento in Aspose.Words per .NET?

 R: Per creare un documento in Aspose.Words per .NET, puoi utilizzare il file`Document`classe. Ecco un codice di esempio:

```csharp
Document doc = new Document();
```

#### D: Come creare un segnalibro principale in un documento utilizzando Aspose.Words per .NET?

 R: Per creare un segnalibro principale in un documento utilizzando Aspose.Words per .NET, è possibile utilizzare il file`StartBookmark` metodo per avviare il segnalibro, aggiungere testo o altri segnalibri all'interno, quindi utilizzare il file` EndBookmark` per finirlo. Ecco un codice di esempio:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### D: Come creare un segnalibro nidificato all'interno di un segnalibro principale utilizzando Aspose.Words per .NET?

 A: Per creare un segnalibro nidificato all'interno di un segnalibro principale utilizzando Aspose.Words per .NET, puoi utilizzare lo stesso`StartBookmark` E`EndBookmark` metodi per avviare e terminare il segnalibro nidificato. Ecco un codice di esempio:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### D: Come specificare i livelli di anteprima dei segnalibri in un PDF di output utilizzando Aspose.Words per .NET?

 A: Per specificare i livelli di anteprima dei segnalibri in un PDF di output utilizzando Aspose.Words per .NET, è possibile utilizzare il`PdfSaveOptions` classe e il`BookmarksOutlineLevels` proprietà. Puoi aggiungere segnalibri principali e segnalibri nidificati con i rispettivi livelli. Ecco un codice di esempio:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### D: Come salvare un documento dopo aver creato i segnalibri utilizzando Aspose.Words per .NET?

 R: Per salvare un documento dopo aver creato i segnalibri utilizzando Aspose.Words per .NET, è possibile utilizzare il file`Save` metodo del`Document` oggetto che specifica il percorso del file di destinazione. Ecco un codice di esempio:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### D: Come specificare i livelli di anteprima dei segnalibri in un PDF di output utilizzando Aspose.Words per .NET?

 A: Per specificare i livelli di anteprima dei segnalibri in un PDF di output utilizzando Aspose.Words per .NET, è possibile utilizzare il`PdfSaveOptions` classe e il`BookmarksOutlineLevels` proprietà. Puoi aggiungere segnalibri principali e segnalibri nidificati con i rispettivi livelli. Ecco un codice di esempio:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### D: Come creare segnalibri nidificati all'interno di un segnalibro principale utilizzando Aspose.Words per .NET?

 R: Per creare segnalibri nidificati all'interno di un segnalibro principale utilizzando Aspose.Words per .NET, puoi utilizzare lo stesso`StartBookmark` E`EndBookmark` metodi per avviare e terminare i segnalibri nidificati. Assicurati di specificare il segnalibro principale come parametro quando chiami il file`StartBookmark` metodo. Ecco un codice di esempio:

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

#### D: Come aggiungere testo all'interno di un segnalibro utilizzando Aspose.Words per .NET?

 R: Per aggiungere testo all'interno di un segnalibro utilizzando Aspose.Words per .NET, puoi utilizzare il file`Write` metodo del`DocumentBuilder` oggetto che specifica il testo da aggiungere. Ecco un codice di esempio:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### D: Come creare un segnalibro principale in un documento utilizzando Aspose.Words per .NET?

 R: Per creare un segnalibro principale in un documento utilizzando Aspose.Words per .NET, è possibile utilizzare il file`StartBookmark` metodo per avviare il segnalibro e il file`EndBookmark` metodo per porvi fine. Ecco un codice di esempio:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```