---
title: Ignora caselle di testo
linktitle: Ignora caselle di testo
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere un documento ignorando la formattazione della casella di testo utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/ignore-text-boxes/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per aggiungere un documento preservando la formattazione delle caselle di testo. Il codice sorgente fornito dimostra come impostare le opzioni del formato di importazione per includere caselle di testo durante il processo di aggiunta.

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

## Passaggio 3: imposta le opzioni del formato di importazione

 Crea un'istanza di`ImportFormatOptions` classe e impostare il file`IgnoreTextBoxes`proprietà a`false`. Ciò garantisce che le caselle di testo vengano incluse durante il processo di aggiunta preservandone la formattazione.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Passaggio 4: aggiungi il contenuto della casella di testo

 Creare un`NodeImporter`oggetto e utilizzarlo per importare i nodi della casella di testo dal documento di origine al documento di destinazione. Scorri ogni paragrafo del documento di origine e importalo nel documento di destinazione.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Passaggio 5: salva il documento di destinazione

Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Ciò completa l'implementazione dell'aggiunta di un documento preservando la formattazione della casella di testo utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Ignora caselle di testo utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Mantieni la formattazione delle caselle di testo di origine durante l'importazione.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```