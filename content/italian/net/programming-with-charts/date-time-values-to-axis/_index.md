---
title: Aggiungi valori di data e ora all'asse di un grafico
linktitle: Aggiungi valori di data e ora all'asse di un grafico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere valori di data e ora all'asse di un grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/date-time-values-to-axis/
---

Questo tutorial spiega come aggiungere valori di data e ora all'asse di un grafico utilizzando Aspose.Words per .NET.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# ed elaborazione testi con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui desideri salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: crea un nuovo documento e DocumentBuilder
 Crea una nuova istanza di`Document` classe e a`DocumentBuilder` oggetto di lavorare con il documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserisci e configura una forma grafico
 Inserisci una forma grafico nel documento utilizzando il comando`InsertChart` metodo del`DocumentBuilder` oggetto. Imposta il tipo di grafico e le dimensioni desiderate.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Passaggio 4: aggiungi dati al grafico
Aggiungi dati alle serie di grafici, inclusi i valori di data e ora.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Passaggio 5: configurare l'asse
Configurare l'asse X del grafico per visualizzare i valori di data e ora.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Passaggio 6: salva il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Codice sorgente di esempio per Date Time Values To Axis utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Imposta le unità principali su una settimana e le unità minori su un giorno.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Questo codice di esempio crea un nuovo documento di Word, inserisce un istogramma con valori di data e ora sull'asse X e salva il documento nella directory specificata.

## Conclusione
In questo tutorial, hai imparato come aggiungere valori di data e ora all'asse di un grafico utilizzando Aspose.Words per .NET. Seguendo la guida passo passo, puoi creare un grafico, aggiungere valori di data e ora alla serie e configurare l'asse per visualizzare i valori di data e ora in modo accurato. Aspose.Words per .NET fornisce un potente set di funzionalità per l'elaborazione di parole con grafici nei documenti Word, consentendo di rappresentare e visualizzare i dati con valori di data e ora in modo efficace.

### Domande frequenti

#### Q1. Posso aggiungere valori di data e ora all'asse di un grafico utilizzando Aspose.Words per .NET?
Sì, con Aspose.Words per .NET, puoi aggiungere e visualizzare valori di data e ora sull'asse di un grafico in un documento Word. Aspose.Words fornisce API e funzionalità per lavorare con vari tipi di grafici e personalizzarne l'aspetto, inclusa la gestione dei valori di data e ora sull'asse.

#### Q2. Come posso aggiungere valori di data e ora alle serie di grafici?
 Per aggiungere valori di data e ora alle serie di grafici, è possibile utilizzare il comando`Add`metodo delle serie del grafico. Fornire una matrice di valori di data e ora come dati della categoria (asse X), insieme ai valori della serie corrispondente. Ciò consente di tracciare punti dati con valori di data e ora sul grafico.

#### Q3. Come posso configurare l'asse per visualizzare i valori di data e ora?
 È possibile configurare l'asse del grafico per visualizzare i valori di data e ora impostando le proprietà appropriate. Ad esempio, è possibile specificare i valori minimo e massimo per l'asse utilizzando il comando`Scaling.Minimum` E`Scaling.Maximum` proprietà, rispettivamente. Inoltre, è possibile impostare le unità maggiori e minori per definire l'intervallo e i segni di graduazione per l'asse.
