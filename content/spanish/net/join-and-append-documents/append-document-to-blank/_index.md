---
title: Anexar documento a espacio en blanco
linktitle: Anexar documento a espacio en blanco
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a agregar un documento a un documento de destino en blanco en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/append-document-to-blank/
---

Este tutorial explica cómo usar Aspose.Words para .NET para agregar el contenido de un documento a un documento de destino en blanco. El código fuente proporcionado demuestra cómo crear un nuevo documento, eliminar su contenido y luego agregarle el documento fuente.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puedes descargarlo desde[Aspose.Releases]https://releases.aspose.com/words/net/ o use el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio de documentos donde se encuentran los documentos de origen y de destino.

## Paso 2: Crear un nuevo documento de destino

 Crear un nuevo`Document` objeto para el documento de destino.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Paso 3: Elimina el contenido existente del documento de destino

 Para garantizar un documento de destino limpio, elimine todo el contenido existente del documento con el`RemoveAllChildren` método.

```csharp
dstDoc.RemoveAllChildren();
```

## Paso 4: agregue el documento de origen al documento de destino

 Añada el contenido del documento de origen al documento de destino utilizando el`AppendDocument` método con`ImportFormatMode.KeepSourceFormatting` opción.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 5: Guarde el documento de destino

 Finalmente, guarde el documento de destino modificado usando el`Save` metodo de la`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Esto completa la implementación de agregar un documento a un documento de destino en blanco usando Aspose.Words para .NET.

### Ejemplo de código fuente para agregar documento a espacio en blanco usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	//El documento de destino no está vacío, lo que a menudo hace que aparezca una página en blanco antes del documento adjunto.
	// Esto se debe a que el documento base tiene una sección vacía y el nuevo documento se inicia en la página siguiente.
	// Elimine todo el contenido del documento de destino antes de agregarlo.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```