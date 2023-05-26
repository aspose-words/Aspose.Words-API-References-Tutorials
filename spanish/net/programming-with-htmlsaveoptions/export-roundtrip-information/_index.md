---
title: Exportar información de ida y vuelta
linktitle: Exportar información de ida y vuelta
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para exportar información de ida y vuelta al guardar un documento como HTML con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

En este tutorial, lo guiaremos a través del código fuente de C# para exportar información de ida y vuelta desde un documento con Aspose.Words para .NET. Esta función le permite incluir información de ida y vuelta en el archivo HTML exportado, lo que facilita la recuperación de los cambios realizados en el documento original.

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

Ahora configuraremos las opciones de guardado de HTML para exportar la información de ida y vuelta del documento. Usa el siguiente código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Este código crea una instancia de`HtmlSaveOptions` establece el`ExportRoundtripInformation` opción a`true` para incluir información de ida y vuelta al exportar.

## Paso 4: Convertir y guardar el documento a HTML

Finalmente, convertiremos el documento a HTML utilizando las opciones de guardado de HTML configuradas anteriormente. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Este código convierte el documento a HTML, incluida la información de ida y vuelta, y guarda el archivo HTML exportado en el directorio especificado.

### Ejemplo de código fuente para exportar información de ida y vuelta usando Aspose.Words para .NET


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Asegúrese de especificar la ruta correcta al directorio de documentos en el`dataDir` variable.