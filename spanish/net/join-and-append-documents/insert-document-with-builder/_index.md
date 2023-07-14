---
title: Insertar documento con Builder
linktitle: Insertar documento con Builder
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a insertar un documento al final de otro documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/insert-document-with-builder/
---

 Este tutorial explica cómo usar Aspose.Words para .NET para insertar un documento en otro documento usando el`DocumentBuilder` clase. El código fuente proporcionado muestra cómo insertar un documento al final de otro documento conservando el formato de origen.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo del sitio web oficial de Aspose o usar el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio de documentos donde se encuentran los documentos de origen y de destino.

## Paso 2: Abra los documentos de origen y destino

 Abra los documentos de origen y de destino con el`Document` constructor de clases. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: inicialice DocumentBuilder

 Crear una nueva instancia de la`DocumentBuilder` class y pasar el documento de destino como parámetro.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Paso 4: Coloque el DocumentBuilder

 Mueve el`DocumentBuilder` hasta el final del documento usando el`MoveToDocumentEnd` método. Inserte un salto de página para separar el contenido existente del documento insertado.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Paso 5: Inserte el documento de origen

 Utilizar el`InsertDocument` metodo de la`DocumentBuilder` class para insertar el documento de origen en el documento de destino. Establezca el modo de formato de importación en`ImportFormatMode.KeepSourceFormatting` para conservar el formato de origen.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 6: Guarde el documento modificado

 Finalmente, guarde el documento de destino modificado usando el`Save` metodo de la`Document` objeto.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Esto completa la implementación de insertar un documento en otro documento usando Aspose.Words para .NET.

### Ejemplo de código fuente para Insertar documento con Builder usando Aspose.Words para .NET 

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