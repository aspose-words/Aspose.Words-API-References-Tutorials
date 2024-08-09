---
title: Inserisci grafico ad area in un documento Word
linktitle: Inserisci grafico ad area in un documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un grafico ad area in un documento utilizzando Aspose.Words per .NET. Aggiungi i dati della serie e salva il documento con il grafico.
type: docs
weight: 10
url: /it/net/programming-with-charts/insert-area-chart/
---
## Introduzione

Benvenuti in questa guida passo passo su come inserire un grafico ad area in un documento Word utilizzando Aspose.Words per .NET. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questo tutorial ti guiderà attraverso tutto ciò che devi sapere per creare grafici ad area straordinari e informativi nei tuoi documenti Word. Tratteremo i prerequisiti, ti mostreremo come importare gli spazi dei nomi necessari e ti guideremo attraverso ogni fase del processo con istruzioni chiare e facili da seguire.

## Prerequisiti

Prima di approfondire, assicuriamoci di avere tutto il necessario per iniziare:

1.  Aspose.Words per .NET: assicurati di avere Aspose.Words per .NET installato. Puoi scaricarlo[Qui](https://releases.aspose.com/words/net/).
2. .NET Framework: assicurati di avere .NET Framework installato sul tuo computer.
3. IDE: un ambiente di sviluppo integrato (IDE) come Visual Studio per scrivere ed eseguire il codice.
4. Conoscenza di base di C#: sarà utile una conoscenza di base della programmazione C#.

Una volta stabiliti questi prerequisiti, sei pronto per iniziare a creare bellissimi grafici ad area nei tuoi documenti Word.

## Importa spazi dei nomi

Per prima cosa, importiamo gli spazi dei nomi necessari. Questi spazi dei nomi forniscono le classi e i metodi necessari per lavorare con documenti e grafici di Word in Aspose.Words per .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System;
```

Ora che abbiamo importato gli spazi dei nomi essenziali, passiamo alla creazione del nostro documento e all'inserimento passo dopo passo di un grafico ad area.

## Passaggio 1: crea un nuovo documento Word

Iniziamo creando un nuovo documento Word. Questa sarà la base in cui inseriremo il nostro grafico ad area.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 In questo passaggio inizializziamo un nuovo file`Document` oggetto che rappresenta il nostro documento Word.

## Passaggio 2: utilizzare DocumentBuilder per inserire un grafico

 Successivamente, utilizzeremo il file`DocumentBuilder` class per inserire un grafico ad area nel nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
```

 Qui creiamo un file`DocumentBuilder` oggetto e utilizzarlo per inserire un grafico ad area di dimensioni specifiche (432x252) nel nostro documento.

## Passaggio 3: accedi all'oggetto grafico

 Dopo aver inserito il grafico, dobbiamo accedere al file`Chart` oggetto per personalizzare il nostro grafico ad area.

```csharp
Chart chart = shape.Chart;
```

 Questa riga di codice recupera il file`Chart` oggetto dalla forma che abbiamo appena inserito.

## Passaggio 4: aggiungi i dati della serie al grafico

Ora è il momento di aggiungere alcuni dati al nostro grafico. Aggiungeremo una serie con date e valori corrispondenti.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

In questo passaggio aggiungiamo una serie denominata "Aspose Series 1" con una serie di date e valori corrispondenti.

## Passaggio 5: salva il documento

Infine, salveremo il nostro documento con il grafico ad area inserito.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Questa riga di codice salva il documento nella directory specificata con il nome file specificato.

## Conclusione

Congratulazioni! Hai inserito con successo un grafico ad area in un documento di Word utilizzando Aspose.Words per .NET. Questa guida ti ha guidato attraverso ogni passaggio, dalla configurazione dell'ambiente al salvataggio del documento finale. Con Aspose.Words per .NET, puoi creare un'ampia varietà di grafici e altri elementi complessi nei tuoi documenti Word, rendendo i tuoi report e presentazioni più dinamici e informativi.

## Domande frequenti

### Posso utilizzare Aspose.Words per .NET con altri linguaggi .NET?
Sì, Aspose.Words per .NET supporta altri linguaggi .NET come VB.NET.

### È possibile personalizzare l'aspetto del grafico?
Assolutamente! Aspose.Words per .NET offre ampie opzioni per personalizzare l'aspetto dei tuoi grafici.

### Posso aggiungere più grafici a un singolo documento Word?
Sì, puoi inserire tutti i grafici di cui hai bisogno in un singolo documento Word.

### Aspose.Words per .NET supporta altri tipi di grafici?
Sì, Aspose.Words per .NET supporta vari tipi di grafici tra cui barre, linee, torta e altro.

### Dove posso ottenere una licenza temporanea per Aspose.Words per .NET?
 È possibile ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).