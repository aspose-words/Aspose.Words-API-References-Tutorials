---
title: Spuntare l'allineamento delle etichette multilinea in un grafico
linktitle: Spuntare l'allineamento delle etichette multilinea in un grafico
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come allineare le etichette multilinea del segno di spunta in un asse del grafico utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-charts/tick-multi-line-label-alignment/
---

Questo tutorial spiega come utilizzare Aspose.Words per .NET per impostare l'allineamento delle etichette multilinea tick in un asse del grafico. Il codice sorgente fornito mostra come creare un grafico, accedere all'asse e modificare l'allineamento dell'etichetta tick.

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

 Quindi, usa il`InsertChart` metodo del`DocumentBuilder` per inserire un grafico a dispersione nel documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Passaggio 3: impostare l'allineamento dell'etichetta del segno di spunta

 Per impostare l'allineamento delle etichette multilinea del segno di spunta, accedere a`AxisX` proprietà del grafico e impostare la`TickLabelAlignment` proprietà all'allineamento desiderato. In questo esempio, impostiamo l'allineamento su`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Passaggio 4: salvare il documento

 Infine, salva il documento nella directory specificata utilizzando il file`Save` metodo del`Document` oggetto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Questo completa l'implementazione dell'impostazione dell'allineamento dell'etichetta su più righe tick utilizzando Aspose.Words per .NET.

### Esempio di codice sorgente per Tick Multi Line Label Alignment utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Questa proprietà ha effetto solo per le etichette multilinea.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

## Conclusione

In questo tutorial, hai imparato come impostare l'allineamento delle etichette tick multilinea in un asse del grafico utilizzando Aspose.Words per .NET. Seguendo la guida passo-passo e utilizzando il codice sorgente fornito, è possibile creare un nuovo documento, inserire un grafico a dispersione, accedere all'asse del grafico e modificare l'allineamento dell'etichetta tick.

Aspose.Words per .NET fornisce potenti funzionalità per manipolare i grafici nei documenti di Word. Le etichette con segno di spunta su più righe sono utili quando le etichette degli assi contengono testo lungo che richiede il ritorno a capo o la suddivisione su più righe. Impostando l'allineamento delle etichette tick, è possibile controllare l'allineamento orizzontale delle etichette multilinea all'interno dell'asse del grafico, garantendo una presentazione e una leggibilità ottimali.

La personalizzazione dell'allineamento dell'etichetta su più righe consente di ottimizzare l'aspetto del grafico, in particolare quando si tratta di etichette lunghe o complesse. Allineando le etichette a destra, a sinistra, al centro o giustificate, è possibile ottenere una disposizione bilanciata e visivamente accattivante delle etichette di spunta lungo l'asse.

Con Aspose.Words per .NET, puoi facilmente accedere e modificare la proprietà di allineamento delle etichette di spunta di un asse del grafico, fornendoti il pieno controllo sull'aspetto e sul layout delle etichette di spunta nei grafici dei documenti di Word.

### Domande frequenti

#### Q1. Cosa sono le etichette tick multilinea in un asse del grafico?
Le etichette spuntate su più righe in un asse del grafico si riferiscono alle etichette dell'asse che si estendono su più righe quando il testo dell'etichetta è lungo o richiede il ritorno a capo per adattarsi allo spazio disponibile. Invece di troncare il testo dell'etichetta o causare disordine visivo, l'asse del grafico suddivide automaticamente le etichette in più righe per garantire la leggibilità. Le etichette tick su più righe sono particolarmente utili quando si ha a che fare con etichette lunghe di categorie o valori nei grafici.

#### D2. Posso personalizzare l'allineamento delle etichette dei tick in un asse del grafico?
 Sì, puoi personalizzare l'allineamento delle etichette delle tacche in un asse del grafico utilizzando Aspose.Words per .NET. Accedendo al`TickLabelAlignment` proprietà del`ChartAxis` oggetto, è possibile impostare l'allineamento desiderato per le etichette delle tacche. Le opzioni di allineamento includono l'allineamento a sinistra, a destra, al centro o giustificato. La regolazione dell'allineamento consente di controllare il posizionamento orizzontale delle etichette dei tick lungo l'asse del grafico, garantendo una corretta leggibilità e presentazione visiva.

#### D3. Quando dovrei prendere in considerazione la possibilità di modificare l'allineamento dell'etichetta tick in un asse del grafico?
La modifica dell'allineamento dell'etichetta del segno di spunta in un asse del grafico è vantaggiosa quando si hanno etichette lunghe o multilinea che richiedono una presentazione e una leggibilità ottimali. Regolando l'allineamento, puoi assicurarti che le etichette siano correttamente allineate e distanziate, evitando sovrapposizioni o troncamenti. Prendi in considerazione la possibilità di modificare l'allineamento dell'etichetta del segno di spunta quando hai a che fare con grafici con nomi di categoria lunghi, etichette di valori dettagliate o qualsiasi altro scenario in cui l'allineamento predefinito non fornisce l'aspetto visivo desiderato.

#### D4. L'allineamento dell'etichetta del segno di spunta influisce sulle etichette a riga singola in un asse del grafico?
No, la proprietà di allineamento dell'etichetta del segno di spunta non influisce sulle etichette a riga singola in un asse del grafico. È specificamente progettato per etichette multilinea che richiedono l'avvolgimento o la divisione. Le etichette a riga singola sono allineate in base alle impostazioni di allineamento predefinite dell'asse del grafico. La proprietà di allineamento dell'etichetta del segno di spunta si applica solo alle etichette che si estendono su più righe, consentendo di controllare l'allineamento di ciascuna riga all'interno dell'etichetta su più righe.

#### Q5. Posso allineare le etichette dei tick in modo diverso per l'asse X e l'asse Y in un grafico?
 Sì, puoi allineare le etichette delle tacche in modo diverso per l'asse X e l'asse Y in un grafico utilizzando Aspose.Words per .NET. La proprietà di allineamento dell'etichetta del segno di spunta è specifica per ogni asse del grafico. Accedendo al corrispondente`ChartAxis` oggetto per l'asse X o l'asse Y, è possibile impostare indipendentemente l'allineamento dell'etichetta di spunta su valori diversi. Ciò ti offre la flessibilità di allineare le etichette dei tick in modo diverso in base ai tuoi requisiti specifici per ciascun asse del grafico.