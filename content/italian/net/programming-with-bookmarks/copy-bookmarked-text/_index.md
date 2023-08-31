---
title: Copia il testo con segnalibro nel documento Word
linktitle: Copia il testo con segnalibro nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come copiare il testo dei segnalibri nel documento Word in un altro documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/copy-bookmarked-text/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Copia testo con segnalibro nella libreria Aspose.Words per .NET. Questa funzionalità consente di copiare il contenuto di un segnalibro specifico da un documento di origine a un altro documento.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: caricamento del documento di origine

 Prima di copiare il testo del segnalibro, dobbiamo caricare il documento sorgente in un file`Document` oggetto utilizzando il percorso del file:

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

Specifichiamo la posizione in cui vogliamo aggiungere il testo copiato. Nel nostro esempio aggiungiamo il testo alla fine del corpo dell'ultima sezione del documento di destinazione:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Passaggio 5: importa e copia il testo dei segnalibri

 Usiamo a`NodeImporter` oggetto per importare e copiare il testo del segnalibro da un documento di origine al documento di destinazione:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Codice sorgente di esempio per copiare testo con segnalibro utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare la copia del testo da un segnalibro utilizzando Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Questo è il segnalibro di cui vogliamo copiare il contenuto.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Aggiungeremo a questo documento.
	Document dstDoc = new Document();

	//Diciamo che verremo aggiunti alla fine del corpo dell'ultima sezione.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Se importi più volte senza un singolo contesto, verranno creati molti stili.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Copia testo con segnalibro da Aspose.Words per .NET. Abbiamo seguito una guida passo passo per copiare il contenuto di un segnalibro da un documento di origine a un altro documento.

### Domande frequenti per copiare il testo con segnalibro in un documento Word

#### D: Quali sono i requisiti per utilizzare la funzionalità "Copia testo con segnalibri" in Aspose.Words per .NET?

R: Per utilizzare la funzione "Copia testo con segnalibri" in Aspose.Words per .NET, è necessario avere una conoscenza di base del linguaggio C#. È inoltre necessario un ambiente di sviluppo .NET con la libreria Aspose.Words installata.

#### D: Come carico un documento sorgente in Aspose.Words per .NET?

 R: Per caricare un documento sorgente in Aspose.Words per .NET, è possibile utilizzare il file`Document`classe specificando il percorso del file del documento. Ecco un codice di esempio:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### D: Come ottenere il contenuto di un segnalibro specifico in un documento di origine utilizzando Aspose.Words per .NET?

 R: Per ottenere il contenuto di un segnalibro specifico in un documento di origine utilizzando Aspose.Words per .NET, puoi accedere a`Bookmarks` proprietà dell'intervallo del documento di origine e utilizzare il nome del segnalibro per recuperare il segnalibro specifico. Ecco un codice di esempio:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### D: Come specificare la posizione della copia del testo del segnalibro in un documento di destinazione utilizzando Aspose.Words per .NET?

 R: Per specificare dove si desidera aggiungere il testo del segnalibro copiato in un documento di destinazione utilizzando Aspose.Words per .NET, è possibile accedere al corpo dell'ultima sezione del documento di destinazione. Puoi usare il`LastSection` property per accedere all'ultima sezione e al`Body` property per accedere al corpo di quella sezione. Ecco un codice di esempio:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### D: Come importare e copiare il testo dei segnalibri dal documento di origine al documento di destinazione utilizzando Aspose.Words per .NET?

A: Per importare e copiare il testo dei segnalibri da un documento di origine a un documento di destinazione utilizzando Aspose.Words per .NET, è possibile utilizzare il`NodeImporter` classe specificando il documento di origine, il documento di destinazione e la modalità di formattazione da conservare. Quindi puoi usare il`AppendBookmarkedText` metodo per aggiungere il testo del segnalibro nel documento di destinazione. Ecco un codice di esempio:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### D: Come salvare un documento di destinazione dopo aver copiato il testo del segnalibro utilizzando Aspose.Words per .NET?

 R: Per salvare un documento di destinazione dopo aver copiato il testo da un segnalibro utilizzando Aspose.Words per .NET, è possibile utilizzare`Save` metodo del`Document` oggetto che specifica il percorso del file di destinazione. Ecco un codice di esempio:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```