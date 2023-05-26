---
title: Aggiungi segni Bidi
linktitle: Aggiungi segni Bidi
second_title: Riferimento all'API Aspose.Words per .NET
description: Impara ad aggiungere segni Bidi a un documento Word utilizzando Aspose.Words per .NET e crea documenti multilingue professionali.
type: docs
weight: 10
url: /it/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words per .NET è una potente libreria per creare, modificare e manipolare documenti Word in un'applicazione C#. Tra le funzionalità offerte da Aspose.Words c'è la possibilità di aggiungere segni Bidi (bidirezionali) a un documento. In questa guida, ti illustreremo come utilizzare il codice sorgente C# di Aspose.Words per .NET per aggiungere contrassegni Bidi a un documento.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una libreria popolare che rende il lavoro con i documenti di Word facile ed efficiente. Offre una vasta gamma di funzionalità per la creazione, la modifica e la manipolazione di documenti Word, inclusa l'aggiunta di segni Bidi.

## Creazione del documento e aggiunta di contenuto

Il primo passaggio consiste nel creare un nuovo documento e aggiungervi del contenuto. Utilizzare la classe Document per creare una nuova istanza del documento. Quindi utilizzare la classe DocumentBuilder per aggiungere testo al documento. Ecco un esempio:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

In questo esempio, creiamo un nuovo documento e utilizziamo DocumentBuilder per aggiungere del testo. Abbiamo aggiunto tre righe di testo: una in inglese, una in ebraico e una in arabo per dimostrare l'aggiunta di contenuti in diverse lingue.

## Aggiunti segni Bidi

Una volta che il contenuto è stato aggiunto, ora possiamo aggiungere i segni Bidi al documento. Per questo, utilizziamo la classe TxtSaveOptions e impostiamo la proprietà AddBidiMarks su true. Ecco come:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

In questo esempio creiamo un'istanza di TxtSaveOptions e impostiamo la proprietà AddBidiMarks su true. Successivamente, utilizziamo il metodo Save della classe Document per salvare il documento con i contrassegni Bidi.

### Esempio di codice sorgente per la funzionalità "Aggiungi segni Bidi" con Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea il documento e aggiungi il contenuto
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Aggiungi segni Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Conclusione

In questa guida, abbiamo spiegato come utilizzare Aspose.Words per .NET per aggiungere contrassegni Bidi a un documento Word utilizzando il codice sorgente C# fornito. Seguendo i passaggi forniti, puoi facilmente aggiungere segni Bidi ai tuoi documenti Word nella tua applicazione C#. Aspose.Words offre un'enorme flessibilità e potenza per lavorare con la formattazione del testo e la gestione della lingua, consentendoti di creare documenti multilingue in modo professionale.