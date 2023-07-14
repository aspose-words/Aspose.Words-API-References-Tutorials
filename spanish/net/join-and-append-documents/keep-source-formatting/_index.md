---
title: Coserva el formato original
linktitle: Coserva el formato original
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a adjuntar un documento de origen a un documento de destino conservando el formato original con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/keep-source-formatting/
---

Este tutorial demuestra cómo adjuntar un documento de origen a un documento de destino conservando el formato original del documento de origen mediante Aspose.Words para .NET.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo del sitio web oficial de Aspose o usar el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio de documentos donde se guardarán los documentos de origen y de destino.

## Paso 2: Crear los documentos de origen y de destino

 Crear instancias de`Document` para los documentos de origen y de destino.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Paso 3: anexar el documento de origen al documento de destino

 Utilizar el`AppendDocument`del documento de destino para anexar el documento de origen. Aprobar`ImportFormatMode.KeepSourceFormatting` como modo de formato de importación para conservar el formato original del documento de origen.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 4: Guarde el documento modificado

 Guarde el documento modificado usando el`Save` metodo de la`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Esto completa la implementación de agregar un documento de origen a un documento de destino manteniendo el formato original usando Aspose.Words para .NET.

### Ejemplo de código fuente para mantener el formato de origen usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Añada el documento de origen al documento de destino.
	// Pase el modo de formato para conservar el formato original del documento de origen al importarlo.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```