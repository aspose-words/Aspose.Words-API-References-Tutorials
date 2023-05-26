---
title: Por Secciones Html
linktitle: Por Secciones Html
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a dividir un documento de Word en secciones Html usando Aspose.Words para .NET con un ejemplo de código completo.
type: docs
weight: 10
url: /es/net/split-document/by-sections-html/
---

En este ejemplo, le mostraremos cómo dividir un documento de Word en secciones separadas en formato HTML utilizando la función Por secciones HTML de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y generar documentos HTML separados para cada sección.

## Paso 1: Cargar el documento

Para comenzar, especifique el directorio de su documento y cárguelo en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Paso 2: Dividir el documento en secciones en formato HTML

Ahora configuraremos las opciones de guardado para dividir el documento en secciones en formato HTML. Aquí está cómo hacerlo:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Código fuente de ejemplo para HTML por secciones usando Aspose.Words para .NET

Aquí está el código fuente completo de la función Por secciones HTML de Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Rendering.docx");

	
	HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };
	
	
	doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);

```

Con este código podrá dividir un documento de Word en secciones separadas en formato HTML utilizando Aspose.Words para .NET.

Ahora puede generar documentos HTML separados para cada sección del documento inicial.



