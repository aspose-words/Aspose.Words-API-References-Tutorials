---
title: Docx a descuento
linktitle: Docx a descuento
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir documentos de Word de formato Docx a Markdown usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/basic-conversions/docx-to-markdown/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para convertir un documento de Word en formato Docx a Markdown. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización de los objetos Document y DocumentBuilder

 Primero, inicialice el`Document` objeto y el`DocumentBuilder` objeto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: agregar contenido al documento

 A continuación, utilice el`DocumentBuilder` objeto para agregar contenido al documento. En este ejemplo, agregaremos un párrafo de texto simple usando el`Writeln` método:

```csharp
builder.Writeln("Some text!");
```

Siéntase libre de agregar contenido más complejo, como encabezados, tablas, listas o formato, según sea necesario.

## Paso 3: Guardar el documento en formato Markdown

 Para guardar el documento en formato Markdown, use el`Save` método en el`Document` objeto y proporcione la ruta y el nombre de archivo para el documento de salida. En este ejemplo, lo guardaremos como`"BaseConversions.DocxToMarkdown.md"`:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");
```

¡Eso es todo! Ha convertido con éxito un documento de Word en formato Docx a Markdown usando Aspose.Words para .NET.

### Ejemplo de código fuente para Docx To Markdown usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Some text!");

	doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");

```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.