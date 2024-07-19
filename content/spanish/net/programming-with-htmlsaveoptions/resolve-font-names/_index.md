---
title: Resolver nombres de fuentes
linktitle: Resolver nombres de fuentes
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para resolver nombres de fuentes que faltan al convertir a HTML con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/resolve-font-names/
---

En este tutorial, lo guiaremos a través del código fuente de C# para resolver los nombres de fuentes que faltan con Aspose.Words para .NET. Esta función le permite resolver automáticamente los nombres de fuentes que faltan al convertir un documento a HTML.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso cargaremos el documento a procesar. Utilice el siguiente código para cargar el documento desde un directorio específico:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Este código crea una instancia de`Document` cargando el documento desde el directorio especificado.

## Paso 3: configurar las opciones de copia de seguridad HTML

Ahora configuraremos las opciones de guardado de HTML para resolver los nombres de fuentes que faltan durante la conversión. Utilice el siguiente código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Este código crea una instancia de`HtmlSaveOptions` y establece el`ResolveFontNames` opción de`true`para resolver los nombres de fuentes que faltan al convertir a HTML. También el`PrettyFormat` La opción está configurada en`true` para obtener un código HTML con un buen formato.

## Paso 4: convertir y guardar el documento a HTML

Finalmente, convertiremos el documento a HTML usando las opciones de guardado de HTML configuradas anteriormente. Utilice el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Este código convierte el documento a HTML resolviendo automáticamente los nombres de fuentes que faltan y guarda el archivo HTML convertido en el directorio especificado.

### Código fuente de ejemplo para resolver nombres de fuentes usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Asegúrese de especificar la ruta correcta al directorio de documentos en el`dataDir` variable.