---
title: Limiti dell'asse
linktitle: Limiti dell'asse
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare i limiti di un asse in un grafico utilizzando Aspose.Words per .NET controllando l'intervallo di valori visualizzati sull'asse.
type: docs
weight: 10
url: /it/net/programming-with-charts/bounds-of-axis/
---

Questo tutorial spiega come impostare i limiti di un asse in un grafico utilizzando Aspose.Words per .NET. Inserendo un grafico, aggiungendo dati di serie e configurando il ridimensionamento dell'asse, è possibile definire i valori minimo e massimo per l'asse.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e lavoro con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"`con il percorso effettivo della directory in cui si desidera salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un nuovo documento e DocumentBuilder
 Crea una nuova istanza di`Document` classe e a`DocumentBuilder` opporsi a lavorare con il documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire e configurare un grafico
 Inserire un grafico nel documento utilizzando il file`InsertChart` metodo del`DocumentBuilder` oggetto. Impostare il tipo e le dimensioni del grafico desiderati.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 4: aggiungere i dati della serie
Cancella tutte le serie esistenti nel grafico e aggiungi nuovi dati di serie. In questo esempio, aggiungiamo una serie con le etichette "Articolo 1" a "Articolo 5" e i valori corrispondenti.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Passaggio 5: impostare i limiti dell'asse
 Configurare il ridimensionamento dell'asse Y impostando i valori minimo e massimo utilizzando il`Scaling.Minimum` E`Scaling.Maximum` proprietà dell'asse

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Passaggio 6: salvare il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Esempio di codice sorgente per Bounds Of Axis utilizzando Aspose.Words per .NET 

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
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Questo è tutto! Hai impostato correttamente i limiti di un asse in un grafico utilizzando Aspose.Words per .NET.