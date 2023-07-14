---
title: Immagine
linktitle: Immagine
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come inserire e personalizzare l'immagine con Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/working-with-markdown/image/
---

In questo esempio, spiegheremo come utilizzare la funzione immagine con Aspose.Words per .NET. Le immagini consentono di inserire illustrazioni e grafici in un documento.

## Passaggio 1: utilizzo di un generatore di documenti

Innanzitutto, utilizzeremo un generatore di documenti per aggiungere contenuto al nostro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passaggio 2: Inserimento di un'immagine

 Possiamo inserire un'immagine usando il`Shape` class e specificando il tipo di immagine, qui`ShapeType.Image` . Impostiamo anche il tipo di avvolgimento dell'immagine su`WrapType.Inline`.

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


### FAQ

#### D: Come posso inserire un'immagine da un file locale in Aspose.Words?

 R: Per inserire un'immagine da un file locale in Aspose.Words, puoi usare il file`Shape` classe e il`InsertImage` metodo.

#### D: Posso inserire un'immagine da un URL in Aspose.Words?

 A: Sì, puoi inserire un'immagine da un URL in Aspose.Words. Puoi usare lo stesso`InsertImage`metodo e specificare l'URL dell'immagine anziché il percorso del file locale.

#### D: Come posso ridimensionare un'immagine in Aspose.Words?

 A: Per ridimensionare un'immagine in Aspose.Words, puoi usare il`Width` E`Height` proprietà del`Shape` oggetto.

#### D: Posso applicare filtri alle immagini in Aspose.Words?

 R: Sì, puoi applicare filtri alle immagini in Aspose.Words. Ad esempio, puoi applicare un filtro di sfocatura a un'immagine utilizzando il`ApplyGaussianBlur` metodo del`Shape` oggetto.

#### D: Come posso sostituire un'immagine con un'altra in Aspose.Words?

 A: Per sostituire un'immagine con un'altra in Aspose.Words, puoi usare il`Replace` metodo del`Shape` classe. Questo metodo prende come parametro il`Shape` oggetto dell'immagine da sostituire e il`Shape` oggetto della nuova immagine.