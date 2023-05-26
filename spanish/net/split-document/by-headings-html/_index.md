---
title: Por encabezados HTML
linktitle: Por encabezados HTML
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para explicar el código fuente C# de la función HTML Por encabezado de Aspose.Words para .NET
type: docs
weight: 10
url: /es/net/split-document/by-headings-html/
---
En este tutorial, lo guiaremos a través de cómo dividir un documento de Word en partes más pequeñas utilizando la función Por encabezado HTML de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y generar documentos HTML separados basados en el encabezado.

## Paso 1: Cargar el documento

Para comenzar, especifique el directorio de su documento y cárguelo en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Paso 2: Dividir el documento por Título en formato HTML

Ahora configuraremos las opciones de guardado para dividir el documento en partes más pequeñas según el encabezado en formato HTML. Así es cómo:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Divide el documento en partes más pequeñas, en este caso separándolo por título.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Ejemplo de código fuente para Por encabezados HTML usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Por encabezado HTML de Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Rendering.docx");

	HtmlSaveOptions options = new HtmlSaveOptions
	{
		// Divida un documento en partes más pequeñas, en este caso dividido por encabezado.
		DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
	};
	

	doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
	

```

Con este código, podrá dividir un documento de Word en partes más pequeñas usando Aspose.Words para .NET, según los encabezados. Luego puede generar documentos HTML separados para cada parte.

