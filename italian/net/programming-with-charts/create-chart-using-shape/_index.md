---
title: Crea grafico usando la forma
linktitle: Crea grafico usando la forma
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare e personalizzare un grafico utilizzando una forma in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/create-chart-using-shape/
---

Questo tutorial spiega come creare un grafico utilizzando una forma in un documento di Word utilizzando Aspose.Words per .NET.

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

## Passaggio 3: inserire e configurare una forma del grafico
 Inserisci una forma di grafico nel documento usando il`InsertChart` metodo del`DocumentBuilder` oggetto. Impostare il tipo e le dimensioni del grafico desiderati.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 4: personalizza il grafico
Personalizza il grafico modificando varie proprietà come il titolo e la legenda del grafico.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Passaggio 5: salvare il documento
 Salvare il documento nella directory specificata utilizzando il file`Save`metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Esempio di codice sorgente per Crea grafico utilizzando la forma utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Si noti che se viene specificato un valore nullo o vuoto come testo del titolo, verrà mostrato il titolo generato automaticamente.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Questo è tutto! Hai creato correttamente un grafico utilizzando una forma in un documento di Word utilizzando Aspose.Words per .NET.