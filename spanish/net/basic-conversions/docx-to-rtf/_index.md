---
title: docx a rtf
linktitle: docx a rtf
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir documentos de Word de formato Docx a RTF usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/basic-conversions/docx-to-rtf/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para convertir un documento de Word en formato Docx a RTF. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: Leer el documento de Stream

Primero, abra una secuencia para leer el documento Docx:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## Paso 2: Cargar el documento

A continuación, cargue el documento desde la secuencia:

```csharp
Document doc = new Document(stream);
```

## Paso 3: Cerrar la secuencia

Dado que el documento se carga en la memoria, puede cerrar la transmisión:

```csharp
stream.Close();
```

## Paso 4: Realización de operaciones en el documento

En este punto, puede realizar cualquier operación deseada en el documento.

## Paso 5: Guardar el documento en formato RTF

Para guardar el documento en formato RTF, guárdelo en un flujo de memoria:

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## Paso 6: rebobinar la secuencia

Antes de escribir el flujo de memoria en un archivo, retroceda su posición a cero:

```csharp
dstStream.Position = 0;
```

## Paso 7: escribir la secuencia en un archivo

Finalmente, escriba el flujo de memoria en un archivo RTF:

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

¡Eso es todo! Ha convertido con éxito un documento de Word en formato Docx a RTF utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para Docx To Rtf usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// El acceso de solo lectura es suficiente para que Aspose.Words cargue un documento.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	//Puede cerrar la transmisión ahora, ya no es necesaria porque el documento está en la memoria.
	stream.Close();

	// ... hacer algo con el documento.

	// Convierta el documento a un formato diferente y guárdelo para transmitir.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// Rebobina la posición de la transmisión a cero para que esté lista para el siguiente lector.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.