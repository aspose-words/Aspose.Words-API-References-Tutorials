---
title: Inserisci un semplice istogramma in un documento di Word
linktitle: Inserisci un semplice istogramma in un documento di Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come inserire un semplice istogramma in un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/insert-simple-column-chart/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per inserire un semplice istogramma in un documento. Il codice sorgente fornito mostra come creare un grafico, aggiungere dati di serie e salvare il documento.

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

 Quindi, usa il`InsertChart` metodo del`DocumentBuilder` per inserire un istogramma nel documento. È possibile specificare diversi tipi e dimensioni di grafici in base alle proprie esigenze.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio, aggiungeremo più serie con due categorie ciascuna.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Passaggio 4: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Questo completa l'implementazione dell'inserimento di un semplice istogramma utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Inserisci grafico a colonne semplice utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// È possibile specificare diversi tipi e dimensioni di grafici.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Elimina le serie generate di default.
	seriesColl.Clear();
	// Crea un array di nomi di categoria, in questo tutorial abbiamo due categorie.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Si noti che gli array di dati non devono essere vuoti e gli array devono avere le stesse dimensioni.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Conclusione

In questo tutorial, hai imparato come inserire un semplice istogramma in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida passo-passo e utilizzando il codice sorgente fornito, puoi creare un nuovo documento, inserire un istogramma, aggiungere più serie con categorie e valori corrispondenti e salvare il documento con il grafico.

Aspose.Words per .NET fornisce un'API potente e flessibile per l'elaborazione di testi con grafici nei documenti di Word. Il semplice istogramma è un modo efficace per rappresentare e confrontare i dati in diverse categorie. Con Aspose.Words per .NET, puoi creare facilmente istogrammi con dati personalizzati, aggiungere più serie per il confronto visivo e personalizzare l'aspetto del grafico in base alle tue esigenze.

Utilizzando Aspose.Words per .NET, puoi automatizzare il processo di generazione di documenti con istogrammi, risparmiando tempo e fatica nella creazione manuale di documenti. La libreria offre un'ampia gamma di tipi di grafici, inclusi semplici istogrammi, e fornisce varie opzioni di personalizzazione per personalizzare l'aspetto del grafico in base alle proprie esigenze.

### Domande frequenti

#### Q1. Cos'è un istogramma?
Un istogramma è un tipo di grafico che visualizza i dati utilizzando barre verticali di varie altezze. Ogni colonna rappresenta una categoria e l'altezza della colonna corrisponde al valore di tale categoria. I grafici a colonne sono comunemente usati per confrontare i dati tra diverse categorie o per tenere traccia delle modifiche nel tempo.

#### D2. Posso aggiungere più serie all'istogramma?
Sì, utilizzando Aspose.Words per .NET, puoi aggiungere più serie all'istogramma. Ogni serie rappresenta un insieme di punti dati con le rispettive categorie e valori. Aggiungendo più serie, puoi confrontare e analizzare diversi set di dati all'interno dello stesso istogramma, fornendo una visione completa dei tuoi dati.

#### D3. Posso personalizzare l'aspetto dell'istogramma?
Sì, Aspose.Words per .NET consente di personalizzare vari aspetti dell'aspetto dell'istogramma. È possibile modificare proprietà come il colore della serie, le etichette degli assi, le etichette dei dati e la formattazione dell'area del grafico. La libreria fornisce un ricco set di API per controllare gli elementi visivi del grafico e creare un aspetto personalizzato adatto alle tue esigenze.

#### D4. Posso salvare il documento con l'istogramma inserito in diversi formati?
 Sì, Aspose.Words per .NET ti consente di salvare il documento con l'istogramma inserito in vari formati, come DOCX, PDF, HTML e altro. È possibile scegliere il formato di output desiderato in base alle proprie esigenze e utilizzare il file`Save` metodo del`Document` oggetto per salvare il documento. L'istogramma inserito verrà conservato nel documento salvato.

#### Q5. Posso modificare i dati e l'aspetto dell'istogramma dopo averlo inserito?
Sì, dopo aver inserito l'istogramma nel documento, puoi modificarne i dati e l'aspetto utilizzando le API fornite da Aspose.Words per .NET. Puoi aggiornare i dati della serie con nuove categorie e valori, modificare i colori e la formattazione delle colonne, personalizzare le proprietà degli assi e applicare varie opzioni di formattazione per creare grafici dinamici e visivamente accattivanti nei tuoi documenti Word.