---
title: Nascondi asse grafico
linktitle: Nascondi asse grafico
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come nascondere l'asse del grafico in un documento utilizzando Aspose.Words per .NET. Nascondi l'asse per una visualizzazione del grafico più chiara e mirata.
type: docs
weight: 10
url: /it/net/programming-with-charts/hide-chart-axis/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per nascondere l'asse del grafico in un documento. Il codice sorgente fornito mostra come creare un grafico, aggiungere dati di serie e nascondere l'asse del grafico.

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

 Successivamente, inserisci un grafico nel documento utilizzando il file`InsertChart` metodo del`DocumentBuilder`. In questo esempio, inseriremo un istogramma.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio, aggiungeremo cinque elementi ei loro valori corrispondenti.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Passaggio 4: nascondi l'asse del grafico

 Per nascondere l'asse del grafico, accedere a`AxisY` proprietà del grafico e impostare la`Hidden` proprietà a`true`.

```csharp
chart.AxisY.Hidden = true;
```

In questo esempio, nascondiamo l'asse Y del grafico.

## Passaggio 5: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Questo completa l'implementazione di nascondere l'asse del grafico utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per nascondere l'asse del grafico utilizzando Aspose.Words per .NET 

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
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```