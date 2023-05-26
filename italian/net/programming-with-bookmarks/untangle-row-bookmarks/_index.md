---
title: Districare i segnalibri di riga
linktitle: Districare i segnalibri di riga
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come districare i segnalibri di riga nidificati per rimuovere righe specifiche senza influire su altri segnalibri.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/untangle-row-bookmarks/
---

In questo articolo, esploreremo il codice sorgente C# precedente per comprendere come utilizzare la funzione Untangle Row Bookmarks nella libreria Aspose.Words per .NET. Questa funzione consente di mettere le estremità dei segnalibri delle righe nella stessa riga dell'inizio dei segnalibri.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: caricamento del documento

 Noi usiamo il`Document` class per caricare il documento esistente da un file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Passaggio 2: svela i segnalibri della linea

 Noi usiamo il`Untangle` funzione per districare i segnalibri dalle righe. Questa funzione esegue l'attività personalizzata di inserire le estremità delle righe del segnalibro nella stessa riga in cui inizia il segnalibro:

```csharp
Untangle(doc);
```

## Passaggio 3: elimina la riga per segnalibro

 Noi usiamo il`DeleteRowByBookmark` funzione per eliminare una riga specifica tramite il suo segnalibro:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Passaggio 4: verifica l'integrità degli altri segnalibri

Verifichiamo che gli altri segnalibri non siano stati danneggiati controllando se la fine del segnalibro è ancora presente:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Esempio di codice sorgente per Untangle Row Bookmarks utilizzando Aspose.Words per .NET**

Ecco il codice sorgente di esempio completo per districare i segnalibri dalle righe utilizzando Aspose.Words per .NET:


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Questo esegue l'attività personalizzata di inserire la fine del segnalibro di riga nella stessa riga con l'inizio del segnalibro.
	Untangle(doc);

	// Ora possiamo eliminare facilmente le righe da un segnalibro senza danneggiare i segnalibri di qualsiasi altra riga.
	DeleteRowByBookmark(doc, "ROW2");

	// Questo serve solo per verificare che l'altro segnalibro non sia stato danneggiato.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzionalità Untangle Row Bookmarks di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per districare i segnalibri di riga ed eliminare una riga specifica senza danneggiare altri segnalibri.