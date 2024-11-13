---
title: Inserisci grafico ad area in un documento Word
linktitle: Inserisci grafico ad area in un documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un grafico ad area in un documento utilizzando Aspose.Words per .NET. Aggiungi dati di serie e salva il documento con il grafico.
type: docs
weight: 10
url: /it/net/programming-with-charts/insert-area-chart/
---
## Introduzione

Benvenuti a questa guida passo passo su come inserire un grafico ad area in un documento Word usando Aspose.Words per .NET. Che siate sviluppatori esperti o alle prime armi, questo tutorial vi guiderà attraverso tutto ciò che dovete sapere per creare grafici ad area sorprendenti e informativi nei vostri documenti Word. Tratteremo i prerequisiti, vi mostreremo come importare i namespace necessari e vi guideremo attraverso ogni fase del processo con istruzioni chiare e facili da seguire.

## Prerequisiti

Prima di iniziare, assicuriamoci di avere tutto il necessario per iniziare:

1.  Aspose.Words per .NET: assicurati di avere Aspose.Words per .NET installato. Puoi scaricarlo[Qui](https://releases.aspose.com/words/net/).
2. .NET Framework: assicurati che .NET Framework sia installato sul tuo computer.
3. IDE: un ambiente di sviluppo integrato (IDE) come Visual Studio per scrivere ed eseguire il codice.
4. Conoscenza di base del linguaggio C#: sarà utile una conoscenza di base della programmazione C#.

Una volta soddisfatti questi prerequisiti, sarai pronto per iniziare a creare splendidi grafici ad area nei tuoi documenti Word.

## Importazione degli spazi dei nomi

Per prima cosa, importiamo i namespace necessari. Questi namespace forniscono le classi e i metodi richiesti per lavorare con documenti e grafici Word in Aspose.Words per .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System;
```

Ora che abbiamo importato gli spazi dei nomi essenziali, passiamo alla creazione del nostro documento e all'inserimento passo dopo passo di un grafico ad area.

## Passaggio 1: creare un nuovo documento Word

Iniziamo creando un nuovo documento Word. Questa sarà la base in cui inseriremo il nostro grafico ad area.

```csharp
// Percorso alla directory del documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 In questo passaggio, inizializziamo un nuovo`Document` oggetto che rappresenta il nostro documento Word.

## Passaggio 2: utilizzare DocumentBuilder per inserire un grafico

 Successivamente, useremo il`DocumentBuilder` classe per inserire un grafico ad area nel nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
```

 Qui creiamo un`DocumentBuilder` oggetto e utilizzarlo per inserire un grafico ad area di dimensioni specifiche (432x252) nel nostro documento.

## Passaggio 3: accedere all'oggetto grafico

 Dopo aver inserito il grafico, dobbiamo accedere al`Chart` oggetto per personalizzare il nostro grafico ad area.

```csharp
Chart chart = shape.Chart;
```

 Questa riga di codice recupera il`Chart` oggetto dalla forma che abbiamo appena inserito.

## Passaggio 4: aggiungere i dati della serie al grafico

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

In questo passaggio aggiungiamo una serie denominata "Aspose Series 1" con un set di date e valori corrispondenti.

## Passaggio 5: Salvare il documento

Infine, salveremo il nostro documento con il grafico ad area inserito.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Questa riga di codice salva il documento nella directory specificata con il nome file indicato.

## Conclusione

Congratulazioni! Hai inserito con successo un grafico ad area in un documento Word utilizzando Aspose.Words per .NET. Questa guida ti ha guidato attraverso ogni passaggio, dalla configurazione dell'ambiente al salvataggio del documento finale. Con Aspose.Words per .NET, puoi creare un'ampia varietà di grafici e altri elementi complessi nei tuoi documenti Word, rendendo i tuoi report e le tue presentazioni più dinamici e informativi.

## Domande frequenti

### Posso usare Aspose.Words per .NET con altri linguaggi .NET?
Sì, Aspose.Words per .NET supporta altri linguaggi .NET come VB.NET.

### È possibile personalizzare l'aspetto del grafico?
Assolutamente! Aspose.Words per .NET fornisce ampie opzioni per personalizzare l'aspetto dei tuoi grafici.

### Posso aggiungere più grafici a un singolo documento Word?
Sì, puoi inserire tutti i grafici di cui hai bisogno in un singolo documento Word.

### Aspose.Words per .NET supporta altri tipi di grafici?
Sì, Aspose.Words per .NET supporta vari tipi di grafici, tra cui grafici a barre, a linee, a torta e altri ancora.

### Dove posso ottenere una licenza temporanea per Aspose.Words per .NET?
 È possibile ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).