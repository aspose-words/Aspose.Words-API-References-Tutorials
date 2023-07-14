---
title: Testo semplice Trova e sostituisci in Word
linktitle: Testo semplice Trova e sostituisci in Word
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come eseguire una semplice ricerca e sostituzione di testo in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/find-and-replace-text/simple-find-replace/
---
In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare il testo semplice Trova e sostituisci nella parola Aspose.Words per la libreria .NET. Questa funzione consente di eseguire una semplice sostituzione del testo cercando una specifica stringa di caratteri e sostituendola con un'altra stringa di caratteri in un documento Word.

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

### FAQ

#### D: Cos'è la funzione Trova e sostituisci testo semplice in Aspose.Words per .NET?

R: La funzione Trova e sostituisci testo semplice in Aspose.Words per .NET ti consente di eseguire semplici sostituzioni di testo in un documento Word. Consente di cercare una stringa di caratteri specifica e sostituirla con un'altra stringa di caratteri. Ciò può essere utile quando si desidera apportare modifiche globali a un documento, come sostituire nomi, date o altre informazioni.

#### D: Come creare un nuovo documento in Aspose.Words per .NET?

R: Prima di utilizzare la funzione Trova e sostituisci testo semplice, è necessario creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto. Ecco un esempio di codice per creare un nuovo documento:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### D: Come inserire testo in un documento utilizzando Aspose.Words per .NET?

 R: Una volta che hai un documento, puoi inserire il testo usando a`DocumentBuilder` oggetto. Nel nostro esempio, usiamo il`Writeln` metodo per inserire la frase "Ciao_CustomerName_:::

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### D: Come posso eseguire una semplice sostituzione del testo in un documento utilizzando Aspose.Words per .NET?

 R: Per eseguire una semplice sostituzione del testo, puoi utilizzare il file`Range.Replace` metodo. Nel nostro esempio, sostituiamo tutte le occorrenze della stringa "_ClientName_ " con "James Bond" usando il`FindReplaceOptions` opzione con il`FindReplaceDirection.Forward` direzione di ricerca:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### D: Come salvare il documento modificato in Aspose.Words per .NET?

 R: Una volta effettuata la sostituzione del testo, è possibile salvare il documento modificato in una directory specificata utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```