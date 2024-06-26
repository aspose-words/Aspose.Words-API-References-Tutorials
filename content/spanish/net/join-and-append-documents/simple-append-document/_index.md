---
title: Adjuntar documento simple
linktitle: Adjuntar documento simple
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a unir y anexar documentos de Word con formato conservado utilizando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/simple-append-document/
---

Este tutorial lo guiará a través del proceso de uso de la función Anexar documento simple de Aspose.Words para .NET. Esta función le permite unir y adjuntar documentos de Word sin opciones adicionales.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Aspose.Words para .NET instalado. Puede descargarlo del sitio web de Aspose o instalarlo a través de NuGet.
2. Visual Studio o cualquier otro entorno de desarrollo C#.

## Paso 1: inicializar los directorios de documentos

 Primero, debe establecer la ruta a su directorio de documentos. Modificar el valor de la`dataDir` variable a la ruta donde se encuentran sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue los documentos de origen y de destino

 continuación, debe cargar los documentos de origen y de destino utilizando Aspose.Words.`Document` clase. Actualice los nombres de los archivos en el`Document` constructor de acuerdo con los nombres de sus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: agregue el documento de origen al documento de destino

 Ahora, puede adjuntar el documento de origen al documento de destino utilizando el`AppendDocument` método de la`Document` clase. El`ImportFormatMode.KeepSourceFormatting` El parámetro garantiza que el formato de origen se conserve durante la operación de adición.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 4: guarde el documento final

 Finalmente, guarde el documento combinado con la función Anexar documento simple usando el`Save` método de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Código fuente de ejemplo para un documento con anexión simple usando Aspose.Words para .NET

Aquí está el código fuente completo para la función "Anexar documento simple" en C# usando Aspose.Words para .NET:

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Adjunte el documento de origen al documento de destino sin utilizar opciones adicionales.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

¡Eso es todo! Ha implementado con éxito la función Anexar documento simple utilizando Aspose.Words para .NET. El documento final contendrá el contenido combinado conservando el formato original.