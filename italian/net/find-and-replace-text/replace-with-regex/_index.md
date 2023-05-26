---
title: Sostituisci con espressioni regolari
linktitle: Sostituisci con espressioni regolari
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come eseguire la sostituzione del testo basata su espressioni regolari in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/find-and-replace-text/replace-with-regex/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come usare la funzione Replace With Regex nella libreria Aspose.Words per .NET. Questa funzione consente di eseguire la sostituzione del testo in base a modelli specifici definiti da un'espressione regolare.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione di un nuovo documento

 Prima di iniziare a utilizzare la sostituzione delle espressioni regolari, è necessario creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Passaggio 2: inserire il testo nel documento

 Una volta che abbiamo un documento, possiamo inserire il testo usando a`DocumentBuilder` oggetto. Nel nostro esempio, usiamo il`Writeln` metodo per inserire la frase "sad crazy bad":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Passaggio 3: configurazione delle opzioni Trova e sostituisci

 Ora configureremo le opzioni di ricerca e sostituzione utilizzando a`FindReplaceOptions` oggetto. Nel nostro esempio, utilizziamo le opzioni predefinite:

```csharp
FindReplaceOptions options = new FindReplaceOptions();
```

## Passaggio 4: sostituisci con un'espressione regolare

 Noi uSiamo il`Range.Replace` metodo per eseguire la sostituzione del testo utilizzando un'espressione regolare. Nel nostro esempio, usiamo l'espressione regolare "[s|m]ad" to find the words "sad" and "mad" and replace them with the word "bad":

```csharp
doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);
```

## Passaggio 5: salvare il documento modificato

 Infine, salviamo il documento modificato in una directory specificata utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
```

### Esempio di codice sorgente per Replace With Regex utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'uso della sostituzione delle espressioni regolari con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	FindReplaceOptions options = new FindReplaceOptions();

	doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
  
```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come usare la funzione Replace With Regex di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per creare un documento, inserire testo, eseguire la sostituzione con un'espressione regolare e salvare il documento modificato.
