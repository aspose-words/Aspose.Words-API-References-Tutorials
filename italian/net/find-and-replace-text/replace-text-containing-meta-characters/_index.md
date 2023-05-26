---
title: Sostituisci testo contenente metacaratteri
linktitle: Sostituisci testo contenente metacaratteri
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come sostituire il testo contenente metacaratteri nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/find-and-replace-text/replace-text-containing-meta-characters/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Sostituisci testo contenente metacaratteri nella libreria Aspose.Words per .NET. Questa funzione consente di sostituire porzioni di testo in un documento contenente metacaratteri specifici.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: creazione di un nuovo documento

 Prima di iniziare a utilizzare la sostituzione del testo con metacaratteri, è necessario creare un nuovo documento utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Passaggio 2: inserire il testo nel documento

 Una volta che abbiamo un documento, possiamo inserire il testo usando a`DocumentBuilder` oggetto. Nel nostro esempio, usiamo il`Writeln`metodo per inserire più paragrafi di testo in diverse sezioni:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## Passaggio 3: configurazione delle opzioni Trova e sostituisci

 Ora configureremo le opzioni di ricerca e sostituzione utilizzando a`FindReplaceOptions` oggetto. Nel nostro esempio, impostiamo l'allineamento dei paragrafi sostituiti su "Centrato":

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment

.Center;
```

## Passaggio 4: sostituzione del testo contenente metacaratteri

 Noi usiamo il`Range.Replace` metodo per eseguire la sostituzione di testo contenente metacaratteri. Nel nostro esempio, sostituiamo ogni occorrenza della parola "sezione" seguita da un'interruzione di paragrafo con la stessa parola seguita da diversi trattini e una nuova interruzione di paragrafo:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## Passaggio 5: sostituzione di un tag di testo personalizzato

 Usiamo anche il`Range.Replace` metodo per sostituire un'impostazione personalizzata "{insert-section}" tag di testo con un'interruzione di sezione. Nel nostro esempio, sostituiamo "{insert-section}" con "&b" per inserire un'interruzione di sezione:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## Passaggio 6: salvare il documento modificato

 Infine, salviamo il documento modificato in una directory specificata utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Esempio di codice sorgente per Sostituisci testo contenente metacaratteri utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'uso della sostituzione del testo contenente metacaratteri con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// Raddoppia ogni interruzione di paragrafo dopo la parola "sezione", aggiungi una sorta di sottolineatura e rendila centrata.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// Inserisci un'interruzione di sezione anziché un tag di testo personalizzato.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzionalità Sostituisci testo contenente metacaratteri di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per creare un documento, inserire testo, sostituire testo contenente metacaratteri e salvare il documento modificato.

