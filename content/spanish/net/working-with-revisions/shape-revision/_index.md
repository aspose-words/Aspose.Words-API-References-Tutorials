---
title: Revisión de forma
linktitle: Revisión de forma
second_title: API de procesamiento de documentos Aspose.Words
description: Revisar formas en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/shape-revision/
---

En esta guía paso a paso, le explicaremos cómo realizar revisiones de formas en un documento de Word utilizando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de rebajas.

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

## Paso 2: realice un seguimiento de las revisiones y agregue otra forma

Activaremos el seguimiento de revisiones y agregaremos otra forma.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Paso 3: obtenga la colección de formas y verifique las revisiones.

Obtendremos la colección de formas del documento y verificaremos las revisiones asociadas con cada forma.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Paso 4: Verificar las revisiones de movimiento de formas

Cargaremos un documento existente que contiene revisiones de desplazamiento de forma y verificaremos las revisiones asociadas.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Código fuente de ejemplo para Shape Revision usando Aspose.Words para .NET

Aquí está el código fuente completo para realizar revisiones de formas en un documento usando Aspose.Words para .NET:

```csharp
Document doc = new Document();

//Inserte una forma en línea sin realizar un seguimiento de las revisiones.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Comience a realizar un seguimiento de las revisiones y luego inserte otra forma.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Obtenga la colección de formas del documento que incluye solo las dos formas que agregamos.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Retire la primera forma.
shapes[0].Remove();

// Debido a que eliminamos esa forma mientras se realizaban el seguimiento de los cambios, la forma cuenta como una revisión de eliminación.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// E insertamos otra forma mientras realizamos el seguimiento de los cambios, por lo que esa forma contará como una revisión de inserción.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// El documento tiene una forma que se movió, pero las revisiones de movimiento de forma tendrán dos instancias de esa forma.
// Una será la forma en su destino de llegada y la otra será la forma en su ubicación original.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Este es el paso a la revisión, también la forma en su destino de llegada.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Este es el movimiento desde la revisión, que es la forma en su ubicación original.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Conclusión

En este tutorial, aprendimos cómo realizar revisiones de formas en un documento de Word usando Aspose.Words para .NET. Al seguir los pasos para crear el documento, habilitar el seguimiento de revisiones, verificar las revisiones asociadas con cada forma y verificar las revisiones para mover las formas, pudimos administrar las revisiones con éxito. Aspose.Words para .NET ofrece una potente API para procesamiento de textos con revisiones y formularios en documentos de Word.

### Preguntas frecuentes

#### P: ¿Cómo puedo crear un documento nuevo y agregar formas en Aspose.Words para .NET?

R: Para crear un nuevo documento y agregar formas en Aspose.Words para .NET, puede usar el siguiente código. Aquí agregamos dos formas, un cubo y un sol, a la primera sección del documento:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### P: ¿Cómo habilito el seguimiento de revisiones en Aspose.Words para .NET?

 R: Para habilitar el seguimiento de revisiones en Aspose.Words para .NET, puede utilizar el`StartTrackRevisions` método de la`Document` objeto. Este método toma como parámetro el nombre del autor de las revisiones:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### P: ¿Cómo puedo verificar las revisiones asociadas con cada forma en un documento Aspose.Words para .NET?

R: Para verificar las revisiones asociadas con cada forma en un documento Aspose.Words para .NET, puede obtener la colección de formas del documento usando el`GetChildNodes` método con el`NodeType.Shape` tipo de nodo. Luego podrás acceder a cada forma.`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , y`IsMoveToRevision` propiedades para determinar qué tipo de revisión está asociada con la forma:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### P: ¿Cómo puedo comprobar las revisiones de desplazamiento de las formas en un documento de Aspose.Words para .NET?

 R: Para verificar las revisiones de desplazamiento de forma en un documento de Aspose.Words para .NET, puede cargar un documento existente que contenga revisiones de desplazamiento de forma. Luego podrás acceder a cada forma.`IsMoveFromRevision` y`IsMoveToRevision` propiedades para determinar si se está moviendo y, de ser así, desde dónde y hacia dónde:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```