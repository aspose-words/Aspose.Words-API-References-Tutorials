---
title: Ignora il testo all'interno delle revisioni di inserimento
linktitle: Ignora il testo all'interno delle revisioni di inserimento
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare la funzionalità "Ignora testo all'interno delle revisioni di inserimento" di Aspose.Words per .NET per manipolare le revisioni di inserimento nei documenti di Word.
type: docs
weight: 10
url: /it/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

In questo articolo, esploreremo il codice sorgente C# riportato sopra per comprendere come utilizzare la funzione Ignora testo all'interno di inserimento revisioni nella libreria Aspose.Words per .NET. Questa funzionalità è utile quando vogliamo ignorare il testo all'interno delle revisioni inserite durante la manipolazione dei documenti.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione di un nuovo documento

 Prima di iniziare a manipolare il testo all'interno delle revisioni di inserimento, dobbiamo creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto:

```csharp
Document doc = new Document();
```

## Passaggio 2: inserisci il testo con il monitoraggio delle revisioni

 Una volta che abbiamo un documento, possiamo inserire testo con tracciamento delle revisioni utilizzando a`DocumentBuilder`oggetto. Ad esempio, per inserire il testo "Inserito" con tracciamento delle revisioni, possiamo utilizzare il file`StartTrackRevisions`, `Writeln` E`StopTrackRevisions` metodi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Passaggio 3: inserisci il testo non revisionato

 Oltre al testo con tracciamento delle revisioni, possiamo anche inserire testo non rivisto utilizzando il file`DocumentBuilder` oggetto. Ad esempio, per inserire il testo "Testo" senza revisione, possiamo utilizzare il file`Write` metodo:

```csharp
builder.Write("Text");
```

## Passaggio 4: utilizzo della funzione Ignora testo all'interno di Inserisci revisioni

 Per ignorare il testo all'interno delle revisioni di inserimento nelle operazioni successive, possiamo usare a`FindReplaceOptions` oggetto e impostare il`IgnoreInserted`proprietà a`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Passaggio 5: utilizzo delle espressioni regolari per la ricerca e la sostituzione

Per eseguire operazioni di ricerca e sostituzione sul testo del documento, utilizzeremo le espressioni regolari. Nel nostro esempio cercheremo tutte le occorrenze della lettera "e" e le sostituiremo con un asterisco "* ". Utilizzeremo .NET`Regex` classe per questo:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Passaggio 6: visualizzazione dell'output del documento modificato

 Dopo aver applicato la ricerca e sostituzione, possiamo visualizzare il contenuto modificato del documento utilizzando il file`GetText` metodo:

```csharp
Console.WriteLine(doc.GetText());
```

## Passaggio 7: modifica delle opzioni per includere le revisioni di inserimento

Se vogliamo includere il testo all'interno delle revisioni di inserimento nel risultato di output, possiamo modificare le opzioni per non ignorare le revisioni di inserimento. Per questo imposteremo il`IgnoreInserted`proprietà a`false`:

```csharp
options.IgnoreInserted = false;
```

## Passaggio 8: visualizzazione del documento modificato con inserimento revisioni

Dopo aver modificato le opzioni, possiamo eseguire nuovamente la ricerca e sostituzione per ottenere il risultato con il testo all'interno dell'inserto revisioni incluso:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Codice sorgente di esempio per Ignora testo all'interno di revisioni di inserimento utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'uso della funzione Ignora testo all'interno di inserimento revisioni con Aspose.Words per .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Inserisci testo con revisioni di tracciamento.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Inserisci testo non rivisto.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per comprendere come utilizzare la funzione Ignora testo all'interno di inserimento revisioni in Aspose.Words per .NET. Abbiamo seguito una guida passo passo per creare un documento, inserire testo con revisioni di tracciamento e testo non rivisto, utilizzando la funzione Ignora testo all'interno di Inserisci revisioni, eseguendo operazioni di ricerca e sostituzione con espressioni regolari e visualizzando il documento modificato.

### Domande frequenti

#### D: Qual è la funzionalità "Ignora testo all'interno delle revisioni di inserimento" in Aspose.Words per .NET?

R: La funzione "Ignora testo all'interno delle revisioni di inserimento" in Aspose.Words per .NET consente di specificare se il testo all'interno delle revisioni di inserimento deve essere ignorato durante determinate operazioni, come la ricerca e la sostituzione del testo. Quando questa funzionalità è abilitata, il testo all'interno delle revisioni di inserimento non viene considerato durante le operazioni.

#### D: Come posso creare un nuovo documento utilizzando Aspose.Words per .NET?

 R: Per creare un nuovo documento utilizzando Aspose.Words per .NET, puoi creare un'istanza di a`Document` oggetto. Ecco un esempio di codice C# per creare un nuovo documento:

```csharp
Document doc = new Document();
```

#### D: Come posso inserire testo con tracciamento delle revisioni in Aspose.Words per .NET?

R: Una volta che hai un documento, puoi inserire testo con tracciamento delle revisioni utilizzando a`DocumentBuilder` oggetto. Ad esempio, per inserire il testo "Inserito" con tracciamento delle revisioni, è possibile utilizzare il file`StartTrackRevisions`, `Writeln` , E`StopTrackRevisions` metodi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### D: Come posso inserire testo non revisionato in Aspose.Words per .NET?

 R: Oltre al testo con tracciamento delle revisioni, puoi anche inserire testo non rivisto utilizzando il file`DocumentBuilder` oggetto. Ad esempio, per inserire il testo "Testo" senza revisione, è possibile utilizzare il file`Write` metodo:

```csharp
builder.Write("Text");
```

#### D: Come posso ignorare il testo all'interno delle revisioni di inserimento in Aspose.Words per .NET?

 R: Per ignorare il testo all'interno delle revisioni di inserimento durante le operazioni successive, puoi utilizzare a`FindReplaceOptions` oggetto e impostare il`IgnoreInserted`proprietà a`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### D: Come posso eseguire la ricerca e la sostituzione utilizzando le espressioni regolari in Aspose.Words per .NET?

 R: Per eseguire operazioni di ricerca e sostituzione sul testo del documento utilizzando le espressioni regolari, è possibile utilizzare .NET`Regex` classe. Ad esempio, per cercare tutte le occorrenze della lettera "e" e sostituirle con un asterisco "* ", puoi creare un file`Regex` oggetto e usarlo con il`Replace` metodo:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### D: Come posso visualizzare l'output modificato del documento in Aspose.Words per .NET?

 R: Dopo aver applicato le operazioni di ricerca e sostituzione, è possibile visualizzare il contenuto modificato del documento utilizzando il file`GetText` metodo:

```csharp
Console.WriteLine(doc.GetText());
```

#### D: Come posso includere le revisioni di inserimento nel risultato di output in Aspose.Words per .NET?

 R: Per includere il testo all'interno delle revisioni di inserimento nel risultato di output, puoi modificare le opzioni per non ignorare le revisioni di inserimento. Per questo è possibile impostare il file`IgnoreInserted` proprietà del`FindReplaceOptions` opporsi a`false`:

```csharp
options.IgnoreInserted = false;
```

#### D: Come posso visualizzare il documento modificato con le revisioni di inserimento in Aspose.Words per .NET?

R: Dopo aver modificato le opzioni per includere le revisioni dell'inserto, puoi eseguire nuovamente la ricerca e sostituzione per ottenere il risultato con il testo all'interno delle revisioni dell'inserto incluse:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```