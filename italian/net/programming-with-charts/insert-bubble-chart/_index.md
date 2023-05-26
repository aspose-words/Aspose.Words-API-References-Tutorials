---
title: Inserisci grafico a bolle
linktitle: Inserisci grafico a bolle
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire un grafico a bolle in un documento utilizzando Aspose.Words per .NET. Aggiungi i dati della serie con i valori X, Y e delle dimensioni delle bolle.
type: docs
weight: 10
url: /it/net/programming-with-charts/insert-bubble-chart/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per inserire un grafico a bolle in un documento. Il codice sorgente fornito mostra come creare un grafico, aggiungere dati di serie e salvare il documento.

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

 Quindi, usa il`InsertChart` metodo del`DocumentBuilder` per inserire un grafico a bolle nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio, aggiungeremo tre punti dati con i corrispondenti valori X, Y e dimensione della bolla.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Passaggio 4: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

Questo completa l'implementazione dell'inserimento di un grafico a bolle utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Inserisci grafico a bolle utilizzando Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```