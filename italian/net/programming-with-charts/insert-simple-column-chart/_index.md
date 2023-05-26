---
title: Inserisci grafico a colonne semplice
linktitle: Inserisci grafico a colonne semplice
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un semplice istogramma in un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/insert-simple-column-chart/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per inserire un semplice istogramma in un documento. Il codice sorgente fornito mostra come creare un grafico, aggiungere dati di serie e salvare il documento.

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

 Quindi, usa il`InsertChart` metodo del`DocumentBuilder` per inserire un istogramma nel documento. È possibile specificare diversi tipi e dimensioni di grafici in base alle proprie esigenze.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio, aggiungeremo più serie con due categorie ciascuna.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Passaggio 4: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Questo completa l'implementazione dell'inserimento di un semplice istogramma utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Inserisci grafico a colonne semplice utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// È possibile specificare diversi tipi e dimensioni di grafici.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Elimina le serie generate di default.
	seriesColl.Clear();
	// Crea un array di nomi di categoria, in questo tutorial abbiamo due categorie.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Si noti che gli array di dati non devono essere vuoti e gli array devono avere le stesse dimensioni.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```