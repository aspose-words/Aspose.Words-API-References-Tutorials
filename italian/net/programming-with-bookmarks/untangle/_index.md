---
title: Districare
linktitle: Districare
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come districare i segnalibri nidificati nelle righe adiacenti della tabella utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/untangle/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come usare la funzione Untangle nella libreria Aspose.Words per .NET. Questa funzione svela i segnalibri nidificati che si trovano nelle righe adiacenti della tabella.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: sfoglia i segnalibri del documento

Usiamo un ciclo foreach per scorrere tutti i segnalibri presenti nel documento:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Codice per la gestione dei segnalibri qui
}
```

## Passaggio 2: ottieni le righe principali dai segnalibri

 Noi usiamo il`GetAncestor` metodi per recuperare le righe padre dei nodi iniziale e finale del segnalibro:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Passaggio 3: districare i segnalibri nidificati

Se vengono trovate entrambe le righe principali e il segnalibro inizia e finisce in righe adiacenti, spostiamo il nodo finale del segnalibro alla fine dell'ultimo paragrafo dell'ultima cella nella riga superiore:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Esempio di codice sorgente per Untangle utilizzando Aspose.Words per .NET

Ecco l'esempio di codice sorgente completo per districare i segnalibri nidificati utilizzando Aspose.Words per .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Ottieni la riga padre sia del segnalibro che del nodo finale del segnalibro.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Se entrambe le righe vengono trovate correttamente e l'inizio e la fine del segnalibro sono contenuti in righe adiacenti,
		// sposta il nodo finale del segnalibro alla fine dell'ultimo paragrafo nell'ultima cella della riga superiore.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come usare la funzione Untangle di Aspose.Words per .NET. Abbiamo seguito una guida dettagliata per districare i segnalibri nidificati nelle righe adiacenti della tabella.