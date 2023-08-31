---
title: Formato Numero Di Etichetta Dati In Un Grafico
linktitle: Formato Numero Di Etichetta Dati In Un Grafico
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come formattare il numero di etichette dati in un grafico utilizzando Aspose.Words per .NET. Personalizza facilmente i formati numerici per le etichette dei dati.
type: docs
weight: 10
url: /it/net/programming-with-charts/format-number-of-data-label/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per formattare il numero di etichette dati in un grafico. Il codice sorgente fornito mostra come creare un grafico, aggiungere dati di serie e personalizzare il formato numerico delle etichette dei dati.

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

 Successivamente, inserisci un grafico nel documento utilizzando il file`InsertChart` metodo del`DocumentBuilder`. In questo esempio, inseriremo un grafico a linee.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio, aggiungeremo tre categorie e i valori corrispondenti.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Passaggio 4: personalizzare il formato numerico delle etichette dei dati

 Per formattare il numero di etichette dati, accedere a`DataLabels` raccolta associata alla serie.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

In questo esempio, impostiamo diversi formati numerici per ciascuna etichetta dati. La prima etichetta dati è formattata come valuta, la seconda come data e la terza come percentuale.

## Passaggio 5: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Questo completa l'implementazione della formattazione del numero di etichette dati in un grafico utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Format Number Of Data Label utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Elimina le serie generate di default.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// Oppure puoi impostare il codice del formato in modo che sia collegato a una cella di origine,
	// in questo caso NumberFormat verrà reimpostato su generale ed ereditato da una cella di origine.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Conclusione

In questo tutorial, hai imparato come formattare il numero di etichette dati in un grafico utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata e utilizzando il codice sorgente fornito, è possibile creare un grafico, aggiungere dati di serie e personalizzare il formato numerico delle etichette dei dati in base alle proprie esigenze.

 Aspose.Words per .NET fornisce un'API completa per l'elaborazione di parole con grafici nei documenti di Word, consentendo di manipolare vari aspetti del grafico, comprese le etichette dei dati. Accedendo al`DataLabels` raccolta associata a una serie, è possibile personalizzare il formato numerico delle singole etichette dati.

L'API consente di controllare la visualizzazione dei valori, impostare diversi formati numerici per ciascuna etichetta dati e collegare il formato numerico a una cella di origine. Questa flessibilità consente di presentare dati numerici nei grafici con la formattazione desiderata, ad esempio simboli di valuta, formati di data e valori percentuali.

Utilizzando Aspose.Words per .NET, puoi incorporare potenti funzionalità di creazione di grafici nelle tue applicazioni .NET e generare documenti dall'aspetto professionale con grafici ed etichette dati completamente formattati.

### Domande frequenti

#### Q1. Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una libreria di elaborazione documenti ricca di funzionalità che consente agli sviluppatori di creare, manipolare e salvare documenti Word a livello di codice nelle applicazioni .NET. Fornisce una vasta gamma di funzionalità per l'elaborazione di testi con elementi del documento, inclusi grafici ed etichette di dati.

#### D2. Come posso installare Aspose.Words per .NET?
È possibile installare Aspose.Words per .NET scaricandolo tramite il gestore pacchetti NuGet in Visual Studio. Cerca semplicemente "Aspose.Words" nel gestore pacchetti NuGet e installalo nel tuo progetto.

#### D3. Posso formattare altri aspetti del grafico utilizzando Aspose.Words per .NET?
Sì, Aspose.Words per .NET offre funzionalità estese per la formattazione di vari aspetti di un grafico. Oltre alle etichette dei dati, puoi personalizzare il tipo di grafico, i dati della serie, le proprietà degli assi, la legenda, il titolo, l'area del tracciato e molti altri elementi del grafico. L'API offre un controllo granulare sull'aspetto e la formattazione del grafico.

#### D4. Posso applicare formati numerici diversi a etichette dati diverse nella stessa serie?
 Sì, Aspose.Words per .NET consente di applicare diversi formati numerici a singole etichette di dati all'interno della stessa serie. Accedendo al`DataLabels` raccolta associata a una serie, è possibile impostare il`FormatCode` proprietà di ciascuna etichetta dati per specificare il formato numerico desiderato. Ciò consente di presentare valori numerici in diversi formati all'interno dello stesso grafico.

#### Q5. Posso utilizzare formati numerici personalizzati per le etichette dati?
 Sì, Aspose.Words per .NET supporta i formati numerici personalizzati per le etichette dei dati. È possibile specificare il formato numerico desiderato impostando il`FormatCode`proprietà di un'etichetta dati a un codice di formato personalizzato. Ciò offre la flessibilità di applicare un'ampia gamma di formati numerici, come simboli di valuta, formati di data, valori percentuali e altro ancora.

#### D6. Posso salvare il grafico con etichette dati formattate in diversi formati?
 Sì, Aspose.Words per .NET ti consente di salvare il documento contenente il grafico con etichette dati formattate in vari formati, come DOCX, PDF, HTML e altro. È possibile scegliere il formato appropriato in base alle proprie esigenze e utilizzare il file`Save` metodo del`Document` oggetto per salvare il documento. Le etichette dati formattate verranno mantenute nel documento salvato.