---
title: Actualizar diseño de página
linktitle: Actualizar diseño de página
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a actualizar el diseño de página al unir y adjuntar documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/update-page-layout/
---

Este tutorial lo guiará a través del proceso de uso de la función Actualizar diseño de página de Aspose.Words para .NET. Esta función garantiza que el diseño de la página se actualice correctamente al unir y adjuntar documentos de Word.

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

## Paso 3: actualice el diseño de página para el documento de destino

 Para asegurarse de que el diseño de la página se actualice correctamente antes de adjuntar el documento de origen, puede llamar al`UpdatePageLayout` método en el documento de destino.

```csharp
dstDoc.UpdatePageLayout();
```

## Paso 4: agregue el documento de origen al documento de destino

 Ahora, puede agregar el documento de origen al documento de destino usando el`AppendDocument` metodo de la`Document` clase. El`ImportFormatMode.KeepSourceFormatting` El parámetro garantiza que el formato de origen se conserve durante la operación de adición.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 5: actualice el diseño de la página nuevamente

 Después de adjuntar el documento de origen, debe llamar al`UpdatePageLayout` de nuevo en el documento de destino para asegurarse de que los cambios realizados después de la operación de agregar se reflejen en la salida procesada.

```csharp
dstDoc.UpdatePageLayout();
```

## Paso 6: Guarde el documento final

 Finalmente, guarde el documento combinado con la función Actualizar diseño de página habilitada usando el`Save` metodo de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Ejemplo de código fuente para Actualizar diseño de página usando Aspose.Words para .NET

Aquí está el código fuente completo para la función "Actualizar diseño de página" en C# usando Aspose.Words para .NET:

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Si el documento de destino se representa en PDF, imagen, etc.
	// o se llama a UpdatePageLayout antes del documento de origen. se adjunta,
	// entonces cualquier cambio realizado después no se reflejará en la salida renderizada
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Para que los cambios se actualicen en la salida representada, se debe volver a llamar a UpdatePageLayout.
	// Si no se vuelve a llamar, el documento adjunto no aparecerá en la salida de la próxima representación.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

¡Eso es todo! Ha implementado correctamente la función Actualizar diseño de página con Aspose.Words para .NET. El documento final contendrá el contenido fusionado con el diseño de página actualizado correctamente.