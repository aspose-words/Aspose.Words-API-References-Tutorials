---
title: Establecer estilo de control de contenido
linktitle: Establecer estilo de control de contenido
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a establecer el estilo de un control de contenido en un documento de Word usando Aspose.Words para .NET, aplicando un formato consistente.
type: docs
weight: 10
url: /es/net/programming-with-sdt/set-content-control-style/
---

Este tutorial explica cómo configurar el estilo de un control de contenido en un documento de Word utilizando Aspose.Words para .NET. Puede aplicar estilos predefinidos o personalizados a los controles de contenido para lograr un formato uniforme.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y Procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde se encuentra su documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento y recupere el control de contenido
 Cargue el documento de Word usando el`Document` constructor, pasando la ruta al documento como parámetro. Recupere el control de contenido deseado del documento. En este ejemplo, asumimos que el control de contenido es la primera etiqueta de documento estructurado en el documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Paso 3: recuperar el estilo y aplicarlo al control de contenido
 Recupere el estilo deseado de la colección de estilos del documento. En este ejemplo, recuperamos el estilo "Cita" usando`StyleIdentifier.Quote` . Luego, asigne el estilo recuperado al`Style` propiedad de la etiqueta del documento estructurado.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Paso 4: Guarde el documento
 Guarde el documento modificado en el directorio especificado usando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Ejemplo de código fuente para establecer el estilo de control de contenido usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

¡Eso es todo! Ha establecido con éxito el estilo de un control de contenido en su documento de Word utilizando Aspose.Words para .NET.