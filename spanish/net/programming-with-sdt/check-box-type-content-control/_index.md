---
title: Control de contenido de tipo de casilla de verificación
linktitle: Control de contenido de tipo de casilla de verificación
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a crear un control de contenido de tipo casilla de verificación en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/check-box-type-content-control/
---

Este tutorial explica cómo crear un control de contenido de tipo casilla de verificación en un documento de Word usando Aspose.Words para .NET. Los controles de contenido de la casilla de verificación permiten a los usuarios seleccionar o borrar una casilla de verificación dentro del documento.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y Procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cree un documento y DocumentBuilder
 Crear una nueva instancia de la`Document` clase y un`DocumentBuilder` para construir el contenido del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: agregue un control de contenido de tipo de casilla de verificación
 Crear un`StructuredDocumentTag` con`SdtType.Checkbox` para representar el control de contenido de la casilla de verificación. Especificar`MarkupLevel.Inline` para colocarlo dentro del texto.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Paso 4: Guarde el documento
 Guarde el documento en el directorio especificado usando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.CheckBoxTypeContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Ejemplo de código fuente para el control de contenido de tipo de casilla de verificación usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

¡Eso es todo! Ha creado con éxito un control de contenido de tipo casilla de verificación en su documento de Word utilizando Aspose.Words para .NET.