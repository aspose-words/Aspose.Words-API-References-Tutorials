---
title: Aggiungi con le opzioni del formato di importazione
linktitle: Aggiungi con le opzioni del formato di importazione
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere un documento con le opzioni del formato di importazione utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/append-with-import-format-options/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per aggiungere il contenuto di un documento a un altro con opzioni di formato di importazione. Il codice sorgente fornito dimostra come aprire i documenti di origine e di destinazione, specificare le opzioni del formato di importazione e aggiungere il documento di origine al documento di destinazione.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

-  Aspose.Words per la libreria .NET installata. Puoi scaricarlo da[Aspose.Releases]https://releases.aspose.com/words/net/ o utilizzare il gestore pacchetti NuGet per installarlo.
- Un percorso di directory di documenti in cui si trovano i documenti di origine e di destinazione.

## Passaggio 2: apri i documenti di origine e di destinazione

 Apri i documenti di origine e di destinazione utilizzando il file`Document` costruttore di classi. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Passaggio 3: specifica le opzioni del formato di importazione

 Crea un'istanza di`ImportFormatOptions` classe per specificare le opzioni del formato di importazione. In questo esempio utilizziamo il file`KeepSourceNumbering` per garantire che venga utilizzata la numerazione del documento di origine in caso di conflitti con il documento di destinazione.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Passaggio 4: aggiungi il documento di origine al documento di destinazione

 Usa il`AppendDocument` metodo del documento di destinazione per aggiungere il documento di origine. Passaggio`ImportFormatMode.UseDestinationStyles` come secondo parametro per utilizzare gli stili e la formattazione del documento di destinazione.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Passaggio 5: salva il documento di destinazione

 Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Ciò completa l'implementazione dell'aggiunta di un documento con le opzioni del formato di importazione utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Aggiungi con opzioni di formato di importazione utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Specificare che se la numerazione è in conflitto nei documenti di origine e di destinazione,
	//verrà quindi utilizzata la numerazione del documento di origine.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```