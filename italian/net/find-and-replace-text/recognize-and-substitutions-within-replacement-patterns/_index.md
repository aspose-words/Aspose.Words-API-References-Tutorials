---
title: Riconoscere e sostituzioni all'interno di modelli di sostituzione
linktitle: Riconoscere e sostituzioni all'interno di modelli di sostituzione
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare i modelli di sostituzione con riconoscimenti e sostituzioni in Aspose.Words per .NET per manipolare i documenti di Word.
type: docs
weight: 10
url: /it/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

In questo articolo, esploreremo il codice sorgente C# precedente per comprendere come utilizzare la funzione Riconosci e sostituzioni all'interno dei modelli di sostituzione nella libreria Aspose.Words per .NET. Questa funzione aiuta a riconoscere schemi di ricerca complessi ed eseguire sostituzioni basate su gruppi acquisiti durante la manipolazione del documento.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione di un nuovo documento

 Prima di iniziare a utilizzare corrispondenze e sostituzioni nei modelli di sostituzione, è necessario creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto:

```csharp
Document doc = new Document();
```

## Passaggio 2: inserire il testo nel documento

 Una volta che abbiamo un documento, possiamo inserire il testo usando a`DocumentBuilder`oggetto. Nel nostro esempio, stiamo usando il`Write` metodo per inserire la frase "Jason dà a Paul dei soldi". :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Passaggio 3: Riconoscimenti e sostituzioni nei modelli di sostituzione

 Ora useremo il`Range.Replace` funzione per eseguire la ricerca e la sostituzione del testo utilizzando un'espressione regolare per riconoscere modelli specifici. Nel nostro esempio, usiamo l'espressione regolare`([A-z]+) gives money to ([A-z]+)` riconoscere frasi in cui qualcuno dà soldi a qualcun altro. Usiamo il modello di sostituzione`$2 takes money from $1` effettuare la sostituzione invertendo i ruoli. L'impiego di`$1` E`$2` si riferisce ai gruppi catturati dall'espressione regolare:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Esempio di codice sorgente per Riconosci e sostituzioni all'interno di modelli di sostituzione utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per illustrare l'uso di corrispondenze e sostituzioni nei modelli di sostituzione con Aspose.Words per .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per comprendere come utilizzare la funzionalità Riconosci e sostituzioni all'interno dei modelli di sostituzione di Aspose.Words per .NET. Abbiamo seguito una guida dettagliata per creare un documento, inserire testo, eseguire ricerca e sostituzione utilizzando espressioni regolari e modelli di sostituzione basati su gruppi acquisiti e manipolare il documento.
