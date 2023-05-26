---
title: Mostra Nascondi segnalibri
linktitle: Mostra Nascondi segnalibri
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come mostrare o nascondere un segnalibro specifico in un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/show-hide-bookmarks/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Mostra nascondi segnalibri nella libreria Aspose.Words per .NET. Questa funzione consente di mostrare o nascondere un segnalibro specifico in un documento.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: caricamento del documento

 Noi usiamo il`Document` class per caricare il documento esistente da un file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Passaggio 2: mostra o nascondi un segnalibro specifico

 Noi usiamo il`ShowHideBookmarkedContent` funzione per mostrare o nascondere un segnalibro specifico nel documento. Questa funzione prende come parametri il documento, il nome del segnalibro e un valore booleano per indicare se mostrare o nascondere il segnalibro:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Passaggio 3: salvare il documento modificato

 Noi usiamo il`Save` metodo per salvare il documento modificato in un file:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Esempio di codice sorgente per Mostra nascondi segnalibri utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per mostrare o nascondere un segnalibro specifico utilizzando Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzionalità Mostra nascondi segnalibri di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per mostrare o nascondere un segnalibro specifico in un documento.