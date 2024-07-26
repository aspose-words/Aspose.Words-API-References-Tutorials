---
title: Formato numerico per l'asse in un grafico
linktitle: Formato numerico per l'asse in un grafico
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come formattare i numeri degli assi del grafico utilizzando Aspose.Words per .NET con questa guida passo passo. Migliora la leggibilità e la professionalità del tuo documento senza sforzo.
type: docs
weight: 10
url: /it/net/programming-with-charts/number-format-for-axis/
---
## introduzione

Ehilà! Hai mai lavorato con i grafici nei tuoi documenti e vorresti poter formattare i numeri sul tuo asse per farli sembrare più professionali? Bene, sei fortunato! In questo tutorial, approfondiremo come ottenere questo risultato utilizzando Aspose.Words per .NET. Questa potente libreria ti consente di gestire i documenti Word in un modo semplicissimo. E oggi ci concentreremo sul rinnovamento degli assi del grafico con formati numerici personalizzati.

## Prerequisiti

Prima di iniziare, assicuriamoci che tu abbia tutto ciò di cui hai bisogno. Ecco una rapida lista di controllo:

-  Aspose.Words per .NET: assicurati di averlo installato. In caso contrario, puoi[scaricalo qui](https://releases.aspose.com/words/net/).
- .NET Framework: assicurati di avere installato un .NET Framework compatibile.
- Ambiente di sviluppo: un IDE come Visual Studio funzionerà perfettamente.
- Conoscenza di base di C#: questo ti aiuterà a seguire gli esempi di codifica.

## Importa spazi dei nomi

Per prima cosa, devi importare gli spazi dei nomi necessari nel tuo progetto. È come gettare le fondamenta prima di costruire una casa. Aggiungi le seguenti direttive using nella parte superiore del file di codice:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Reporting;
```

Ora suddividiamo il processo in passaggi semplici e facili da seguire.

## Passaggio 1: impostazione del documento

Intestazione: Inizializza il tuo documento

Innanzitutto, devi creare un nuovo documento e un generatore di documenti. Pensa a questo passaggio come a preparare la tela e il pennello prima di iniziare il tuo capolavoro.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Qui,`dataDir` è il percorso della directory dei documenti in cui salverai il file finale.`Document`E`DocumentBuilder` sono classi di Aspose.Words che ti aiutano a creare e manipolare documenti Word.

## Passaggio 2: inserimento di un grafico

Titolo: Aggiungi un grafico al tuo documento

Successivamente, aggiungiamo un grafico al tuo documento. È qui che inizia la magia. Inseriremo un istogramma che fungerà da tela bianca.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

 IL`InsertChart` Il metodo inserisce un grafico del tipo (colonna in questo caso) e delle dimensioni specificati nel documento.

## Passaggio 3: personalizzare la serie di grafici

Titolo: Compila il tuo grafico con i dati

Ora dobbiamo aggiungere alcuni dati al nostro grafico. Questo passaggio equivale a riempire il grafico con informazioni significative.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

 Qui stiamo aggiungendo una nuova serie chiamata "Aspose Series 1" con cinque punti dati. IL`Series.Clear` Il metodo garantisce che tutti i dati preesistenti vengano rimossi prima di aggiungere la nostra nuova serie.

## Passaggio 4: formattazione dei numeri degli assi

Intestazione: Abbellisci i numeri dei tuoi assi

Infine, formattiamo i numeri sull'asse Y per renderli più leggibili. È come dare gli ultimi ritocchi alla tua opera d'arte.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

 IL`FormatCode` La proprietà consente di impostare un formato personalizzato per i numeri sull'asse. In questo esempio,`#,##0`garantisce che i numeri grandi vengano visualizzati con virgole per le migliaia.

## Passaggio 5: salvataggio del documento

Titolo: Salva il tuo capolavoro

Ora che tutto è impostato, è il momento di salvare il documento. Questo passaggio è la grande rivelazione del tuo lavoro.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

 Ecco, il`Save` Il metodo salva il documento nel percorso specificato con il nome file`WorkingWithCharts.NumberFormatForAxis.docx`.

## Conclusione

E il gioco è fatto! Hai formattato con successo i numeri sull'asse Y del tuo grafico utilizzando Aspose.Words per .NET. Ciò non solo conferisce ai tuoi grafici un aspetto più professionale, ma migliora anche la leggibilità. Aspose.Words offre una vasta gamma di funzionalità che possono aiutarti a creare straordinari documenti Word a livello di programmazione. Quindi, perché non esplorare di più e vedere cos'altro puoi fare?

## Domande frequenti

### Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una potente libreria che consente agli sviluppatori di creare, manipolare e convertire documenti Word a livello di codice.

### Posso formattare altri aspetti del grafico oltre ai numeri degli assi?
Assolutamente! Aspose.Words per .NET ti consente di formattare titoli, etichette e persino personalizzare l'aspetto del grafico.

### È disponibile una prova gratuita per Aspose.Words per .NET?
 Sì, puoi ottenere un[prova gratuita qui](https://releases.aspose.com/).

### Posso utilizzare Aspose.Words per .NET con altri linguaggi .NET oltre a C#?
Sì, Aspose.Words per .NET è compatibile con qualsiasi linguaggio .NET, inclusi VB.NET e F#.

### Dove posso trovare documentazione più dettagliata?
 La documentazione dettagliata è disponibile su[Aspose.Words per la pagina della documentazione .NET](https://reference.aspose.com/words/net/).
