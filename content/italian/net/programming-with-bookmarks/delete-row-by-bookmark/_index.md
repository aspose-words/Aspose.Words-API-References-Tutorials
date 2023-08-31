---
title: Elimina riga per segnalibro nel documento di Word
linktitle: Elimina riga per segnalibro nel documento di Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come eliminare una riga di tabella in base a un segnalibro specifico nel documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/delete-row-by-bookmark/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Elimina riga per segnalibro nella libreria Aspose.Words per .NET. Questa funzione ti consente di eliminare una riga della tabella in base a un segnalibro specifico nel documento Word.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: ottenere il segnalibro

 Noi usiamo il`Bookmarks` proprietà dell'intervallo di documenti per ottenere il segnalibro specifico che vogliamo utilizzare per eliminare la riga della tabella:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Passaggio 2: eliminazione della riga della tabella

 Noi usiamo il`GetAncestor` metodo per ottenere il`Row` digitare l'elemento principale del segnalibro. Successivamente, utilizziamo il`Remove` metodo per rimuovere la riga della tabella:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Codice sorgente di esempio per Elimina riga per segnalibro utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'eliminazione di una riga di tabella basata su un segnalibro specifico utilizzando Aspose.Words per .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzione Elimina riga per segnalibro di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per eliminare una riga di tabella in base a un segnalibro specifico in un documento.

### Domande frequenti sull'eliminazione di righe tramite segnalibro nel documento Word

#### D: Posso eliminare più righe utilizzando lo stesso segnalibro?

R: Sì, puoi eliminare più righe utilizzando lo stesso segnalibro. Tuttavia, devi gestire la logica del tuo codice per determinare il numero di righe da eliminare e apportare le modifiche necessarie allo snippet di codice fornito.

#### D: Cosa succede se il segnalibro non esiste nel documento?

R: Se il segnalibro specificato non esiste nel documento, lo snippet di codice restituirà un valore nullo per l'oggetto segnalibro. Pertanto, è necessario gestire questo scenario nel codice aggiungendo controlli appropriati prima di tentare di eliminare la riga della tabella.

#### D: La libreria Aspose.Words è gratuita?

 R: La libreria Aspose.Words è una libreria commerciale e potresti richiedere una licenza valida per utilizzarla nei tuoi progetti. Puoi visitare il[Aspose.Words per riferimenti API .NET](https://reference.aspose.com/words/net/) per saperne di più sulle opzioni di licenza e sui prezzi.

#### D: posso eliminare righe da una tabella in una sezione specifica del documento di Word?

R: Sì, puoi eliminare righe da una tabella in una sezione specifica di un documento di Word. Puoi modificare lo snippet di codice fornito per indirizzare una sezione specifica utilizzando l'intervallo o il segnalibro appropriato all'interno di quella sezione.