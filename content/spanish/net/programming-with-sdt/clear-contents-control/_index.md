---
title: Control de contenido claro
linktitle: Control de contenido claro
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo borrar el contenido de un control en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/clear-contents-control/
---

Este tutorial demuestra cómo borrar el contenido de una SDT en un documento de Word usando Aspose.Words para .NET. Al borrar el contenido de una SDT, se elimina cualquier texto o nodos secundarios dentro del control de contenido.

## Requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde se encuentra su documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue el documento y obtenga la etiqueta StructuredDocumentTag
 Cargue el documento de Word usando el`Document` constructor, pasando la ruta al documento como parámetro. Luego, recupere el deseado`StructuredDocumentTag`del documento. En este ejemplo, asumimos que SDT es el primer nodo secundario del documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Paso 3: borrar el contenido de StructuredDocumentTag
 Borre el contenido del SDT utilizando el`Clear` método. Esto elimina cualquier texto o nodos secundarios dentro del control de contenido.

```csharp
sdt.Clear();
```

## Paso 4: guarde el documento
 Guarde el documento modificado usando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Código fuente de ejemplo para Clear Contents Control usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

¡Eso es todo! Ha borrado con éxito el contenido de StructuredDocumentTag en su documento de Word usando Aspose.Words para .NET.