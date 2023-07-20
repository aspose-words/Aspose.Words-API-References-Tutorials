---
title: Copiar texto marcado en un documento de Word
linktitle: Copiar texto marcado en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a copiar texto de marcador en un documento de Word a otro documento usando Aspose.Words para .NET.
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

## Paso 3: Crear el documento de destino

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

 usamos un`NodeImporter` objeto para importar y copiar texto de marcador desde un documento de origen al documento de destino:

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

	//Digamos que se agregará al final del cuerpo de la última sección.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Si importa varias veces sin un solo contexto, se crearán muchos estilos.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

## Conclusión

En este artículo, exploramos el código fuente de C# para entender cómo usar la función Copiar texto marcado de Aspose.Words para .NET. Seguimos una guía paso a paso para copiar el contenido de un marcador de un documento de origen a otro documento.

### Preguntas frecuentes para copiar texto marcado en un documento de Word

#### P: ¿Cuáles son los requisitos para usar la función "Copiar texto con marcadores" en Aspose.Words para .NET?

R: Para usar la función "Copiar texto con marcadores" en Aspose.Words para .NET, debe tener conocimientos básicos del lenguaje C#. También necesita un entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

#### P: ¿Cómo cargo un documento de origen en Aspose.Words para .NET?

 R: Para cargar un documento de origen en Aspose.Words para .NET, puede usar el`Document`clase especificando la ruta del archivo del documento. Aquí hay un código de muestra:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### P: ¿Cómo obtener el contenido de un marcador específico en un documento de origen usando Aspose.Words para .NET?

 R: Para obtener el contenido de un marcador específico en un documento de origen mediante Aspose.Words para .NET, puede acceder al`Bookmarks` propiedad del rango del documento de origen y use el nombre del marcador para recuperar el marcador específico. Aquí hay un código de muestra:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### P: ¿Cómo especificar la ubicación de la copia del texto del marcador en un documento de destino usando Aspose.Words para .NET?

 R: Para especificar dónde desea agregar el texto de marcador copiado en un documento de destino mediante Aspose.Words para .NET, puede navegar hasta el cuerpo de la última sección del documento de destino. Puedes usar el`LastSection` propiedad para acceder a la última sección y la`Body` propiedad para acceder al cuerpo de esa sección. Aquí hay un código de muestra:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### P: ¿Cómo importar y copiar texto de marcador del documento de origen al documento de destino usando Aspose.Words para .NET?

R: Para importar y copiar texto de marcador de un documento de origen a un documento de destino usando Aspose.Words para .NET, puede usar el`NodeImporter` class que especifica el documento de origen, el documento de destino y el modo de formato que se debe mantener. Entonces puedes usar el`AppendBookmarkedText` para agregar el texto del marcador en el documento de destino. Aquí hay un código de muestra:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### P: ¿Cómo guardar un documento de destino después de copiar el texto de un marcador usando Aspose.Words para .NET?

 R: Para guardar un documento de destino después de copiar texto de un marcador usando Aspose.Words para .NET, puede usar el`Save` metodo de la`Document` objeto que especifica la ruta del archivo de destino. Aquí hay un código de muestra:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```