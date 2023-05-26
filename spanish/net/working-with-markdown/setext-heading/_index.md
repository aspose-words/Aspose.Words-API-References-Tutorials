---
title: Encabezado de texto
linktitle: Encabezado de texto
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar los encabezados de Setext para dar formato a sus documentos con la guía paso a paso de Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/setext-heading/
---

En este tutorial, lo guiaremos a través de cómo usar la función de encabezado Setext con Aspose.Words para .NET. Setext Heading es un método alternativo para formatear títulos en documentos Markdown.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: Usar el estilo de encabezado Setext

Vamos a utilizar el estilo de párrafo predeterminado "Título 1" para crear un título de nivel 1 en nuestro documento.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Paso 3: Restablecimiento de estilos

Restablecemos los estilos de fuente aplicados previamente para evitar cualquier combinación no deseada de estilos entre párrafos.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Paso 4: Personalización de los niveles de encabezado de Setext

Podemos personalizar los niveles de encabezado de Setext agregando nuevos estilos de párrafo basados en estilos de encabezado existentes. En este ejemplo, estamos creando un estilo "SetextHeading1" basado en el estilo "Título 1" para representar un encabezado de nivel 1 en el formato Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Paso 5: Guardar el documento

Finalmente, podemos guardar el documento en el formato deseado.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Código fuente de ejemplo para títulos de Setext con Aspose.Words para .NET

```csharp
	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Use un generador de documentos para agregar contenido al documento.
	DocumentBuilder builder = new DocumentBuilder();

	builder.ParagraphFormat.StyleName = "Heading 1";
	builder.Writeln("This is an H1 tag");

	// Restablecer estilos del párrafo anterior para no combinar estilos entre párrafos.
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
	builder.ParagraphFormat.Style = setexHeading1;
	builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
	builder.Writeln("Setext Heading level 1");

	builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
	builder.Writeln("This is an H3 tag");

	// Restablecer estilos del párrafo anterior para no combinar estilos entre párrafos.
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
	builder.ParagraphFormat.Style = setexHeading2;
	builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

	// El nivel de encabezado Setex se restablecerá a 2 si el párrafo base tiene un nivel de encabezado superior a 2.
	builder.Writeln("Setext Heading level 2");
	

	builder.Document.Save(dataDir + "Test.md");
```



