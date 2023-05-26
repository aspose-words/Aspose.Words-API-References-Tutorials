---
title: Meta caratteri nel modello di ricerca
linktitle: Meta caratteri nel modello di ricerca
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare i metacaratteri nel modello di ricerca con Aspose.Words per .NET per manipolare i documenti di Word.
type: docs
weight: 10
url: /it/net/find-and-replace-text/meta-characters-in-search-pattern/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Meta Characters In Search Pattern nella libreria Aspose.Words per .NET. Questa funzione consente di utilizzare metacaratteri speciali per eseguire ricerche avanzate e sostituzioni nei documenti di Word.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione di un nuovo documento

 Prima di iniziare a utilizzare i metacaratteri nel modello di ricerca, è necessario creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Passaggio 2: inserire il testo nel documento

 Una volta che abbiamo un documento, possiamo inserire il testo usando a`DocumentBuilder` oggetto. Nel nostro esempio, usiamo il`Writeln` E`Write` metodi per inserire due righe di testo:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Passaggio 3: trova e sostituisci il testo con i metacaratteri

 Ora useremo il`Range.Replace` funzione per cercare e sostituire il testo utilizzando un modello di ricerca contenente metacaratteri speciali. Nel nostro esempio, sostituiamo la frase "Questa è la riga 1&pQuesta è la riga 2" con "Questa riga è stata sostituita" utilizzando il`&p` metacarattere per rappresentare un'interruzione di paragrafo:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Passaggio 4: Inserimento di un'interruzione di pagina nel documento

 Per illustrare l'uso di un altro metacarattere, inseriremo un'interruzione di pagina nel documento utilizzando il`InsertBreak` metodo con il`BreakType.PageBreak` parametro. Per prima cosa spostiamo il cursore dal file`DocumentBuilder` alla fine del documento, poi inseriamo l'interruzione di pagina e una nuova riga di testo:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Passaggio 5: trova e sostituisci con un altro metacarattere

 Ora eseguiremo un'altra ricerca e sostituzione utilizzando il`&m` metacarattere per rappresentare un'interruzione di pagina. Sostituiamo la frase "Questa è la riga 1&mQuesta è la riga 2" con "L'interruzione di pagina viene sostituita con un nuovo testo". :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Passaggio 6: salvare il documento modificato

 Infine, salviamo il documento modificato in una directory specificata utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Codice sorgente di esempio per i meta caratteri nel modello di ricerca utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'uso dei metacaratteri nel modello di ricerca con Aspose.Words per .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare i metacaratteri nel modello di ricerca di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per creare un documento, inserire testo, eseguire ricerca e sostituzione utilizzando metacaratteri speciali, inserire interruzioni di pagina e salvare il documento modificato.
