---
title: Unione verticale
linktitle: Unione verticale
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come unire verticalmente le celle in una tabella in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/vertical-merge/
---

In questo tutorial impareremo come unire verticalmente le celle in una tabella in un documento Word usando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di unire verticalmente le celle nelle tue tabelle nei documenti di Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento
Per avviare l'elaborazione di parole con il documento, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea un nuovo documento
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 3: unione di celle verticali
Successivamente uniremo le celle verticali nella tabella. Usa il seguente codice:

```csharp
// Inserisci una cella
builder. InsertCell();

// Applica l'unione verticale alla prima cella
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Inserisci un'altra cella
builder. InsertCell();

// Non applicare alcuna unione verticale alla cella
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Inserisci una cella
builder. InsertCell();

// Applicare l'unione verticale con la cella precedente
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Inserisci un'altra cella
builder. InsertCell();

// Non applicare alcuna unione verticale alla cella
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Termina la creazione della tabella
builder. EndTable();
```

In questo codice, utilizziamo il costruttore DocumentBuilder per inserire celle in una tabella. Applichiamo l'unione verticale alle celle utilizzando la proprietà CellFormat.VerticalMerge. Usiamo CellMerge.First per la prima unione di celle, CellMerge.Previous per unire con la cella precedente e CellMerge.None per nessuna unione verticale.

## Passaggio 4: salvare il documento modificato
Infine, dobbiamo salvare il documento modificato con le celle unite. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per l'unione verticale utilizzando Aspose.Words per .NET 
```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Questa cella è unita verticalmente alla cella sopra e dovrebbe essere vuota.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come unire verticalmente le celle in una tabella in un documento di Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, puoi unire facilmente le celle Vertical nelle tue tabelle.