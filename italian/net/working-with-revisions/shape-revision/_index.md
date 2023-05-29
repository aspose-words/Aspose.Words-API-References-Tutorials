---
title: Revisione della forma
linktitle: Revisione della forma
second_title: Riferimento all'API Aspose.Words per .NET
description: Rivedi le forme in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/shape-revision/
---

In questa guida dettagliata, ti illustreremo come apportare revisioni alle forme in un documento di Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output del markdown.

## Passaggio 1: creazione del documento e aggiunta di forme

Il primo passo è creare un nuovo documento e aggiungere forme.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Passaggio 2: tenere traccia delle revisioni e aggiungere un'altra forma

Attiveremo il monitoraggio delle revisioni e aggiungeremo un'altra forma.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Passaggio 3: ottieni la raccolta di forme e controlla le revisioni

Otterremo la raccolta di forme dal documento e controlleremo le revisioni associate a ciascuna forma.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Passaggio 4: controllo delle revisioni dello spostamento della forma

Stiamo per caricare un documento esistente contenente revisioni di spostamento della forma e controllare le revisioni associate.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Esempio di codice sorgente per Shape Revision utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per apportare modifiche alle forme in un documento utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document();

// Inserisci una forma in linea senza tenere traccia delle revisioni.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Inizia a tenere traccia delle revisioni e quindi inserisci un'altra forma.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Ottieni la raccolta di forme del documento che include solo le due forme che abbiamo aggiunto.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Rimuovi la prima forma.
shapes[0].Remove();

// Poiché abbiamo rimosso quella forma durante il rilevamento delle modifiche, la forma conta come una revisione di eliminazione.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// E abbiamo inserito un'altra forma durante il monitoraggio delle modifiche, in modo che la forma venga conteggiata come una revisione dell'inserimento.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

//Il documento ha una forma che è stata spostata, ma le revisioni di spostamento forma avranno due istanze di quella forma.
// Uno sarà la forma nella sua destinazione di arrivo e l'altro sarà la forma nella sua posizione originale.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Questo è il passaggio alla revisione, anche la forma al suo arrivo a destinazione.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Questo è lo spostamento dalla revisione, che è la forma nella sua posizione originale.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

