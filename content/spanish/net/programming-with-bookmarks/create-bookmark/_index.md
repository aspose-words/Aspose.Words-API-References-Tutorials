---
title: Crear marcador en un documento de Word
linktitle: Crear marcador en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear marcadores en un documento de Word y especificar niveles de vista previa de marcadores en un PDF usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/create-bookmark/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo usar la función Crear marcador en la biblioteca Aspose.Words para .NET. Esta función le permite crear marcadores en un documento y especificar niveles de vista previa de marcadores en un archivo PDF de salida.

## Requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: crear el documento y el generador

 Antes de crear marcadores, necesitamos crear un documento y un generador de documentos usando el`Document` y`DocumentBuilder` objetos:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: crear el marcador principal

 Usamos el`StartBookmark` método para iniciar un marcador principal y el`EndBookmark` método para terminarlo. Mientras tanto, podemos agregar texto y otros marcadores:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Agregue más marcadores o texto aquí.

builder. EndBookmark("My Bookmark");
```

## Paso 3: crear marcadores anidados

También podemos crear marcadores anidados dentro de un marcador principal. Usamos lo mismo`StartBookmark` y`EndBookmark` Métodos para crear y finalizar marcadores anidados:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Paso 4: especificar niveles de vista previa de marcadores en el archivo PDF de salida

 Usamos el`PdfSaveOptions` objeto para especificar los niveles de vista previa del marcador en el archivo PDF de salida. Usamos el`BookmarksOutlineLevels` propiedad

  para agregar marcadores principales y marcadores anidados con sus respectivos niveles:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Código fuente de ejemplo para Crear marcador usando Aspose.Words para .NET

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

En este artículo, exploramos el código fuente de C# para comprender cómo utilizar la función Crear marcador de Aspose.Words para .NET. Hemos seguido una guía paso a paso para crear marcadores en un documento y especificar niveles de vista previa de marcadores en un archivo PDF de salida.

### Preguntas frecuentes

#### P: ¿Cuáles son los requisitos previos para utilizar la función "Crear marcadores" en Aspose.Words para .NET?

R: Para utilizar la función "Crear marcadores" en Aspose.Words para .NET, debe tener conocimientos básicos del lenguaje C#. También necesita un entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

#### P: ¿Cómo crear un documento en Aspose.Words para .NET?

 R: Para crear un documento en Aspose.Words para .NET, puede utilizar el`Document` clase. Aquí hay un código de muestra:

```csharp
Document doc = new Document();
```

#### P: ¿Cómo crear un marcador maestro en un documento usando Aspose.Words para .NET?

 R: Para crear un marcador principal en un documento usando Aspose.Words para .NET, puede usar el`StartBookmark` método para iniciar el marcador, agregar texto u otros marcadores dentro, luego usar el` EndBookmark` para terminarlo. Aquí hay un código de muestra:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### P: ¿Cómo crear un marcador anidado dentro de un marcador principal usando Aspose.Words para .NET?

 R: Para crear un marcador anidado dentro de un marcador principal usando Aspose.Words para .NET, puede usar el mismo`StartBookmark` y`EndBookmark` métodos para iniciar y finalizar el marcador anidado. Aquí hay un código de muestra:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### P: ¿Cómo especificar niveles de vista previa de marcadores en un PDF de salida usando Aspose.Words para .NET?

 R: Para especificar niveles de vista previa de marcadores en un PDF de salida usando Aspose.Words para .NET, puede usar el`PdfSaveOptions` clase y el`BookmarksOutlineLevels` propiedad. Puede agregar marcadores principales y marcadores anidados con sus respectivos niveles. Aquí hay un código de muestra:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### P: ¿Cómo guardar un documento después de crear marcadores usando Aspose.Words para .NET?

 R: Para guardar un documento después de crear marcadores usando Aspose.Words para .NET, puede usar el`Save` método de la`Document` objeto que especifica la ruta del archivo de destino. Aquí hay un código de muestra:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### P: ¿Cómo especificar niveles de vista previa de marcadores en un PDF de salida usando Aspose.Words para .NET?

 R: Para especificar niveles de vista previa de marcadores en un PDF de salida usando Aspose.Words para .NET, puede usar el`PdfSaveOptions` clase y el`BookmarksOutlineLevels` propiedad. Puede agregar marcadores principales y marcadores anidados con sus respectivos niveles. Aquí hay un código de muestra:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### P: ¿Cómo crear marcadores anidados dentro de un marcador principal usando Aspose.Words para .NET?

 R: Para crear marcadores anidados dentro de un marcador principal usando Aspose.Words para .NET, puede usar el mismo`StartBookmark` y`EndBookmark` Métodos para iniciar y finalizar marcadores anidados. Asegúrese de especificar el marcador principal como parámetro al llamar al`StartBookmark` método. Aquí hay un código de muestra:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### P: ¿Cómo agregar texto dentro de un marcador usando Aspose.Words para .NET?

R: Para agregar texto dentro de un marcador usando Aspose.Words para .NET, puede usar el`Write` método de la`DocumentBuilder` objeto que especifica el texto a agregar. Aquí hay un código de muestra:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### P: ¿Cómo crear un marcador maestro en un documento usando Aspose.Words para .NET?

 R: Para crear un marcador principal en un documento usando Aspose.Words para .NET, puede usar el`StartBookmark` método para iniciar el marcador y el`EndBookmark` método para terminarlo. Aquí hay un código de muestra:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```