---
title: Iscriviti a una nuova pagina
linktitle: Iscriviti a una nuova pagina
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come unire due documenti su una nuova pagina preservando la formattazione utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/join-new-page/
---

Questo tutorial spiega come unire due documenti su una nuova pagina utilizzando Aspose.Words per .NET. Il codice sorgente fornito dimostra come aggiungere un documento alla fine di un altro documento mentre si avvia il documento aggiunto su una nuova pagina.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

-  Aspose.Words per la libreria .NET installata. Puoi scaricarlo da[Aspose.Releases]https://releases.aspose.com/words/net/ o utilizzare il gestore pacchetti NuGet per installarlo.
- Un percorso di directory di documenti in cui si trovano i documenti di origine e di destinazione.

## Passaggio 2: apri i documenti di origine e di destinazione

 Apri i documenti di origine e di destinazione utilizzando il file`Document` costruttore di classi. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: imposta l'inizio della nuova sezione della pagina

Per iniziare il documento aggiunto su una nuova pagina, impostare il file`SectionStart` proprietà della prima sezione nel documento di origine a`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Passaggio 4: aggiungi il documento di origine

Aggiungi il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. Imposta la modalità del formato di importazione su`ImportFormatMode.KeepSourceFormatting` per preservare gli stili originali del documento di origine.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 5: salva il documento modificato

 Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Ciò completa l'implementazione dell'unione di due documenti su una nuova pagina utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Unisciti a una nuova pagina utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Imposta il documento aggiunto in modo che inizi su una nuova pagina.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Aggiungi il documento di origine utilizzando gli stili originali trovati nel documento di origine.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```