---
title: Imagen
linktitle: Imagen
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar y personalizar imágenes con Aspose.Words para .NET Guía paso a paso.
type: docs
weight: 10
url: /es/net/working-with-markdown/image/
---

En este ejemplo, explicaremos cómo utilizar la función de imagen con Aspose.Words para .NET. Las imágenes le permiten insertar ilustraciones y gráficos en un documento.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: Insertar una imagen

 Podemos insertar una imagen usando el`Shape` clase y especificando el tipo de imagen, aquí`ShapeType.Image` . También configuramos el tipo de envoltura de la imagen en`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Paso 3: Personalización de la imagen

 Personalizamos la imagen especificando su ruta completa, por ejemplo`"/attachment/1456/pic001.png"`y agregando un título a la imagen.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Código fuente de ejemplo para imágenes con Aspose.Words para .NET

```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// Insertar imagen.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

¡Enhorabuena! Ahora ha aprendido a utilizar la función de imágenes con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo puedo insertar una imagen de un archivo local en Aspose.Words?

 R: Para insertar una imagen de un archivo local en Aspose.Words, puede usar el`Shape` clase y el`InsertImage` método.

#### P: ¿Puedo insertar una imagen desde una URL en Aspose.Words?

 R: Sí, puedes insertar una imagen desde una URL en Aspose.Words. Puedes usar lo mismo`InsertImage` especifique la URL de la imagen en lugar de la ruta del archivo local.

#### P: ¿Cómo puedo cambiar el tamaño de una imagen en Aspose.Words?

 R: Para cambiar el tamaño de una imagen en Aspose.Words, puede usar el`Width` y`Height` propiedades de la`Shape` objeto.

#### P: ¿Puedo aplicar filtros a imágenes en Aspose.Words?

 R: Sí, puedes aplicar filtros a las imágenes en Aspose.Words. Por ejemplo, puede aplicar un filtro de desenfoque a una imagen usando el`ApplyGaussianBlur` método de la`Shape` objeto.

#### P: ¿Cómo puedo reemplazar una imagen por otra en Aspose.Words?

 R: Para reemplazar una imagen con otra en Aspose.Words, puede usar el`Replace` método de la`Shape` clase. Este método toma como parámetro el`Shape` objeto de la imagen a reemplazar y el`Shape` objeto de la nueva imagen.