---
title: Costruisci tavolo con stile
linktitle: Costruisci tavolo con stile
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata alla creazione di una tabella con uno stile personalizzato utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

In questo tutorial, ti guideremo attraverso il processo passo-passo per creare una tabella con stili utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come creare una tabella con uno stile personalizzato nei tuoi documenti Word utilizzando Aspose.Words per .NET.

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

## Passaggio 3: inizia una nuova tabella e inserisci una cella
 Per iniziare a costruire la tabella, usiamo il`StartTable()` metodo del generatore di documenti, quindi inseriamo una cella nella tabella utilizzando il`InsertCell()` metodo.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Passaggio 4: definire lo stile della tabella
 Ora possiamo impostare lo stile della tabella usando il`StyleIdentifier` proprietà. In questo esempio, stiamo usando lo stile "MediumShading1Accent1".

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Passaggio 5: applica le opzioni di stile alla tabella
 Possiamo specificare quali caratteristiche devono essere formattate dallo stile utilizzando il file`StyleOptions`proprietà dell'array. In questo esempio applichiamo le seguenti opzioni: "FirstColumn", "RowBands" e "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Passaggio 6: regola automaticamente le dimensioni del tavolo
 Per regolare automaticamente la dimensione dell'array in base al suo contenuto, usiamo il file`AutoFit()` metodo con il`AutoFitBehavior.AutoFitToContents` comportamento.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Passaggio 7: aggiungi contenuto alle celle
 Ora possiamo aggiungere contenuto alle celle usando il`Writeln()` E`InsertCell()` metodi del costruttore di documenti. In questo esempio, aggiungiamo le intestazioni per "Articolo" e "Quantità (

kg)" e i relativi dati.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## Passaggio 8: salvare il documento modificato
Infine, salviamo il documento modificato in un file. È possibile scegliere un nome e una posizione appropriati per il documento di output.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Congratulazioni! Ora hai creato una tabella con uno stile personalizzato utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Build Table With Style utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Dobbiamo inserire almeno una riga prima di impostare qualsiasi formattazione della tabella.
	builder.InsertCell();
	// Imposta lo stile della tabella utilizzato in base all'identificatore di stile univoco.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Applicare quali funzionalità devono essere formattate dallo stile.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come creare una tabella con stili utilizzando Aspose.Words per .NET. Seguendo questa guida passo-passo, puoi facilmente personalizzare lo stile delle tue tabelle nei tuoi documenti Word. Aspose.Words offre un'API potente e flessibile per la manipolazione e la formattazione delle tabelle nei tuoi documenti. Con questa conoscenza, puoi migliorare la presentazione visiva dei tuoi documenti Word e soddisfare esigenze specifiche.