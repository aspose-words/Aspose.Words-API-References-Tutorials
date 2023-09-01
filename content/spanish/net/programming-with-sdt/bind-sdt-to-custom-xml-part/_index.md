---
title: Vincular SDT a una parte XML personalizada
linktitle: Vincular SDT a una parte XML personalizada
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo vincular un SDT a una parte XML personalizada usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Este tutorial demuestra cómo vincular una etiqueta de documento estructurado (SDT) a una parte XML personalizada usando Aspose.Words para .NET. Los SDT le permiten agregar controles de contenido estructurado a un documento de Word y CustomXmlParts proporciona una manera de almacenar datos XML personalizados asociados con el documento.

## Requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y XML.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: crear un documento y CustomXmlPart
 Crear una nueva instancia del`Document` clase y un`CustomXmlPart` para almacenar los datos XML personalizados. El XML personalizado debe tener un formato XML válido. En este ejemplo, utilizamos una cadena XML simple.`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Paso 3: agregar una etiqueta de documento estructurado (SDT) al documento
 Agrega un`StructuredDocumentTag` al documento para que sirva como control de contenido. Especifica el`SdtType` como`PlainText` y el`MarkupLevel` como`Block` para crear un SDT a nivel de bloque.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Paso 4: configurar la asignación XML para SDT
 Asigne el SDT al`CustomXmlPart` usando el`SetMapping` método de la`XmlMapping` propiedad. Especifica el`CustomXmlPart` , la expresión XPath para localizar el nodo XML deseado y el prefijo del espacio de nombres si es necesario. En este ejemplo, asignamos el SDT a`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Paso 5: guarde el documento
 Guarde el documento modificado en el directorio especificado utilizando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Código fuente de ejemplo para Bind Sd Tto Custom Xml Part usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

¡Eso es todo! Ha vinculado con éxito un SDT a un CustomXmlPart en su documento de Word usando Aspose.Words para .NET.