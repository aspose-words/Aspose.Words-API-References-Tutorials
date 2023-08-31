---
title: Unisciti a una nuova pagina
linktitle: Unisciti a una nuova pagina
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come unire due documenti su una nuova pagina preservando la formattazione utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/join-new-page/
---

Questo tutorial spiega come unire due documenti su una nuova pagina utilizzando Aspose.Words per .NET. Il codice sorgente fornito mostra come aggiungere un documento alla fine di un altro documento mentre si avvia il documento aggiunto in una nuova pagina.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo da[Aspose.Releases]https://releases.aspose.com/words/net/ o utilizzare il gestore pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui si trovano i documenti di origine e di destinazione.

## Passaggio 2: apri i documenti di origine e di destinazione

 Apri i documenti di origine e di destinazione utilizzando il file`Document` costruttore di classe. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: impostare l'inizio della nuova sezione della pagina

 Per iniziare il documento aggiunto su una nuova pagina, impostare il file`SectionStart` proprietà della prima sezione nel documento di origine to`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Passaggio 4: aggiungere il documento di origine

 Aggiungi il documento di origine al documento di destinazione utilizzando il file`AppendDocument` metodo del`Document` classe. Imposta la modalità del formato di importazione su`ImportFormatMode.KeepSourceFormatting` per preservare gli stili originali dal documento di origine.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 5: salvare il documento modificato

 Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Questo completa l'implementazione dell'unione di due documenti su una nuova pagina utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Join New Page utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Impostare il documento aggiunto in modo che inizi su una nuova pagina.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Aggiungi il documento di origine utilizzando gli stili originali trovati nel documento di origine.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```