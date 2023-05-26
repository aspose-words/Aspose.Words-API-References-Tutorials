---
title: Sección múltiple
linktitle: Sección múltiple
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a recuperar y procesar etiquetas de documentos estructurados de varias secciones en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/multi-section/
---

Este tutorial explica cómo trabajar con etiquetas de documentos estructurados de varias secciones en un documento de Word usando Aspose.Words para .NET. Puede recuperar y procesar las etiquetas de sección presentes en el documento.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y trabajo con documentos de Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde se encuentra su documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento y recupere las etiquetas de varias secciones
 Cargue el documento de Word usando el`Document` constructor, pasando la ruta al documento como parámetro. Recupere todos los nodos de inicio de rango de etiqueta de documento estructurado en el documento usando el`GetChildNodes` método.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Paso 3: Procese las etiquetas de varias secciones
Iterar a través de la colección de nodos de inicio de rango de etiquetas de documentos estructurados. En este ejemplo, simplemente imprimimos el título de cada etiqueta en la consola. Puede realizar un procesamiento adicional en función de sus requisitos.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Ejemplo de código fuente para varias secciones usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

¡Eso es todo! Ha recuperado y procesado con éxito etiquetas de documentos estructurados de varias secciones en su documento de Word utilizando Aspose.Words para .NET.