---
title: Formato tabella e cella con bordi diversi
linktitle: Formato tabella e cella con bordi diversi
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per formattare tabelle e celle con bordi diversi utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

In questo tutorial ti guideremo attraverso il processo passo passo per formattare una tabella e una cella con bordi diversi utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come applicare bordi personalizzati a tabelle e celle specifiche nei tuoi documenti Word utilizzando Aspose.Words per .NET.

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
Per iniziare a creare la tabella, utilizziamo il file`StartTable()` del generatore di documenti, quindi aggiungiamo celle alla tabella utilizzando il metodo`InsertCell()` metodo e scriviamo il contenuto delle celle utilizzando il metodo`Writeln()` metodo.

```csharp
Table table = builder. StartTable();
builder.InsertCell();
// Imposta i bordi per l'intera tabella.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Imposta il riempimento per questa cella.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Specificare un riempimento cella diverso per la seconda cella.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Cancella la formattazione della cella dalle operazioni precedenti.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Crea bordi più spessi per la prima cella di questa riga. Sarà diverso
// rispetto ai bordi definiti per la tabella.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Passaggio 4: salva il documento

  modificato
Infine salva il documento modificato in un file. È possibile scegliere un nome e una posizione appropriati per il documento di output.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Congratulazioni! Ora hai formattato una tabella e una cella con bordi diversi utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per formato tabella e cella con bordi diversi utilizzando Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
builder.InsertCell();
//Imposta i bordi per l'intera tabella.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Imposta l'ombreggiatura della cella per questa cella.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Specificare un'ombreggiatura diversa per la seconda cella.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Cancella la formattazione della cella dalle operazioni precedenti.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Crea bordi più grandi per la prima cella di questa riga. Questo sarà diverso
// rispetto ai bordi fissati per la tavola.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come formattare una tabella e una cella con bordi diversi utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo, puoi personalizzare facilmente i bordi della tabella e delle celle nei tuoi documenti Word. Aspose.Words offre un'API potente e flessibile per manipolare e formattare le tabelle nei tuoi documenti. Con questa conoscenza, puoi migliorare la presentazione visiva dei tuoi documenti Word e soddisfare esigenze specifiche.