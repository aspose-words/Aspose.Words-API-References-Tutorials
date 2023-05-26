---
title: Pdf a docx
linktitle: Pdf a docx
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir documentos PDF a formato Docx usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/basic-conversions/pdf-to-docx/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para convertir un documento PDF al formato Docx. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto proporcionando la ruta a su documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Paso 2: guardar el documento en formato Docx

 A continuación, guarde el documento en formato Docx llamando al`Save` método en el`Document` proporcionando la ruta y el nombre de archivo para el documento Docx de salida:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
```

¡Eso es todo! Ha convertido con éxito un documento PDF al formato Docx utilizando Aspose.Words para .NET.

### Código fuente de ejemplo para Pdf To Docx usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
	
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.