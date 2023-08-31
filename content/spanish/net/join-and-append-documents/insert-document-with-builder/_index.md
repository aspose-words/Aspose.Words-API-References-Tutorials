---
title: Insertar documento con el constructor
linktitle: Insertar documento con el constructor
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo insertar un documento al final de otro documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/insert-document-with-builder/
---

 Este tutorial explica cómo usar Aspose.Words para .NET para insertar un documento en otro documento usando el`DocumentBuilder` clase. El código fuente proporcionado demuestra cómo insertar un documento al final de otro documento conservando el formato fuente.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puedes descargarlo desde[Aspose.Releases]https://releases.aspose.com/words/net/ o utilice el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio de documentos donde se encuentran los documentos de origen y de destino.

## Paso 2: abra los documentos de origen y destino

 Abra los documentos de origen y destino utilizando el`Document` constructor de clases. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: Inicialice DocumentBuilder

 Crear una nueva instancia del`DocumentBuilder` clase y pasar el documento de destino como parámetro.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Paso 4: Coloque el DocumentBuilder

Mueve el`DocumentBuilder` hasta el final del documento utilizando el`MoveToDocumentEnd` método. Inserte un salto de página para separar el contenido existente del documento insertado.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Paso 5: Inserta el documento fuente

 Utilizar el`InsertDocument` método de la`DocumentBuilder` clase para insertar el documento de origen en el documento de destino. Establezca el modo de formato de importación en`ImportFormatMode.KeepSourceFormatting` para preservar el formato fuente.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 6: guarde el documento modificado

 Finalmente, guarde el documento de destino modificado usando el`Save` método de la`Document` objeto.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Esto completa la implementación de insertar un documento en otro documento usando Aspose.Words para .NET.

### Código fuente de ejemplo para Insertar documento con Builder usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```