---
title: Copiar texto marcado
linktitle: Copiar texto marcado
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a copiar texto de marcador de un documento de origen a otro documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/copy-bookmarked-text/
---

En este artículo, exploraremos el código fuente de C# anterior para entender cómo usar la función Copiar texto marcado en la biblioteca Aspose.Words para .NET. Esta función le permite copiar el contenido de un marcador específico de un documento de origen a otro documento.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: carga del documento de origen

 Antes de copiar el texto del marcador, debemos cargar el documento de origen en un`Document` objeto usando la ruta del archivo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Paso 2: obtener el marcador de origen

 usamos el`Bookmarks` propiedad del rango del documento de origen para obtener el marcador específico que queremos copiar:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Paso 3: Creación del documento de destino

Creamos un nuevo documento que servirá como documento de destino para copiar el contenido del marcador:

```csharp
Document dstDoc = new Document();
```

## Paso 4: Especificación de la ubicación de la copia

Especificamos la ubicación donde queremos agregar el texto copiado. En nuestro ejemplo, agregamos el texto al final del cuerpo de la última sección del documento de destino:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Paso 5: Importe y copie el texto del marcador

 usamos un`NodeImporter`objeto para importar y copiar texto de marcador desde un documento de origen al documento de destino:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Código fuente de ejemplo para Copiar texto marcado con Aspose.Words para .NET

Aquí está el código fuente de ejemplo completo para demostrar cómo copiar texto de un marcador usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Este es el marcador cuyo contenido queremos copiar.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Estaremos agregando a este documento.
	Document dstDoc = new Document();

	// Digamos que se agregará al final del cuerpo de la última sección.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Si importa varias veces sin un solo contexto, se crearán muchos estilos.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Conclusión

En este artículo, exploramos el código fuente de C# para entender cómo usar la función Copiar texto marcado de Aspose.Words para .NET. Seguimos una guía paso a paso para copiar el contenido de un marcador de un documento de origen a otro documento.