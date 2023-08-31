---
title: Exportar fuentes como Base 64
linktitle: Exportar fuentes como Base 64
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para exportar fuentes base 64 al guardar un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

En este tutorial, lo guiaremos a través del código fuente de C# para exportar fuentes base 64 con Aspose.Words para .NET. Esta función le permite exportar fuentes como datos base 64 al guardar un documento en formato HTML.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso, cargaremos el documento a exportar. Utilice el siguiente código para cargar el documento desde un directorio específico:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Este código crea una instancia de`Document` cargando el documento desde el directorio especificado.

## Paso 3: configurar las opciones de copia de seguridad HTML

Ahora configuraremos las opciones de guardado de HTML para exportar fuentes base 64. Utilice el siguiente código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Este código crea una instancia de`HtmlSaveOptions` y conjuntos`ExportFontsAsBase64` a`true` para especificar que las fuentes deben exportarse como datos base 64 al guardarlas como HTML.

## Paso 4: convertir y guardar el documento a HTML

Finalmente, convertiremos el documento a HTML usando las opciones de guardado de HTML configuradas anteriormente. Utilice el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Este código convierte el documento a HTML y lo guarda en un archivo con las fuentes exportadas como datos base 64.

### Código fuente de ejemplo para exportar fuentes como Base 64 usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Asegúrese de especificar la ruta correcta al directorio de documentos en el`dataDir` variable.

Ahora ha aprendido cómo exportar fuentes base 64 al guardar un documento como HTML usando Aspose.Words para .NET. Si sigue la guía paso a paso proporcionada en este tutorial, puede exportar fácilmente fuentes de forma segura e incrustarlas en sus documentos HTML.