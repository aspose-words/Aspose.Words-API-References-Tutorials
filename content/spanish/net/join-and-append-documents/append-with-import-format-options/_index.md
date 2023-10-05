---
title: Agregar con opciones de formato de importación
linktitle: Agregar con opciones de formato de importación
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo adjuntar un documento con opciones de formato de importación usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/append-with-import-format-options/
---

Este tutorial explica cómo usar Aspose.Words para .NET para agregar el contenido de un documento a otro con opciones de formato de importación. El código fuente proporcionado muestra cómo abrir los documentos de origen y de destino, especificar opciones de formato de importación y adjuntar el documento de origen al documento de destino.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

-  Aspose.Words para la biblioteca .NET instalada. Puedes descargarlo desde[Aspose.Releases]https://releases.aspose.com/words/net/ o utilice el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio de documentos donde se encuentran los documentos de origen y de destino.

## Paso 2: abra los documentos de origen y destino

 Abra los documentos de origen y destino utilizando el`Document` constructor de clases. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Paso 3: especificar las opciones de formato de importación

 Crear una instancia del`ImportFormatOptions` clase para especificar las opciones de formato de importación. En este ejemplo, utilizamos el`KeepSourceNumbering` propiedad para garantizar que se utilice la numeración del documento de origen si hay conflictos con el documento de destino.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Paso 4: agregue el documento de origen al documento de destino

 Utilizar el`AppendDocument` método del documento de destino para adjuntar el documento de origen. Aprobar`ImportFormatMode.UseDestinationStyles` como segundo parámetro para utilizar los estilos y el formato del documento de destino.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Paso 5: guarde el documento de destino

 Finalmente, guarde el documento de destino modificado usando el`Save` método de la`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Esto completa la implementación de agregar un documento con opciones de formato de importación usando Aspose.Words para .NET.

### Código fuente de ejemplo para Agregar con opciones de formato de importación usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Especifique que si la numeración choca en los documentos de origen y de destino,
	//entonces se utilizará la numeración del documento fuente.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```