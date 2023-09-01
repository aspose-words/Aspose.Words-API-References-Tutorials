---
title: Mantieni la numerazione delle fonti
linktitle: Mantieni la numerazione delle fonti
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere un documento preservando la formattazione della numerazione dell'origine in Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/keep-source-numbering/
---

Questo tutorial spiega come aggiungere un documento di origine a un documento di destinazione preservando la formattazione della numerazione originale dei paragrafi numerati utilizzando Aspose.Words per .NET.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

-  Aspose.Words per la libreria .NET installata. Puoi scaricarlo da[Aspose.Releases]https://releases.aspose.com/words/net/ o utilizzare il gestore pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui verranno salvati i documenti di origine e di destinazione.

## Passaggio 2: crea i documenti di destinazione e di origine

 Crea istanze di`Document` per i documenti di destinazione e di origine.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: mantieni la numerazione della fonte durante l'importazione

Per preservare la formattazione della numerazione dei paragrafi numerati del documento di origine, creare un'istanza di`ImportFormatOptions` e impostare`KeepSourceNumbering` A`true` . Usare un`NodeImporter` per importare i nodi dal documento di origine al documento di destinazione, specificando`ImportFormatMode.KeepSourceFormatting` e il`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Passaggio 4: importa e aggiungi paragrafi

 Scorri i paragrafi nel documento di origine e importa ogni paragrafo nel documento di destinazione utilizzando il file`importer`. Aggiungi i nodi importati al corpo del documento di destinazione.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Passaggio 5: salva il documento modificato

 Salvare il documento modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Ciò completa l'implementazione dell'aggiunta di un documento di origine a un documento di destinazione mantenendo la formattazione della numerazione originale utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Keep Source Numbering utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Mantieni la formattazione dell'elenco di origine durante l'importazione dei paragrafi numerati.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```