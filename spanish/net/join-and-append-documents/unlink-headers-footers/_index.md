---
title: Desvincular encabezados y pies de página
linktitle: Desvincular encabezados y pies de página
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a unir y adjuntar documentos de Word mientras desvincula encabezados y pies de página con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/unlink-headers-footers/
---

Este tutorial lo guiará a través del proceso de uso de la función Desvincular encabezados y pies de página de Aspose.Words para .NET. Esta característica le permite unir y agregar documentos de Word mientras desvincula encabezados y pies de página del documento de origen.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Aspose.Words para .NET instalado. Puede descargarlo del sitio web de Aspose o instalarlo a través de NuGet.
2. Visual Studio o cualquier otro entorno de desarrollo C#.

## Paso 1: inicialice los directorios de documentos

 Primero, debe establecer la ruta a su directorio de documentos. Modificar el valor de la`dataDir`variable a la ruta donde se encuentran sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue los documentos de origen y destino

 A continuación, debe cargar los documentos de origen y destino utilizando Aspose.Words`Document` clase. Actualice los nombres de los archivos en el`Document` constructor de acuerdo con los nombres de sus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: Desvincular encabezados y pies de página en el documento de origen

 Para desvincular los encabezados y pies de página en el documento de origen de continuar con los encabezados y pies de página del documento de destino, debe configurar el`LinkToPrevious`propiedad de la`HeadersFooters` colección en la primera sección del documento fuente para`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Paso 4: agregue el documento de origen al documento de destino

 Ahora, puede agregar el documento de origen al documento de destino usando el`AppendDocument` metodo de la`Document` clase. El`ImportFormatMode.KeepSourceFormatting` El parámetro garantiza que el formato de origen se conserve durante la operación de adición.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 5: Guarde el documento final

Finalmente, guarde el documento combinado con la función Desvincular encabezados y pies de página habilitada usando el`Save` metodo de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Ejemplo de código fuente para desvincular encabezados y pies de página usando Aspose.Words para .NET

Aquí está el código fuente completo para la función "Desvincular encabezados y pies de página" en C# usando Aspose.Words para .NET:

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Desvincule los encabezados y pies de página en el documento de origen para detener esto
	// de continuar con los encabezados y pies de página del documento de destino.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

¡Eso es todo! Ha implementado correctamente la función Desvincular encabezados y pies de página con Aspose.Words para .NET. El documento final contendrá el contenido combinado con los encabezados y pies de página del documento de origen desvinculados del documento de destino.