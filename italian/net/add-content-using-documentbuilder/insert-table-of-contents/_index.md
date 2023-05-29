---
title: Inserisci sommario
linktitle: Inserisci sommario
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un sommario nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-table-of-contents/
---

In questo tutorial completo imparerai come inserire un sommario in un documento Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di generare un sommario con intestazioni e numeri di pagina appropriati.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserire un sommario
Utilizzare quindi il metodo InsertTableOfContents della classe DocumentBuilder per inserire un sommario. Specificare le opzioni di formattazione richieste all'interno del metodo:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Passaggio 3: aggiungi il contenuto del documento
Dopo aver inserito il sommario, aggiungi il contenuto effettivo del documento. Imposta gli stili di intestazione appropriati utilizzando StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Passaggio 4: aggiorna il sommario
Il sommario appena inserito sarà inizialmente vuoto. Per popolarlo, aggiorna i campi nel documento:

```csharp
doc.UpdateFields();
```

## Passaggio 5: salvare il documento
Dopo aver inserito il sommario e aggiornato i campi, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Esempio di codice sorgente per Inserisci sommario utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di un sommario utilizzando Aspose.Words per .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inizializza DocumentBuilder con l'oggetto Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci la tabella dei contenutia
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Avviare il contenuto effettivo del documento nella seconda pagina.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// Il sommario appena inserito sarà inizialmente vuoto.
// Deve essere popolato aggiornando i campi nel documento.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```
