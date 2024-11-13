---
title: Aggiungere valori di data e ora all'asse di un grafico
linktitle: Aggiungere valori di data e ora all'asse di un grafico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere valori di data e ora all'asse di un grafico utilizzando Aspose.Words per .NET in questa guida completa passo dopo passo.
type: docs
weight: 10
url: /it/net/programming-with-charts/date-time-values-to-axis/
---
## Introduzione

Creare grafici nei documenti può essere un modo potente per visualizzare i dati. Quando si gestiscono dati di serie temporali, aggiungere valori di data e ora all'asse di un grafico è fondamentale per la chiarezza. In questo tutorial, ti guideremo attraverso il processo di aggiunta di valori di data e ora all'asse di un grafico utilizzando Aspose.Words per .NET. Questa guida passo passo ti aiuterà a configurare il tuo ambiente, scrivere il codice e comprendere ogni parte del processo. Immergiamoci!

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. Visual Studio o qualsiasi IDE .NET: è necessario un ambiente di sviluppo per scrivere ed eseguire il codice .NET.
2.  Aspose.Words per .NET: dovresti avere la libreria Aspose.Words per .NET installata. Puoi scaricarla da[Qui](https://releases.aspose.com/words/net/).
3. Conoscenza di base di C#: questo tutorial presuppone una conoscenza di base della programmazione in C#.
4.  Una licenza Aspose valida: puoi ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).

## Importazione degli spazi dei nomi

Per iniziare, assicurati di aver importato i namespace necessari nel tuo progetto. Questo passaggio è fondamentale per accedere alle classi e ai metodi di Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Passaggio 1: imposta la directory dei documenti

Per prima cosa, devi definire la directory in cui verrà salvato il tuo documento. Questo è importante per organizzare i tuoi file e garantire che il tuo codice funzioni correttamente.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: creare un nuovo documento e DocumentBuilder

 Quindi, crea una nuova istanza di`Document` classe e una`DocumentBuilder` oggetto. Questi oggetti ti aiuteranno a creare e manipolare il tuo documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire un grafico nel documento

 Ora, inserisci un grafico nel tuo documento utilizzando`DocumentBuilder` oggetto. In questo esempio, stiamo usando un grafico a colonne, ma puoi scegliere anche altri tipi.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 4: Cancella le serie esistenti

Cancella tutte le serie esistenti nel grafico per assicurarti di iniziare con una tabula rasa. Questo passaggio è essenziale per i dati personalizzati.

```csharp
chart.Series.Clear();
```

## Passaggio 5: aggiungere valori di data e ora alla serie

Aggiungi i tuoi valori di data e ora alla serie di grafici. Questo passaggio comporta la creazione di array per le date e i valori corrispondenti.

```csharp
chart.Series.Add("Aspose Series 1",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Passaggio 6: configurare l'asse X

Imposta la scala e i segni di spunta per l'asse X. Ciò assicura che le date siano visualizzate correttamente e a intervalli appropriati.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Passaggio 7: Salvare il documento

Infine, salva il tuo documento nella directory specificata. Questo passaggio conclude il processo e il tuo documento dovrebbe ora contenere un grafico con valori di data e ora sull'asse X.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

## Conclusione

Aggiungere valori di data e ora all'asse di un grafico in un documento è un processo semplice con Aspose.Words per .NET. Seguendo i passaggi descritti in questo tutorial, puoi creare grafici chiari e informativi che visualizzano in modo efficace i dati delle serie temporali. Che tu stia preparando report, presentazioni o qualsiasi documento che richieda una rappresentazione dettagliata dei dati, Aspose.Words fornisce gli strumenti di cui hai bisogno per avere successo.

## Domande frequenti

### Posso utilizzare altri tipi di grafici con Aspose.Words per .NET?

Sì, Aspose.Words supporta vari tipi di grafici, tra cui grafici a linee, a barre, a torta e altri ancora.

### Come posso personalizzare l'aspetto del mio grafico?

È possibile personalizzare l'aspetto accedendo alle proprietà del grafico e impostando stili, colori e altro ancora.

### È possibile aggiungere più serie a un grafico?

 Assolutamente! Puoi aggiungere più serie al tuo grafico chiamando il`Series.Add` metodo più volte con dati diversi.

### Cosa succede se ho bisogno di aggiornare dinamicamente i dati del grafico?

È possibile aggiornare i dati del grafico in modo dinamico manipolando le proprietà delle serie e degli assi a livello di programmazione, in base alle proprie esigenze.

### Dove posso trovare una documentazione più dettagliata per Aspose.Words per .NET?

 Puoi trovare una documentazione più dettagliata[Qui](https://reference.aspose.com/words/net/).