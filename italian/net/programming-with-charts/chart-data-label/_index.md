---
title: Etichetta dati grafico
linktitle: Etichetta dati grafico
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come aggiungere e personalizzare le etichette dei dati in un grafico utilizzando Aspose.Words per .NET per fornire ulteriori informazioni sui punti dati.
type: docs
weight: 10
url: /it/net/programming-with-charts/chart-data-label/
---

Questo tutorial spiega come aggiungere e personalizzare le etichette dei dati in un grafico utilizzando Aspose.Words per .NET. Le etichette dati forniscono informazioni aggiuntive sui punti dati in un grafico.

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
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 4: personalizzare le etichette dei dati
Accedi alla raccolta di etichette dati della serie di grafici e modifica varie proprietà per personalizzare l'aspetto delle etichette dati.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Passaggio 5: salvare il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Codice sorgente di esempio per l'etichetta dei dati del grafico utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	//Per impostazione predefinita, quando aggiungi etichette dati ai punti dati in un grafico a torta, le linee guida vengono visualizzate per le etichette dati che lo sono
	// posizionato molto al di fuori della fine dei punti dati. Le linee guida creano una connessione visiva tra un'etichetta dati e la sua
	// punto dati corrispondente.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

Questo è tutto! Hai aggiunto e personalizzato correttamente le etichette dei dati in un grafico utilizzando Aspose.Words per .NET.