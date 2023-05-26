---
title: Crear marcador
linktitle: Crear marcador
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a crear marcadores en un documento y especifique niveles de vista previa de marcadores en un PDF usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/create-bookmark/
---

En este artículo, exploraremos el código fuente de C# anterior para entender cómo usar la función Crear marcador en la biblioteca Aspose.Words para .NET. Esta función le permite crear marcadores en un documento y especificar niveles de vista previa de marcadores en un archivo PDF de salida.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Crear el Documento y el Generador

 Antes de crear marcadores, necesitamos crear un documento y un generador de documentos usando el`Document` y`DocumentBuilder` objetos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Crear el marcador principal

 usamos el`StartBookmark` método para iniciar un marcador principal y el`EndBookmark` método para terminarlo. En el medio, podemos agregar texto y otros marcadores:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Agregue más marcadores o texto aquí.

builder. EndBookmark("My Bookmark");
```

## Paso 3: crear marcadores anidados

 También podemos crear marcadores anidados dentro de un marcador principal. usamos lo mismo`StartBookmark` y`EndBookmark` métodos para crear y finalizar marcadores anidados:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Paso 4: Especificación de niveles de vista previa de marcadores en el archivo PDF de salida

 usamos el`PdfSaveOptions` objeto para especificar los niveles de vista previa del marcador en el archivo PDF de salida. usamos el`BookmarksOutlineLevels` propiedad

  para agregar marcadores principales y marcadores anidados con sus respectivos niveles:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Ejemplo de código fuente para Crear marcador usando Aspose.Words para .NET

Aquí está el código fuente de ejemplo completo para demostrar la creación de marcadores usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo usar la función Crear marcador de Aspose.Words para .NET. Hemos seguido una guía paso a paso para crear marcadores en un documento y especificar niveles de vista previa de marcadores en un archivo PDF de salida.