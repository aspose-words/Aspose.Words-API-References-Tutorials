---
title: Aplicar estilo de párrafo
linktitle: Aplicar estilo de párrafo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a aplicar un estilo de párrafo con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/apply-paragraph-style/
---

En este tutorial, lo guiaremos a través de cómo aplicar un estilo de párrafo usando Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar el estilo de párrafo.

## Paso 1: Crear y configurar el documento

Para comenzar, cree un nuevo documento y un objeto DocumentBuilder asociado. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Configurar el estilo de párrafo

Ahora configuraremos el estilo de párrafo utilizando el identificador de estilo incorporado. Así es cómo:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## Paso 3: Agregar contenido

Vamos a añadir contenido al párrafo. Así es cómo:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### Código fuente de ejemplo para Aplicar estilo de párrafo usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Aplicar estilo de párrafo con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

Con este código podrás aplicar un estilo de párrafo usando Aspose.Words para .NET.

