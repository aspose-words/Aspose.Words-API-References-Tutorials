---
title: Opzioni predefinite per le etichette dati
linktitle: Opzioni predefinite per le etichette dati
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come impostare le opzioni predefinite per le etichette dei dati in un grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/default-options-for-data-labels/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per impostare le opzioni predefinite per le etichette dati in un grafico. Il codice fornito mostra come creare un grafico, aggiungere serie di dati e personalizzare le etichette dei dati utilizzando Aspose.Words.

## Passaggio 1: impostare il progetto

Prima di iniziare, assicurati di disporre dei seguenti requisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare il gestore di pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui verrà salvato il documento di output.

## Passaggio 2: crea un nuovo documento e inserisci un grafico

 Per prima cosa, creiamo un nuovo`Document` oggetto e a`DocumentBuilder` per costruire il documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Successivamente, inseriamo un grafico nel documento utilizzando il file`InsertChart` metodo del`DocumentBuilder`. In questo esempio, inseriremo un grafico a torta.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi serie di dati al grafico

Ora, aggiungiamo una serie di dati al grafico. In questo esempio, aggiungeremo tre categorie e i valori corrispondenti.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Passaggio 4: personalizzare le etichette dei dati

 Per personalizzare le etichette dei dati nel grafico, dobbiamo accedere al file`ChartDataLabelCollection` oggetto associato alla serie.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Possiamo quindi modificare varie proprietà del file`labels` oggetto per impostare le opzioni desiderate per le etichette dei dati. In questo esempio, abiliteremo la visualizzazione della percentuale e del valore, disabiliteremo le linee guida e imposteremo un separatore personalizzato.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Passaggio 5: salvare il documento

 Infine, salviamo il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Questo completa l'implementazione dell'impostazione delle opzioni predefinite per le etichette dei dati in un grafico utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per le opzioni predefinite per le etichette dati utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```