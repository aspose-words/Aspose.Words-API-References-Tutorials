---
title: Inserisci il sommario nel documento di Word
linktitle: Inserisci il sommario nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un sommario nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-table-of-contents/
---
In questo tutorial completo imparerai come inserire un sommario in un documento Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo gli snippet di codice C# necessari. Al termine di questa guida sarai in grado di generare un sommario con titoli e numeri di pagina appropriati.

## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: crea un nuovo documento e DocumentBuilder
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
Il sommario appena inserito sarà inizialmente vuoto. Per compilarlo, aggiorna i campi nel documento:

```csharp
doc.UpdateFields();
```

## Passaggio 5: salva il documento
Dopo aver inserito il sommario e aggiornato i campi, salva il documento su un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Esempio di codice sorgente per inserire il sommario utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di un sommario utilizzando Aspose.Words per .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inizializza DocumentBuilder con l'oggetto Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci il sommario
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Inizia il contenuto effettivo del documento nella seconda pagina.
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

## Conclusione

Congratulazioni! Hai imparato con successo come inserire un sommario in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo e utilizzando il codice sorgente fornito, ora puoi generare un sommario con intestazioni e numeri di pagina appropriati per i tuoi documenti.

### Domande frequenti sull'inserimento del sommario nel documento Word

#### D: Posso personalizzare l'aspetto del sommario?

 R: Sì, puoi personalizzare l'aspetto del sommario modificando le opzioni di formattazione specificate nel file`InsertTableOfContents` metodo. I parametri consentono di controllare i numeri di pagina, il rientro e altri stili.

#### D: Cosa succede se desidero includere livelli di intestazione specifici nel sommario?

 R: È possibile specificare i livelli di intestazione desiderati da includere nel sommario regolando il valore all'interno di`InsertTableOfContents` metodo. Ad esempio, utilizzando`"\\o \"1-3\""` includerà i livelli di intestazione da 1 a 3.

#### D: Posso aggiornare automaticamente il sommario se apporto modifiche al contenuto del documento?

 R: Sì, puoi aggiornare automaticamente il sommario chiamando il`UpdateFields` metodo sul documento. Ciò garantirà che qualsiasi modifica apportata al contenuto del documento, come l'aggiunta o la rimozione di intestazioni, si rifletta nel sommario.

#### D: Come posso definire diversamente i livelli di intestazione nel sommario?

 R: Puoi applicare stili diversi ai livelli di intestazione utilizzando stili di paragrafo diversi per ciascun livello di intestazione. Assegnando diversi`StyleIdentifier` valori al`ParagraphFormat` del`DocumentBuilder`, puoi creare stili distinti per ciascun livello di intestazione.

#### D: È possibile aggiungere ulteriore formattazione alle intestazioni del sommario?

 R: Sì, puoi aggiungere ulteriore formattazione alle intestazioni del sommario, come stili di carattere, colori o altre proprietà. Regolando il`Font` proprietà del`DocumentBuilder`, puoi applicare una formattazione personalizzata alle intestazioni.