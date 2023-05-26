---
title: Trova semplice Sostituisci
linktitle: Trova semplice Sostituisci
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come eseguire una semplice sostituzione di ricerca in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/find-and-replace-text/simple-find-replace/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come usare la funzione Simple Find Replace nella libreria Aspose.Words per .NET. Questa funzione consente di eseguire una semplice sostituzione del testo cercando una specifica stringa di caratteri e sostituendola con un'altra stringa di caratteri in un documento Word.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione di un nuovo documento

 Prima di iniziare a utilizzare la semplice ricerca e sostituzione, è necessario creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Passaggio 2: inserire il testo nel documento

 Una volta che abbiamo un documento, possiamo inserire il testo usando a`DocumentBuilder` oggetto. Nel nostro esempio, usiamo il`Writeln` metodo per inserire la frase "Ciao_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Passaggio 3: semplice sostituzione del testo

 Noi usiamo il`Range.Replace` metodo per eseguire semplici sostituzioni di testo. Nel nostro esempio, sostituiamo tutte le occorrenze della stringa "_ClientName_ " con "James Bond" usando il`FindReplaceOptions` opzione con il`FindReplaceDirection.Forward` direzione di ricerca:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Passaggio 4: salvare il documento modificato

 Infine, salviamo il documento modificato in una directory specificata utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Esempio di codice sorgente per Simple Find Replace utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'uso della semplice ricerca e sostituzione con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Salva il documento modificato
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come usare la funzione Simple Find Replace di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per creare un documento, inserire testo, eseguire una semplice sostituzione del testo e salvare il documento modificato.
