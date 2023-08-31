---
title: Actualizar diseño de página
linktitle: Actualizar diseño de página
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo actualizar el diseño de la página al unir y agregar documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/update-page-layout/
---

Este tutorial lo guiará a través del proceso de uso de la función Actualizar diseño de página de Aspose.Words para .NET. Esta característica garantiza que el diseño de la página se actualice correctamente al unir y agregar documentos de Word.

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

## Paso 3: actualizar el diseño de página del documento de destino

 Para asegurarse de que el diseño de la página se actualice correctamente antes de agregar el documento fuente, puede llamar al`UpdatePageLayout` método en el documento de destino.

```csharp
dstDoc.UpdatePageLayout();
```

## Paso 4: agregue el documento de origen al documento de destino

 Ahora, puede adjuntar el documento de origen al documento de destino utilizando el`AppendDocument` método de la`Document` clase. El`ImportFormatMode.KeepSourceFormatting` El parámetro garantiza que el formato de origen se conserve durante la operación de adición.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 5: actualice el diseño de la página nuevamente

 Después de adjuntar el documento fuente, debe llamar al`UpdatePageLayout` método en el documento de destino nuevamente para garantizar que cualquier cambio realizado después de la operación de agregar se refleje en la salida representada.

```csharp
dstDoc.UpdatePageLayout();
```

## Paso 6: guarde el documento final

 Finalmente, guarde el documento combinado con la función Actualizar diseño de página habilitada usando el`Save` método de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Código fuente de ejemplo para actualizar el diseño de página usando Aspose.Words para .NET

Aquí está el código fuente completo para la función "Actualizar diseño de página" en C# usando Aspose.Words para .NET:

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Si el documento de destino se procesa en PDF, imagen, etc.
	// o se llama a UpdatePageLayout antes del documento fuente. Se adjunta,
	// entonces cualquier cambio realizado después no se reflejará en la salida renderizada
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Para que los cambios se actualicen en la salida representada, se debe volver a llamar a UpdatePageLayout.
	// Si no se vuelve a llamar, el documento adjunto no aparecerá en el resultado de la siguiente representación.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

¡Eso es todo! Ha implementado con éxito la función Actualizar diseño de página utilizando Aspose.Words para .NET. El documento final contendrá el contenido fusionado con el diseño de página actualizado correctamente.