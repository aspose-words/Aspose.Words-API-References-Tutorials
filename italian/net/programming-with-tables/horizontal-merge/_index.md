---
title: Unione orizzontale
linktitle: Unione orizzontale
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come unire orizzontalmente le celle in una tabella di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-tables/horizontal-merge/
---

In questo tutorial impareremo come unire orizzontalmente le celle in una tabella in un documento Word utilizzando Aspose.Words per .NET. Seguiremo una guida passo passo per comprendere il codice e implementare questa funzione. Alla fine di questo tutorial, sarai in grado di unire le celle orizzontalmente nelle tabelle di Word a livello di programmazione.

## Passaggio 1: impostazione del progetto
1. Avvia Visual Studio e crea un nuovo progetto C#.
2. Aggiungere un riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento e inizializzazione del generatore di documenti
Per iniziare a lavorare con la tabella e le celle, dobbiamo creare un nuovo documento e inizializzare il generatore di documenti. Segui questi passi:

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e inizializzare il generatore di documenti
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assicurati di sostituire "LA TUA DIRECTORY DEI DOCUMENTI" con il percorso effettivo della tua directory dei documenti.

## Passaggio 3: creazione della tabella con l'unione orizzontale delle celle
Successivamente, creeremo la tabella e applicheremo l'unione di celle orizzontali utilizzando le proprietà fornite da Aspose.Words per .NET. Usa il seguente codice:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Questa cella è unita alla precedente e dovrebbe essere vuota.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Qui usiamo il generatore di documenti per costruire la tabella e impostare le proprietà di unione orizzontale delle celle. Noi usiamo il`HorizontalMerge` proprietà del`CellFormat` oggetto per specificare il tipo di unione orizzontale da applicare a ciascuna cella. Usando`CellMerge.First` uniamo la prima cella con quella successiva, durante l'utilizzo`CellMerge.Previous` uniamo la cella corrente con la cella precedente.`CellMerge.None` indica che la cella non deve essere unita.

## Passaggio 4: salvare il documento modificato
Infine, dobbiamo salvare il documento modificato con le celle unite orizzontalmente. Usa il seguente codice:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Assicurati di specificare il percorso e il nome file corretti per il documento di output.

### Codice sorgente di esempio per l'unione orizzontale utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Questa cella è unita alla precedente e dovrebbe essere vuota.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come unire orizzontalmente le celle in una tabella in un documento di Word utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata e implementando il codice C# fornito, è possibile applicare l'unione di celle orizzontali nelle tabelle di Word a livello di codice. Questa funzione ti consente di creare layout di tabella più complessi e di organizzare meglio i tuoi dati.