---
title: Crea stile tabella
linktitle: Crea stile tabella
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per creare uno stile di tabella personalizzato utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-styles-and-formatting/create-table-style/
---

In questo tutorial ti guideremo attraverso il processo passo passo per creare uno stile di tabella utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come creare uno stile personalizzato per le tue tabelle nei tuoi documenti Word utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Questa è la posizione in cui desideri salvare il documento Word modificato. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: crea un nuovo documento e un generatore di documenti
 Successivamente, è necessario creare una nuova istanza del file`Document` classe e un costruttore di documenti per quel documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: avvia una nuova tabella e aggiungi celle
Per iniziare a creare la tabella, utilizziamo il file`StartTable()` del generatore di documenti, quindi aggiungiamo celle alla tabella utilizzando il metodo`InsertCell()` metodo e scriviamo il contenuto delle celle utilizzando il metodo`Write()` metodo.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## Passaggio 4: crea uno stile di tabella
 Ora possiamo creare uno stile di tabella utilizzando il file`TableStyle` classe e il`Add()` metodo dal documento`s `Collezione di stili. Definiamo le proprietà dello stile, come bordi, margini e riempimenti.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Passaggio 5: applica lo stile tabella alla tabella
 Infine, applichiamo lo stile di tabella che abbiamo creato alla tabella utilizzando il comando`Style` proprietà della tabella.

```csharp
table.Style = tableStyle;
```

## Passaggio 6: salva il documento modificato
Infine salva il documento modificato in un file. È possibile scegliere un nome e una posizione appropriati per il documento di output.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Congratulazioni! Ora hai creato uno stile personalizzato per la tua tabella utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Crea stile tabella utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come creare uno stile di tabella utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo, puoi personalizzare facilmente lo stile delle tabelle nei tuoi documenti Word. Aspose.Words offre un'API potente e flessibile per manipolare e formattare le tabelle nei tuoi documenti. Con questa conoscenza, puoi migliorare la presentazione visiva dei tuoi documenti Word e soddisfare esigenze specifiche.