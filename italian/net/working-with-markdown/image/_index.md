---
title: Immagine
linktitle: Immagine
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire e personalizzare l'immagine con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/image/
---

In questo esempio, spiegheremo come utilizzare la funzione immagine con Aspose.Words per .NET. Le immagini consentono di inserire illustrazioni e grafica in un documento.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: Inserimento di un'immagine

 Possiamo inserire un'immagine usando il`Shape` class e specificando il tipo di immagine, qui`ShapeType.Image` Impostiamo anche il tipo di avvolgimento dell'immagine su`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Passaggio 3: personalizzazione dell'immagine

 Ad esempio, personalizziamo l'immagine specificandone il percorso completo`"/attachment/1456/pic001.png"`e aggiungendo un titolo all'immagine.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Esempio di codice sorgente per immagini con Aspose.Words per .NET

```csharp
// Utilizzare un generatore di documenti per aggiungere contenuto al documento.
DocumentBuilder builder = new DocumentBuilder();

// Inserisci immagine.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Congratulazioni! Ora hai imparato come utilizzare la funzionalità delle immagini con Aspose.Words per .NET.

