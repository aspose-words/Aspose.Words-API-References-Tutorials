---
title: Asignación Xml de inicio de rango de etiquetas de documento estructurado
linktitle: Asignación Xml de inicio de rango de etiquetas de documento estructurado
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar la asignación XML para un rango de etiquetas de documento estructurado que comienza en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Este tutorial explica cómo configurar la asignación XML para un rango de etiquetas de documento estructurado que comienza en un documento de Word usando Aspose.Words para .NET. El mapeo XML le permite mostrar partes específicas de una fuente de datos XML dentro del control de contenido.

## Requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde se encuentra su documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue el documento y cree la parte XML
 Cargue el documento de Word usando el`Document`constructor, pasando la ruta al documento como parámetro. Cree una parte XML que contenga los datos que desea mostrar dentro de la etiqueta del documento estructurado.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Paso 3: configurar la asignación XML para la etiqueta de documento estructurado
Recupere el rango de etiquetas del documento estructurado a partir del documento. Luego, configure la asignación XML para la etiqueta del documento estructurado para mostrar una parte específica de la parte XML personalizada mediante una expresión XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Paso 4: guarde el documento
 Guarde el documento modificado en el directorio especificado utilizando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Código fuente de ejemplo para el rango de etiquetas de documentos estructurados Iniciar mapeo XML usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Construya una parte XML que contenga datos y agréguela a la colección CustomXmlPart del documento.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Cree una StructuredDocumentTag que mostrará el contenido de nuestro CustomXmlPart en el documento.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Si configuramos una asignación para nuestra StructuredDocumentTag,
	//solo mostrará una parte de CustomXmlPart a la que apunta XPath.
	// Este XPath apuntará al segundo elemento "<text>" del contenido del primer elemento "<root>" de nuestro CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

¡Eso es todo! Ha configurado correctamente la asignación XML para un inicio de rango de etiquetas de documento estructurado en su documento de Word utilizando Aspose.Words para .NET.