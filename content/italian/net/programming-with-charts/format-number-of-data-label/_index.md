---
title: Formato Numero di etichette dati in un grafico
linktitle: Formato Numero di etichette dati in un grafico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come formattare le etichette dei dati nei grafici utilizzando Aspose.Words per .NET con questa guida passo passo. Migliora i tuoi documenti Word senza sforzo.
type: docs
weight: 10
url: /it/net/programming-with-charts/format-number-of-data-label/
---
## Introduzione

La creazione di documenti accattivanti e informativi spesso implica l'inclusione di grafici con etichette dati ben formattate. Se sei uno sviluppatore .NET che desidera migliorare i tuoi documenti Word con grafici sofisticati, Aspose.Words per .NET è una fantastica libreria per aiutarti a raggiungere questo obiettivo. Questo tutorial ti guiderà attraverso il processo di formattazione delle etichette dei numeri in un grafico utilizzando Aspose.Words per .NET, passo dopo passo.

## Prerequisiti

Prima di immergerti nel codice, ci sono alcuni prerequisiti che devi avere:

-  Aspose.Words per .NET: assicurati di aver installato la libreria Aspose.Words per .NET. Se non l'hai ancora installato, puoi farlo[scaricalo qui](https://releases.aspose.com/words/net/).
- Ambiente di sviluppo: è necessario avere configurato un ambiente di sviluppo .NET. Visual Studio è altamente raccomandato.
- Conoscenza di base di C#: la familiarità con la programmazione C# è essenziale poiché questo tutorial prevede la scrittura e la comprensione del codice C#.
-  Licenza temporanea: per utilizzare Aspose.Words senza limitazioni, puoi ottenere a[licenza temporanea](https://purchase.aspose.com/temporary-license/).

Ora, tuffiamoci nel processo passo passo di formattazione delle etichette dei numeri in un grafico.

## Importa spazi dei nomi

Per prima cosa, dobbiamo importare gli spazi dei nomi necessari per lavorare con Aspose.Words per .NET. Aggiungi le seguenti righe nella parte superiore del file C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Passaggio 1: imposta la directory dei documenti

Prima di poter iniziare a manipolare il tuo documento Word, devi specificare la directory in cui verrà salvato il documento. Ciò è essenziale per l'operazione di salvataggio successiva.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory dei documenti.

## Passaggio 2: inizializzare il documento e DocumentBuilder

 Il passo successivo è inizializzare un nuovo file`Document` e un`DocumentBuilder` . IL`DocumentBuilder` è una classe helper che ci consente di costruire il contenuto del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserire un grafico nel documento

 Ora inseriamo un grafico nel documento utilizzando il file`DocumentBuilder`. In questo tutorial utilizzeremo un grafico a linee come esempio.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

Qui inseriamo un grafico a linee con larghezza e altezza specifiche e impostiamo il titolo del grafico.

## Passaggio 4: cancella la serie predefinita e aggiungi nuova serie

Per impostazione predefinita, il grafico avrà alcune serie pregenerate. Dobbiamo cancellarli e aggiungere le nostre serie con punti dati specifici.

```csharp
// Elimina le serie generate predefinite.
chart.Series.Clear();

// Aggiungi nuove serie con punti dati personalizzati.
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
	new string[] { "Category 1", "Category 2", "Category 3" }, 
	new double[] { 2.5, 1.5, 3.5 });
```

## Passaggio 5: attiva le etichette dati

Per visualizzare le etichette dati sul grafico, dobbiamo abilitarle per le nostre serie.

```csharp
series1.HasDataLabels = true;
series1.DataLabels.ShowValue = true;
```

## Passaggio 6: formattare le etichette dati

Il nocciolo di questo tutorial è la formattazione delle etichette dei dati. Possiamo applicare diversi formati numerici a ciascuna etichetta dati individualmente.

```csharp
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00"; // Formato valuta
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy"; // Formato data
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%"; // Formato percentuale
```

 Inoltre, puoi collegare il formato di un'etichetta dati a una cella di origine. Quando collegato, il`NumberFormat` verrà reimpostato su generale ed ereditato dalla cella di origine.

```csharp
series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
```

## Passaggio 7: salva il documento

Infine, salva il documento nella directory specificata.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Ciò salva il documento con il nome specificato e garantisce che il grafico con etichette dati formattate venga preservato.

## Conclusione

La formattazione delle etichette dati in un grafico utilizzando Aspose.Words per .NET può migliorare notevolmente la leggibilità e la professionalità dei tuoi documenti Word. Seguendo questa guida passo passo, ora dovresti essere in grado di creare un grafico, aggiungere serie di dati e formattare le etichette dei dati per soddisfare le tue esigenze. Aspose.Words per .NET è un potente strumento che consente un'ampia personalizzazione e automazione dei documenti Word, rendendolo una risorsa inestimabile per gli sviluppatori .NET.

## Domande frequenti

### Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una potente libreria per creare, manipolare e convertire documenti Word a livello di codice utilizzando C#.

### Posso formattare altri tipi di grafici con Aspose.Words per .NET?
Sì, Aspose.Words per .NET supporta una varietà di tipi di grafici, tra cui barre, colonne, torta e altro.

### Come posso ottenere una licenza temporanea per Aspose.Words per .NET?
 È possibile ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).

### È possibile collegare le etichette dei dati alle celle di origine in Excel?
Sì, puoi collegare le etichette dati alle celle di origine, consentendo l'ereditarietà del formato numerico dalla cella di origine.

### Dove posso trovare una documentazione più dettagliata per Aspose.Words per .NET?
 È possibile trovare una documentazione completa[Qui](https://reference.aspose.com/words/net/).
