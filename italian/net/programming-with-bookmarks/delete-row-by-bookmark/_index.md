---
title: Elimina riga per segnalibro
linktitle: Elimina riga per segnalibro
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come eliminare una riga della tabella in base a un segnalibro specifico in un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/delete-row-by-bookmark/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Elimina riga per segnalibro nella libreria Aspose.Words per .NET. Questa funzione consente di eliminare una riga della tabella in base a un segnalibro specifico in un documento.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: ottenere il segnalibro

 Noi usiamo il`Bookmarks`proprietà dell'intervallo di documenti per ottenere il segnalibro specifico che vogliamo utilizzare per eliminare la riga della tabella:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Passaggio 2: eliminazione della riga della tabella

 Noi usiamo il`GetAncestor` metodo per ottenere il`Row` digitare l'elemento genitore del segnalibro. Successivamente, usiamo il`Remove` metodo per rimuovere la riga della tabella:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Codice sorgente di esempio per Elimina riga per segnalibro utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'eliminazione di una riga della tabella basata su un segnalibro specifico utilizzando Aspose.Words per .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Delete Row By Bookmark di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per eliminare una riga della tabella in base a un segnalibro specifico in un documento.