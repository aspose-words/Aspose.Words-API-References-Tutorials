---
title: Ignorar encabezado de pie de página
linktitle: Ignorar encabezado de pie de página
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a agregar un documento ignorando el contenido del encabezado y el pie de página con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/ignore-header-footer/
---

Este tutorial explica cómo usar Aspose.Words para .NET para agregar un documento ignorando el contenido del encabezado y el pie de página. El código fuente proporcionado muestra cómo configurar las opciones de formato de importación para excluir el encabezado y el pie de página durante el proceso de adición.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puedes descargarlo desde[Aspose.Releases]https://releases.aspose.com/words/net/ o use el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio de documentos donde se encuentran los documentos de origen y de destino.

## Paso 2: Abra los documentos de origen y destino

 Abra los documentos de origen y de destino con el`Document` constructor de clases. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: Configure las opciones de formato de importación

 Crear una instancia de la`ImportFormatOptions`clase y establecer el`IgnoreHeaderFooter` propiedad a`false`. Esto garantiza que el contenido del encabezado y pie de página se incluya durante el proceso de adición.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Paso 4: agregue el documento de origen al documento de destino

 Utilizar el`AppendDocument`del documento de destino para anexar el documento de origen. Aprobar`ImportFormatMode.KeepSourceFormatting` como segundo parámetro y las opciones de formato de importación como tercer parámetro.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Paso 5: Guarde el documento de destino

 Finalmente, guarde el documento de destino modificado usando el`Save` metodo de la`Document` objeto.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Esto completa la implementación de agregar un documento mientras se ignora el contenido del encabezado y pie de página usando Aspose.Words para .NET.

### Ejemplo de código fuente para Ignorar encabezado y pie de página usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```