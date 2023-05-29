---
title: Mover nodo en documento con seguimiento
linktitle: Mover nodo en documento con seguimiento
second_title: Referencia de API de Aspose.Words para .NET
description: Mueva nodos en un documento con seguimiento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/move-node-in-tracked-document/
---

En esta guía paso a paso, lo guiaremos a través de cómo mover un nodo en un documento de Word rastreado usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de Markdown.

## Paso 1: Crear el documento

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

## Paso 2: seguimiento de las revisiones

Vamos a habilitar el seguimiento de revisiones en el documento.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Paso 3: Mover un nodo

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

## Paso 4: deja de rastrear las reseñas

Dejaremos de rastrear las revisiones en el documento.

```csharp
doc.StopTrackRevisions();
```

## Paso 5: Guardar el documento

 Después de insertar el campo de formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Código fuente de ejemplo para Mover nodo en documento rastreado usando Aspose.Words para .NET

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

// Comience a rastrear las revisiones.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Genera revisiones al mover un nodo de una ubicación a otra.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Detener el proceso de seguimiento de revisiones.
doc.StopTrackRevisions();

// Hay 3 párrafos adicionales en el rango de origen.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

