---
title: Mantieni la formattazione dell'origine
linktitle: Mantieni la formattazione dell'origine
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere un documento di origine a un documento di destinazione preservando la formattazione originale utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/keep-source-formatting/
---

Questo tutorial dimostra come aggiungere un documento di origine a un documento di destinazione preservando la formattazione originale del documento di origine utilizzando Aspose.Words per .NET.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

-  Aspose.Words per la libreria .NET installata. Puoi scaricarlo da[Aspose.Releases]https://releases.aspose.com/words/net/ o utilizzare il gestore pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui verranno salvati i documenti di origine e di destinazione.

## Passaggio 2: crea i documenti di destinazione e di origine

 Crea istanze di`Document` per i documenti di destinazione e di origine.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Passaggio 3: aggiungi il documento di origine al documento di destinazione

 Usa il`AppendDocument` metodo del documento di destinazione per aggiungere il documento di origine. Passaggio`ImportFormatMode.KeepSourceFormatting` come modalità di formato di importazione per mantenere la formattazione originale del documento di origine.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Passaggio 4: salva il documento modificato

 Salvare il documento modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Ciò completa l'implementazione dell'aggiunta di un documento di origine a un documento di destinazione mantenendo la formattazione originale utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Keep Source Formatting utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Aggiungi il documento di origine al documento di destinazione.
	// Passa modalità formato per mantenere la formattazione originale del documento di origine durante l'importazione.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```