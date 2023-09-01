---
title: Ottieni la distanza tra il testo circostante la tabella
linktitle: Ottieni la distanza tra il testo circostante la tabella
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per ottenere la distanza tra il testo e una tabella in un documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

In questo tutorial ti guideremo attraverso il processo passo passo per ottenere la distanza tra il testo circostante in una tabella utilizzando Aspose.Words per .NET. Spiegheremo il codice sorgente C# in bundle e ti forniremo una guida completa per aiutarti a comprendere e implementare questa funzionalità nei tuoi progetti. Alla fine di questo tutorial, saprai come accedere alle varie distanze tra una tabella e il testo circostante nei tuoi documenti Word utilizzando Aspose.Words per .NET.

## Passaggio 1: definire la directory dei documenti
Innanzitutto, devi impostare il percorso della directory dei documenti. Qui è dove si trova il tuo documento Word. Sostituisci "DIRECTORY DOCUMENTI" con il percorso appropriato.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: carica il documento esistente
 Successivamente, è necessario caricare il documento Word esistente in un'istanza del file`Document` classe.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Passaggio 3: ottieni la distanza tra la tabella e il testo circostante
 Per ottenere la distanza tra la tabella e il testo circostante, dobbiamo accedere alla tabella nel documento utilizzando il comando`GetChild()` metodo e il`NodeType.Table` proprietà. Possiamo quindi visualizzare le diverse distanze utilizzando le proprietà dell'array`DistanceTop`, `DistanceBottom`, `DistanceRight` E`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Codice sorgente di esempio per ottenere la distanza tra la tabella che circonda il testo utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Conclusione
In questo tutorial, abbiamo imparato come ottenere la distanza tra il testo circostante in una tabella utilizzando Aspose.Words per .NET. Seguendo questa guida passo passo, puoi accedere facilmente alle varie distanze tra una tabella e il testo circostante nei tuoi documenti Word. Aspose.Words offre un'API potente e flessibile per manipolare e formattare le tabelle nei tuoi documenti. Con questa conoscenza potrai analizzare la disposizione delle tue tabelle in relazione al testo e soddisfare esigenze specifiche.