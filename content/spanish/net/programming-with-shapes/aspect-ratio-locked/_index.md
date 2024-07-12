---
title: Relación de aspecto bloqueada
linktitle: Relación de aspecto bloqueada
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a bloquear o desbloquear la relación de aspecto de una forma en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-shapes/aspect-ratio-locked/
---

Este tutorial explica cómo bloquear o desbloquear la relación de aspecto de una forma en un documento de Word usando Aspose.Words para .NET. Al bloquear la relación de aspecto, puede mantener las proporciones originales de la forma al cambiar su tamaño.

## Requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"`con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cree un nuevo documento y DocumentBuilder
 Crear una nueva instancia del`Document` clase y un`DocumentBuilder` objeto de trabajar con el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: insertar una forma de imagen
 Utilizar el`InsertImage` método de la`DocumentBuilder`objeto para insertar una forma de imagen en el documento. Proporcione la ruta al archivo de imagen como parámetro.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Paso 4: bloquear o desbloquear la relación de aspecto
 Selecciona el`AspectRatioLocked` propiedad de la forma para`true` o`false` para bloquear o desbloquear la relación de aspecto, respectivamente.

```csharp
shape.AspectRatioLocked = false; // Desbloquear la relación de aspecto
```

## Paso 5: guarde el documento
 Guarde el documento en el directorio especificado utilizando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Código fuente de ejemplo para relación de aspecto bloqueada usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

¡Eso es todo! Ha bloqueado o desbloqueado con éxito la relación de aspecto de una forma en su documento de Word usando Aspose.Words para .NET.