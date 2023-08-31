---
title: Obtener puntos de límites de forma reales
linktitle: Obtener puntos de límites de forma reales
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a recuperar los límites reales de una forma en puntos (unidad de medida) en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Este tutorial explica cómo recuperar los límites reales de una forma en puntos (unidad de medida) en un documento de Word utilizando Aspose.Words para .NET. Los límites representan el tamaño y la posición de la forma dentro del documento.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y Procesamiento de textos con documentos Word.

## Paso 1: Cree un nuevo documento y DocumentBuilder
 Crear una nueva instancia de la`Document` clase y un`DocumentBuilder` objeto de trabajar con el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: inserta una forma de imagen
 Utilizar el`InsertImage` metodo de la`DocumentBuilder` objeto para insertar una forma de imagen en el documento. Proporcione la ruta al archivo de imagen como parámetro.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Paso 3: recuperar puntos de límites de forma reales
 Accede a la forma`ShapeRenderer` utilizando el`GetShapeRenderer` método. Luego, recupere los límites reales de la forma en puntos usando el`BoundsInPoints` propiedad.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Ejemplo de código fuente para Obtener puntos de límites de formas reales usando Aspose.Words para .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

¡Eso es todo! Ha recuperado con éxito los límites reales de una forma en puntos en su documento de Word utilizando Aspose.Words para .NET.