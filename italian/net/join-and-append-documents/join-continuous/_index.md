---
title: Iscriviti continuo
linktitle: Iscriviti continuo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come unire due documenti in modo continuo preservando la formattazione utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/join-continuous/
---

Questo tutorial spiega come unire due documenti in modo continuo utilizzando Aspose.Words per .NET. Il codice sorgente fornito mostra come aggiungere un documento alla fine di un altro documento mantenendo la formattazione originale.

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

## Passaggio 3: impostare l'inizio della sezione continua

 Per fare in modo che il documento di origine appaia subito dopo il contenuto del documento di destinazione, imposta il file`SectionStart` proprietà della prima sezione nel documento di origine to`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Passaggio 4: aggiungere il documento di origine

 Aggiungi il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. Imposta la modalità del formato di importazione su`ImportFormatMode.KeepSourceFormatting`per preservare gli stili originali dal documento di origine.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 5: salvare il documento modificato

 Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Questo completa l'implementazione dell'unione continua di due documenti utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Join Continuous utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Fai apparire il documento subito dopo il contenuto dei documenti di destinazione.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Aggiungi il documento di origine utilizzando gli stili originali trovati nel documento di origine.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```