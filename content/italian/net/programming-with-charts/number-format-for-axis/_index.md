---
title: Formato numerico per l'asse in un grafico
linktitle: Formato numerico per l'asse in un grafico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare il formato numerico per un asse in un grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/number-format-for-axis/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per impostare il formato numerico per un asse in un grafico. Il codice sorgente fornito dimostra come creare un grafico, aggiungere dati di serie e formattare le etichette degli assi.

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

Aggiungi i dati della serie al grafico. In questo esempio aggiungeremo cinque elementi con i relativi valori corrispondenti.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Passaggio 4: formattare le etichette degli assi

 Per impostare il formato numerico per le etichette dell'asse Y, accedere a`AxisY` proprietà del grafico e impostare il file`NumberFormat.FormatCode` proprietà nel formato desiderato. In questo esempio, impostiamo il formato su "#,##0" per visualizzare i numeri con separatori delle migliaia.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Passaggio 5: salva il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Ciò completa l'implementazione dell'impostazione del formato numerico per l'asse utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per Number Format For Axis utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Conclusione

In questo tutorial, hai imparato come impostare il formato numerico per un asse in un grafico utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, puoi creare un nuovo documento, inserire un istogramma, aggiungere dati di serie e formattare le etichette degli assi per visualizzare i numeri in un formato specifico.

Aspose.Words per .NET fornisce potenti funzionalità per personalizzare l'aspetto dei grafici nei documenti di Word. Impostando il formato numerico per le etichette degli assi, puoi controllare il modo in cui vengono visualizzati i numeri, incluse opzioni come cifre decimali, separatori delle migliaia, simboli di valuta e altro. Ciò consente di presentare i dati numerici in modo chiaro e significativo.

Con Aspose.Words per .NET, hai la flessibilità di formattare vari aspetti del grafico, comprese le etichette degli assi. Impostando il formato numerico per l'asse, è possibile garantire la coerenza e migliorare la leggibilità del grafico, facilitando l'interpretazione dei valori rappresentati da parte degli utenti.

### Domande frequenti

#### Q1. Qual è il formato numerico di un asse in un grafico?
Il formato numerico per un asse in un grafico si riferisce alla formattazione applicata ai valori numerici visualizzati sull'asse. Ti consente di controllare come vengono presentati i numeri, comprese opzioni come cifre decimali, separatori delle migliaia, simboli di valuta, segni di percentuale e altro. Impostando il formato numerico, è possibile personalizzare l'aspetto dei dati numerici nel grafico in base alle proprie esigenze specifiche.

#### Q2. Come posso impostare il formato numerico per le etichette degli assi?
 Per impostare il formato numerico per le etichette degli assi in un grafico utilizzando Aspose.Words per .NET, è possibile accedere a`AxisY` proprietà del grafico e impostare il file`NumberFormat.FormatCode`proprietà al codice del formato desiderato. Il codice del formato segue la sintassi dei modelli di formattazione numerica standard e determina la modalità di visualizzazione dei numeri. Ad esempio, puoi utilizzare "#,##0.00" per visualizzare i numeri con due cifre decimali e separatori delle migliaia.

#### Q3. Posso impostare formati numerici diversi per le etichette dell'asse X e dell'asse Y?
Sì, puoi impostare diversi formati numerici per le etichette dell'asse X e dell'asse Y utilizzando Aspose.Words per .NET. Accedere al rispettivo asse (`AxisX` per l'asse X o`AxisY` per l'asse Y) del grafico e modificare il file`NumberFormat.FormatCode` proprietà individualmente per ciascun asse. Ciò ti consente di applicare diversi formati numerici alle etichette su ciascun asse in base ai tuoi requisiti specifici.

#### Q4. Quali sono alcuni codici di formato numerico comuni che posso utilizzare?
Aspose.Words per .NET supporta un'ampia gamma di codici di formato numerico che è possibile utilizzare per formattare le etichette degli assi in un grafico. Alcuni codici di formato comuni includono:

- `0` O`#` - Visualizza il numero senza cifre decimali.
- `0.00` O`#.00` - Visualizza il numero con due cifre decimali.
- `#,##0` Visualizza il numero con separatori di migliaia.
- `"€"0.00` - Visualizza il numero con il simbolo della valuta Euro e due cifre decimali.
- `"%"0` - Visualizza il numero come percentuale.

 Puoi trovare ulteriori informazioni sul numero[codici di formato](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) nel riferimento API di Aspose.Words per .NET.

#### Q5. Posso personalizzare altre proprietà delle etichette degli assi?
Sì, Aspose.Words per .NET fornisce un'ampia gamma di proprietà per personalizzare l'aspetto e il comportamento delle etichette degli assi. Oltre al formato del numero, puoi modificare proprietà quali carattere, dimensione, colore, orientamento, allineamento e altro. Ciò ti consente di personalizzare completamente le etichette degli assi in modo che corrispondano ai requisiti di stile e presentazione desiderati.