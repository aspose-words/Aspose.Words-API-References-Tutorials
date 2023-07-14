---
title: Exportar fuentes como base 64
linktitle: Exportar fuentes como base 64
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para exportar fuentes base 64 al guardar un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

En este tutorial, lo guiaremos a través del código fuente de C# para exportar fuentes base 64 con Aspose.Words para .NET. Esta función le permite exportar fuentes como datos base 64 al guardar un documento en formato HTML.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Cargar el documento

En este paso cargaremos el documento a exportar. Use el siguiente código para cargar el documento desde un directorio específico:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Este código crea una instancia de`Document` cargando el documento desde el directorio especificado.

## Paso 3: Configuración de las opciones de copia de seguridad de HTML

Ahora configuraremos las opciones de guardado de HTML para exportar fuentes base 64. Usa el siguiente código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Este código crea una instancia de`HtmlSaveOptions` y conjuntos`ExportFontsAsBase64` a`true` para especificar que las fuentes deben exportarse como datos base 64 cuando se guardan como HTML.

## Paso 4: Convertir y guardar el documento a HTML

Finalmente, convertiremos el documento a HTML utilizando las opciones de guardado de HTML configuradas anteriormente. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Este código convierte el documento a HTML y lo guarda en un archivo con las fuentes exportadas como datos base 64.

### Ejemplo de código fuente para exportar fuentes como base 64 usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Asegúrese de especificar la ruta correcta al directorio de documentos en el`dataDir` variable.

Ahora ha aprendido cómo exportar fuentes base 64 al guardar un documento como HTML usando Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede exportar fácilmente fuentes de forma segura e incrustadas en sus documentos HTML.