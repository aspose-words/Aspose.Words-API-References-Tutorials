---
title: Convertir metarchivos a emf o wmf
linktitle: Convertir metarchivos a emf o wmf
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para convertir metarchivos a formatos EMF o WMF al convertir un documento a HTML con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

En este tutorial, lo guiaremos a través del código fuente de C# para convertir metarchivos a formato EMF o WMF con Aspose.Words para .NET. Esta función le permite convertir imágenes en formato de metarchivo a formatos más compatibles, como EMF o WMF, al convertir un documento a HTML.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Insertar una imagen en el documento

En este paso, insertaremos una imagen en el documento a convertir. Use el siguiente código para insertar una imagen de una fuente de datos usando una etiqueta HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Este código crea una instancia de`Document` y`DocumentBuilder` para construir el documento. Se inserta un`<img>` etiqueta en el documento con una imagen codificada en base64.

## Paso 3: establece las opciones de guardado de HTML

Ahora configuraremos las opciones de guardado de HTML, incluido el formato de metarchivo que se usará para las imágenes. Usa el siguiente código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Este código crea una instancia de`HtmlSaveOptions` y conjuntos`MetafileFormat` a`HtmlMetafileFormat.EmfOrWmf` para especificar que los metarchivos deben convertirse a formato EMF o WMF al convertirlos a HTML.

## Paso 4: Convertir y guardar el documento a HTML

Finalmente convertiremos el documento a HTML utilizando las opciones de guardar HTML previamente definidas. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Este código convierte el documento a HTML y lo guarda en un archivo con los metarchivos convertidos en formato EMF o WMF, según las opciones de guardado establecidas.

### Ejemplo de código fuente para convertir metarchivos a Emf o Wmf usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Asegúrese de especificar la ruta correcta al directorio de documentos en el`dataDir` variable.

Ahora ha aprendido cómo convertir metarchivos a formatos EMF o WMF al convertir un documento a HTML usando Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede administrar fácilmente metarchivos en sus documentos HTML convertidos.