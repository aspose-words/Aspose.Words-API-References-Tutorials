---
title: Personalizza l'etichetta dei dati del grafico
linktitle: Personalizza l'etichetta dei dati del grafico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come aggiungere e personalizzare le etichette dei dati in un grafico utilizzando Aspose.Words per .NET per fornire ulteriori informazioni sui punti dati.
type: docs
weight: 10
url: /it/net/programming-with-charts/chart-data-label/
---

Questo tutorial spiega come aggiungere e personalizzare le etichette dei dati in un grafico utilizzando Aspose.Words per .NET. Le etichette dati forniscono informazioni aggiuntive sui punti dati in un grafico.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# ed elaborazione testi con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui desideri salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: crea un nuovo documento e DocumentBuilder
 Crea una nuova istanza di`Document` classe e a`DocumentBuilder` oggetto di lavorare con il documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 3: inserisci e configura un grafico
 Inserisci un grafico nel documento utilizzando il comando`InsertChart` metodo del`DocumentBuilder` oggetto. Imposta il tipo di grafico e le dimensioni desiderate.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Passaggio 4: personalizzare le etichette dati
Accedi alla raccolta di etichette dati delle serie di grafici e modifica varie proprietà per personalizzare l'aspetto delle etichette dati.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Passaggio 5: salva il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Codice sorgente di esempio per l'etichetta dati del grafico utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// Per impostazione predefinita, quando aggiungi etichette dati ai punti dati in un grafico a torta, vengono visualizzate le linee guida per le etichette dati che lo sono
	// posizionato molto al di fuori della fine dei punti dati. Le linee guida creano una connessione visiva tra un'etichetta dati e la sua
	// punto dati corrispondente.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

Questo è tutto! Hai aggiunto e personalizzato con successo le etichette dei dati in un grafico utilizzando Aspose.Words per .NET.

## Conclusione
In questo tutorial, hai imparato come aggiungere e personalizzare le etichette dei dati in un grafico utilizzando Aspose.Words per .NET. Seguendo la guida passo passo, puoi inserire un grafico, accedere alla raccolta di etichette dati e modificare le proprietà per personalizzare l'aspetto delle etichette dati. Aspose.Words per .NET fornisce una potente API per l'elaborazione di parole con documenti e grafici di Word, consentendo di creare grafici visivamente accattivanti e informativi con etichette di dati personalizzate.

### Domande frequenti

#### Q1. Cosa sono le etichette dati in un grafico?
Le etichette dati in un grafico forniscono informazioni aggiuntive sui punti dati rappresentati nel grafico. Possono visualizzare valori, categorie, nomi di serie, percentuali o altri dettagli rilevanti a seconda del tipo di grafico e della configurazione.

#### Q2. Posso personalizzare l'aspetto delle etichette dati?
Sì, puoi personalizzare l'aspetto delle etichette dati in un grafico. Aspose.Words per .NET fornisce opzioni per modificare varie proprietà delle etichette dati, come mostrare chiavi di legenda, linee direttrici, nomi di categorie, nomi di serie, valori e altro. Puoi anche impostare separatori e formattare le etichette per soddisfare i tuoi requisiti specifici.

#### Q3. Posso aggiungere etichette dati a qualsiasi tipo di grafico?
Sì, puoi aggiungere etichette dati a vari tipi di grafici, inclusi grafici a barre, grafici a torta, grafici a linee e altro ancora. Il processo di aggiunta e personalizzazione delle etichette dati può variare leggermente a seconda del tipo di grafico e della libreria o dello strumento che stai utilizzando.
