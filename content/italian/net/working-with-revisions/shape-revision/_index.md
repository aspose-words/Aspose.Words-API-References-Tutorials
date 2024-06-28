---
title: Revisione della forma
linktitle: Revisione della forma
second_title: API di elaborazione dei documenti Aspose.Words
description: Rivedi le forme in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-revisions/shape-revision/
---

In questa guida passo passo ti spiegheremo come apportare revisioni alle forme in un documento Word utilizzando Aspose.Words per .NET. Ti forniremo il codice sorgente completo e ti mostreremo come formattare l'output di markdown.

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

## Passaggio 2: tieni traccia delle revisioni e aggiungi un'altra forma

Attiveremo il tracciamento delle revisioni e aggiungeremo un'altra forma.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Passaggio 3: ottieni la raccolta di forme e controlla le revisioni.

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

Caricheremo un documento esistente contenente revisioni di spostamento della forma e controlleremo le revisioni associate.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Codice sorgente di esempio per Shape Revision utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per apportare revisioni alle forme in un documento utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document();

//Inserisci una forma in linea senza tenere traccia delle revisioni.
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

// Poiché la forma è stata rimossa durante il rilevamento delle modifiche, la forma conta come una revisione di eliminazione.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// E abbiamo inserito un'altra forma durante il monitoraggio delle modifiche, in modo che quella forma venga conteggiata come una revisione di inserimento.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// Il documento ha una forma che è stata spostata, ma le revisioni dello spostamento della forma avranno due istanze di quella forma.
// Una sarà la forma nella destinazione di arrivo e l'altra sarà la forma nella posizione originale.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Questo è il passaggio alla revisione, anche la forma alla sua destinazione d'arrivo.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Questo è il passaggio dalla revisione, ovvero la forma nella sua posizione originale.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Conclusione

In questo tutorial, abbiamo imparato come apportare revisioni alle forme in un documento Word utilizzando Aspose.Words per .NET. Seguendo i passaggi di creazione del documento, abilitando il tracciamento delle revisioni, controllando le revisioni associate a ciascuna forma e controllando le revisioni per lo spostamento delle forme, siamo stati in grado di gestire le revisioni con successo. Aspose.Words per .NET offre una potente API per l'elaborazione di parole con revisioni e moduli nei documenti Word.

### Domande frequenti

#### D: Come posso creare un nuovo documento e aggiungere forme in Aspose.Words per .NET?

R: Per creare un nuovo documento e aggiungere forme in Aspose.Words per .NET, è possibile utilizzare il seguente codice. Qui aggiungiamo due forme, un cubo e un sole, alla prima sezione del documento:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### D: Come abilito il monitoraggio delle revisioni in Aspose.Words per .NET?

 R: Per abilitare il monitoraggio delle revisioni in Aspose.Words per .NET, è possibile utilizzare il file`StartTrackRevisions` metodo del`Document` oggetto. Questo metodo prende come parametro il nome dell'autore delle revisioni:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### D: Come posso verificare le revisioni associate a ciascuna forma in un documento Aspose.Words per .NET?

R: Per verificare le revisioni associate a ciascuna forma in un documento Aspose.Words per .NET, è possibile ottenere la raccolta di forme del documento utilizzando il comando`GetChildNodes` metodo con il`NodeType.Shape` tipo di nodo. Quindi puoi accedere a ciascuna forma`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , E`IsMoveToRevision` proprietà per determinare quale tipo di revisione è associata alla forma:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### D: Come posso verificare le revisioni di spostamento delle forme in un documento Aspose.Words per .NET?

 R: Per verificare la presenza di revisioni di spostamento della forma in un documento Aspose.Words per .NET, è possibile caricare un documento esistente che contiene revisioni di spostamento della forma. Quindi puoi accedere a ciascuna forma`IsMoveFromRevision` E`IsMoveToRevision` proprietà per determinare se viene spostato e, in tal caso, da dove e a dove:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```