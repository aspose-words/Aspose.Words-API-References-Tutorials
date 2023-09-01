---
title: Encabezados de enlaces y pies de página
linktitle: Encabezados de enlaces y pies de página
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a vincular encabezados y pies de página mientras une y agrega documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/link-headers-footers/
---

Este tutorial lo guiará a través del proceso de uso de la función Pies de página de encabezados de enlace de Aspose.Words para .NET. Esta función le permite unir y agregar varios documentos de Word mientras vincula los encabezados y pies de página del documento de origen a la sección anterior del documento de destino.

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

 A continuación, debe cargar los documentos de origen y de destino utilizando Aspose.Words.`Document` clase. Actualice los nombres de los archivos en el`Document` constructor de acuerdo con los nombres de sus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: configurar el documento adjunto para que aparezca en una página nueva

Para garantizar que el contenido del documento de origen aparezca en una nueva página del documento de destino, debe configurar el`SectionStart` propiedad de la primera sección del documento fuente para`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Paso 4: vincular encabezados y pies de página a la sección anterior

 Para vincular los encabezados y pies de página del documento de origen a la sección anterior del documento de destino, puede utilizar el`LinkToPrevious` método de la`HeadersFooters` recopilación. Al pasar`true` como parámetro, anula cualquier encabezado o pie de página existente en el documento fuente.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Paso 5: agregue el documento de origen al documento de destino

 Ahora, puede adjuntar el documento de origen al documento de destino utilizando el`AppendDocument` método de la`Document` clase. El`ImportFormatMode.KeepSourceFormatting` El parámetro garantiza que el formato de origen se conserve durante la operación de adición.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 6: guarde el documento final

 Finalmente, guarde el documento combinado con los encabezados y pies de página vinculados usando el`Save` método de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Código fuente de ejemplo para encabezados de enlace y pies de página usando Aspose.Words para .NET 

Aquí está el código fuente completo para la función "Enlaces encabezados y pies de página" en C# usando Aspose.Words para .NET:


```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Configure el documento adjunto para que aparezca en una página nueva.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Vincula los encabezados y pies de página del documento fuente a la sección anterior.
	// Esto anulará cualquier encabezado o pie de página que ya se encuentre en el documento fuente.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

¡Eso es todo! Ha implementado con éxito la función Enlaces de encabezados y pies de página utilizando Aspose.Words para .NET. El documento final contendrá el contenido combinado con los encabezados y pies de página del documento de origen vinculados a la sección anterior del documento de destino.