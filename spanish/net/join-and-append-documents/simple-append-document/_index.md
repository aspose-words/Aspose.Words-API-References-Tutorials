---
title: Documento adjunto simple
linktitle: Documento adjunto simple
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a unir y adjuntar documentos de Word con formato preservado usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/simple-append-document/
---

Este tutorial lo guiará a través del proceso de uso de la función Agregar documento simple de Aspose.Words para .NET. Esta función le permite unir y adjuntar documentos de Word sin opciones adicionales.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Aspose.Words para .NET instalado. Puede descargarlo del sitio web de Aspose o instalarlo a través de NuGet.
2. Visual Studio o cualquier otro entorno de desarrollo C#.

## Paso 1: inicialice los directorios de documentos

 Primero, debe establecer la ruta a su directorio de documentos. Modificar el valor de la`dataDir` variable a la ruta donde se encuentran sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue los documentos de origen y destino

 A continuación, debe cargar los documentos de origen y destino utilizando Aspose.Words`Document` clase. Actualice los nombres de los archivos en el`Document` constructor de acuerdo con los nombres de sus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: agregue el documento de origen al documento de destino

 Ahora, puede agregar el documento de origen al documento de destino usando el`AppendDocument` metodo de la`Document` clase. El`ImportFormatMode.KeepSourceFormatting` El parámetro garantiza que el formato de origen se conserve durante la operación de adición.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 4: Guarde el documento final

 Finalmente, guarde el documento fusionado con la función Documento adjunto simple usando el`Save` metodo de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Código fuente de ejemplo para documento de anexo simple usando Aspose.Words para .NET

Aquí está el código fuente completo para la característica "Simple Add Document" en C# usando Aspose.Words para .NET:

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Añada el documento de origen al documento de destino sin utilizar opciones adicionales.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

¡Eso es todo! Ha implementado con éxito la función Agregar documento simple utilizando Aspose.Words para .NET. El documento final contendrá el contenido combinado con el formato de origen conservado.