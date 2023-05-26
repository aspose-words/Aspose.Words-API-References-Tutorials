---
title: docx a txt
linktitle: docx a txt
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir documentos de Word de Docx a texto sin formato (Txt) usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/basic-conversions/docx-to-txt/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para convertir un documento de Word en formato Docx a texto sin formato (Txt). Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto con la ruta a su documento de origen en formato Docx:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Paso 2: guardar el documento en formato Txt

 A continuación, guarde el documento en formato de texto sin formato (Txt) llamando al`Save` método en el`Document` objeto y proporcionando la ruta y el nombre del archivo para el documento Txt de salida:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");
```

¡Eso es todo! Ha convertido con éxito un documento de Word en formato Docx a texto sin formato (Txt) utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para Docx To Txt usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");

```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.