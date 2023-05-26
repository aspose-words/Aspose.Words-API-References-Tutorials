---
title: Título
linktitle: Título
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar el encabezado con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/heading/
---

En este ejemplo, le mostraremos cómo usar la función de encabezados con Aspose.Words para .NET. Los encabezados se utilizan para estructurar y priorizar el contenido de un documento.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: Personalización de estilos de título

De forma predeterminada, los estilos de título en Word pueden tener formato de negrita y cursiva. Si no queremos que se apliquen estas propiedades, debemos establecerlas explícitamente en "falso".

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Paso 3: agregar un título de nivel 1

 Podemos agregar un título de nivel 1 especificando el nombre de estilo de párrafo apropiado y usando el`Writeln` método para escribir el contenido del título.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

### Ejemplo de código fuente para encabezado con Aspose.Words para .NET


```csharp
	// Use un generador de documentos para agregar contenido al documento.
	DocumentBuilder builder = new DocumentBuilder();

	// De forma predeterminada, los estilos de título en Word pueden tener formato de negrita y cursiva.
	//Si no queremos que se nos enfatice, establezca estas propiedades explícitamente en falso.
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	builder.ParagraphFormat.StyleName = "Heading 1";
	builder.Writeln("This is an H1 tag");
            
```

¡Felicidades! Ahora ha aprendido a usar la función de encabezados con Aspose.Words para .NET.


