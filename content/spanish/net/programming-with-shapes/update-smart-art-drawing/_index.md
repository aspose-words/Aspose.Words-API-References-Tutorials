---
title: Actualizar dibujo artístico inteligente
linktitle: Actualizar dibujo artístico inteligente
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo actualizar el dibujo Smart Art en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-shapes/update-smart-art-drawing/
---

Este tutorial explica cómo actualizar el dibujo Smart Art en un documento de Word usando Aspose.Words para .NET. Al recorrer las formas en el documento y verificar si tienen Smart Art, puede actualizar el dibujo Smart Art para reflejar cualquier cambio realizado en sus datos.

## Requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde se encuentra su documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue el documento
 Cargue el documento de Word que contiene el dibujo Smart Art usando el`Document` constructor de clases.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Paso 3: actualice el dibujo de Smart Art
 Iterar a través de las formas en el documento usando el`GetChildNodes` método con el`NodeType.Shape` parámetro. Compruebe si cada forma tiene Smart Art usando el`HasSmartArt` propiedad, y si es cierto, llame a la`UpdateSmartArtDrawing` método para actualizar el dibujo Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Código fuente de ejemplo para actualizar Smart Art Drawing usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

¡Eso es todo! Ha actualizado con éxito el dibujo Smart Art en su documento de Word utilizando Aspose.Words para .NET.