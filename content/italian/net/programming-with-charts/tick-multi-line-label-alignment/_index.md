---
title: Spuntare l'allineamento delle etichette su più righe in un grafico
linktitle: Spuntare l'allineamento delle etichette su più righe in un grafico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come allineare le etichette su più righe in un asse del grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/tick-multi-line-label-alignment/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per impostare l'allineamento delle etichette su più righe in un asse del grafico. Il codice sorgente fornito dimostra come creare un grafico, accedere all'asse e modificare l'allineamento dell'etichetta del segno di spunta.

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

 Successivamente, utilizzare il`InsertChart` metodo del`DocumentBuilder` per inserire un grafico a dispersione nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Passaggio 3: impostare l'allineamento dell'etichetta di spunta

 Per impostare l'allineamento delle etichette multiriga, accedi al file`AxisX` proprietà del grafico e impostare il file`TickLabelAlignment` proprietà all'allineamento desiderato. In questo esempio, impostiamo l'allineamento su`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Passaggio 4: salva il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Ciò completa l'implementazione dell'impostazione dell'allineamento dell'etichetta su più righe utilizzando Aspose.Words per .NET.

### Codice sorgente di esempio per l'allineamento delle etichette Tick Multi Line utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Questa proprietà ha effetto solo per le etichette su più righe.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Conclusione

In questo tutorial, hai imparato come impostare l'allineamento delle etichette su più righe in un asse del grafico utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, puoi creare un nuovo documento, inserire un grafico a dispersione, accedere all'asse del grafico e modificare l'allineamento dell'etichetta di spunta.

Aspose.Words per .NET fornisce potenti funzionalità per manipolare i grafici nei documenti Word. Le etichette su più righe sono utili quando le etichette degli assi contengono testo lungo che richiede il ritorno a capo o la suddivisione su più righe. Impostando l'allineamento delle etichette di spunta, puoi controllare l'allineamento orizzontale delle etichette su più righe all'interno dell'asse del grafico, garantendo presentazione e leggibilità ottimali.

La personalizzazione dell'allineamento delle etichette su più righe consente di ottimizzare l'aspetto del grafico, soprattutto quando si tratta di etichette lunghe o complesse. Allineando le etichette a destra, a sinistra, al centro o giustificate, puoi ottenere una disposizione equilibrata e visivamente accattivante delle etichette di spunta lungo l'asse.

Con Aspose.Words per .NET, puoi facilmente accedere e modificare la proprietà di allineamento delle etichette di spunta di un asse del grafico, fornendoti il pieno controllo sull'aspetto e sul layout delle etichette di spunta nei grafici dei documenti Word.

### Domande frequenti

#### Q1. Cosa sono le etichette multilinea in un asse del grafico?
Le etichette su più righe nell'asse del grafico si riferiscono alle etichette dell'asse che si estendono su più righe quando il testo dell'etichetta è lungo o richiede il ritorno a capo per adattarsi allo spazio disponibile. Invece di troncare il testo dell'etichetta o creare confusione visiva, l'asse del grafico divide automaticamente le etichette in più righe per garantirne la leggibilità. Le etichette su più righe sono particolarmente utili quando si ha a che fare con etichette di categorie o valori lunghe nei grafici.

#### Q2. Posso personalizzare l'allineamento delle etichette dei segni di spunta nell'asse di un grafico?
 Sì, puoi personalizzare l'allineamento delle etichette di spunta in un asse del grafico utilizzando Aspose.Words per .NET. Accedendo al`TickLabelAlignment` proprietà del`ChartAxis` oggetto, è possibile impostare l'allineamento desiderato per le etichette dei segni di spunta. Le opzioni di allineamento includono l'allineamento a sinistra, a destra, al centro o giustificato. La regolazione dell'allineamento consente di controllare il posizionamento orizzontale delle etichette dei segni di spunta lungo l'asse del grafico, garantendo una corretta leggibilità e presentazione visiva.

#### Q3. Quando dovrei considerare di modificare l'allineamento dell'etichetta di spunta nell'asse di un grafico?
La modifica dell'allineamento delle etichette di spunta nell'asse di un grafico è utile quando si hanno etichette lunghe o su più righe che richiedono presentazione e leggibilità ottimali. Regolando l'allineamento, puoi garantire che le etichette siano allineate e distanziate correttamente, evitando sovrapposizioni o troncamenti. Valuta la possibilità di modificare l'allineamento delle etichette di graduazione quando hai a che fare con grafici con nomi di categoria lunghi, etichette di valori dettagliate o qualsiasi altro scenario in cui l'allineamento predefinito non fornisce l'aspetto visivo desiderato.

#### Q4. L'allineamento delle etichette di spunta influisce sulle etichette a riga singola nell'asse del grafico?
No, la proprietà di allineamento delle etichette di spunta non influisce sulle etichette a riga singola nell'asse del grafico. È specificamente progettato per etichette multilinea che richiedono l'avvolgimento o la suddivisione. Le etichette a riga singola vengono allineate in base alle impostazioni di allineamento predefinite dell'asse del grafico. La proprietà di allineamento dell'etichetta con segno di spunta si applica solo alle etichette che si estendono su più righe, consentendo di controllare l'allineamento di ciascuna riga all'interno dell'etichetta su più righe.

#### Q5. Posso allineare le etichette dei segni di spunta in modo diverso per l'asse X e l'asse Y in un grafico?
 Sì, puoi allineare le etichette dei segni di spunta in modo diverso per l'asse X e l'asse Y in un grafico utilizzando Aspose.Words per .NET. La proprietà di allineamento dell'etichetta di graduazione è specifica per ciascun asse del grafico. Accedendo al corrispondente`ChartAxis` oggetto per l'asse X o l'asse Y, è possibile impostare in modo indipendente l'allineamento dell'etichetta di spunta su valori diversi. Ciò ti offre la flessibilità di allineare le etichette dei segni di spunta in modo diverso in base ai tuoi requisiti specifici per ciascun asse nel grafico.