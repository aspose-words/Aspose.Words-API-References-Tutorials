---
title: docx a epub
linktitle: docx a epub
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir documentos de Word de formato Docx a Epub usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/basic-conversions/docx-to-epub/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para convertir un documento de Word en formato Docx a formato Epub. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 En primer lugar, debe inicializar el`Document` objeto proporcionando la ruta a su documento de origen en formato Docx. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta del directorio real donde se encuentra su documento, y`"Document.docx"` con el nombre de su documento fuente. Aquí está el fragmento de código:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Paso 2: Conversión del documento a formato Epub

 A continuación, puede continuar con el proceso de conversión. Llama a`Save` método en el`Document` objeto y proporcione la ruta y el nombre de archivo para el documento de salida en formato Epub. En este ejemplo, lo guardaremos como`"BaseConversions.DocxToEpub.epub"`. Aquí está el fragmento de código:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");
```

¡Eso es todo! Ha convertido con éxito un documento de Word en formato Docx al formato Epub utilizando Aspose.Words para .NET.

### Código fuente de ejemplo para Docx To Epub usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");

```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.