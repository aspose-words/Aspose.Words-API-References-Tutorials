---
title: Ignora il testo all'interno delle revisioni degli inserti
linktitle: Ignora il testo all'interno delle revisioni degli inserti
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare la funzione "Ignora testo all'interno delle revisioni degli inserti" di Aspose.Words per .NET per manipolare le revisioni degli inserti nei documenti di Word.
type: docs
weight: 10
url: /it/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come usare la funzione Ignore Text Inside Insert Revisions nella libreria Aspose.Words per .NET. Questa caratteristica è utile quando vogliamo ignorare il testo all'interno delle revisioni degli inserti durante la manipolazione dei documenti.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione di un nuovo documento

 Prima di iniziare a manipolare il testo all'interno delle revisioni degli inserti, è necessario creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto:

```csharp
Document doc = new Document();
```

## Passaggio 2: inserisci il testo con il tracciamento delle revisioni

 Una volta che abbiamo un documento, possiamo inserire il testo con il tracciamento della revisione usando a`DocumentBuilder` oggetto. Ad esempio, per inserire il testo "Inserito" con il tracciamento della revisione, possiamo utilizzare il file`StartTrackRevisions`, `Writeln` E`StopTrackRevisions` metodi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Passaggio 3: inserisci il testo non rivisto

 Oltre al testo con il tracciamento delle revisioni, possiamo anche inserire testo non revisionato utilizzando il`DocumentBuilder`oggetto. Ad esempio, per inserire il testo "Testo" senza revisione, possiamo utilizzare il file`Write` metodo:

```csharp
builder.Write("Text");
```

## Passaggio 4: utilizzo della funzione Ignora testo all'interno di Inserisci revisioni

 Per ignorare il testo all'interno delle revisioni di inserimento nelle operazioni successive, possiamo usare a`FindReplaceOptions` oggetto e impostare il`IgnoreInserted` proprietà a`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Passaggio 5: utilizzo delle espressioni regolari per la ricerca e la sostituzione

Per eseguire operazioni di ricerca e sostituzione sul testo del documento, utilizzeremo espressioni regolari. Nel nostro esempio, cercheremo tutte le occorrenze della lettera "e" e le sostituiremo con un asterisco "* ". Useremo .NET`Regex` classe per questo:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Passaggio 6: visualizzazione dell'output del documento modificato

Dopo aver applicato la ricerca e la sostituzione, possiamo visualizzare il contenuto modificato del documento utilizzando il file`GetText` metodo:

```csharp
Console.WriteLine(doc.GetText());
```

## Passaggio 7: modifica delle opzioni per includere le revisioni degli inserti

 Se vogliamo includere il testo all'interno delle revisioni dell'inserimento nel risultato di output, possiamo modificare le opzioni per non ignorare le revisioni dell'inserimento. Per questo imposteremo il`IgnoreInserted` proprietà a`false`:

```csharp
options.IgnoreInserted = false;
```

## Passaggio 8: visualizzazione del documento modificato con l'inserimento delle revisioni

Dopo aver modificato le opzioni, possiamo eseguire nuovamente la ricerca e sostituzione per ottenere il risultato con il testo all'interno dell'inserto revisioni incluso:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Esempio di codice sorgente per Ignore Text Inside Inserisci revisioni utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'uso della funzione Ignore Text Inside Insert Revisions con Aspose.Words per .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Inserisci il testo con le revisioni di tracciamento.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Inserisci testo non revisionato.
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

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Ignore Text Inside Insert Revisions in Aspose.Words per .NET. Abbiamo seguito una guida passo passo per creare un documento, inserire testo con revisioni di tracciamento e testo non revisionato, utilizzare la funzione Ignora testo all'interno di Inserisci revisioni, eseguire operazioni di ricerca e sostituzione con espressioni regolari e visualizzare il documento modificato.