---
title: Definire le proprietà dell'asse XY in un grafico
linktitle: Definire le proprietà dell'asse XY in un grafico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come definire le proprietà degli assi XY in un grafico utilizzando Aspose.Words per .NET. Vengono dimostrate le opzioni di personalizzazione per gli assi X e Y.
type: docs
weight: 10
url: /it/net/programming-with-charts/define-xyaxis-properties/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per definire le proprietà per gli assi X e Y in un grafico. Il codice sorgente fornito dimostra come creare un grafico, aggiungere dati di serie e personalizzare le proprietà dell'asse.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. È possibile scaricarlo utilizzando Gestione pacchetti NuGet per installarlo.
- Un percorso della directory del documento in cui verrà salvato il documento di output.

## Passaggio 2: crea un nuovo documento e inserisci un grafico

 Creane uno nuovo`Document` oggetto e a`DocumentBuilder` per costruire il documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Successivamente, inserisci un grafico nel documento utilizzando il comando`InsertChart` metodo del`DocumentBuilder`. In questo esempio inseriremo un grafico ad area.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio aggiungeremo cinque punti dati con date e valori corrispondenti.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## Passaggio 4: personalizzare le proprietà degli assi X e Y

 Per personalizzare le proprietà degli assi X e Y, accedere a`ChartAxis` oggetti associati al grafico.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Modificare le proprietà del`xAxis` E`yAxis`oggetti per impostare le opzioni desiderate per gli assi X e Y. In questo esempio verranno illustrate alcune proprietà comuni che possono essere personalizzate.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Passaggio 5: salva il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Ciò completa l'implementazione della definizione delle proprietà degli assi XY in un grafico utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per definire le proprietà XYAxis utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Inserisci grafico
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Cambia l'asse X in categoria anziché data, quindi tutti i punti verranno inseriti con uguale intervallo sull'asse X.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //Misurato in unità di visualizzazione dell'asse Y (centinaia).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Conclusione

In questo tutorial, hai imparato come definire le proprietà per gli assi X e Y in un grafico utilizzando Aspose.Words per .NET. Seguendo la guida passo passo, puoi creare un grafico, aggiungere dati di serie e personalizzare le proprietà dell'asse per soddisfare i tuoi requisiti specifici. Aspose.Words per .NET fornisce un'API completa per l'elaborazione delle parole con grafici nei documenti Word, consentendo di manipolare vari aspetti del grafico, inclusi gli assi.

Accedendo al`ChartAxis` oggetti associati al grafico, puoi modificare proprietà come il tipo di categoria, le croci degli assi, i segni di graduazione, le posizioni delle etichette, il ridimensionamento e altro ancora. Questa flessibilità ti consente di personalizzare l'aspetto e il comportamento degli assi del grafico per presentare i dati in modo efficace.

Utilizzando Aspose.Words per .NET, puoi integrare perfettamente le funzionalità di creazione e personalizzazione di grafici nelle tue applicazioni .NET e automatizzare la generazione di documenti dall'aspetto professionale con visualizzazioni avanzate.

### Domande frequenti

#### Q1. Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una potente libreria di elaborazione documenti che consente agli sviluppatori di creare, manipolare e salvare documenti Word a livello di codice nelle applicazioni .NET. Fornisce un'ampia gamma di funzionalità per l'elaborazione di parole con elementi di documenti, inclusi i grafici.

#### Q2. Come posso installare Aspose.Words per .NET?
È possibile installare Aspose.Words per .NET scaricandolo utilizzando il gestore pacchetti NuGet in Visual Studio. Cerca semplicemente "Aspose.Words" nel gestore pacchetti NuGet e installalo nel tuo progetto.

#### Q3. Posso personalizzare altri aspetti del grafico utilizzando Aspose.Words per .NET?
Sì, Aspose.Words per .NET offre ampie funzionalità per personalizzare vari aspetti di un grafico. Oltre a definire le proprietà degli assi, puoi modificare il tipo di grafico, le serie di dati, la legenda, il titolo, l'area del tracciato, le etichette dei dati e molti altri elementi del grafico. L'API offre un controllo capillare sull'aspetto e sul comportamento del grafico.

#### Q4. Posso creare diversi tipi di grafici utilizzando Aspose.Words per .NET?
 Sì, Aspose.Words per .NET supporta un'ampia gamma di tipi di grafici, inclusi ad area, a barre, a linee, a torta, a dispersione e altro. Puoi usare il`ChartType` enumerazione per specificare il tipo di grafico desiderato quando si inserisce una forma di grafico in un documento di Word.

#### Q5. Posso salvare il grafico in diversi formati?
Sì, Aspose.Words per .NET ti consente di salvare il documento contenente il grafico in vari formati, come DOCX, PDF, HTML e altro. Puoi scegliere il formato appropriato in base alle tue esigenze e utilizzare il file`Save` metodo del`Document` oggetto per salvare il documento.

#### Q6. Posso applicare queste tecniche a più grafici in un documento?
 Sì, puoi applicare queste tecniche a più grafici in un documento ripetendo i passaggi necessari per ciascun grafico. Puoi creare file separati`Chart` E`ChartAxis` oggetti per ogni grafico e personalizzarne le proprietà di conseguenza. Aspose.Words per .NET fornisce il supporto completo per l'elaborazione di parole con più grafici in un unico documento.