---
title: Estado actual de la casilla de verificación
linktitle: Estado actual de la casilla de verificación
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a recuperar y establecer el estado actual de un control de contenido de casilla de verificación en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/current-state-of-check-box/
---

Este tutorial explica cómo recuperar y establecer el estado actual de un control de contenido de casilla de verificación en un documento de Word usando Aspose.Words para .NET. Puede marcar o desmarcar la casilla de verificación según su estado actual.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y trabajo con documentos de Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde se encuentra su documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento y recupere el control de contenido de la casilla de verificación
 Cargue el documento de Word usando el`Document` constructor, pasando la ruta al documento como parámetro. Luego, recupere el control de contenido de casilla de verificación deseado del documento. En este ejemplo, asumimos que la casilla de verificación es la primera etiqueta de documento estructurado en el documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Paso 3: marque o desmarque la casilla de verificación según su estado actual
 Compruebe si la etiqueta del documento estructurado recuperado es del tipo`SdtType.Checkbox` . Si es así, configure el`Checked` propiedad del control de contenido para`true` para marcar la casilla. De lo contrario, puede dejarlo sin marcar.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Paso 4: Guarde el documento
 Guarde el documento modificado en el directorio especificado usando el`Save`método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Ejemplo de código fuente para el estado actual de la casilla de verificación usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Obtenga el primer control de contenido del documento.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

¡Eso es todo! Ha recuperado y establecido con éxito el estado actual de un control de contenido de casilla de verificación en su documento de Word usando Aspose.Words para .NET.