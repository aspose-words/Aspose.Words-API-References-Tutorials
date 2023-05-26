---
title: docx a pdf
linktitle: docx a pdf
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir documentos de Word de Docx a PDF usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/basic-conversions/docx-to-pdf/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para convertir un documento de Word en formato Docx a PDF. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto con la ruta a su documento de origen en formato Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Paso 2: Guardar el documento en formato PDF

 A continuación, guarde el documento en formato PDF llamando al`Save` método en el`Document` objeto y proporcionando la ruta y el nombre de archivo para el documento PDF de salida:

```csharp
doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
```

¡Eso es todo! Ha convertido con éxito un documento de Word en formato Docx a PDF usando Aspose.Words para .NET.

### Código fuente de ejemplo para Docx To Pdf usando Aspose.Words para .NET

```csharp

	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
	
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.
