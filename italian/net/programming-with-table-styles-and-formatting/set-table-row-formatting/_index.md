---
title: Imposta la formattazione delle righe della tabella
linktitle: Imposta la formattazione delle righe della tabella
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata all'impostazione della formattazione delle righe della tabella utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

In questo tutorial, ti guideremo attraverso il processo passo-passo per impostare la formattazione delle righe della tabella utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come regolare l'altezza e il padding di una riga della tabella nei tuoi documenti Word usando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui desideri salvare il documento Word modificato. Sostituisci "LA TUA CARTELLA DEI DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creare un nuovo documento e un generatore di documenti
 Successivamente, è necessario creare una nuova istanza del file`Document` class e un costruttore di documenti per quel documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inizia una nuova tabella e aggiungi una cella
Per iniziare a creare la tabella, usiamo il file`StartTable()` metodo del costruttore del documento, quindi aggiungiamo una cella alla tabella utilizzando il`InsertCell()` metodo.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Passaggio 4: definire la formattazione della riga
 Ora possiamo impostare la formattazione della riga accedendo al file`RowFormat` oggetto del`DocumentBuilder` oggetto. Possiamo impostare l'altezza della linea ei margini (padding) utilizzando le proprietà corrispondenti.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Passaggio 5: imposta i margini della tabella
 Successivamente, possiamo impostare i padding della tabella accedendo alle proprietà corrispondenti del file`Table` oggetto. Questi margini verranno applicati a tutte le righe della tabella.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Passaggio 6: aggiungi contenuto alla riga
 Infine, possiamo aggiungere contenuto alla riga utilizzando il generatore di documenti`Writeln()` metodo.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Passaggio 7: completa la tabella e salva il documento
In

 fine, finiamo di creare la tabella usando il`EndRow()` E`EndTable()` metodo, quindi salviamo il documento modificato in un file.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Codice sorgente di esempio per impostare la formattazione delle righe della tabella utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Queste proprietà di formattazione vengono impostate sulla tabella e vengono applicate a tutte le righe della tabella.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare la formattazione delle righe della tabella utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata, puoi facilmente regolare l'altezza e i margini delle righe della tabella nei tuoi documenti Word. Aspose.Words offre un'API potente e flessibile per la manipolazione e la formattazione delle tabelle nei tuoi documenti. Con questa conoscenza, puoi personalizzare il layout visivo dei tuoi tavoli in base alle tue esigenze specifiche.