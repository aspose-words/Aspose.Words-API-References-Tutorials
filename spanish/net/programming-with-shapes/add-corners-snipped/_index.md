---
title: Añadir esquinas cortadas
linktitle: Añadir esquinas cortadas
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a agregar una forma con esquinas recortadas a un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-shapes/add-corners-snipped/
---

 Este tutorial explica cómo agregar una forma con esquinas recortadas a un documento de Word usando Aspose.Words para .NET. La forma de las esquinas recortadas se puede personalizar e insertar usando el`InsertShape` método.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y trabajo con documentos de Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"`con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cree un nuevo documento y DocumentBuilder
 Crear una nueva instancia de la`Document` clase y un`DocumentBuilder` objeto de trabajar con el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: inserte la forma recortada de las esquinas
 Utilizar el`InsertShape` metodo de la`DocumentBuilder` objeto para insertar una forma con las esquinas recortadas. Especifique el tipo de forma (en este caso,`ShapeType.TopCornersSnipped`) y proporcione el tamaño deseado para la forma.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Paso 4: Guarde el documento
 Guarde el documento en el directorio especificado usando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Ejemplo de código fuente para agregar esquinas cortadas usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

¡Eso es todo! Ha agregado con éxito una forma recortada en las esquinas a su documento de Word usando Aspose.Words para .NET.