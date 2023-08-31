---
title: Agregar forma de grupo
linktitle: Agregar forma de grupo
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a agregar una forma de grupo con varias formas a un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-shapes/add-group-shape/
---

Este tutorial explica cómo agregar una forma de grupo que contenga varias formas a un documento de Word usando Aspose.Words para .NET. Las formas grupales le permiten combinar y manipular múltiples formas como una sola entidad.

## Requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cree un nuevo documento y GroupShape
 Crear una nueva instancia del`Document` clase y`GroupShape` objeto de trabajar con el documento.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Paso 3: crear y agregar formas a GroupShape
 Crea formas individuales como`accentBorderShape` y`actionButtonShape` utilizando el`Shape` clase. Personaliza sus propiedades como desees. Añade estas formas a la`groupShape` objeto.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Paso 4: Establecer dimensiones para GroupShape
 Establezca el ancho, alto y tamaño de coordenadas para el`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Paso 5: inserte GroupShape en el documento
 Crear un`DocumentBuilder` objeto e inserte el`groupShape` en el documento utilizando el`InsertNode` método.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Paso 6: guarde el documento
 Guarde el documento en el directorio especificado utilizando el`Save`método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Código fuente de ejemplo para Agregar forma de grupo usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

¡Eso es todo! Ha agregado con éxito una forma de grupo que contiene varias formas a su documento de Word usando Aspose.W