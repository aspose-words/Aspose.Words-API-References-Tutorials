---
title: Revisión de forma
linktitle: Revisión de forma
second_title: Referencia de API de Aspose.Words para .NET
description: Revise formas en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/shape-revision/
---

En esta guía paso a paso, lo guiaremos a través de cómo hacer revisiones a las formas en un documento de Word usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de Markdown.

## Paso 1: crear el documento y agregar formas

El primer paso es crear un nuevo documento y agregar formas.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Paso 2: Realiza un seguimiento de las revisiones y agrega otra forma

Activaremos el seguimiento de revisiones y agregaremos otra forma.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Paso 3: obtenga la colección de formas y busque revisiones

Obtendremos la colección de formas del documento y verificaremos las revisiones asociadas con cada forma.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Paso 4: Comprobación de las revisiones de movimiento de forma

Vamos a cargar un documento existente que contiene revisiones de desplazamiento de formas y verificar las revisiones asociadas.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Ejemplo de código fuente para Shape Revision usando Aspose.Words para .NET

Aquí está el código fuente completo para hacer revisiones a las formas en un documento usando Aspose.Words para .NET:

```csharp
Document doc = new Document();

// Inserte una forma en línea sin seguimiento de revisiones.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Comience a rastrear las revisiones y luego inserte otra forma.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Obtenga la colección de formas del documento que incluye solo las dos formas que agregamos.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Elimina la primera forma.
shapes[0].Remove();

// Debido a que eliminamos esa forma mientras se realizaba un seguimiento de los cambios, la forma cuenta como una revisión eliminada.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// E insertamos otra forma mientras rastreamos los cambios, por lo que esa forma contará como una revisión de inserción.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

//El documento tiene una forma que se movió, pero las revisiones de movimiento de forma tendrán dos instancias de esa forma.
// Uno será la forma en su destino de llegada y el otro será la forma en su ubicación original.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Este es el paso a revisión, también la forma en su destino de llegada.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Este es el movimiento desde la revisión, que es la forma en su ubicación original.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

