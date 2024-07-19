---
title: Agregar prefijo de nombre de clase CSS
linktitle: Agregar prefijo de nombre de clase CSS
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para agregar un prefijo de nombre de clase CSS al convertir un documento a HTML con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

En este tutorial, lo guiaremos a través del código fuente de C# para agregar un prefijo de nombre de clase CSS con Aspose.Words para .NET. Esta característica le permite agregar un prefijo personalizado a los nombres de clases CSS generados al convertir un documento a HTML.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso, cargaremos el documento de Word que queremos convertir a HTML. Utilice el siguiente código para cargar el documento:

```csharp
//Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: configurar las opciones de guardado de HTML

Ahora configuremos las opciones para guardar HTML, incluido el tipo de hoja de estilo CSS y el prefijo de nombre de clase CSS. Utilice el siguiente código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Este código crea una instancia de`HtmlSaveOptions` y conjuntos`CssStyleSheetType` a`CssStyleSheetType.External` para generar una hoja de estilo CSS externa, y`CssClassNamePrefix` a`"pfx_"` prefijar`"pfx_"` para nombrar la clase CSS.

## Paso 4: convertir y guardar el documento a HTML

Finalmente, convertiremos el documento a HTML usando las opciones de guardar HTML definidas anteriormente. Utilice el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Este código convierte el documento a HTML y lo guarda en un archivo con el prefijo de nombre de clase CSS agregado.

### Código fuente de ejemplo para Agregar prefijo de nombre de clase Css usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido cómo agregar un prefijo de nombre de clase CSS al convertir un documento a HTML usando Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede personalizar los nombres de las clases CSS en sus documentos HTML convertidos.