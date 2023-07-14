---
title: Personalizza un singolo punto dati del grafico in un grafico
linktitle: Personalizza un singolo punto dati del grafico in un grafico
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come personalizzare un singolo punto dati in un grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/single-chart-data-point/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per personalizzare un singolo punto dati in un grafico. Il codice sorgente fornito mostra come creare un grafico, accedere a punti dati specifici e modificarne le proprietà.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo utilizzando il gestore pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui verrà salvato il documento di output.

## Passaggio 2: crea un nuovo documento e inserisci un grafico

 Crea un nuovo`Document` oggetto e a`DocumentBuilder` per costruire il documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Quindi, usa il`InsertChart` metodo del`DocumentBuilder` per inserire un grafico a linee nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: accedi e personalizza i punti dati

 Per modificare i singoli punti dati, è necessario accedere al file`ChartDataPointCollection` della serie e selezionare il punto dati desiderato utilizzando l'indice.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Passaggio 4: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

Questo completa l'implementazione della personalizzazione di un singolo punto dati in un grafico utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per punto dati grafico singolo utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Conclusione

In questo tutorial, hai imparato a personalizzare un singolo punto dati in un grafico utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, è possibile creare un nuovo documento, inserire un grafico a linee, accedere a punti dati specifici all'interno della serie di grafici e modificarne le proprietà per ottenere la personalizzazione desiderata.

Aspose.Words per .NET fornisce potenti funzionalità per manipolare i grafici nei documenti di Word. Accedendo ai singoli punti dati all'interno di una serie di grafici, è possibile applicare modifiche specifiche per personalizzarne l'aspetto e il comportamento. Ciò consente di evidenziare punti dati specifici, modificare i simboli degli indicatori, regolare le dimensioni degli indicatori e altro ancora, per migliorare la rappresentazione visiva del grafico.

La personalizzazione dei singoli punti dati ti offre la flessibilità di enfatizzare dati importanti o evidenziare tendenze specifiche nel tuo grafico. Con Aspose.Words per .NET, puoi facilmente accedere e modificare i punti dati in vari tipi di grafici, consentendoti di creare grafici visivamente accattivanti e informativi nei tuoi documenti Word.

### Domande frequenti

#### Q1. Posso personalizzare più punti dati in un grafico?
 Sì, puoi personalizzare più punti dati in un grafico utilizzando Aspose.Words per .NET. Accedendo al`ChartDataPointCollection`di una serie, è possibile selezionare e modificare più punti dati in base ai relativi indici. Utilizzare un loop o singole assegnazioni per modificare le proprietà desiderate per ogni punto dati. In questo modo, puoi applicare personalizzazioni diverse a più punti dati all'interno dello stesso grafico.

#### D2. Come posso cambiare il simbolo dell'indicatore per un punto dati?
 Per modificare il simbolo dell'indicatore per un punto dati in un grafico utilizzando Aspose.Words per .NET, è necessario accedere al`Marker`proprietà del`ChartDataPoint` oggetto e impostare il`Symbol` proprietà al simbolo del marcatore desiderato. I simboli dei marcatori rappresentano la forma o l'icona utilizzata per rappresentare ciascun punto dati sul grafico. Puoi scegliere tra una varietà di simboli di marcatori incorporati come cerchio, quadrato, diamante, triangolo, stella e altro.

#### D3. Posso regolare le dimensioni di un indicatore di punto dati?
 Sì, puoi regolare la dimensione di un indicatore di punto dati in un grafico utilizzando Aspose.Words per .NET. Accedi al`Marker`proprietà del`ChartDataPoint` oggetto e impostare il`Size`proprietà alla dimensione del marker desiderata. La dimensione dell'indicatore è generalmente specificata in punti, dove un valore maggiore rappresenta una dimensione maggiore dell'indicatore. La regolazione della dimensione dell'indicatore consente di enfatizzare punti dati specifici o differenziarli in base al loro significato.

#### D4. Quali altre proprietà posso modificare per un punto dati?
Aspose.Words per .NET fornisce una gamma di proprietà che è possibile modificare per un punto dati in un grafico. Alcune delle proprietà comunemente modificate includono il simbolo del marcatore, la dimensione del marcatore, il colore del marcatore, la visibilità dell'etichetta dati, l'esplosione, l'inversione se negativa e altro ancora. Queste proprietà consentono di personalizzare l'aspetto, il comportamento e l'interattività dei singoli punti dati, consentendo di creare grafici personalizzati in base alle proprie esigenze specifiche.

#### Q5. Posso personalizzare i punti dati in altri tipi di grafici?
Sì, puoi personalizzare i punti dati in vari tipi di grafici utilizzando Aspose.Words per .NET. Mentre questo tutorial dimostra la personalizzazione dei punti dati in un grafico a linee, puoi applicare tecniche simili ad altri tipi di grafici come istogrammi, grafici a barre, grafici a torta e altro ancora. Il processo prevede l'accesso alle serie e ai punti dati all'interno del grafico e la modifica delle relative proprietà di conseguenza.