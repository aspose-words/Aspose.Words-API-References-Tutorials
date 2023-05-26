---
title: Convertir Metarchivos a Svg
linktitle: Convertir Metarchivos a Svg
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para convertir metarchivos a formato SVG al convertir un documento a HTML con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

En este tutorial, lo guiaremos a través del código fuente de C# para convertir metarchivos al formato SVG con Aspose.Words para .NET. Esta función le permite convertir metarchivos a formato SVG al convertir un documento a HTML.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Insertar una imagen SVG en el documento

En este paso, insertaremos una imagen SVG en el documento a convertir. Use el siguiente código para insertar una imagen SVG usando una etiqueta HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Este código crea una instancia de`Document` y`DocumentBuilder` para construir el documento. Se inserta un`<svg>` etiqueta que contiene un`<polygon>` elemento con atributos para definir la forma y el estilo de la imagen SVG.

## Paso 3: establece las opciones de guardado de HTML

Ahora configuraremos las opciones de guardado de HTML, especificando que los metarchivos deben convertirse al formato SVG. Usa el siguiente código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Este código crea una instancia de`HtmlSaveOptions` y conjuntos`MetafileFormat` a`HtmlMetafileFormat.Svg` para especificar que los metarchivos deben convertirse a formato SVG al convertirlos a HTML.

## Paso 4: Convertir y guardar el documento a HTML

Finalmente, convertiremos el documento a HTML utilizando las opciones de guardado de HTML definidas anteriormente. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Este código convierte el documento a HTML y lo guarda en un archivo con los metarchivos convertidos a SVG.

### Ejemplo de código fuente para convertir metarchivos a Svg usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
