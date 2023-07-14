---
title: Crea e personalizza il grafico utilizzando la forma
linktitle: Crea e personalizza il grafico utilizzando la forma
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come creare e personalizzare un grafico utilizzando una forma in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/create-chart-using-shape/
---

Questo tutorial spiega come creare un grafico utilizzando una forma in un documento di Word utilizzando Aspose.Words per .NET.

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

## Passaggio 3: inserire e configurare una forma del grafico
 Inserisci una forma di grafico nel documento usando il`InsertChart` metodo del`DocumentBuilder` oggetto. Impostare il tipo e le dimensioni del grafico desiderati.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 4: personalizza il grafico
Personalizza il grafico modificando varie proprietà come il titolo e la legenda del grafico.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Passaggio 5: salvare il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Esempio di codice sorgente per Crea grafico utilizzando la forma utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Si noti che se viene specificato un valore nullo o vuoto come testo del titolo, verrà mostrato il titolo generato automaticamente.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

Questo è tutto! Hai creato correttamente un grafico utilizzando una forma in un documento di Word utilizzando Aspose.Words per .NET.

## Conclusione
In questo tutorial, hai imparato come creare un grafico utilizzando una forma in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida passo-passo, puoi inserire e configurare una forma del grafico, personalizzarne l'aspetto e salvare il documento. Aspose.Words per .NET offre un set completo di funzionalità per l'elaborazione di testi con documenti e grafici Word, consentendoti di creare grafici dall'aspetto professionale e visivamente accattivanti direttamente nelle tue applicazioni .NET.

### Domande frequenti

#### Q1. Posso creare grafici in un documento Word utilizzando Aspose.Words per .NET?
Sì, con Aspose.Words per .NET, puoi creare grafici in un documento Word a livello di programmazione. Aspose.Words fornisce API e funzionalità per inserire vari tipi di grafici, personalizzarne l'aspetto e manipolare i dati dei grafici.

#### D2. Quali tipi di grafici sono supportati da Aspose.Words per .NET?
Aspose.Words per .NET supporta un'ampia gamma di tipi di grafici, inclusi grafici a linee, grafici a barre, grafici a torta, grafici ad area, grafici a dispersione e altro ancora. È possibile scegliere il tipo di grafico appropriato in base ai requisiti di dati e visualizzazione.

#### D3. Posso personalizzare l'aspetto del grafico creato?
Sì, puoi personalizzare l'aspetto del grafico creato utilizzando Aspose.Words per .NET. È possibile modificare proprietà come il titolo del grafico, la posizione della legenda, le etichette dei dati, le etichette degli assi, i colori e altri elementi visivi per soddisfare le esigenze specifiche di progettazione e formattazione.
