---
title: Imposta le opzioni predefinite per le etichette dati in un grafico
linktitle: Imposta le opzioni predefinite per le etichette dati in un grafico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come impostare le opzioni predefinite per le etichette dei dati in un grafico utilizzando Aspose.Words per .NET. Segui la nostra guida passo passo per creare e personalizzare i grafici senza sforzo.
type: docs
weight: 10
url: /it/net/programming-with-charts/default-options-for-data-labels/
---
## introduzione

Ehilà! Sei entusiasta di tuffarti nel mondo dell'automazione dei documenti? Oggi esploreremo come utilizzare Aspose.Words per .NET per creare documenti straordinari a livello di codice. Aspose.Words è una potente libreria che ti consente di manipolare facilmente i documenti di Word e in questo tutorial ci concentreremo sull'impostazione delle opzioni predefinite per le etichette dei dati in un grafico. Che tu sia uno sviluppatore esperto o un principiante, questa guida ti guiderà attraverso ogni passaggio per renderti operativo in pochissimo tempo.

## Prerequisiti

Prima di iniziare, assicuriamoci di avere tutto ciò di cui hai bisogno per seguire questo tutorial. Ecco una rapida lista di controllo:

- Visual Studio o qualsiasi altro IDE compatibile con .NET: qui è dove scriverai ed eseguirai il tuo codice.
-  Aspose.Words per .NET: puoi[scaricare l'ultima versione](https://releases.aspose.com/words/net/) e installalo nel tuo progetto.
- Conoscenza di base della programmazione C#: sebbene questa guida sia adatta ai principianti, sarà utile un po' di familiarità con C#.
- .NET Framework installato: assicurati di avere .NET Framework configurato sul tuo computer.
-  Una licenza temporanea per Aspose.Words: prendine una[Qui](https://purchase.aspose.com/temporary-license/) per sbloccare la piena funzionalità.

Una volta sistemati questi prerequisiti, siamo pronti a partire!

## Importa spazi dei nomi

Per prima cosa, configuriamo il nostro progetto e importiamo gli spazi dei nomi necessari. Questi spazi dei nomi sono fondamentali per accedere alla funzionalità Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.ReportingServices;
```

## Passaggio 1: crea un nuovo documento


 Il viaggio inizia creando un nuovo documento e inizializzando a`DocumentBuilder` . IL`DocumentBuilder` fornisce una serie di metodi per manipolare facilmente il contenuto del documento.

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un nuovo documento
Document doc = new Document();

// Inizializza DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Spiegazione

 In questo passaggio, abbiamo configurato il documento e il builder che utilizzeremo per inserire e formattare il nostro contenuto. IL`dataDir` la variabile contiene il percorso in cui salveremo il nostro documento finale.

## Passaggio 2: inserisci un grafico

 Successivamente, aggiungeremo un grafico a torta al nostro documento. IL`InsertChart` metodo del`DocumentBuilder` la lezione lo rende super facile.

```csharp
// Inserisci un grafico a torta
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);

// Accedi all'oggetto grafico
Chart chart = shape.Chart;
```

### Spiegazione

Qui stiamo inserendo un grafico a torta nel nostro documento. IL`InsertChart` Il metodo richiede il tipo di grafico, la larghezza e l'altezza come parametri. Dopo aver inserito il grafico, accediamo all'oggetto grafico per manipolarlo ulteriormente.

## Passaggio 3: personalizza la serie di grafici

Ora cancelleremo tutte le serie esistenti nel grafico e aggiungeremo le nostre serie personalizzate. Questa serie rappresenterà i nostri punti dati.

```csharp
// Cancella le serie di grafici esistenti
chart.Series.Clear();

// Aggiungi nuove serie al grafico
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

### Spiegazione

In questo passaggio, ci assicuriamo che il nostro grafico sia vuoto cancellando qualsiasi serie preesistente. Quindi, aggiungiamo una nuova serie con categorie e valori personalizzati, che verranno visualizzati nel nostro grafico a torta.

## Passaggio 4: impostare le opzioni predefinite per le etichette dati

Le etichette dei dati sono fondamentali per rendere il tuo grafico informativo. Imposteremo le opzioni per mostrare la percentuale, il valore e personalizzare il separatore.

```csharp
// Accedi alla raccolta delle etichette dati
ChartDataLabelCollection labels = series.DataLabels;

// Imposta le opzioni dell'etichetta dati
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

### Spiegazione

 Qui stiamo accedendo a`DataLabels`proprietà della nostra serie per personalizzare l'aspetto e le informazioni visualizzate su ciascuna etichetta dati. Abbiamo scelto di mostrare sia la percentuale che il valore, nascondere le linee guida e impostare un separatore personalizzato.

## Passaggio 5: salva il documento

Infine, salveremo il nostro documento nella directory specificata. Questo passaggio garantisce che tutte le nostre modifiche vengano scritte in un file.

```csharp
// Salva il documento
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

### Spiegazione

 In quest'ultimo passaggio, salviamo il nostro documento utilizzando il file`Save` metodo. Il documento verrà salvato nella directory specificata da`dataDir`, con il nome "WorkingWithCharts.DefaultOptionsForDataLabels.docx".

## Conclusione

E il gioco è fatto! Hai creato con successo un documento Word con un grafico a torta personalizzato utilizzando Aspose.Words per .NET. Questa potente libreria semplifica l'automazione della creazione e della manipolazione dei documenti, risparmiando tempo e fatica. Che tu stia generando report, fatture o qualsiasi altro tipo di documento, Aspose.Words ti copre.

 Sentiti libero di esplorare il[Documentazione Aspose.Words](https://reference.aspose.com/words/net/) per ulteriori funzionalità ed esempi. Buona programmazione!

## Domande frequenti

### Posso usare Aspose.Words gratuitamente?
Puoi utilizzare Aspose.Words gratuitamente con a[licenza temporanea](https://purchase.aspose.com/temporary-license/) o esplora le sue funzionalità utilizzando il[prova gratuita](https://releases.aspose.com/).

### Come posso ottenere supporto per Aspose.Words?
 Puoi ottenere supporto attraverso il[Forum di supporto di Aspose.Words](https://forum.aspose.com/c/words/8).

### Posso aggiungere altri tipi di grafici?
 Sì, Aspose.Words supporta vari tipi di grafici come grafici a barre, a linee e a colonne. Controlla il[documentazione](https://reference.aspose.com/words/net/) per ulteriori dettagli.

### Aspose.Words è compatibile con .NET Core?
 Sì, Aspose.Words è compatibile con .NET Core. Puoi trovare maggiori informazioni in[documentazione](https://reference.aspose.com/words/net/).

### Come posso acquistare una licenza per Aspose.Words?
 È possibile acquistare una licenza da[Aspose negozio](https://purchase.aspose.com/buy).

