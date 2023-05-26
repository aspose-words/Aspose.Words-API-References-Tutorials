---
title: Sostituisci il testo nella tabella
linktitle: Sostituisci il testo nella tabella
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come sostituire il testo in una tabella in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/find-and-replace-text/replace-text-in-table/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Sostituisci testo nella tabella nella libreria Aspose.Words per .NET. Questa funzione consente di trovare e sostituire testo specifico all'interno di una tabella in un documento di Word.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: caricare il documento

 Prima di iniziare a utilizzare la sostituzione del testo in una tabella, dobbiamo caricare il documento in Aspose.Words per .NET. Questo può essere fatto usando il`Document` class e specificando il percorso del file del documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

## Passaggio 2: accedi alla scheda

 Una volta caricato il documento, dobbiamo navigare fino alla tabella in cui vogliamo eseguire la sostituzione del testo. Nel nostro esempio, usiamo il`GetChild` metodo con il`NodeType.Table` parametro per ottenere la prima tabella nel documento:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Passaggio 3: eseguire la sostituzione del testo

 Ora usiamo il`Range.Replace` metodo per eseguire la sostituzione del testo nell'array. Nel nostro esempio, sostituiamo tutte le occorrenze della parola "Carote" con "Uova" utilizzando l'`FindReplaceOptions` opzione con il`FindReplaceDirection.Forward` direzione di ricerca. Inoltre, sostituiamo il valore "50" con "20" nell'ultima cella dell'ultima riga della tabella:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Passaggio 4: salvare il documento modificato

 Infine, salviamo il documento modificato in una directory specificata utilizzando il file`Save` metodo:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
```

Aspose.Words per .NET Abbiamo seguito una guida passo passo per caricare un documento, accedere alla tabella, eseguire la sostituzione del testo e salvare il documento modificato.

### Esempio di codice sorgente per Sostituisci testo nella tabella utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'utilizzo della sostituzione del testo in una tabella con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Tables.docx");

	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
	table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
    
```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Sostituisci testo nella tabella di Aspose.
