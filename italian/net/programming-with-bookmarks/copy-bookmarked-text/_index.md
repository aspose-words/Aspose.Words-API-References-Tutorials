---
title: Copia testo con segnalibro
linktitle: Copia testo con segnalibro
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come copiare il testo del segnalibro da un documento di origine a un altro documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/copy-bookmarked-text/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Copia testo con segnalibro nella libreria Aspose.Words per .NET. Questa funzione consente di copiare il contenuto di un segnalibro specifico da un documento di origine a un altro documento.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: caricamento del documento di origine

 Prima di copiare il testo del segnalibro, dobbiamo caricare il documento di origine in a`Document` oggetto utilizzando il percorso del file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Passaggio 2: ottenere il segnalibro di origine

 Noi usiamo il`Bookmarks` proprietà dell'intervallo del documento di origine per ottenere il segnalibro specifico che vogliamo copiare:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Passaggio 3: creazione del documento di destinazione

Creiamo un nuovo documento che servirà come documento di destinazione per copiare il contenuto del segnalibro:

```csharp
Document dstDoc = new Document();
```

## Passaggio 4: specificare la posizione della copia

Specifichiamo la posizione in cui vogliamo aggiungere il testo copiato. Nel nostro esempio, aggiungiamo il testo alla fine del corpo dell'ultima sezione del documento di destinazione:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Passaggio 5: importa e copia il testo del segnalibro

 Usiamo un`NodeImporter`oggetto per importare e copiare il testo del segnalibro da un documento di origine al documento di destinazione:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Codice sorgente di esempio per copiare il testo con segnalibro utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare la copia del testo da un segnalibro utilizzando Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Questo è il segnalibro di cui vogliamo copiare il contenuto.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Aggiungeremo a questo documento.
	Document dstDoc = new Document();

	// Diciamo che verremo aggiunti alla fine del corpo dell'ultima sezione.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Se importi più volte senza un singolo contesto, verranno creati molti stili.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Copia testo con segnalibro da Aspose.Words per .NET. Abbiamo seguito una guida passo passo per copiare il contenuto di un segnalibro da un documento di origine a un altro documento.