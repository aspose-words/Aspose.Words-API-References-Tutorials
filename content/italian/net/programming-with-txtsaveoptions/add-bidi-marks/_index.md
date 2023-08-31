---
title: Aggiungi segni Bidi nel documento Word
linktitle: Aggiungi segni Bidi nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Impara ad aggiungere segni Bidi a un documento Word utilizzando Aspose.Words per .NET e crea documenti multilingue professionali.
type: docs
weight: 10
url: /it/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words per .NET è una potente libreria per creare, modificare e manipolare documenti Word in un'applicazione C#. Tra le funzionalità offerte da Aspose.Words c'è la possibilità di aggiungere segni Bidi (bidirezionali) a un documento. In questa guida ti spiegheremo come utilizzare il codice sorgente C# di Aspose.Words per .NET per aggiungere segni Bidi a un documento.

## Comprensione della libreria Aspose.Words

Prima di immergersi nel codice, è importante comprendere la libreria Aspose.Words per .NET. Aspose.Words è una libreria popolare che rende l'elaborazione delle parole con documenti Word semplice ed efficiente. Offre un'ampia gamma di funzionalità per creare, modificare e manipolare documenti Word, inclusa l'aggiunta di segni Bidi.

## Creazione del documento e aggiunta di contenuti

Il primo passo è creare un nuovo documento e aggiungervi contenuto. Utilizza la classe Document per creare una nuova istanza del documento. Quindi utilizzare la classe DocumentBuilder per aggiungere testo al documento. Ecco un esempio:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

In questo esempio creiamo un nuovo documento e utilizziamo DocumentBuilder per aggiungere testo. Abbiamo aggiunto tre righe di testo: una in inglese, una in ebraico e una in arabo per dimostrare l'aggiunta di contenuti in diverse lingue.

## Aggiunti segni Bidi

Una volta aggiunto il contenuto, ora possiamo aggiungere i segni Bidi al documento. Per questo utilizziamo la classe TxtSaveOptions e impostiamo la proprietà AddBidiMarks su true. Ecco come:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

In questo esempio creiamo un'istanza di TxtSaveOptions e impostiamo la proprietà AddBidiMarks su true. Successivamente, utilizziamo il metodo Save della classe Document per salvare il documento con segni Bidi.

### Codice sorgente di esempio per la funzionalità "Aggiungi segni Bidi" con Aspose.Words per .NET

```csharp
// Percorso della directory dei documenti
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea il documento e aggiungi contenuto
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

In questa guida, abbiamo spiegato come utilizzare Aspose.Words per .NET per aggiungere segni Bidi a un documento Word utilizzando il codice sorgente C# fornito. Seguendo i passaggi forniti, puoi aggiungere facilmente i segni Bidi ai tuoi documenti Word nella tua applicazione C#. Aspose.Words offre un'enorme flessibilità e potenza per l'elaborazione di parole con formattazione del testo e gestione della lingua, consentendoti di creare documenti multilingue in modo professionale.

### Domande frequenti

#### D: Cos'è Aspose.Words per .NET?
Aspose.Words per .NET è una potente libreria per creare, modificare e manipolare documenti Word in un'applicazione C#. Offre molte funzionalità per l'elaborazione di parole con documenti Word, inclusa l'aggiunta di segni Bidi (bidirezionali).

#### D: Quali funzionalità offre Aspose.Words per .NET?
Aspose.Words per .NET offre un'ampia gamma di funzionalità per creare, modificare e manipolare documenti Word. Alcune di queste funzionalità includono la creazione di documenti, l'aggiunta di contenuti, la formattazione del testo, la gestione delle tabelle, l'unione e la divisione di documenti, la conversione di documenti e altro ancora.

#### D: Come posso aggiungere segni Bidi a un documento Word utilizzando Aspose.Words per .NET?
Puoi aggiungere segni Bidi a un documento Word seguendo questi passaggi:

 Crea un nuovo documento utilizzando il file`Document` classe.

 Usa il`DocumentBuilder` classe per aggiungere contenuto al documento.

 Dopo aver aggiunto il contenuto, utilizzare il file`TxtSaveOptions`classe e impostare il file`AddBidiMarks` proprietà a`true`.

 Salva il documento con i segni Bidi utilizzando il file`Save` metodo del`Document` classe.

#### D: Aspose.Words supporta più lingue per l'aggiunta di segni Bidi?
Sì, Aspose.Words supporta più lingue per l'aggiunta di segni Bidi. È possibile aggiungere segni Bidi al testo in diverse lingue, come inglese, ebraico e arabo, utilizzando Aspose.Words per .NET.

#### D: Sono disponibili opzioni aggiuntive per salvare il documento con i contrassegni Bidi?
 Sì, puoi specificare altre opzioni quando salvi il documento con i segni Bidi utilizzando il file`TxtSaveOptions` classe. Ad esempio, puoi impostare il formato di salvataggio del documento, le opzioni di codifica, ecc.