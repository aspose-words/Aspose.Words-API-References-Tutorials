---
title: Formato numero di etichetta dati
linktitle: Formato numero di etichetta dati
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come formattare il numero di etichette dati in un grafico utilizzando Aspose.Words per .NET. Personalizza facilmente i formati numerici per le etichette dei dati.
type: docs
weight: 10
url: /it/net/programming-with-charts/format-number-of-data-label/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per formattare il numero di etichette dati in un grafico. Il codice sorgente fornito mostra come creare un grafico, aggiungere dati di serie e personalizzare il formato numerico delle etichette dei dati.

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

 Successivamente, inserisci un grafico nel documento utilizzando il file`InsertChart` metodo del`DocumentBuilder`In questo esempio, inseriremo un grafico a linee.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio, aggiungeremo tre categorie e i valori corrispondenti.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Passaggio 4: personalizzare il formato numerico delle etichette dei dati

 Per formattare il numero di etichette dati, accedere a`DataLabels` raccolta associata alla serie.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

In questo esempio, impostiamo diversi formati numerici per ciascuna etichetta dati. La prima etichetta dati è formattata come valuta, la seconda come data e la terza come percentuale.

## Passaggio 5: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Questo completa l'implementazione della formattazione del numero di etichette dati in un grafico utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Format Number Of Data Label utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Elimina le serie generate di default.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Oppure puoi impostare il codice del formato in modo che sia collegato a una cella di origine,
	// in questo caso NumberFormat verrà reimpostato su generale ed ereditato da una cella di origine.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```