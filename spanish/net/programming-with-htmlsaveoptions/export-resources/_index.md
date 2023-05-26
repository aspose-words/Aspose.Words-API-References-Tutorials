---
title: Recursos de exportación
linktitle: Recursos de exportación
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para exportar recursos de documentos al guardarlos como HTML con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/export-resources/
---

En este tutorial, lo guiaremos a través del código fuente de C# para exportar recursos de documentos con Aspose.Words para .NET. Esta función le permite exportar recursos, como fuentes, como archivos externos al guardar un documento en formato HTML.

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

Ahora configuraremos las opciones de guardado de HTML para exportar los recursos del documento. Usa el siguiente código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://ejemplo.com/recursos"
};
```

 Este código crea una instancia de`HtmlSaveOptions` y establece las siguientes opciones:

- `CssStyleSheetType` se establece en`CssStyleSheetType.External`para exportar la hoja de estilo CSS a un archivo externo.
- `ExportFontResources` se establece en`true` para exportar recursos de fuentes.
- `ResourceFolder` especifica el directorio de destino donde se guardarán los recursos.
- `ResourceFolderAlias` especifica el alias de URL que se utilizará para acceder a los recursos.

## Paso 4: Convertir y guardar el documento a HTML

Finalmente, convertiremos el documento a HTML utilizando las opciones de guardado de HTML configuradas anteriormente. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Este código convierte el documento a HTML y guarda los recursos en el directorio especificado, utilizando el alias de URL especificado.

### Ejemplo de código fuente para exportar recursos usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://ejemplo.com/recursos"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Asegúrese de especificar la ruta correcta al directorio de documentos en el`dataDir` variable.