---
title: Crea segnalibro nel documento di Word
linktitle: Crea segnalibro nel documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come creare segnalibri nel documento word e specificare i livelli di anteprima dei segnalibri in un PDF utilizzando Aspose.Words per .NET.
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

### Domande frequenti

#### D: Quali sono i prerequisiti per utilizzare la funzione "Crea segnalibri" in Aspose.Words per .NET?

R: Per utilizzare la funzione "Crea segnalibri" in Aspose.Words per .NET, devi avere una conoscenza di base del linguaggio C#. È inoltre necessario un ambiente di sviluppo .NET con la libreria Aspose.Words installata.

#### D: Come creare un documento in Aspose.Words per .NET?

 R: Per creare un documento in Aspose.Words per .NET, puoi usare il file`Document`classe. Ecco un codice di esempio:

```csharp
Document doc = new Document();
```

#### D: Come creare un segnalibro principale in un documento utilizzando Aspose.Words per .NET?

 R: Per creare un segnalibro principale in un documento utilizzando Aspose.Words per .NET, puoi utilizzare il`StartBookmark` metodo per avviare il segnalibro, aggiungere testo o altri segnalibri all'interno, quindi utilizzare il` EndBookmark` per farla finita. Ecco un codice di esempio:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### D: Come creare un segnalibro nidificato all'interno di un segnalibro principale utilizzando Aspose.Words per .NET?

 R: Per creare un segnalibro nidificato all'interno di un segnalibro principale utilizzando Aspose.Words per .NET, puoi utilizzare lo stesso`StartBookmark` E`EndBookmark` metodi per iniziare e terminare il segnalibro annidato. Ecco un codice di esempio:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### D: Come specificare i livelli di anteprima dei segnalibri in un PDF di output utilizzando Aspose.Words per .NET?

 R: Per specificare i livelli di anteprima dei segnalibri in un PDF di output utilizzando Aspose.Words per .NET, è possibile utilizzare il`PdfSaveOptions` classe e il`BookmarksOutlineLevels` proprietà. È possibile aggiungere segnalibri principali e segnalibri nidificati con i rispettivi livelli. Ecco un codice di esempio:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### D: Come salvare un documento dopo aver creato i segnalibri utilizzando Aspose.Words per .NET?

 R: Per salvare un documento dopo aver creato i segnalibri usando Aspose.Words per .NET, puoi usare il`Save` metodo del`Document` oggetto che specifica il percorso del file di destinazione. Ecco un codice di esempio:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### D: Come specificare i livelli di anteprima dei segnalibri in un PDF di output utilizzando Aspose.Words per .NET?

 R: Per specificare i livelli di anteprima dei segnalibri in un PDF di output utilizzando Aspose.Words per .NET, è possibile utilizzare il`PdfSaveOptions` classe e il`BookmarksOutlineLevels` proprietà. È possibile aggiungere segnalibri principali e segnalibri nidificati con i rispettivi livelli. Ecco un codice di esempio:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### D: Come creare segnalibri nidificati all'interno di un segnalibro principale utilizzando Aspose.Words per .NET?

 A: Per creare segnalibri nidificati all'interno di un segnalibro principale utilizzando Aspose.Words per .NET, è possibile utilizzare lo stesso`StartBookmark` E`EndBookmark` metodi per iniziare e terminare i segnalibri nidificati. Assicurati di specificare il segnalibro padre come parametro quando chiami il file`StartBookmark` metodo. Ecco un codice di esempio:

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

 R: Per aggiungere del testo all'interno di un segnalibro utilizzando Aspose.Words per .NET, puoi utilizzare il`Write` metodo del`DocumentBuilder` oggetto specificando il testo da aggiungere. Ecco un codice di esempio:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### D: Come creare un segnalibro principale in un documento utilizzando Aspose.Words per .NET?

 R: Per creare un segnalibro principale in un documento utilizzando Aspose.Words per .NET, puoi utilizzare il`StartBookmark` metodo per avviare il segnalibro e il file`EndBookmark` metodo per farla finita. Ecco un codice di esempio:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```