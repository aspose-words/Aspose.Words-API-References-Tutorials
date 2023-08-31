---
title: Testo semplice Trova e sostituisci in Word
linktitle: Testo semplice Trova e sostituisci in Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come eseguire una semplice ricerca e sostituzione di testo in un documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/find-and-replace-text/simple-find-replace/
---
In questo articolo, esploreremo il codice sorgente C# riportato sopra per comprendere come utilizzare la funzione Trova e sostituisci testo semplice in Word nella libreria Aspose.Words per .NET. Questa funzionalità consente di eseguire una semplice sostituzione del testo cercando una stringa di caratteri specifica e sostituendola con un'altra stringa di caratteri in un documento di Word.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione di un nuovo documento

 Prima di iniziare a utilizzare la semplice ricerca e sostituzione, dobbiamo creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Passaggio 2: inserisci il testo nel documento

 Una volta che abbiamo un documento, possiamo inserire del testo usando a`DocumentBuilder` oggetto. Nel nostro esempio, utilizziamo il file`Writeln` metodo per inserire la frase "Ciao_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Passaggio 3: semplice sostituzione del testo

 Noi usiamo il`Range.Replace` metodo per eseguire una semplice sostituzione del testo. Nel nostro esempio sostituiamo tutte le occorrenze della stringa "_ClientName_ " con "James Bond" utilizzando il file`FindReplaceOptions` opzione con il`FindReplaceDirection.Forward` direzione della ricerca:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Passaggio 4: salvataggio del documento modificato

 Infine, salviamo il documento modificato in una directory specificata utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Codice sorgente di esempio per Simple Find replace utilizzando Aspose.Words per .NET

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

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Semplice Trova Sostituisci di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per creare un documento, inserire testo, eseguire una semplice sostituzione del testo e salvare il documento modificato.

### Domande frequenti

#### D: Qual è la funzione Trova e sostituisci testo semplice in Aspose.Words per .NET?

R: La funzionalità Trova e sostituisci testo semplice in Aspose.Words per .NET consente di eseguire una semplice sostituzione del testo in un documento Word. Ti consente di cercare una stringa di caratteri specifica e sostituirla con un'altra stringa di caratteri. Ciò può essere utile quando desideri apportare modifiche globali a un documento, ad esempio sostituendo nomi, date o altre informazioni.

#### D: Come creare un nuovo documento in Aspose.Words per .NET?

R: Prima di utilizzare la funzione Trova e sostituisci testo semplice, è necessario creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto. Ecco un codice di esempio per creare un nuovo documento:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### D: Come inserire testo in un documento utilizzando Aspose.Words per .NET?

 R: Una volta che hai un documento, puoi inserire del testo usando a`DocumentBuilder` oggetto. Nel nostro esempio, utilizziamo il file`Writeln` metodo per inserire la frase "Ciao_CustomerName_:::

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### D: Come posso eseguire una semplice sostituzione del testo in un documento utilizzando Aspose.Words per .NET?

 R: Per eseguire una semplice sostituzione del testo, puoi utilizzare il file`Range.Replace` metodo. Nel nostro esempio sostituiamo tutte le occorrenze della stringa "_ClientName_ " con "James Bond" utilizzando il file`FindReplaceOptions` opzione con il`FindReplaceDirection.Forward` direzione della ricerca:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### D: Come salvare il documento modificato in Aspose.Words per .NET?

 R: Una volta effettuata la sostituzione del testo, puoi salvare il documento modificato in una directory specificata utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```