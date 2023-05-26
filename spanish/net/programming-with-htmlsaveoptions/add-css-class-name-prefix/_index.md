---
title: Agregar prefijo de nombre de clase Css
linktitle: Agregar prefijo de nombre de clase Css
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para agregar un prefijo de nombre de clase CSS al convertir un documento a HTML con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

En este tutorial, lo guiaremos a través del código fuente de C# para agregar un prefijo de nombre de clase CSS con Aspose.Words para .NET. Esta función le permite agregar un prefijo personalizado a los nombres de clase CSS generados al convertir un documento a HTML.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Cargar el documento

En este paso, cargaremos el documento de Word que queremos convertir a HTML. Use el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: establece las opciones de guardado de HTML

Ahora configuremos las opciones de guardado de HTML, incluido el tipo de hoja de estilo CSS y el prefijo de nombre de clase CSS. Usa el siguiente código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Este código crea una instancia de`HtmlSaveOptions` y conjuntos`CssStyleSheetType` a`CssStyleSheetType.External` para generar una hoja de estilo CSS externa, y`CssClassNamePrefix` a`"pfx_"`anteponer`"pfx_"` para nombrar la clase CSS.

## Paso 4: Convertir y guardar el documento a HTML

Finalmente, convertiremos el documento a HTML utilizando las opciones de guardado de HTML definidas anteriormente. Usa el siguiente código:

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

Ahora ha aprendido cómo agregar un prefijo de nombre de clase CSS al convertir un documento a HTML usando Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede personalizar los nombres de clase CSS en sus documentos HTML convertidos.