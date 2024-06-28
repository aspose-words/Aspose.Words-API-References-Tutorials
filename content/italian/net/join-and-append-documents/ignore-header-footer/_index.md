---
title: Ignora il piè di pagina dell'intestazione
linktitle: Ignora il piè di pagina dell'intestazione
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere un documento ignorando il contenuto di intestazione e piè di pagina utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/ignore-header-footer/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per aggiungere un documento ignorando il contenuto dell'intestazione e del piè di pagina. Il codice sorgente fornito dimostra come impostare le opzioni del formato di importazione per escludere l'intestazione e il piè di pagina durante il processo di aggiunta.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

-  Aspose.Words per la libreria .NET installata. Puoi scaricarlo da[Aspose.Releases]https://releases.aspose.com/words/net/ o utilizzare il gestore pacchetti NuGet per installarlo.
- Un percorso di directory di documenti in cui si trovano i documenti di origine e di destinazione.

## Passaggio 2: apri i documenti di origine e di destinazione

 Apri i documenti di origine e di destinazione utilizzando il file`Document` costruttore di classi. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Passaggio 3: imposta le opzioni del formato di importazione

 Crea un'istanza di`ImportFormatOptions` classe e impostare il file`IgnoreHeaderFooter`proprietà a`false`. Ciò garantisce che il contenuto dell'intestazione e del piè di pagina venga incluso durante il processo di aggiunta.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Passaggio 4: aggiungi il documento di origine al documento di destinazione

 Usa il`AppendDocument` metodo del documento di destinazione per aggiungere il documento di origine. Passaggio`ImportFormatMode.KeepSourceFormatting`come secondo parametro e le opzioni del formato di importazione come terzo parametro.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Passaggio 5: salva il documento di destinazione

Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Ciò completa l'implementazione dell'aggiunta di un documento ignorando il contenuto dell'intestazione e del piè di pagina utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Ignora Header Footer utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```