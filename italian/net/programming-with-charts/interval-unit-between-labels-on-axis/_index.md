---
title: Unità di intervallo tra le etichette sull'asse di un grafico
linktitle: Unità di intervallo tra le etichette sull'asse di un grafico
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come impostare l'unità di intervallo tra le etichette sull'asse di un grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per impostare l'unità di intervallo tra le etichette sull'asse di un grafico. Il codice sorgente fornito mostra come creare un grafico, aggiungere dati di serie e personalizzare le etichette degli assi.

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

 Quindi, usa il`InsertChart` metodo del`DocumentBuilder` per inserire un istogramma nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 3: aggiungi i dati della serie al grafico

Aggiungi i dati della serie al grafico. In questo esempio, aggiungeremo cinque elementi con i valori corrispondenti.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Passaggio 4: personalizzare le etichette degli assi

 Per impostare l'unità di intervallo tra le etichette sull'asse X, accedere a`AxisX` proprietà del grafico e impostare la`TickLabelSpacing` proprietà al valore desiderato. In questo esempio, impostiamo la spaziatura su 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Passaggio 5: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Questo completa l'implementazione dell'impostazione dell'unità di intervallo tra le etichette sull'asse utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Interval Unit Between Labels On Axis utilizzando Aspose.Words per .NET 

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
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

## Conclusione

In questo tutorial, hai imparato come impostare l'unità di intervallo tra le etichette sull'asse di un grafico utilizzando Aspose.Words per .NET. Seguendo la guida passo-passo e utilizzando il codice sorgente fornito, puoi creare un nuovo documento, inserire un istogramma, aggiungere dati di serie e personalizzare le etichette degli assi per controllare la spaziatura tra le etichette.

Aspose.Words per .NET fornisce potenti funzionalità per manipolare i grafici nei documenti di Word. Impostando l'unità di intervallo tra le etichette sull'asse, è possibile controllare la densità di visualizzazione delle etichette e migliorare la leggibilità dei grafici. Ciò consente di ottimizzare la presentazione dei dati e migliorare l'esperienza complessiva dell'utente.

Con Aspose.Words per .NET, hai la flessibilità di personalizzare vari aspetti del grafico, comprese le etichette degli assi. È possibile impostare l'unità di intervallo desiderata per garantire che le etichette siano adeguatamente distanziate e forniscano una rappresentazione chiara dei punti dati.

### Domande frequenti

#### Q1. Cosa sono le etichette degli assi in un grafico?
Le etichette degli assi in un grafico si riferiscono alla rappresentazione testuale dei valori lungo l'asse orizzontale (asse X) o verticale (asse Y) del grafico. Queste etichette aiutano a identificare e interpretare i punti dati tracciati sul grafico. Le etichette degli assi forniscono un contesto e consentono agli utenti di comprendere la scala e l'intervallo di valori nel grafico.

#### D2. Come posso personalizzare la spaziatura tra le etichette degli assi?
 Per personalizzare la spaziatura tra le etichette degli assi in un grafico utilizzando Aspose.Words per .NET, è possibile accedere a`AxisX` O`AxisY` proprietà del grafico e modificare il file`TickLabelSpacing` proprietà. Impostando il`TickLabelSpacing` ad un valore specifico, è possibile controllare l'unità di intervallo tra le etichette sul rispettivo asse, regolando la spaziatura in base alle proprie esigenze.

#### D3. Posso impostare una spaziatura diversa per le etichette dell'asse X e dell'asse Y?
Sì, puoi impostare una spaziatura diversa per le etichette dell'asse X e dell'asse Y utilizzando Aspose.Words per .NET. Accedere al rispettivo asse (`AxisX` per l'asse X o`AxisY` per l'asse Y) del grafico e modificare il file`TickLabelSpacing`proprietà singolarmente per ciascun asse. Ciò consente di avere diverse unità di intervallo e spaziatura per le etichette sull'asse X e sull'asse Y, fornendo un controllo granulare sull'aspetto del grafico.

#### D4. Qual è il significato dell'unità di intervallo tra le etichette sull'asse?
L'unità di intervallo tra le etichette sull'asse determina la spaziatura tra le etichette consecutive visualizzate sul grafico. Impostando l'unità di intervallo, è possibile controllare la densità delle etichette e assicurarsi che siano opportunamente distanziate per evitare il sovraffollamento e la sovrapposizione. La regolazione dell'unità di intervallo consente di presentare i dati in modo più leggibile e visivamente accattivante.

#### Q5. Posso modificare altre proprietà delle etichette degli assi?
Sì, Aspose.Words per .NET offre un'ampia gamma di proprietà per personalizzare l'aspetto e il comportamento delle etichette degli assi. È possibile modificare proprietà come carattere, dimensione, colore, orientamento, allineamento e altro per ottenere la formattazione e lo stile desiderati per le etichette degli assi. La libreria offre un ampio controllo sugli elementi del grafico, consentendoti di creare grafici dall'aspetto professionale su misura per le tue esigenze specifiche.