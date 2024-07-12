---
title: Mover nodo en documento rastreado
linktitle: Mover nodo en documento rastreado
second_title: API de procesamiento de documentos Aspose.Words
description: Mueva nodos en un documento rastreado con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/move-node-in-tracked-document/
---

En esta guía paso a paso, le explicaremos cómo mover un nodo en un documento de Word con seguimiento utilizando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de rebajas.

## Paso 1: crear el documento

El primer paso es crear un nuevo documento y agregar párrafos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Paso 2: realizar un seguimiento de las revisiones

Vamos a habilitar el seguimiento de revisiones en el documento.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Paso 3: mover un nodo

Moveremos un nodo (párrafo) de una posición a otra mientras generamos revisiones.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Paso 4: Deje de rastrear reseñas

Dejaremos de rastrear las revisiones en el documento.

```csharp
doc.StopTrackRevisions();
```

## Paso 5: guardar el documento

 Después de insertar el campo del formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save`método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Código fuente de ejemplo para mover nodo en documento rastreado usando Aspose.Words para .NET

Aquí está el código fuente completo para mover un nodo en un documento rastreado usando Aspose.Words para .NET:


```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Comience a realizar un seguimiento de las revisiones.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Generar revisiones al mover un nodo de una ubicación a otra.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Detenga el proceso de seguimiento de revisiones.
doc.StopTrackRevisions();

// Hay 3 párrafos adicionales en el rango de salida.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Conclusión

En este tutorial, aprendimos cómo mover un nodo en un documento de Word con seguimiento usando Aspose.Words para .NET. Siguiendo los pasos para crear el documento, habilitar el seguimiento de revisiones, mover el nodo y detener el seguimiento de revisiones, pudimos realizar esta manipulación con éxito. Aspose.Words para .NET es una poderosa herramienta para el procesamiento de textos con documentos de Word y ofrece funciones avanzadas para administrar revisiones. Ahora puede utilizar este conocimiento para mover nodos en sus propios documentos de Word mientras realiza un seguimiento de las revisiones utilizando Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cómo puedo habilitar el seguimiento de revisiones en un documento de Aspose.Words para .NET?

 R: Para habilitar el seguimiento de revisiones en un documento Aspose.Words para .NET, puede utilizar el`StartTrackRevisions` método de la`Document` objeto. Este método toma como parámetros el nombre del autor de las revisiones y la fecha de inicio del seguimiento de las revisiones.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### P: ¿Cómo puedo mover un nodo en un documento rastreado sin generar revisiones?

 R: Si desea mover un nodo en un documento rastreado sin generar revisiones, puede usar el`Remove`y`InsertAfter` o`InsertBefore` métodos de la`Node` objeto. Por ejemplo, para mover un párrafo tras otro, puede utilizar el siguiente código:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### P: ¿Cómo puedo detener el seguimiento de revisiones en un documento de Aspose.Words para .NET?

 R: Para detener el seguimiento de las revisiones en un documento de Aspose.Words para .NET, puede utilizar el`StopTrackRevisions` método de la`Document` objeto.

```csharp
doc.StopTrackRevisions();
```