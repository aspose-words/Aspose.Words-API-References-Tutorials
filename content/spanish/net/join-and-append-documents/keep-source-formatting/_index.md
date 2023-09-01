---
title: Coserva el formato original
linktitle: Coserva el formato original
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo adjuntar un documento de origen a un documento de destino mientras conserva el formato original usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/keep-source-formatting/
---

Este tutorial demuestra cómo adjuntar un documento de origen a un documento de destino mientras se conserva el formato original del documento de origen utilizando Aspose.Words para .NET.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

-  Aspose.Words para la biblioteca .NET instalada. Puedes descargarlo desde[Aspose.Releases]https://releases.aspose.com/words/net/ o utilice el administrador de paquetes NuGet para instalarlo.
- Una ruta del directorio de documentos donde se guardarán los documentos de origen y de destino.

## Paso 2: crear los documentos de destino y de origen

 Crear instancias de`Document` para los documentos de destino y de origen.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Paso 3: agregue el documento de origen al documento de destino

 Utilizar el`AppendDocument` método del documento de destino para adjuntar el documento de origen. Aprobar`ImportFormatMode.KeepSourceFormatting`como modo de formato de importación para conservar el formato original del documento de origen.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 4: guarde el documento modificado

 Guarde el documento modificado usando el`Save` método de la`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Esto completa la implementación de agregar un documento de origen a un documento de destino mientras se mantiene el formato original usando Aspose.Words para .NET.

### Código fuente de ejemplo para mantener el formato fuente usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Adjunte el documento de origen al documento de destino.
	// Pase el modo de formato para conservar el formato original del documento de origen al importarlo.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```