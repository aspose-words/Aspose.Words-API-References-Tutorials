---
title: Impostare le opzioni predefinite per le etichette dei dati in un grafico
linktitle: Impostare le opzioni predefinite per le etichette dei dati in un grafico
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come impostare le opzioni predefinite per le etichette dei dati in un grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/default-options-for-data-labels/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per impostare le opzioni predefinite per le etichette dati in un grafico. Il codice fornito mostra come creare un grafico, aggiungere serie di dati e personalizzare le etichette dei dati utilizzando Aspose.Words.

## Passaggio 1: impostare il progetto

Prima di iniziare, assicurati di disporre dei seguenti requisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo utilizzando il gestore pacchetti NuGet per installarlo.
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

 Possiamo quindi modificare varie proprietà del file`labels`oggetto per impostare le opzioni desiderate per le etichette dei dati. In questo esempio, abiliteremo la visualizzazione della percentuale e del valore, disabiliteremo le linee guida e imposteremo un separatore personalizzato.

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
	//Percorso della directory dei documenti
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

## Conclusione

In questo tutorial, hai imparato come impostare le opzioni predefinite per le etichette dei dati in un grafico utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata, puoi creare un grafico, aggiungere serie di dati e personalizzare le etichette dei dati per soddisfare i tuoi requisiti specifici. Aspose.Words per .NET fornisce una potente API per l'elaborazione di testi con grafici nei documenti Word, consentendo di manipolare vari elementi del grafico e ottenere l'aspetto e la funzionalità desiderati.

 Impostando le proprietà del file`ChartDataLabelCollection`oggetto associato alla serie del grafico, è possibile controllare la visualizzazione delle etichette dei dati, comprese opzioni quali la visualizzazione di percentuali, valori, linee direttrici e separatori personalizzati. Questa flessibilità consente di presentare i dati in modo efficace e di migliorare la rappresentazione visiva dei grafici.

### Domande frequenti

#### Q1. Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una libreria che consente agli sviluppatori di creare, manipolare e salvare documenti Word in modo programmatico utilizzando applicazioni .NET. Fornisce una vasta gamma di funzionalità per l'elaborazione di testi con elementi del documento, inclusi i grafici.

#### D2. Come posso installare Aspose.Words per .NET?
È possibile installare Aspose.Words per .NET scaricandolo tramite Gestione pacchetti NuGet in Visual Studio. Cerca semplicemente "Aspose.Words" nel gestore pacchetti NuGet e installalo nel tuo progetto.

#### D3. Posso personalizzare altri aspetti del grafico utilizzando Aspose.Words per .NET?
Sì, Aspose.Words per .NET ti consente di personalizzare vari aspetti di un grafico, come il tipo di grafico, le etichette degli assi, la legenda, l'area del grafico e altro. È possibile accedere e modificare diverse proprietà dell'oggetto grafico per ottenere l'aspetto e il comportamento desiderati.

#### D4. Posso salvare il grafico in diversi formati?
 Sì, Aspose.Words per .NET supporta il salvataggio del documento contenente il grafico in vari formati, inclusi DOCX, PDF, HTML e altro. È possibile scegliere il formato appropriato in base alle proprie esigenze e utilizzare il file`Save` metodo del`Document` oggetto per salvare il documento.

#### Q5. Posso applicare queste tecniche ad altri tipi di grafici?
Sì, le tecniche descritte in questo tutorial possono essere applicate ad altri tipi di grafici supportati da Aspose.Words per .NET. La chiave è accedere agli oggetti e alle proprietà pertinenti specifici del tipo di grafico con cui stai elaborando le parole.