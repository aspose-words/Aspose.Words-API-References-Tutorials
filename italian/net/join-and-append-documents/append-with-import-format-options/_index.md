---
title: Aggiungi con le opzioni del formato di importazione
linktitle: Aggiungi con le opzioni del formato di importazione
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come aggiungere un documento con opzioni di formato di importazione utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/join-and-append-documents/append-with-import-format-options/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per aggiungere il contenuto di un documento a un altro con le opzioni del formato di importazione. Il codice sorgente fornito mostra come aprire i documenti di origine e di destinazione, specificare le opzioni del formato di importazione e aggiungere il documento di origine al documento di destinazione.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare il gestore di pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui si trovano i documenti di origine e di destinazione.

## Passaggio 2: apri i documenti di origine e di destinazione

 Apri i documenti di origine e di destinazione utilizzando il file`Document` costruttore di classe. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Passaggio 3: specificare le opzioni del formato di importazione

 Crea un'istanza di`ImportFormatOptions` class per specificare le opzioni del formato di importazione. In questo esempio, usiamo il`KeepSourceNumbering` proprietà per garantire che la numerazione del documento di origine venga utilizzata in caso di conflitti con il documento di destinazione.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Passaggio 4: aggiungere il documento di origine al documento di destinazione

 Usa il`AppendDocument`metodo del documento di destinazione per aggiungere il documento di origine. Passaggio`ImportFormatMode.UseDestinationStyles` come secondo parametro per utilizzare gli stili e la formattazione del documento di destinazione.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Passaggio 5: salvare il documento di destinazione

 Infine, salva il documento di destinazione modificato utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Questo completa l'implementazione dell'aggiunta di un documento con opzioni di formato di importazione utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Aggiungi con opzioni di formato di importazione utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Specificare che se la numerazione è in conflitto nei documenti di origine e di destinazione,
	// quindi verrà utilizzata la numerazione dal documento di origine.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```