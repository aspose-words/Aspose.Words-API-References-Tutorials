---
title: Ignora testo all'interno Elimina revisioni
linktitle: Ignora testo all'interno Elimina revisioni
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come utilizzare la funzionalità "Ignora testo all'interno Elimina revisioni" di Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

In questo articolo, esploreremo il codice sorgente C# riportato sopra per comprendere come utilizzare la funzionalità "Ignora testo all'interno di eliminazione revisioni" nella libreria Aspose.Words per .NET. Questa funzionalità è utile quando vogliamo ignorare il testo all'interno delle revisioni di eliminazione durante l'elaborazione di parole con i documenti.

## Panoramica della libreria Aspose.Words per .NET

Prima di immergerci nei dettagli del codice, vorrei presentare brevemente la libreria Aspose.Words per .NET. È una potente libreria che consente di creare, modificare e convertire documenti Word in applicazioni .NET. Offre molte funzionalità avanzate per l'elaborazione di testi con documenti, inclusa la gestione delle revisioni.

## Comprensione della funzione "Ignora testo all'interno di Elimina revisioni".

La funzione "Ignora testo all'interno delle revisioni di eliminazione" in Aspose.Words per .NET consente di specificare se il testo all'interno delle revisioni di eliminazione deve essere ignorato durante determinate operazioni, come la ricerca e la sostituzione del testo. Quando questa funzionalità è abilitata, il testo eliminato all'interno delle revisioni non viene considerato durante le operazioni.

## Passaggio 1: creazione di un nuovo documento utilizzando Aspose.Words per .NET

 Prima di iniziare a manipolare il testo in un documento, dobbiamo creare un nuovo documento utilizzando Aspose.Words per .NET. Può essere fatto istanziando a`Document` oggetto:

```csharp
Document doc = new Document();
```

## Passaggio 2: inserimento di testo non rivisto nel documento

 Una volta che abbiamo un documento, possiamo inserire testo non revisionato utilizzando a`DocumentBuilder` oggetto. Ad esempio, per inserire il testo "Testo Eliminato", possiamo utilizzare il file`Writeln` E`Write` metodi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Passaggio 3: rimozione di un paragrafo con monitoraggio delle revisioni

