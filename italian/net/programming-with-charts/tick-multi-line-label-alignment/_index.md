---
title: Selezionare Allineamento etichetta multilinea
linktitle: Selezionare Allineamento etichetta multilinea
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come allineare le etichette multilinea del segno di spunta in un asse del grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/tick-multi-line-label-alignment/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per impostare l'allineamento delle etichette multilinea tick in un asse del grafico. Il codice sorgente fornito mostra come creare un grafico, accedere all'asse e modificare l'allineamento dell'etichetta tick.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo dal sito Web ufficiale di Aspose o utilizzare il gestore di pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui verrà salvato il documento di output.

## Passaggio 2: crea un nuovo documento e inserisci un grafico

 Crea un nuovo`Document` oggetto e a`DocumentBuilder` per costruire il documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Quindi, usa il`InsertChart` metodo del`DocumentBuilder` per inserire un grafico a dispersione nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Passaggio 3: impostare l'allineamento dell'etichetta del segno di spunta

 Per impostare l'allineamento delle etichette multilinea del segno di spunta, accedere a`AxisX` proprietà del grafico e impostare la`TickLabelAlignment` proprietà all'allineamento desiderato. In questo esempio, impostiamo l'allineamento su`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Passaggio 4: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Questo completa l'implementazione dell'impostazione dell'allineamento dell'etichetta su più righe tick utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Tick Multi Line Label Alignment utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Questa proprietà ha effetto solo per le etichette multilinea.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```