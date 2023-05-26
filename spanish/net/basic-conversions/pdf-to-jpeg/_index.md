---
title: PDF a JPEG
linktitle: PDF a JPEG
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir documentos PDF a imágenes JPEG usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/basic-conversions/pdf-to-jpeg/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para convertir un documento PDF a imágenes JPEG. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto proporcionando la ruta a su documento PDF:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## Paso 2: Guardar el documento como imágenes Jpeg

 A continuación, guarde el documento como imágenes Jpeg llamando al`Save` método en el`Document` objeto y proporcionando la ruta y el nombre del archivo para las imágenes Jpeg de salida:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");
```

¡Eso es todo! Ha convertido con éxito un documento PDF a imágenes Jpeg utilizando Aspose.Words para .NET.

### Código fuente de ejemplo para Pdf To Jpeg usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToJpeg.jpeg");

```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.