Per illustrare l'uso della funzione "Ignora testo all'interno di eliminazione revisioni", elimineremo un paragrafo dal documento utilizzando il monitoraggio delle revisioni. Questo ci permetterà di vedere come questa funzionalità influisce sulle operazioni successive.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Passaggio 4: applicazione della funzione "Ignora testo all'interno di Elimina revisioni".

 Ora che abbiamo preparato il nostro documento eliminando un paragrafo, possiamo abilitare la funzione "Ignora testo all'interno di Elimina revisioni" utilizzando un`FindReplaceOptions` oggetto. Imposteremo il`IgnoreDeleted`proprietà a`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Passaggio 5: utilizzo delle espressioni regolari per trovare e sostituire

Per eseguire operazioni di ricerca e sostituzione sul testo del documento, utilizzeremo le espressioni regolari. Nel nostro esempio cercheremo tutte le occorrenze della lettera "e" e le sostituiremo con un asterisco "* ". .NETTO`Regex` la classe viene utilizzata per questo:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Passaggio 6: visualizzazione dell'output del documento modificato

 Dopo aver applicato la ricerca e sostituzione, possiamo visualizzare il contenuto modificato del documento utilizzando il file`GetText` metodo:

```csharp
Console.WriteLine(doc.GetText());
```

## Passaggio 7: modifica delle opzioni per includere il testo eliminato

 Se vogliamo includere il testo cancellato nel risultato di output, possiamo modificare le opzioni per non ignorare il testo cancellato. Per questo imposteremo il`IgnoreDeleted`proprietà a`false`:

```csharp
options. IgnoreDeleted = false;
```

## Passaggio 8: output del documento modificato con testo eliminato

Dopo aver modificato le opzioni, possiamo eseguire nuovamente la ricerca e sostituzione per ottenere il risultato con il testo cancellato incluso:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Codice sorgente di esempio per Ignora testo all'interno Elimina revisioni utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'uso della funzionalità "Ignora testo all'interno Elimina revisioni" con Aspose.Words per .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Inserisci testo non rivisto.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Rimuovere il primo paragrafo con le revisioni di monitoraggio.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per comprendere come utilizzare la funzionalità "Ignora testo all'interno Elimina revisioni" in Aspose.Words per .NET. Questa funzionalità è utile per ignorare il testo all'interno delle revisioni di eliminazione durante la manipolazione dei documenti. Abbiamo seguito una guida passo passo per creare un documento, inserire testo, eliminare un paragrafo con tracciamento delle revisioni, applicare la funzione "Ignora testo all'interno di elimina revisioni" ed eseguire operazioni di ricerca e sostituzione.

### Domande frequenti

#### D: Qual è la funzione "Ignora testo all'interno Elimina revisioni" in Aspose.Words per .NET?

R: La funzione "Ignora testo all'interno delle revisioni di eliminazione" in Aspose.Words per .NET consente di specificare se il testo all'interno delle revisioni di eliminazione deve essere ignorato durante determinate operazioni, come la ricerca e la sostituzione del testo. Quando questa funzionalità è abilitata, il testo eliminato all'interno delle revisioni non viene considerato durante le operazioni.

#### D: Cos'è Aspose.Words per .NET?

R: Aspose.Words per .NET è una potente libreria per creare, modificare e convertire documenti Word in applicazioni .NET. Offre molte funzionalità avanzate per l'elaborazione di testi con documenti, inclusa la gestione delle revisioni.

#### D: Come creare un nuovo documento in Aspose.Words per .NET?

 R: Prima di iniziare a manipolare il testo in un documento, è necessario creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto. Ecco un codice di esempio per creare un nuovo documento:

```csharp
Document doc = new Document();
```

#### D: Come inserire testo non modificato in un documento utilizzando Aspose.Words per .NET?

 R: Una volta che hai un documento, puoi inserire testo non revisionato utilizzando a`DocumentBuilder` oggetto. Ad esempio, per inserire il testo "Testo Eliminato", è possibile utilizzare il file`Writeln` E`Write` metodi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### D: Come posso eliminare un paragrafo con tracciamento delle revisioni in Aspose.Words per .NET?

R: Per illustrare l'uso della funzione "Ignora testo all'interno di elimina revisioni", elimineremo un paragrafo dal documento utilizzando il tracciamento delle revisioni. Questo ci permetterà di vedere come questa funzione influisce sulle operazioni successive.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### D: Come abilitare la funzione "Ignora testo all'interno Elimina revisioni" in Aspose.Words per .NET?

 R: Ora che abbiamo preparato il nostro documento eliminando un paragrafo, possiamo abilitare la funzione "Ignora testo all'interno di elimina revisioni" utilizzando un`FindReplaceOptions` oggetto. Imposteremo il`IgnoreDeleted`proprietà a`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### D: Come cercare e sostituire utilizzando le espressioni regolari in Aspose.Words per .NET?

R: Per eseguire operazioni di ricerca e sostituzione sul testo del documento, utilizzeremo le espressioni regolari. Nel nostro esempio cercheremo tutte le occorrenze della lettera "e" e le sostituiremo con un asterisco "* ". Utilizzeremo .NET`Regex` classe per questo:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### D: Come visualizzare il contenuto del documento modificato in Aspose.Words per .NET?

R: Dopo aver applicato la ricerca e sostituzione, possiamo visualizzare il contenuto modificato del documento utilizzando il file`GetText` metodo:

```csharp
Console.WriteLine(doc.GetText());
```

#### D: Come includere il testo eliminato nel risultato di output in Aspose.Words per .NET?

 R: Se vogliamo includere il testo cancellato nel risultato di output, possiamo modificare le opzioni per non ignorare il testo cancellato. Per questo, imposteremo il file`IgnoreDeleted`proprietà a`false`:

```csharp
options. IgnoreDeleted = false;
```

#### D: Come mostrare il documento modificato con testo eliminato in Aspose.Words per .NET?

R: Dopo aver modificato le opzioni, possiamo eseguire una nuova ricerca e sostituire per ottenere il risultato con il testo eliminato incluso:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
