---
title: Resolver nombres de fuentes
linktitle: Resolver nombres de fuentes
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para resolver nombres de fuentes faltantes al convertir a HTML con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/resolve-font-names/
---

En este tutorial, lo guiaremos a través del código fuente de C# para resolver los nombres de fuentes faltantes con Aspose.Words para .NET. Esta característica le permite resolver automáticamente los nombres de fuentes faltantes al convertir un documento a HTML.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Cargar el documento

En este paso cargaremos el documento a procesar. Use el siguiente código para cargar el documento desde un directorio específico:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Este código crea una instancia de`Document` cargando el documento desde el directorio especificado.

## Paso 3: Configuración de las opciones de copia de seguridad de HTML

Ahora configuraremos las opciones de guardado de HTML para resolver los nombres de fuentes faltantes durante la conversión. Usa el siguiente código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Este código crea una instancia de`HtmlSaveOptions` establece el`ResolveFontNames` opción a`true` para resolver los nombres de fuentes que faltan al convertir a HTML. También el`PrettyFormat` la opción está configurada para`true` para obtener un código HTML bien formateado.

## Paso 4: Convertir y guardar el documento a HTML

Finalmente, convertiremos el documento a HTML utilizando las opciones de guardado de HTML configuradas anteriormente. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Este código convierte el documento a HTML resolviendo automáticamente los nombres de fuentes que faltan y guarda el archivo HTML convertido en el directorio especificado.

### Ejemplo de código fuente para resolver nombres de fuentes usando Aspose.Words para .NET

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