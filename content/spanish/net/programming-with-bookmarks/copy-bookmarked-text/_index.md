---
title: Copiar texto marcado en un documento de Word
linktitle: Copiar texto marcado en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a copiar texto de marcador en un documento de Word a otro documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/copy-bookmarked-text/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo utilizar la función Copiar texto marcado como favorito en la biblioteca Aspose.Words para .NET. Esta función le permite copiar el contenido de un marcador específico de un documento fuente a otro documento.

## Requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: cargar el documento fuente

 Antes de copiar el texto del marcador, debemos cargar el documento fuente en un`Document` objeto usando la ruta del archivo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Paso 2: Obtener el marcador fuente

 Usamos el`Bookmarks` propiedad del rango del documento fuente para obtener el marcador específico que queremos copiar:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Paso 3: crear el documento de destino

Creamos un nuevo documento que servirá como documento de destino para copiar el contenido del marcador:

```csharp
Document dstDoc = new Document();
```

## Paso 4: especificar la ubicación de la copia

Especificamos la ubicación donde queremos agregar el texto copiado. En nuestro ejemplo, agregamos el texto al final del cuerpo de la última sección del documento de destino:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Paso 5: importar y copiar el texto del marcador

 Usamos un`NodeImporter`objeto para importar y copiar texto de marcador desde un documento de origen al documento de destino:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Código fuente de ejemplo para copiar texto marcado usando Aspose.Words para .NET

Aquí está el código fuente de ejemplo completo para demostrar cómo copiar texto de un marcador usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Este es el marcador cuyo contenido queremos copiar.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Iremos agregando a este documento.
	Document dstDoc = new Document();

	// Digamos que se agregará al final del cuerpo de la última sección.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Si importa varias veces sin un solo contexto, se crearán muchos estilos.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo utilizar la función Copiar texto marcado como favorito de Aspose.Words para .NET. Seguimos una guía paso a paso para copiar el contenido de un marcador de un documento fuente a otro documento.

### Preguntas frecuentes para copiar texto marcado como favorito en un documento de Word

#### P: ¿Cuáles son los requisitos para utilizar la función "Copiar texto con marcadores" en Aspose.Words para .NET?

R: Para utilizar la función "Copiar texto con marcadores" en Aspose.Words para .NET, debe tener conocimientos básicos del lenguaje C#. También necesita un entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

#### P: ¿Cómo cargo un documento fuente en Aspose.Words para .NET?

 R: Para cargar un documento fuente en Aspose.Words para .NET, puede usar el`Document` clase especificando la ruta del archivo del documento. Aquí hay un código de muestra:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### P: ¿Cómo obtener el contenido de un marcador específico en un documento fuente usando Aspose.Words para .NET?

 R: Para obtener el contenido de un marcador específico en un documento fuente usando Aspose.Words para .NET, puede acceder al`Bookmarks` propiedad del rango del documento de origen y utilice el nombre del marcador para recuperar el marcador específico. Aquí hay un código de muestra:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### P: ¿Cómo especificar la ubicación de la copia del texto del marcador en un documento de destino usando Aspose.Words para .NET?

R: Para especificar dónde desea agregar el texto copiado del marcador en un documento de destino usando Aspose.Words para .NET, puede navegar hasta el cuerpo de la última sección del documento de destino. Puedes usar el`LastSection` propiedad para acceder a la última sección y a la`Body` propiedad para acceder al cuerpo de esa sección. Aquí hay un código de muestra:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### P: ¿Cómo importar y copiar texto de marcador desde el documento de origen al documento de destino usando Aspose.Words para .NET?

 R: Para importar y copiar texto de marcador desde un documento de origen a un documento de destino usando Aspose.Words para .NET, puede usar el`NodeImporter` clase que especifica el documento de origen, el documento de destino y el modo de formato a conservar. Entonces puedes usar el`AppendBookmarkedText` método para agregar el texto del marcador en el documento de destino. Aquí hay un código de muestra:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### P: ¿Cómo guardar un documento de destino después de copiar el texto del marcador usando Aspose.Words para .NET?

R: Para guardar un documento de destino después de copiar texto de un marcador usando Aspose.Words para .NET, puede usar el`Save` método de la`Document` objeto que especifica la ruta del archivo de destino. Aquí hay un código de muestra:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```