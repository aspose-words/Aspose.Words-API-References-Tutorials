---
title: Impostazioni di larghezza preferite
linktitle: Impostazioni di larghezza preferite
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare le larghezze delle celle di tabella preferite in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/preferred-width-settings/
---

In questo tutorial impareremo come impostare le impostazioni di larghezza preferite per le celle della tabella in un documento di Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di specificare diverse larghezze preferite per le celle della tua tabella nei tuoi documenti Word.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento e inizializzazione del generatore di documenti
Per iniziare a lavorare con il documento e il generatore di documenti, attenersi alla seguente procedura:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creazione di documenti
Document doc = new Document();

// Inizializza il generatore di documenti
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 3: costruire il tavolo con le larghezze preferite
Successivamente, creeremo una tabella con tre celle che hanno larghezze preferite diverse. Usa il seguente codice:

```csharp
// Inizio del tavolo
builder. StartTable();

// Inserisci una cella di dimensioni assolute
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Inserisci una cella di dimensioni relative (in percentuale)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Inserisci una cella di dimensioni automatiche
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Fine del tavolo
builder. EndTable();
```

Qui usiamo il generatore di documenti per costruire una tabella con tre celle. La prima cella ha una larghezza preferita di 40 punti, la seconda cella ha una larghezza preferita del 20% della larghezza della tabella e la terza cella ha una larghezza preferita automatica che regola

  a seconda dello spazio disponibile.

## Passaggio 4: salvare il documento modificato
Infine, dobbiamo salvare il documento modificato con le impostazioni di larghezza preferite definite per le celle della tabella. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per le impostazioni di larghezza preferite utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Inserisci una riga della tabella composta da tre celle che hanno larghezze preferite diverse.
	builder.StartTable();
	// Inserisci una cella di dimensioni assolute.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Inserisci una cella di dimensione relativa (percentuale).
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Inserisci una cella di dimensioni automatiche.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come impostare le impostazioni di larghezza preferite per le celle della tabella in un documento di Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, puoi personalizzare le larghezze delle celle della tabella in base alle tue esigenze specifiche nei documenti di Word.