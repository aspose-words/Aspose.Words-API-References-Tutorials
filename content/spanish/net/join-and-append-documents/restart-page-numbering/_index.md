---
title: Reiniciar numeración de páginas
linktitle: Reiniciar numeración de páginas
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo reiniciar la numeración de páginas mientras une y agrega documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/restart-page-numbering/
---

Este tutorial lo guiará a través del proceso de uso de la función Reiniciar numeración de páginas de Aspose.Words para .NET. Esta función le permite unir y agregar documentos de Word mientras reinicia la numeración de páginas en el documento fuente.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Aspose.Words para .NET instalado. Puede descargarlo del sitio web de Aspose o instalarlo a través de NuGet.
2. Visual Studio o cualquier otro entorno de desarrollo C#.

## Paso 1: inicializar los directorios de documentos

 Primero, debe establecer la ruta a su directorio de documentos. Modificar el valor de la`dataDir`variable a la ruta donde se encuentran sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue los documentos de origen y de destino

 A continuación, debe cargar los documentos de origen y de destino utilizando Aspose.Words.`Document` clase. Actualice los nombres de los archivos en el`Document` constructor de acuerdo con los nombres de sus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: configurar el documento fuente para reiniciar la numeración de páginas

 Para reiniciar la numeración de páginas en el documento fuente, debe configurar el`SectionStart` propiedad de la primera sección del documento fuente para`SectionStart.NewPage` y establecer el`RestartPageNumbering` propiedad a`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Paso 4: agregue el documento de origen al documento de destino

 Ahora, puede adjuntar el documento de origen al documento de destino utilizando el`AppendDocument` método de la`Document` clase. El`ImportFormatMode.KeepSourceFormatting` El parámetro garantiza que el formato de origen se conserve durante la operación de adición.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 5: guarde el documento final

 Finalmente, guarde el documento combinado con la función Reiniciar numeración de páginas habilitada usando el`Save` método de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Código fuente de ejemplo para reiniciar la numeración de páginas usando Aspose.Words para .NET

Aquí está el código fuente completo para la función "Reiniciar numeración de páginas" en C# usando Aspose.Words para .NET:
 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

¡Eso es todo! Ha implementado con éxito la función Reiniciar numeración de páginas utilizando Aspose.Words para .NET. El documento final contendrá el contenido combinado con la numeración de páginas reiniciada en el documento fuente.