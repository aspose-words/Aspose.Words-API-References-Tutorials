---
title: Sposta nel documento Inizio Fine
linktitle: Sposta nel documento Inizio Fine
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come utilizzare Aspose.Words per .NET per passare all'inizio e alla fine del documento nei documenti di Word con questa guida dettagliata.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/move-to-document-start-end/
---

In questo esempio, esploreremo la funzionalità Move To Document Start/End di Aspose.Words per .NET. Aspose.Words è una potente libreria di manipolazione dei documenti che consente agli sviluppatori di creare, modificare e convertire i documenti di Word a livello di codice. La funzione Move To Document Start/End ci consente di navigare all'inizio o alla fine di un documento utilizzando la classe DocumentBuilder.

## Spiegando il codice sorgente passo dopo passo

Esaminiamo il codice sorgente passo dopo passo per capire come utilizzare la funzionalità Sposta in inizio/fine documento utilizzando Aspose.Words per .NET.


## Passaggio 1: inizializzazione del documento e del generatore di documenti

Successivamente, inizializza gli oggetti Document e DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: passare all'inizio del documento

Per spostare la posizione del cursore all'inizio del documento, utilizzare il metodo MoveToDocumentStart della classe DocumentBuilder:

```csharp
builder.MoveToDocumentStart();
```

## Passaggio 3: spostamento alla fine del documento

Per spostare la posizione del cursore alla fine del documento, utilizzare il metodo MoveToDocumentEnd della classe DocumentBuilder:

```csharp
builder.MoveToDocumentEnd();
```

## Passaggio 4: emissione della posizione del cursore

È possibile emettere la posizione del cursore utilizzando Console.WriteLine o qualsiasi altro metodo desiderato. Per esempio:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### Esempio di codice sorgente per Move To Document Start/End utilizzando Aspose.Words per .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sposta la posizione del cursore all'inizio del documento.
builder.MoveToDocumentStart();
Console.WriteLine("\nThis is the beginning of the document.");

// Sposta la posizione del cursore alla fine del documento.
builder.MoveToDocumentEnd();
Console.WriteLine("\nThis is the end of the document.");
```

## Conclusione

In questo esempio, abbiamo esplorato la funzionalità Move To Document Start/End di Aspose.Words per .NET. Abbiamo imparato come navigare all'inizio e alla fine di un documento utilizzando la classe DocumentBuilder. Questa funzionalità è utile quando si lavora a livello di codice con documenti di Word e si ha la necessità di manipolare o inserire contenuto in posizioni specifiche all'interno del documento.