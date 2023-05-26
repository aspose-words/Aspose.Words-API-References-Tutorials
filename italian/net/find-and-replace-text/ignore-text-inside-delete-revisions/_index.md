---
title: Ignora il testo all'interno Elimina revisioni
linktitle: Ignora il testo all'interno Elimina revisioni
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare la funzione "Ignora testo all'interno di Elimina revisioni" di Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzionalità "Ignora testo all'interno di Elimina revisioni" nella libreria Aspose.Words per .NET. Questa funzione è utile quando si desidera ignorare il testo all'interno delle revisioni di eliminazione quando si lavora con i documenti.

## Panoramica della libreria Aspose.Words per .NET

Prima di approfondire i dettagli del codice, vorrei introdurre brevemente la libreria Aspose.Words per .NET. È una potente libreria che consente di creare, modificare e convertire documenti Word in applicazioni .NET. Offre molte funzionalità avanzate per lavorare con i documenti, inclusa la gestione delle revisioni.

## Comprensione della funzione "Ignora testo all'interno di Elimina revisioni".

La funzione "Ignora testo all'interno delle revisioni di eliminazione" in Aspose.Words per .NET consente di specificare se il testo all'interno delle revisioni di eliminazione deve essere ignorato durante determinate operazioni, come la ricerca e la sostituzione del testo. Quando questa funzione è abilitata, il testo eliminato all'interno delle revisioni non viene considerato durante le operazioni.

## Passaggio 1: creazione di un nuovo documento utilizzando Aspose.Words per .NET

 Prima di iniziare a manipolare il testo in un documento, è necessario creare un nuovo documento utilizzando Aspose.Words per .NET. Può essere fatto istanziando a`Document` oggetto:

```csharp
Document doc = new Document();
```

## Passaggio 2: inserimento di testo non revisionato nel documento

 Una volta che abbiamo un documento, possiamo inserire il testo non rivisto usando a`DocumentBuilder` oggetto. Ad esempio, per inserire il testo "Deleted Text", possiamo utilizzare l'`Writeln` E`Write` metodi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Passaggio 3: rimozione di un paragrafo con revisioni di tracciamento

Per illustrare l'uso della funzione "Ignora testo all'interno di Elimina revisioni", elimineremo un paragrafo dal documento utilizzando il monitoraggio delle revisioni. Questo ci permetterà di vedere come questa funzione influisce sulle operazioni successive.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Passaggio 4: applicazione della funzione "Ignora testo all'interno di Elimina revisioni".

 Ora che abbiamo preparato il nostro documento eliminando un paragrafo, possiamo abilitare la funzione "Ignora testo all'interno Elimina revisioni" utilizzando un`FindReplaceOptions` oggetto. Imposteremo il`IgnoreDeleted` proprietà a`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Passaggio 5: utilizzo delle espressioni regolari per trovare e sostituire

Per eseguire operazioni di ricerca e sostituzione sul testo del documento, utilizzeremo espressioni regolari. Nel nostro esempio, cercheremo tutte le occorrenze della lettera "e" e le sostituiremo con un asterisco "* ". .NETTO`Regex` la classe è utilizzata per questo:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Passaggio 6: visualizzazione dell'output del documento modificato

Dopo aver applicato la ricerca e la sostituzione, possiamo visualizzare il contenuto modificato del documento utilizzando il file`GetText` metodo:

```csharp
Console.WriteLine(doc.GetText());
```

## Passaggio 7: modifica delle opzioni per includere il testo eliminato

 Se vogliamo includere il testo eliminato nel risultato di output, possiamo modificare le opzioni per non ignorare il testo eliminato. Per questo imposteremo il`IgnoreDeleted` proprietà a`false`:

```csharp
options. IgnoreDeleted = false;
```

## Passaggio 8: emettere il documento modificato con il testo eliminato

Dopo aver modificato le opzioni, possiamo eseguire nuovamente la ricerca e sostituire per ottenere il risultato con il testo eliminato incluso:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Esempio di codice sorgente per Ignore Text Inside Delete Revisions utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'uso della funzione "Ignora testo all'interno di Elimina revisioni" con Aspose.Words per .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Inserisci testo non revisionato.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Rimuovi il primo paragrafo con il monitoraggio delle revisioni.
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

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzionalità "Ignora testo all'interno di Elimina revisioni" in Aspose.Words per .NET. Questa funzione è utile per ignorare il testo all'interno delle revisioni di eliminazione durante la manipolazione dei documenti. Abbiamo seguito una guida passo-passo per creare un documento, inserire testo, eliminare un paragrafo con il monitoraggio delle revisioni, applicare la funzione "Ignora testo all'interno di Elimina revisioni" ed eseguire operazioni di ricerca e sostituzione.

