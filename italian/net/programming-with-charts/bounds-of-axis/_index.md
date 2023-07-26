---
title: Limiti dell'asse in un grafico
linktitle: Limiti dell'asse in un grafico
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come impostare i limiti di un asse in un grafico utilizzando Aspose.Words per .NET controllando l'intervallo di valori visualizzati sull'asse.
type: docs
weight: 10
url: /it/net/programming-with-charts/bounds-of-axis/
---

Questo tutorial spiega come impostare i limiti di un asse in un grafico utilizzando Aspose.Words per .NET. Inserendo un grafico, aggiungendo dati di serie e configurando il ridimensionamento dell'asse, è possibile definire i valori minimo e massimo per l'asse.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e Word Processing con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si desidera salvare il documento.

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 4: aggiungere i dati della serie
Cancella tutte le serie esistenti nel grafico e aggiungi nuovi dati di serie. In questo esempio, aggiungiamo una serie con le etichette "Articolo 1" a "Articolo 5" e i valori corrispondenti.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Passaggio 5: impostare i limiti dell'asse
 Configurare il ridimensionamento dell'asse Y impostando i valori minimo e massimo utilizzando il`Scaling.Minimum` E`Scaling.Maximum` proprietà dell'asse

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Passaggio 6: salvare il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Esempio di codice sorgente per Bounds Of Axis utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Questo è tutto! Hai impostato correttamente i limiti di un asse in un grafico utilizzando Aspose.Words per .NET.

## Conclusione
In questo tutorial, hai imparato come impostare i limiti di un asse in un grafico utilizzando Aspose.Words per .NET. Seguendo la guida passo-passo, puoi inserire e configurare un grafico, aggiungere dati di serie e definire i valori minimo e massimo per il ridimensionamento dell'asse. Aspose.Words per .NET fornisce un'API potente e flessibile per l'elaborazione di testi con documenti Word, che consente di creare grafici dinamici e visivamente accattivanti con facilità.


### Domande frequenti

#### Q1. Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una libreria che consente agli sviluppatori di lavorare con i documenti di Word a livello di codice. Fornisce una vasta gamma di caratteristiche e funzionalità per la creazione, la manipolazione e il salvataggio di documenti Word.

#### D2. Come posso installare Aspose.Words per .NET?
Per installare Aspose.Words per .NET, puoi usare NuGet Package Manager in Visual Studio. Cerca semplicemente "Aspose.Words" nel gestore pacchetti NuGet e installalo nel tuo progetto.

#### D3. Posso usare Aspose.Words per .NET con altri linguaggi di programmazione?
No, Aspose.Words per .NET è specificamente progettato per le applicazioni .NET. Funziona con linguaggi di programmazione come C# e VB.NET.

#### D4. Esistono altri prerequisiti per l'utilizzo di Aspose.Words per .NET?
Oltre all'installazione della libreria Aspose.Words per .NET, è necessario disporre di una conoscenza di base della programmazione C# e dell'elaborazione di testi con documenti Word. Sarà utile anche la familiarità con il framework .NET.
