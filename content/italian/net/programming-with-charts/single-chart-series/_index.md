---
title: Personalizza serie di grafici singoli in un grafico
linktitle: Personalizza serie di grafici singoli in un grafico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come personalizzare singole serie di grafici in un grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/single-chart-series/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per personalizzare singole serie di grafici in un grafico. Il codice sorgente fornito dimostra come creare un grafico, accedere a serie specifiche e modificarne le proprietà.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. È possibile scaricarlo utilizzando Gestione pacchetti NuGet per installarlo.
- Un percorso della directory del documento in cui verrà salvato il documento di output.

## Passaggio 2: crea un nuovo documento e inserisci un grafico.

 Creane uno nuovo`Document` oggetto e a`DocumentBuilder` per costruire il documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Successivamente, utilizzare il`InsertChart` metodo del`DocumentBuilder` per inserire un grafico a linee nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: accedi e personalizza le serie di grafici

 Per modificare singole serie di grafici è necessario accedere al file`ChartSeries` oggetti della carta.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Passaggio 4: salva il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Ciò completa l'implementazione della personalizzazione di una singola serie di grafici utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per serie di grafici singoli utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// È inoltre possibile specificare se la linea che collega i punti sul grafico deve essere smussata utilizzando le spline Catmull-Rom.
	series0.Smooth = true;
	series1.Smooth = true;
	// Specifica se per impostazione predefinita l'elemento genitore deve invertire i suoi colori se il valore è negativo.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Conclusione

In questo tutorial, hai imparato come personalizzare una singola serie di grafici in un grafico utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, puoi creare un nuovo documento, inserire un grafico a linee, accedere a serie di grafici specifici e modificare le loro proprietà per ottenere la personalizzazione desiderata.

Aspose.Words per .NET fornisce potenti funzionalità per manipolare i grafici nei documenti Word. Accedendo alle singole serie di grafici, è possibile applicare modifiche specifiche per personalizzarne l'aspetto e il comportamento. Ciò ti consente di modificare il nome della serie, abilitare lo smussamento della linea del grafico, personalizzare gli indicatori per i punti dati, invertire i colori per i valori negativi e altro ancora per migliorare la rappresentazione visiva del tuo grafico.

La personalizzazione di una singola serie di grafici ti offre la flessibilità di evidenziare dati specifici o enfatizzare tendenze particolari all'interno del tuo grafico. Con Aspose.Words per .NET, puoi accedere e modificare facilmente le proprietà delle serie di grafici, consentendoti di creare grafici visivamente accattivanti e informativi nei tuoi documenti Word.

### Domande frequenti

#### Q1. Posso personalizzare più serie di grafici in un grafico?
 Sì, puoi personalizzare più serie di grafici in un grafico utilizzando Aspose.Words per .NET. Accedendo al`ChartSeries`oggetti all'interno del grafico, è possibile selezionare e modificare più serie in base ai relativi indici o criteri specifici. Utilizzare un ciclo o assegnazioni individuali per modificare le proprietà desiderate per ciascuna serie di grafici. In questo modo, puoi applicare personalizzazioni diverse a più serie all'interno dello stesso grafico.

#### Q2. Come posso cambiare il nome di una serie di grafici?
 Per modificare il nome di una serie di grafici in un grafico utilizzando Aspose.Words per .NET, è necessario accedere a`Name` proprietà del`ChartSeries` oggetto e impostarlo con il nome desiderato. Il nome della serie viene in genere visualizzato nella legenda del grafico o nelle etichette dei dati, fornendo un'etichetta descrittiva per la serie. Modificando il nome della serie, puoi fornire nomi significativi che riflettono i dati rappresentati da ciascuna serie.

#### Q3. Cos'è lo smoothing delle serie di grafici?
Lo smussamento delle serie di grafici è una tecnica di miglioramento visivo che consente di creare una linea uniforme che collega i punti sul grafico. Applica un algoritmo di livellamento, come le spline Catmull-Rom, per interpolare tra i punti dati e creare una curva visivamente gradevole. Per abilitare il livellamento delle serie in un grafico utilizzando Aspose.Words per .NET, accedi a`Smooth` proprietà del`ChartSeries` oggetto e impostarlo su`true`. Lo smussamento può essere utile per visualizzare tendenze o modelli nei dati con fluttuazioni irregolari.

#### Q4. Come posso personalizzare gli indicatori per i punti dati in una serie di grafici?
 Per personalizzare gli indicatori per i punti dati in una serie di grafici utilizzando Aspose.Words per .NET, è necessario accedere a`Marker` proprietà del`ChartSeries` oggetto e modificarne le proprietà come`Symbol` E`Size`. I marcatori sono indicatori visivi posizionati sul grafico per rappresentare singoli punti dati. Puoi scegliere tra una varietà di simboli indicatore incorporati e regolarne le dimensioni per evidenziare o differenziare punti dati specifici all'interno della serie.

#### Q5. Posso invertire i colori per i valori negativi in una serie di grafici?
 Sì, puoi invertire i colori per i valori negativi in una serie di grafici utilizzando Aspose.Words per .NET. Impostando il`InvertIfNegative` proprietà del`ChartSeries` opporsi a`true`, i colori per i punti dati con valori negativi verranno invertiti, rendendoli visivamente distinti dai valori positivi. Questa funzionalità può essere utile quando si confrontano valori positivi e negativi in una serie di grafici, fornendo una chiara differenziazione tra i due.