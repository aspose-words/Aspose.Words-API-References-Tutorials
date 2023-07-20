---
title: Mantieni la numerazione delle fonti
linktitle: Mantieni la numerazione delle fonti
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come aggiungere un documento preservando la formattazione della numerazione di origine in Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/keep-source-numbering/
---

Questo tutorial spiega come aggiungere un documento di origine a un documento di destinazione preservando la formattazione della numerazione originale dei paragrafi numerati utilizzando Aspose.Words per .NET.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo da[Aspose.Releases]https://releases.aspose.com/words/net/ o utilizzare il gestore pacchetti NuGet per installarlo.
- Un percorso di directory dei documenti in cui verranno salvati i documenti di origine e di destinazione.

## Passaggio 2: crea i documenti di destinazione e di origine

 Crea istanze di`Document` per i documenti di destinazione e di origine.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: mantieni la numerazione di origine durante l'importazione

 Per conservare la formattazione della numerazione dei paragrafi numerati dal documento di origine, creare un'istanza di`ImportFormatOptions` e impostare`KeepSourceNumbering` A`true` . Usare un`NodeImporter` per importare i nodi dal documento di origine al documento di destinazione, specificando`ImportFormatMode.KeepSourceFormatting` e il`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Passaggio 4: importa e aggiungi paragrafi

 Scorrere i paragrafi nel documento di origine e importare ogni paragrafo nel documento di destinazione utilizzando il file`importer`. Aggiungi i nodi importati al corpo del documento di destinazione.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Passaggio 5: salvare il documento modificato

 Salvare il documento modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Ciò completa l'implementazione dell'aggiunta di un documento di origine a un documento di destinazione mantenendo la formattazione della numerazione originale utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Keep Source Numbering utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Mantieni la formattazione dell'elenco di origine durante l'importazione di paragrafi numerati.
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