---
title: Establecer color de control de contenido
linktitle: Establecer color de control de contenido
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar el color de un control de contenido en un documento de Word usando Aspose.Words para .NET, personalizando su apariencia.
type: docs
weight: 10
url: /es/net/programming-with-sdt/set-content-control-color/
---

Este tutorial explica cómo configurar el color de un control de contenido en un documento de Word usando Aspose.Words para .NET. Puede personalizar la apariencia de los controles de contenido cambiando su color.

## Requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde se encuentra su documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue el documento y recupere el control de contenido
 Cargue el documento de Word usando el`Document` constructor, pasando la ruta al documento como parámetro. Recupere el control de contenido deseado del documento. En este ejemplo, asumimos que el control de contenido es la primera etiqueta de documento estructurado del documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Paso 3: establezca el color de control de contenido
 Establezca el color del control de contenido asignando un`Color` valor a la`Color` Propiedad de la etiqueta del documento estructurado. En este ejemplo, configuramos el color en rojo.

```csharp
sdt.Color = Color.Red;
```

## Paso 4: guarde el documento
 Guarde el documento modificado en el directorio especificado utilizando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.SetContentControlColor.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Código fuente de ejemplo para establecer el color de control de contenido usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

¡Eso es todo! Ha configurado con éxito el color de un control de contenido en su documento de Word usando Aspose.Words para .NET.