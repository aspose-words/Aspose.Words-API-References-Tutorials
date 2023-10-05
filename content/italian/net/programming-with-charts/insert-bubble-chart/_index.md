---
title: Inserisci grafico a bolle nel documento Word
linktitle: Inserisci grafico a bolle nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un grafico a bolle in un documento utilizzando Aspose.Words per .NET. Aggiungi dati di serie con valori X, Y e dimensioni delle bolle.
type: docs
weight: 10
url: /it/net/programming-with-charts/insert-bubble-chart/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per inserire un grafico a bolle in un documento. Il codice sorgente fornito dimostra come creare un grafico, aggiungere dati di serie e salvare il documento.

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

 Successivamente, utilizzare il`InsertChart` metodo del`DocumentBuilder` per inserire un grafico a bolle nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio, aggiungeremo tre punti dati con i valori X, Y e dimensione della bolla corrispondenti.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Passaggio 4: salva il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

Ciò completa l'implementazione dell'inserimento di un grafico a bolle utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Inserisci grafico a bolle utilizzando Aspose.Words per .NET 

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## Conclusione

In questo tutorial, hai imparato come inserire un grafico a bolle in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, puoi creare un nuovo documento, inserire un grafico a bolle, aggiungere dati di serie e salvare il documento con il grafico.

Aspose.Words per .NET fornisce una potente API per l'elaborazione di parole con grafici nei documenti di Word. I grafici a bolle sono ideali per visualizzare dati tridimensionali, in cui ogni punto dati è rappresentato da una bolla con le coordinate X e Y e un valore di dimensione. Con Aspose.Words per .NET, puoi creare grafici a bolle dinamici e informativi che migliorano la rappresentazione visiva dei tuoi dati.

Utilizzando Aspose.Words per .NET, puoi automatizzare il processo di generazione di documenti con grafici a bolle, risparmiando tempo e fatica nella creazione manuale di documenti. La libreria offre un'ampia gamma di tipi di grafici e opzioni di personalizzazione, consentendoti di creare grafici visivamente accattivanti e ricchi di dati nei tuoi documenti Word.

### Domande frequenti

#### Q1. Cos'è un grafico a bolle?
Un grafico a bolle è un tipo di grafico che visualizza dati tridimensionali utilizzando bolle o sfere. Ogni punto dati è rappresentato da una bolla, dove le coordinate X e Y determinano la posizione della bolla sul grafico e la dimensione della bolla rappresenta la terza dimensione dei dati. I grafici a bolle sono utili per visualizzare relazioni e modelli tra più variabili.

#### Q2. Posso aggiungere più serie al grafico a bolle?
Sì, puoi aggiungere più serie al grafico a bolle utilizzando Aspose.Words per .NET. Ciascuna serie rappresenta un insieme di punti dati con i rispettivi valori X, Y e dimensione della bolla. Aggiungendo più serie, puoi confrontare e analizzare diversi set di dati all'interno dello stesso grafico, fornendo una visione completa dei tuoi dati.

#### Q3. Posso personalizzare l'aspetto del grafico a bolle?
Sì, utilizzando Aspose.Words per .NET, puoi personalizzare vari aspetti dell'aspetto del grafico a bolle. Puoi modificare proprietà come il colore della serie, la dimensione della bolla, le etichette degli assi e la formattazione dell'area del grafico. La libreria fornisce un ricco set di API per controllare gli elementi visivi del grafico e creare un aspetto personalizzato adatto alle tue esigenze.

#### Q4. Posso salvare il documento con il grafico a bolle inserito in formati diversi?
 Sì, Aspose.Words per .NET ti consente di salvare il documento con il grafico a bolle inserito in vari formati, come DOCX, PDF, HTML e altro. Puoi scegliere il formato di output desiderato in base alle tue esigenze e utilizzare il file`Save` metodo del`Document` oggetto per salvare il documento. Il grafico a bolle inserito verrà conservato nel documento salvato.

#### Q5. Posso modificare i dati e l'aspetto del grafico a bolle dopo averlo inserito?
Sì, dopo aver inserito il grafico a bolle nel documento, puoi modificarne i dati e l'aspetto utilizzando le API fornite da Aspose.Words per .NET. Puoi aggiornare i dati delle serie, modificare la dimensione delle bolle, personalizzare le proprietà degli assi e applicare opzioni di formattazione per creare grafici dinamici e interattivi nei tuoi documenti Word.