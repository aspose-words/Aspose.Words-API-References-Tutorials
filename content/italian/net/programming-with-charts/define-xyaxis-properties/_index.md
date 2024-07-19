---
title: Definire le proprietà dell'asse XY in un grafico
linktitle: Definire le proprietà dell'asse XY in un grafico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come definire le proprietà degli assi XY in un grafico utilizzando Aspose.Words per .NET con questa guida passo passo. Perfetto per gli sviluppatori .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/define-xyaxis-properties/
---
## introduzione

I grafici sono un potente strumento per visualizzare i dati. Quando hai bisogno di creare documenti professionali con grafici dinamici, Aspose.Words per .NET è una libreria inestimabile. Questo articolo ti guiderà attraverso il processo di definizione delle proprietà dell'asse XY in un grafico utilizzando Aspose.Words per .NET, suddividendo ogni passaggio per garantire chiarezza e facilità di comprensione.

## Prerequisiti

Prima di immergerti nella codifica, è necessario soddisfare alcuni prerequisiti:

1. Aspose.Words per .NET: assicurati di avere la libreria Aspose.Words per .NET. Puoi[scaricalo qui](https://releases.aspose.com/words/net/).
2. Ambiente di sviluppo: è necessario un ambiente di sviluppo integrato (IDE) come Visual Studio.
3. .NET Framework: assicurati che il tuo ambiente di sviluppo sia configurato per lo sviluppo .NET.
4. Conoscenza di base di C#: questa guida presuppone che tu abbia una conoscenza di base della programmazione C#.

## Importa spazi dei nomi

Per cominciare, devi importare gli spazi dei nomi necessari nel tuo progetto. Ciò garantisce l'accesso a tutte le classi e i metodi necessari per creare e manipolare documenti e grafici.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

Suddivideremo il processo in semplici passaggi, ciascuno incentrato su una parte specifica della definizione delle proprietà dell'asse XY in un grafico.

## Passaggio 1: inizializzare il documento e DocumentBuilder

 Per prima cosa è necessario inizializzare un nuovo documento e un file`DocumentBuilder` oggetto. IL`DocumentBuilder` aiuta a inserire contenuto nel documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserisci un grafico

Successivamente, inserirai un grafico nel documento. In questo esempio utilizzeremo un grafico ad area. È possibile personalizzare le dimensioni del grafico secondo necessità.

```csharp
// Inserisci grafico
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: cancella le serie predefinite e aggiungi dati personalizzati

Per impostazione predefinita, il grafico avrà alcune serie predefinite. Li cancelleremo e aggiungeremo le nostre serie di dati personalizzate.

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

## Passaggio 4: definire le proprietà dell'asse X

Ora è il momento di definire le proprietà per l'asse X. Ciò include l'impostazione del tipo di categoria, la personalizzazione dell'incrocio degli assi e la regolazione dei segni di graduazione e delle etichette.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3; //Misurato in unità di visualizzazione dell'asse Y (centinaia).
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;
```

## Passaggio 5: definire le proprietà dell'asse Y

Allo stesso modo, imposterai le proprietà per l'asse Y. Ciò include l'impostazione della posizione dell'etichetta di spunta, delle unità maggiori e minori, dell'unità di visualizzazione e del ridimensionamento.

```csharp
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Passaggio 6: salva il documento

Infine, salva il documento nella directory specificata. Questo genererà il documento Word con il grafico personalizzato.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Conclusione

Creare e personalizzare grafici nei documenti Word utilizzando Aspose.Words per .NET è semplice una volta compresi i passaggi coinvolti. Questa guida ti ha guidato attraverso il processo di definizione delle proprietà degli assi XY in un grafico, dall'inizializzazione del documento al salvataggio del prodotto finale. Con queste competenze, puoi creare grafici dettagliati e dall'aspetto professionale che migliorano i tuoi documenti.

## Domande frequenti

### Quali tipi di grafici posso creare con Aspose.Words per .NET?
Puoi creare vari tipi di grafici, inclusi ad area, a barre, a linee, a torta e altro.

### Come installo Aspose.Words per .NET?
 È possibile scaricare Aspose.Words per .NET da[Qui](https://releases.aspose.com/words/net/) e seguire le istruzioni di installazione fornite.

### Posso personalizzare l'aspetto dei miei grafici?
Sì, Aspose.Words per .NET consente un'ampia personalizzazione dei grafici, inclusi colori, caratteri e proprietà degli assi.

### È disponibile una prova gratuita per Aspose.Words per .NET?
 Sì, puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).

### Dove posso trovare altri tutorial e documentazione?
 Puoi trovare ulteriori tutorial e documentazione dettagliata su[Aspose.Words per la pagina della documentazione .NET](https://reference.aspose.com/words/net/).
