---
title: Sostituisci con stringa
linktitle: Sostituisci con stringa
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come sostituire il testo con una stringa in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/find-and-replace-text/replace-with-string/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come usare la funzione Replace With String nella libreria Aspose.Words per .NET. Questa funzione consente di eseguire la sostituzione del testo in base a una stringa di caratteri specifica in un documento di Word.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione di un nuovo documento

Prima di iniziare a utilizzare la sostituzione delle stringhe, è necessario creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto:

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

## Passaggio 3: sostituire con una stringa

 Noi usiamo il`Range.Replace` metodo per sostituire il testo con una stringa. Nel nostro esempio, sostituiamo tutte le occorrenze della parola "triste" con "cattivo" utilizzando il`FindReplaceOptions` opzione con il`FindReplaceDirection.Forward` direzione di ricerca:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Passaggio 4: salvare il documento modificato

 Infine, salviamo il documento modificato in una directory specificata utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Esempio di codice sorgente per Replace With String utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per illustrare l'uso della sostituzione con una stringa di caratteri con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come usare la funzione Replace With String di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per creare un documento, inserire testo, sostituire con una stringa e salvare il documento modificato.
