---
title: Ottieni punti di limiti di forma effettivi
linktitle: Ottieni punti di limiti di forma effettivi
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come recuperare i limiti effettivi di una forma in punti (unità di misura) in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Questo tutorial spiega come recuperare i limiti effettivi di una forma in punti (unità di misura) in un documento di Word utilizzando Aspose.Words per .NET. I limiti rappresentano la dimensione e la posizione della forma all'interno del documento.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e lavoro con documenti Word.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
 Crea una nuova istanza di`Document` classe e a`DocumentBuilder` opporsi a lavorare con il documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserire una forma immagine
 Usa il`InsertImage` metodo del`DocumentBuilder` oggetto per inserire una forma immagine nel documento. Fornire il percorso del file immagine come parametro.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Passaggio 3: Recupera i punti dei limiti di forma effettivi
 Accedi alle forme`ShapeRenderer` usando il`GetShapeRenderer`metodo. Quindi, recupera i limiti effettivi della forma in punti utilizzando il`BoundsInPoints` proprietà.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Codice sorgente di esempio per ottenere punti di limiti di forma effettivi utilizzando Aspose.Words per .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Questo è tutto! Hai recuperato con successo i limiti effettivi di una forma in punti nel documento di Word utilizzando Aspose.Words per .NET.