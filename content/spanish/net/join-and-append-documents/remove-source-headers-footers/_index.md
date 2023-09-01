---
title: Eliminar encabezados de origen y pies de página
linktitle: Eliminar encabezados de origen y pies de página
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a eliminar encabezados y pies de página al unir y agregar documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/remove-source-headers-footers/
---

Este tutorial lo guiará a través del proceso de uso de la función Eliminar encabezados de origen y pies de página de Aspose.Words para .NET. Esta función le permite unir y agregar documentos de Word mientras elimina encabezados y pies de página del documento fuente.

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

## Paso 3: eliminar encabezados y pies de página de las secciones del documento fuente

 Para eliminar los encabezados y pies de página de cada sección del documento fuente, puede recorrer las secciones usando un`foreach` hacer un bucle y llamar al`ClearHeadersFooters` método.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Paso 4: deshabilite la configuración "LinkToPrevious" para encabezados y pies de página

Incluso después de borrar los encabezados y pies de página del documento fuente, existe la posibilidad de que la configuración "LinkToPrevious" para`HeadersFooters` todavía se puede configurar. Para evitar este comportamiento, debe configurarlo explícitamente en`false` para la primera sección`HeadersFooters` propiedad.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Paso 5: agregue el documento de origen al documento de destino

 Ahora, puede adjuntar el documento de origen al documento de destino utilizando el`AppendDocument` método de la`Document` clase. El`ImportFormatMode.KeepSourceFormatting` El parámetro garantiza que el formato de origen se conserve durante la operación de adición.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 6: guarde el documento final

 Finalmente, guarde el documento combinado con la función Eliminar encabezados y pies de página de origen habilitada usando el`Save` método de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Código fuente de ejemplo para eliminar encabezados y pies de página de origen usando Aspose.Words para .NET 

Aquí está el código fuente completo para la función "Eliminar pies de página de encabezados de origen" en C# usando Aspose.Words para .NET:


```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Elimine los encabezados y pies de página de cada una de las secciones del documento fuente.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Incluso después de borrar los encabezados y pies de página del documento fuente, la configuración "LinkToPrevious"
	// para encabezados y pies de página aún se pueden configurar. Esto hará que los encabezados y pies de página continúen desde el destino.
	// documento. Esto debería establecerse en falso para evitar este comportamiento.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
¡Eso es todo! Ha implementado con éxito la función Eliminar encabezados y pies de página de origen utilizando Aspose.Words para .NET. El documento final contendrá el contenido combinado con los encabezados y pies de página eliminados del documento fuente.