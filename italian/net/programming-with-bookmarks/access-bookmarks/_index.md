---
title: Accedi ai segnalibri
linktitle: Accedi ai segnalibri
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come accedere ai segnalibri in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-bookmarks/access-bookmarks/
---

In questo articolo, esploreremo il codice sorgente C# sopra per capire come utilizzare la funzione Access Bookmarks nella libreria Aspose.Words per .NET. Questa funzione fornisce l'accesso a segnalibri specifici in un documento di Word.

## Prerequisiti

- Conoscenza base del linguaggio C#.
- Ambiente di sviluppo .NET con libreria Aspose.Words installata.

## Passaggio 1: caricamento del documento

 Prima di iniziare ad accedere ai segnalibri, dobbiamo caricare un documento Word utilizzando Aspose.Words per .NET. Questo può essere fatto istanziando a`Document` oggetto che specifica il percorso del file del documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Passaggio 2: accesso ai segnalibri

Una volta caricato il documento, possiamo accedere ai segnalibri nel documento. Esistono due modi per accedere ai segnalibri: per indice e per nome.

- Accesso per indice: nel nostro esempio, utilizziamo l'indice 0 per accedere al primo segnalibro del documento:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Accesso per nome: nel nostro esempio, utilizziamo il nome "MyBookmark3" per accedere a un segnalibro specifico nel documento:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Codice sorgente di esempio per i segnalibri di accesso utilizzando Aspose.Words per .NET

Ecco il codice sorgente di esempio completo per dimostrare l'accesso ai segnalibri utilizzando Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// Per indice:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// Per nome:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Conclusione

In questo articolo, abbiamo esplorato il codice sorgente C# per capire come utilizzare la funzionalità di accesso ai segnalibri di Aspose.Words per .NET. Abbiamo seguito una guida passo passo per caricare un documento e accedere ai segnalibri utilizzando indice e nome.