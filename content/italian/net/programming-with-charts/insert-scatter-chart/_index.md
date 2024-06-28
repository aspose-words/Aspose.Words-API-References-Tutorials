---
title: Inserisci grafico a dispersione nel documento di Word
linktitle: Inserisci grafico a dispersione nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un grafico a dispersione in un documento utilizzando Aspose.Words per .NET. Aggiungi dati di serie con le coordinate X e Y.
type: docs
weight: 10
url: /it/net/programming-with-charts/insert-scatter-chart/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per inserire un grafico a dispersione in un documento. Il codice sorgente fornito dimostra come creare un grafico, aggiungere dati di serie e salvare il documento.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. È possibile scaricarlo utilizzando Gestione pacchetti NuGet per installarlo.
- Un percorso della directory del documento in cui verrà salvato il documento di output.

## Passaggio 2: crea un nuovo documento e inserisci un grafico.

 Creane uno nuovo`Document` oggetto e a`DocumentBuilder` per costruire il documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Successivamente, utilizzare il`InsertChart` metodo del`DocumentBuilder` per inserire un grafico a dispersione nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio, aggiungeremo due serie di coordinate X e Y.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Passaggio 4: salva il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Ciò completa l'implementazione dell'inserimento di un grafico a dispersione utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Inserisci grafico a dispersione utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Conclusione

In questo tutorial, hai imparato come inserire un grafico a dispersione in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, puoi creare un nuovo documento, inserire un grafico a dispersione, aggiungere dati di serie con le coordinate X e Y e salvare il documento con il grafico.

Aspose.Words per .NET fornisce un'API completa per l'elaborazione delle parole con grafici nei documenti Word. I grafici a dispersione sono utili per visualizzare e analizzare i dati con due variabili numeriche. Con Aspose.Words per .NET, puoi creare facilmente grafici a dispersione che rappresentano la relazione tra i valori X e Y e identificare modelli o tendenze nei dati.

Utilizzando Aspose.Words per .NET, puoi automatizzare il processo di generazione di documenti con grafici a dispersione, risparmiando tempo e fatica nella creazione manuale di documenti. La libreria offre un'ampia gamma di tipi di grafici, inclusi i grafici a dispersione, e fornisce varie opzioni di personalizzazione per personalizzare l'aspetto del grafico in base alle proprie esigenze.

### Domande frequenti

#### Q1. Cos'è un grafico a dispersione?
Un grafico a dispersione è un tipo di grafico che mostra la relazione tra due variabili numeriche. Consiste in una serie di punti tracciati su una griglia di coordinate, con una variabile rappresentata sull'asse X e l'altra variabile rappresentata sull'asse Y. I grafici a dispersione vengono utilizzati per identificare modelli, correlazioni o tendenze tra due insiemi di punti dati.

#### Q2. Posso aggiungere più serie al grafico a dispersione?
Sì, puoi aggiungere più serie al grafico a dispersione utilizzando Aspose.Words per .NET. Ciascuna serie rappresenta un insieme di punti dati con le rispettive coordinate X e Y. Aggiungendo più serie, puoi confrontare e analizzare diversi set di dati all'interno dello stesso grafico a dispersione, fornendo una visualizzazione completa dei tuoi dati.

#### Q3. Posso personalizzare l'aspetto del grafico a dispersione?
Sì, utilizzando Aspose.Words per .NET, puoi personalizzare vari aspetti dell'aspetto del grafico a dispersione. Puoi modificare proprietà come il colore della serie, la forma dell'indicatore, le etichette degli assi e la formattazione dell'area del grafico. La libreria fornisce un ricco set di API per controllare gli elementi visivi del grafico e creare un aspetto personalizzato adatto alle tue esigenze.

#### Q4. Posso salvare il documento con il grafico a dispersione inserito in diversi formati?
Sì, Aspose.Words per .NET ti consente di salvare il documento con il grafico a dispersione inserito in vari formati, come DOCX, PDF, HTML e altro. Puoi scegliere il formato di output desiderato in base alle tue esigenze e utilizzare il file`Save` metodo del`Document` oggetto per salvare il documento. Il grafico a dispersione inserito verrà conservato nel documento salvato.

#### Q5. Posso modificare i dati e l'aspetto del grafico a dispersione dopo averlo inserito?
Sì, dopo aver inserito il grafico a dispersione nel documento, puoi modificarne i dati e l'aspetto utilizzando le API fornite da Aspose.Words per .NET. Puoi aggiornare i dati della serie con le nuove coordinate X e Y, modificare le forme e i colori dei marcatori, personalizzare le proprietà degli assi e applicare opzioni di formattazione per creare grafici dinamici e interattivi nei tuoi documenti Word.