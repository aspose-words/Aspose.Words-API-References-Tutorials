---
title: Tabella formattata
linktitle: Tabella formattata
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come creare una tabella formattata in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/formatted-table/
---

In questo tutorial impareremo come creare una tabella formattata in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzionalità. Alla fine di questo tutorial, sarai in grado di creare tabelle con formattazione personalizzata nei tuoi documenti Word a livello di codice.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungi un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento e inizializzazione del generatore di documenti
Per iniziare a costruire la tabella formattata, dobbiamo creare un nuovo documento e inizializzare il generatore di documenti. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e inizializzare il generatore di documenti
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assicurati di sostituire "LA TUA DIRECTORY DOCUMENTI" con il percorso effettivo della directory dei documenti.

## Passaggio 3: creazione della tabella formattata
Successivamente, creeremo la tabella formattata utilizzando i metodi forniti dal generatore di documenti. Utilizza il seguente codice:

```csharp
// Inizia la costruzione dell'array
Table table = builder. StartTable();

// Costruzione della riga di intestazione della tabella
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Costruzione del corpo dell'array
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Fine della costruzione dell'array
builder. EndTable();
```

 Qui utilizziamo il generatore di documenti per costruire la tabella passo dopo passo. Iniziamo chiamando`StartTable()` per inizializzare la tabella. Quindi usiamo`InsertCell()` per inserire celle e`Write()` per aggiungere contenuto a ciascuna cella. Utilizziamo anche diverse proprietà di formattazione per definire la formattazione di righe, celle e testo della tabella.

## Passaggio 4: salva il documento
Infine, dobbiamo salvare il documento contenente la tabella formattata. Utilizza il seguente codice:

```csharp
// Salva il documento
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per tabella formattata utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// La formattazione estesa della tabella deve essere applicata dopo che nella tabella è presente almeno una riga.
	table.LeftIndent = 20.0;
	// Imposta l'altezza e definisci la regola dell'altezza per la riga di intestazione.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// Non è necessario specificare la larghezza di questa cella perché è ereditata dalla cella precedente.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Reimposta l'altezza e definisci una regola di altezza diversa per il corpo della tabella.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Reimposta la formattazione dei caratteri.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come creare una tabella formattata in un documento Word utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo e implementando il codice C# fornito, puoi creare tabelle personalizzate con formattazione specifica nei tuoi documenti Word a livello di codice. Questa funzionalità ti consente di presentare e strutturare i tuoi dati in modo visivamente accattivante e organizzato.