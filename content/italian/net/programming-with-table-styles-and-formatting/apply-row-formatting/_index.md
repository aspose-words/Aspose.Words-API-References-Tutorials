---
title: Applica la formattazione delle righe
linktitle: Applica la formattazione delle righe
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida passo passo per applicare la formattazione delle righe a una tabella utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

In questo tutorial, ti guideremo attraverso il processo passo dopo passo per applicare la formattazione delle righe a una tabella utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, avrai una chiara comprensione di come formattare le righe della tabella nei tuoi documenti Word usando Aspose.Words per .NET.

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

## Passaggio 3: avvia una nuova scheda
 Per applicare la formattazione delle righe, dobbiamo prima iniziare una nuova tabella utilizzando il file`StartTable()` metodo del costruttore del documento.

```csharp
Table table = builder. StartTable();
```

## Passaggio 4: inserisci la cella e vai al formato riga
Ora possiamo inserire una cella nella tabella e accedere al formato di riga per quella cella utilizzando il generatore di documenti`InsertCell()` E`RowFormat` metodi.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Passaggio 5: impostare l'altezza della riga
 Per impostare l'altezza della riga, usiamo il`Height` E`HeightRule` proprietà del formato riga. In questo esempio, impostiamo un'altezza di riga di 100 punti e utilizziamo il`Exactly` regola.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Passaggio 6: definire la formattazione della tabella
 Alcune proprietà di formattazione possono essere impostate sulla tabella stessa e vengono applicate a tutte le righe della tabella. In questo esempio, impostiamo le proprietà del margine della tabella utilizzando il`LeftPadding`, `RightPadding`, `TopPadding` E`BottomPadding` proprietà.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Passaggio 7: aggiungi contenuto alla riga
Ora possiamo

 Aggiungeremo contenuto alla riga utilizzando i metodi del costruttore di documenti. In questo esempio, usiamo il`Writeln()` metodo per aggiungere testo alla riga.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Passaggio 8: finisci la linea e il tavolo
 Dopo aver aggiunto il contenuto alla riga, possiamo terminare la riga utilizzando il`EndRow()` metodo e quindi terminare la tabella utilizzando il`EndTable()` metodo.

```csharp
builder. EndRow();
builder. EndTable();
```

## Passaggio 9: salvare il documento modificato
Infine, salviamo il documento modificato in un file. È possibile scegliere un nome e una posizione appropriati per il documento di output.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Congratulazioni! Ora hai applicato la formattazione delle righe a una tabella utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Applicare la formattazione delle righe utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Conclusione
In questo tutorial, abbiamo imparato come applicare la formattazione delle righe a una tabella utilizzando Aspose.Words per .NET. Seguendo questa guida dettagliata, puoi facilmente integrare questa funzionalità nei tuoi progetti C#. La manipolazione della formattazione delle righe della tabella è un aspetto essenziale dell'elaborazione dei documenti e Aspose.Words offre un'API potente e flessibile per raggiungere questo obiettivo. Con questa conoscenza, puoi migliorare la presentazione visiva dei tuoi documenti Word e soddisfare requisiti specifici.