---
title: Lista Mantener formato fuente
linktitle: Lista Mantener formato fuente
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo conservar el formato de la lista al unir y agregar documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/list-keep-source-formatting/
---

Este tutorial lo guiará a través del proceso de uso de la función Listar mantener formato de origen de Aspose.Words para .NET. Esta función le permite unir y adjuntar documentos de Word conservando el formato original de las listas.

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Paso 3: configurar el documento fuente para que fluya continuamente

 Para garantizar que el contenido del documento de origen fluya continuamente cuando se agrega al documento de destino, debe configurar el`SectionStart` propiedad de la primera sección del documento fuente para`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Paso 4: agregue el documento de origen al documento de destino

 Ahora, puede adjuntar el documento de origen al documento de destino utilizando el`AppendDocument` método de la`Document` clase. El`ImportFormatMode.KeepSourceFormatting`El parámetro garantiza que el formato de origen, incluido el formato de las listas, se conserve durante la operación de adición.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 5: guarde el documento final

 Finalmente, guarde el documento combinado con la función Listar mantener formato de origen habilitada usando el`Save` método de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Código fuente de ejemplo para mantener el formato fuente de lista usando Aspose.Words para .NET 

Aquí está el código fuente completo de la función Mantener formato de código fuente en C# usando Aspose.Words para .NET:

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Añade el contenido del documento para que fluya continuamente.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

¡Eso es todo! Ha implementado con éxito la función Listar mantener formato de origen utilizando Aspose.Words para .NET. El documento final contendrá el contenido combinado conservando el formato de lista del documento fuente.