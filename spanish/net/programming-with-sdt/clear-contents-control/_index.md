---
title: Control de contenido claro
linktitle: Control de contenido claro
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a borrar el contenido de un control en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/clear-contents-control/
---

Este tutorial demuestra cómo borrar el contenido de un SDT en un documento de Word usando Aspose.Words para .NET. Borrar el contenido de una SDT elimina cualquier texto o nodos secundarios dentro del control de contenido.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y trabajo con documentos de Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde se encuentra su documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento y obtenga la etiqueta de documento estructurado
 Cargue el documento de Word usando el`Document` constructor, pasando la ruta al documento como parámetro. Luego, recupere el deseado`StructuredDocumentTag` del documento En este ejemplo, asumimos que la SDT es el primer nodo secundario del documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Paso 3: borre el contenido de la etiqueta de documento estructurado
 Borre el contenido de la SDT usando el`Clear` método. Esto elimina cualquier texto o nodos secundarios dentro del control de contenido.

```csharp
sdt.Clear();
```

## Paso 4: Guarde el documento
Guarde el documento modificado usando el`Save`método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Ejemplo de código fuente para Clear Contents Control usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

¡Eso es todo! Ha borrado con éxito el contenido de una etiqueta de documento estructurado en su documento de Word usando Aspose.Words para .NET.