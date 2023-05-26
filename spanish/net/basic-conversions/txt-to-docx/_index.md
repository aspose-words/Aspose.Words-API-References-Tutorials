---
title: Texto a docx
linktitle: Texto a docx
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir archivos de texto sin formato (Txt) a documentos de Word (Docx) usando Aspose.Words para .NET. Tutorial paso a paso con código de ejemplo.
type: docs
weight: 10
url: /es/net/basic-conversions/txt-to-docx/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para convertir un archivo de texto sin formato (Txt) a un documento de Word en formato Docx. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto proporcionando la ruta a su archivo de texto sin formato:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "English text.txt");
```

## Paso 2: guardar el documento en formato Docx

 A continuación, guarde el documento en formato Docx llamando al`Save` método en el`Document` proporcionando la ruta y el nombre de archivo para el documento Docx de salida:

```csharp
doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");
```

¡Eso es todo! Ha convertido con éxito un archivo de texto sin formato (Txt) en un documento de Word en formato Docx utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para Txt To Docx usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// La codificación del archivo de texto se detecta automáticamente.
	Document doc = new Document(MyDir + "English text.txt");

	doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");

```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.