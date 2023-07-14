---
title: Inserisci documento con Builder
linktitle: Inserisci documento con Builder
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come inserire un documento alla fine di un altro documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/insert-document-with-builder/
---

 Questo tutorial spiega come utilizzare Aspose.Words per .NET per inserire un documento in un altro documento utilizzando il file`DocumentBuilder` classe. Il codice sorgente fornito mostra come inserire un documento alla fine di un altro documento preservando la formattazione di origine.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare il gestore di pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui si trovano i documenti di origine e di destinazione.

## Passaggio 2: apri i documenti di origine e di destinazione

 Apri i documenti di origine e di destinazione utilizzando il file`Document` costruttore di classe. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: inizializzare DocumentBuilder

 Crea una nuova istanza di`DocumentBuilder` class e passare il documento di destinazione come parametro.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Passaggio 4: posizionare DocumentBuilder

 Muovi il`DocumentBuilder` alla fine del documento utilizzando il`MoveToDocumentEnd` metodo. Inserisci un'interruzione di pagina per separare il contenuto esistente dal documento inserito.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Passaggio 5: inserire il documento di origine

 Usa il`InsertDocument` metodo del`DocumentBuilder` class per inserire il documento di origine nel documento di destinazione. Imposta la modalità del formato di importazione su`ImportFormatMode.KeepSourceFormatting` per preservare la formattazione della sorgente.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 6: salvare il documento modificato

 Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Questo completa l'implementazione dell'inserimento di un documento in un altro documento utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Inserisci documento con Builder utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```