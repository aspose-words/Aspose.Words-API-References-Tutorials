---
title: docx a byte
linktitle: docx a byte
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir documentos de Word de Docx a una matriz de bytes usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/basic-conversions/docx-to-byte/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para convertir un documento de Word en formato Docx a una matriz de bytes. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización de MemoryStream

 En primer lugar, cree una instancia de la`MemoryStream` clase para almacenar el documento convertido como una matriz de bytes:

```csharp
MemoryStream outStream = new MemoryStream();
```

## Paso 2: guardar el documento en MemoryStream

 A continuación, utilice el`Save` metodo de la`Document` clase para guardar el documento en el`MemoryStream` en formato docx:

```csharp
doc.Save(outStream, SaveFormat.Docx);
```

## Paso 3: Convertir MemoryStream a Byte Array

 para convertir el`MemoryStream` que contiene el documento Docx a una matriz de bytes, use el`ToArray` método:

```csharp
byte[] docBytes = outStream.ToArray();
```

## Paso 4: inicialización de MemoryStream desde Byte Array

 Ahora, inicialice una nueva instancia de`MemoryStream`usando la matriz de bytes obtenida en el paso anterior:

```csharp
MemoryStream inStream = new MemoryStream(docBytes);
```

## Paso 5: Crear un documento desde MemoryStream

 Finalmente, crea una nueva`Document` objeto de la`MemoryStream`:

```csharp
Document docFromBytes = new Document(inStream);
```

¡Eso es todo! Ha convertido con éxito un documento de Word en formato Docx a una matriz de bytes usando Aspose.Words para .NET.

### Ejemplo de código fuente para Docx To Byte usando Aspose.Words para .NET

```csharp

	// MemoryStream outStream = new MemoryStream();
	doc.Save(outStream, SaveFormat.Docx);

	byte[] docBytes = outStream.ToArray();
	MemoryStream inStream = new MemoryStream(docBytes);

	Document docFromBytes = new Document(inStream);
	
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.