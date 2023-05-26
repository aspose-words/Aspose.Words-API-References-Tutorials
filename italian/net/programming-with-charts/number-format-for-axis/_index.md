---
title: Formato numerico per asse
linktitle: Formato numerico per asse
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare il formato numerico per un asse in un grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/number-format-for-axis/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per impostare il formato numerico per un asse in un grafico. Il codice sorgente fornito mostra come creare un grafico, aggiungere dati di serie e formattare le etichette degli assi.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare il gestore di pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui verrà salvato il documento di output.

## Passaggio 2: crea un nuovo documento e inserisci un grafico

 Crea un nuovo`Document` oggetto e a`DocumentBuilder` per costruire il documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Quindi, usa il`InsertChart` metodo del`DocumentBuilder` per inserire un istogramma nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio, aggiungeremo cinque elementi con i valori corrispondenti.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Passaggio 4: formattare le etichette degli assi

 Per impostare il formato numerico per le etichette dell'asse Y, accedere a`AxisY` proprietà del grafico e impostare la`NumberFormat.FormatCode` proprietà nel formato desiderato. In questo esempio, impostiamo il formato su "#,##0" per visualizzare i numeri con separatori delle migliaia.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Passaggio 5: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Questo completa l'implementazione dell'impostazione del formato numerico per l'asse utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Number Format For Axis utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```