---
title: Inserisci il grafico ad area in un documento di Word
linktitle: Inserisci il grafico ad area in un documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come inserire un grafico ad area in un documento utilizzando Aspose.Words per .NET. Aggiungi i dati della serie e salva il documento con il grafico.
type: docs
weight: 10
url: /it/net/programming-with-charts/insert-area-chart/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per inserire un grafico ad area in un documento. Il codice sorgente fornito mostra come creare un grafico, aggiungere dati di serie e salvare il documento.

## Passaggio 1: impostare il progetto

Assicurati di avere i seguenti prerequisiti:

- Aspose.Words per la libreria .NET installata. Puoi scaricarlo utilizzando il gestore pacchetti NuGet per installarlo.
- Un percorso di directory del documento in cui verrà salvato il documento di output.

## Passaggio 2: crea un nuovo documento e inserisci un grafico

 Crea un nuovo`Document` oggetto e a`DocumentBuilder` per costruire il documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Quindi, usa il`InsertChart` metodo del`DocumentBuilder` per inserire un grafico ad area nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio, aggiungeremo cinque punti dati con date e valori corrispondenti.

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

## Passaggio 4: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Questo completa l'implementazione dell'inserimento di un grafico ad area utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Inserisci grafico ad area utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### Conclusione

In questo tutorial, hai imparato come inserire un grafico ad area in un documento di Word usando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, puoi creare un nuovo documento, inserire un grafico ad area, aggiungere dati di serie e salvare il documento con il grafico.

Aspose.Words per .NET fornisce una potente API per l'elaborazione di parole con grafici nei documenti di Word. Con poche righe di codice, puoi creare grafici ad area dall'aspetto professionale e personalizzarli in base alle tue esigenze. I grafici ad area vengono comunemente utilizzati per visualizzare la grandezza e le tendenze dei dati nel tempo o nelle categorie.

Utilizzando Aspose.Words per .NET, puoi automatizzare il processo di generazione di documenti con grafici ad area, risparmiando tempo e fatica nella creazione manuale di documenti. La libreria offre una vasta gamma di tipi di grafici e opzioni di personalizzazione, consentendo di creare grafici accattivanti e informativi nei documenti di Word.

### Domande frequenti

#### Q1. Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una potente libreria di elaborazione dei documenti che consente agli sviluppatori di creare, modificare e convertire i documenti di Word a livello di codice nelle applicazioni .NET. Fornisce un set completo di API per l'elaborazione di testi con elementi del documento, inclusi grafici, paragrafi, tabelle e altro.

#### D2. Come installo Aspose.Words per .NET?
Per installare Aspose.Words per .NET, puoi usare il gestore pacchetti NuGet in Visual Studio per installare la libreria direttamente nel tuo progetto. Basta cercare "Aspose.Words" nel gestore pacchetti NuGet e installare il pacchetto.

#### D3. Posso personalizzare l'aspetto del grafico ad area?
Sì, utilizzando Aspose.Words per .NET, puoi personalizzare vari aspetti dell'aspetto del grafico ad area. È possibile modificare proprietà come il titolo del grafico, il colore della serie, le etichette degli assi e la formattazione dell'area del grafico. La libreria fornisce un ricco set di API per controllare gli elementi visivi del grafico e creare un aspetto personalizzato adatto alle tue esigenze.

#### D4. Posso aggiungere più serie al grafico ad area?
Sì, puoi aggiungere più serie al grafico ad area utilizzando Aspose.Words per .NET. Ogni serie rappresenta un insieme di punti dati tracciati sul grafico. Puoi aggiungere serie con set di dati diversi e personalizzare ciascuna serie individualmente, inclusi nome, punti dati e aspetto.

#### Q5. Posso salvare il documento con il grafico ad area inserito in diversi formati?
 Sì, Aspose.Words per .NET ti consente di salvare il documento con il grafico ad area inserito in vari formati, come DOCX, PDF, HTML e altro. È possibile scegliere il formato di output desiderato in base alle proprie esigenze e utilizzare il file`Save` metodo del`Document` oggetto per salvare il documento. Il grafico ad area inserito verrà conservato nel documento salvato.

#### D6. Posso modificare i dati e l'aspetto del grafico ad area dopo averlo inserito?
Sì, dopo aver inserito il grafico ad area nel documento, puoi modificarne i dati e l'aspetto utilizzando le API fornite da Aspose.Words per .NET. È possibile aggiornare i dati della serie, modificare il tipo di grafico, personalizzare le proprietà degli assi e applicare le opzioni di formattazione per creare grafici dinamici e interattivi nei documenti di Word.