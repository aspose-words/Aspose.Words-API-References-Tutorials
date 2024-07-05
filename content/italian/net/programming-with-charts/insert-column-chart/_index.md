---
title: Inserisci istogramma in un documento Word
linktitle: Inserisci istogramma in un documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come inserire un istogramma in un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/insert-column-chart/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per inserire un istogramma in un documento. Il codice sorgente fornito dimostra come creare un grafico, aggiungere dati di serie e salvare il documento.

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

 Successivamente, utilizzare il`InsertChart` metodo del`DocumentBuilder` per inserire un istogramma nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio aggiungeremo due categorie e i relativi valori corrispondenti.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Passaggio 4: salva il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Ciò completa l'implementazione dell'inserimento di un istogramma utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Inserisci istogramma utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## Conclusione

In questo tutorial, hai imparato come inserire un istogramma in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, puoi creare un nuovo documento, inserire un istogramma, aggiungere dati di serie e salvare il documento con il grafico.

Aspose.Words per .NET fornisce una potente API per l'elaborazione di parole con grafici nei documenti di Word. I grafici a colonne vengono comunemente utilizzati per visualizzare e confrontare i dati di diverse categorie o gruppi. Con Aspose.Words per .NET, puoi creare facilmente istogrammi che visualizzano in modo efficace i tuoi dati e forniscono informazioni preziose.

Utilizzando Aspose.Words per .NET, puoi automatizzare il processo di generazione di documenti con istogrammi, risparmiando tempo e fatica nella creazione manuale di documenti. La libreria offre un'ampia gamma di tipi di grafici e opzioni di personalizzazione, consentendoti di creare grafici visivamente accattivanti e ricchi di dati nei tuoi documenti Word.

### Domande frequenti

#### Q1. Cos'è un grafico a colonne?
Un grafico a colonne è un tipo di grafico che rappresenta i dati in barre o colonne verticali. Ogni colonna rappresenta in genere una categoria o un gruppo e l'altezza o la lunghezza della colonna indica il valore dei dati associati a tale categoria. I grafici a colonne vengono comunemente utilizzati per confrontare i dati di diverse categorie o per tenere traccia delle modifiche nel tempo.

#### Q2. Posso aggiungere più serie al grafico a colonne?
Sì, puoi aggiungere più serie al grafico a colonne utilizzando Aspose.Words per .NET. Ciascuna serie rappresenta un insieme di punti dati con le rispettive categorie e valori. Aggiungendo più serie, puoi confrontare e analizzare diversi set di dati all'interno dello stesso grafico, fornendo una visione completa dei tuoi dati.

#### Q3. Posso personalizzare l'aspetto del grafico a colonne?
Sì, utilizzando Aspose.Words per .NET, puoi personalizzare vari aspetti dell'aspetto dell'istogramma. Puoi modificare proprietà come il colore della serie, le etichette degli assi, la larghezza delle colonne e la formattazione dell'area del grafico. La libreria fornisce un ricco set di API per controllare gli elementi visivi del grafico e creare un aspetto personalizzato adatto alle tue esigenze.

#### Q4. Posso salvare il documento con l'istogramma inserito in diversi formati?
 Sì, Aspose.Words per .NET ti consente di salvare il documento con l'istogramma inserito in vari formati, come DOCX, PDF, HTML e altro. Puoi scegliere il formato di output desiderato in base alle tue esigenze e utilizzare il file`Save` metodo del`Document` oggetto per salvare il documento. L'istogramma inserito verrà conservato nel documento salvato.

#### Q5. Posso modificare i dati e l'aspetto dell'istogramma dopo averlo inserito?
Sì, dopo aver inserito l'istogramma nel documento, puoi modificarne i dati e l'aspetto utilizzando le API fornite da Aspose.Words per .NET. Puoi aggiornare i dati delle serie, modificare i colori delle colonne, personalizzare le proprietà degli assi e applicare opzioni di formattazione per creare grafici dinamici e interattivi nei tuoi documenti Word.