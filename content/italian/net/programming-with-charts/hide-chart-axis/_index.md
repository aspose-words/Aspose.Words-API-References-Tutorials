---
title: Nascondi l'asse del grafico in un documento Word
linktitle: Nascondi l'asse del grafico in un documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come nascondere l'asse del grafico in un documento utilizzando Aspose.Words per .NET. Nascondi l'asse per una visualizzazione del grafico più chiara e mirata.
type: docs
weight: 10
url: /it/net/programming-with-charts/hide-chart-axis/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per nascondere l'asse del grafico in un documento. Il codice sorgente fornito dimostra come creare un grafico, aggiungere dati di serie e nascondere l'asse del grafico.

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

 Successivamente, inserisci un grafico nel documento utilizzando il comando`InsertChart` metodo del`DocumentBuilder`In questo esempio inseriremo un grafico a colonne.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio aggiungeremo cinque elementi e i relativi valori corrispondenti.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Passaggio 4: nascondi l'asse del grafico

 Per nascondere l'asse del grafico, accedi a`AxisY` proprietà del grafico e impostare il file`Hidden` proprietà a`true`.

```csharp
chart.AxisY.Hidden = true;
```

In questo esempio, nascondiamo l'asse Y del grafico.

## Passaggio 5: salva il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Ciò completa l'implementazione di nascondere l'asse del grafico utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Nascondi asse del grafico utilizzando Aspose.Words per .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Conclusione

In questo tutorial, hai imparato come nascondere l'asse del grafico in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, puoi creare un grafico, aggiungere dati di serie e nascondere l'asse del grafico per ottenere l'effetto visivo desiderato.

 Aspose.Words per .NET fornisce un'API completa per l'elaborazione delle parole con grafici nei documenti Word, consentendo di manipolare vari aspetti del grafico, comprese le proprietà degli assi. Accedendo al`AxisY`proprietà del grafico, puoi nascondere l'asse Y per rimuoverlo dalla visualizzazione del grafico.

Nascondere l'asse del grafico può essere utile quando vuoi concentrarti sui dati del grafico senza la distrazione delle linee e delle etichette degli assi. Fornisce un aspetto più pulito e minimalista al grafico.

Utilizzando Aspose.Words per .NET, puoi facilmente incorporare funzionalità di creazione di grafici nelle tue applicazioni .NET e generare documenti dall'aspetto professionale con grafici personalizzati e assi dei grafici nascosti.

### Domande frequenti

#### Q1. Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una potente libreria di elaborazione documenti che consente agli sviluppatori di creare, manipolare e salvare documenti Word a livello di codice nelle applicazioni .NET. Fornisce un'ampia gamma di funzionalità per l'elaborazione di parole con elementi di documenti, inclusi grafici e assi del grafico.

#### Q2. Come posso installare Aspose.Words per .NET?
È possibile installare Aspose.Words per .NET scaricandolo utilizzando il gestore pacchetti NuGet in Visual Studio. Cerca semplicemente "Aspose.Words" nel gestore pacchetti NuGet e installalo nel tuo progetto.

#### Q3. Posso nascondere sia l'asse X che l'asse Y di un grafico?
 Sì, puoi nascondere sia l'asse X che l'asse Y di un grafico utilizzando Aspose.Words per .NET. Per nascondere l'asse X, puoi accedere a`AxisX` proprietà del grafico e impostare il file`Hidden` proprietà a`true` Allo stesso modo, per nascondere l'asse Y, puoi accedere a`AxisY` proprietà e impostare il file`Hidden` proprietà a`true`. Ciò consente di rimuovere entrambi gli assi dalla visualizzazione del grafico.

#### Q4. Posso mostrare nuovamente l'asse dopo averlo nascosto?
 Sì, puoi mostrare nuovamente l'asse del grafico dopo averlo nascosto utilizzando Aspose.Words per .NET. Per mostrare un asse nascosto, è sufficiente impostare il file`Hidden` proprietà del corrispondente`AxisX` O`AxisY` opporsi a`false`. Ciò renderà nuovamente visibile l'asse nel grafico.

#### Q5. Posso personalizzare altre proprietà dell'asse del grafico?
 Sì, Aspose.Words per .NET ti consente di personalizzare varie proprietà dell'asse del grafico, come il titolo dell'asse, le etichette, il colore della linea e altro. Accedendo al`AxisX` E`AxisY` proprietà del grafico, puoi modificare proprietà come`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, e molti altri. Ciò ti offre un controllo dettagliato sull'aspetto e sul comportamento dell'asse del grafico.

#### Q6. Posso salvare il grafico con l'asse nascosto in diversi formati di file?
Sì, Aspose.Words per .NET ti consente di salvare il documento contenente il grafico con un asse nascosto in vari formati di file, come DOCX, PDF, HTML e altro. Puoi scegliere il formato di output desiderato in base alle tue esigenze e utilizzare il file`Save` metodo del`Document` oggetto per salvare il documento. L'asse nascosto verrà conservato nel documento salvato.